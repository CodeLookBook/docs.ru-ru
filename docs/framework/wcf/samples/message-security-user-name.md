---
title: "Безопасность сообщений с использованием имени пользователя"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WS Security
ms.assetid: c63cfc87-6b20-4949-93b3-bcd4b732b0a2
caps.latest.revision: "57"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 3d0c5278cf1860a89ea6a1c3ed33b45ed3c48e92
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="message-security-user-name"></a>Безопасность сообщений с использованием имени пользователя
В этом образце показано, как реализовать приложение, использующее протокол WS-Security и проверку подлинности имен пользователя для клиента и требующее проверки подлинности сервера с использованием сертификата X.509v3 сервера. Все сообщения приложений, которыми обмениваются служба и клиент, подписываются и шифруются. По умолчанию для входа от имени действующей учетной записи Windows используются предоставляемые клиентом имя пользователя и пароль. Этот пример построен на [WSHttpBinding](../../../../docs/framework/wcf/samples/wshttpbinding.md). Этот образец содержит консольную программу клиента (Client.exe) и библиотеку службы (Service.dll), размещаемую в службах IIS. Служба реализует контракт, определяющий шаблон взаимодействия "запрос-ответ".  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 В этом образце также демонстрируется следующее.  
  
-   Сопоставление учетных записей по умолчанию для обеспечения дополнительной авторизации.  
  
-   Способ доступа к данным идентификации клиента из кода службы.  
  
 Эта служба для взаимодействия с ней предоставляет одну конечную точку, которая задается в файле конфигурации Web.config. Конечная точка состоит из адреса, привязки и контракта. Привязка настраивается с помощью стандартного [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), который по умолчанию использует безопасность сообщений. В этом примере задает стандартный [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) использует проверку подлинности имени пользователя клиента. Поведение указывает, что для проверки подлинности службы следует использовать учетные данные пользователя. Сертификат сервера должен содержать то же значение для имени субъекта, как `findValue` атрибута в [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).  
  
```xml  
<system.serviceModel>  
  <protocolMapping>  
    <add scheme="http" binding="wsHttpBinding" />  
  </protocolMapping>  
  <bindings>  
    <wsHttpBinding>  
      <!--   
      This configuration defines the security mode as Message and   
      the clientCredentialType as Username.  
      By default, Username authentication attempts to authenticate the provided  
      username as a Windows computer or domain account.  
      -->  
      <binding>  
        <security mode="Message">  
          <message clientCredentialType="UserName"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
  
  <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true.-->  
  <behaviors>  
    <serviceBehaviors>  
      <behavior>  
        <!--   
      The serviceCredentials behavior allows one to define a service certificate.  
      A service certificate is used by the service to authenticate itself to the client and to provide message protection.  
      This configuration references the "localhost" certificate installed during the setup instructions.  
      -->  
        <serviceCredentials>  
          <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
        </serviceCredentials>  
        <serviceMetadata httpGetEnabled="True"/>  
        <serviceDebug includeExceptionDetailInFaults="False" />  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
 Конфигурация конечной точки клиента состоит из абсолютного адреса конечной точки службы, привязки и контракта. Привязка клиента настраивается с помощью соответствующих `securityMode` и `authenticationMode`. Если сценарий выполняется на нескольких компьютерах, необходимо изменить адрес конечной точки службы соответствующим образом.  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint address="http://localhost/servicemodelsamples/service.svc"   
              binding="wsHttpBinding"   
              bindingConfiguration="Binding1"   
              behaviorConfiguration="ClientCredentialsBehavior"  
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!--   
      This configuration defines the security mode as Message and   
      the clientCredentialType as Username.  
      -->  
      <binding name="Binding1">  
        <security mode="Message">  
          <message clientCredentialType="UserName"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
  
  <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true.-->  
  <behaviors>  
    <endpointBehaviors>  
      <behavior name="ClientCredentialsBehavior">  
        <!--   
      Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
      is in the user's Trusted People store, then it is trusted without performing a  
      validation of the certificate's issuer chain. This setting is used here for convenience so that the   
      sample can be run without having to have certificates issued by a certification authority (CA).  
      This setting is less secure than the default, ChainTrust. The security implications of this   
      setting should be carefully considered before using PeerOrChainTrust in production code.   
      -->  
        <clientCredentials>  
          <serviceCertificate>  
            <authentication certificateValidationMode="PeerOrChainTrust" />  
          </serviceCertificate>  
        </clientCredentials>  
      </behavior>  
    </endpointBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
 Реализация клиента задает используемые имя пользователя и пароль.  
  
```  
// Create a client.  
CalculatorClient client = new CalculatorClient();  
  
// Configure client with valid computer or domain account (username,password).  
client.ClientCredentials.UserName.UserName = username;  
client.ClientCredentials.UserName.Password = password.ToString();  
  
// Call GetCallerIdentity service operation.  
Console.WriteLine(client.GetCallerIdentity());  
...  
//Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
```  
  
 При выполнении примера запросы и ответы операций отображаются в окне консоли клиента. Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
```  
MyMachine\TestAccount  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Press <ENTER> to terminate client.  
```  
  
 Пакетный файл Setup.bat, входящий в состав образца реализации безопасности сообщений с возможностью анонимного доступа, позволяет настроить для сервера соответствующий сертификат, необходимый для выполнения резидентного приложения, которое требует обеспечения безопасности на основе сертификата сервера. Пакетный файл можно выполнять в двух режимах. Чтобы выполнить пакетный файл в режиме одного компьютера, введите `setup.bat` в командной строке. Чтобы выполнить его в режиме службы, введите `setup.bat service`. Этот режим используется для выполнения образца на нескольких компьютерах. Подробные сведения см. в описании процедуры настройки в конце этого раздела.  
  
 Ниже приводится краткое описание различных разделов пакетного файла.  
  
-   Создание сертификата сервера  
  
     Следующие строки из файла Setup.bat создают используемый в дальнейшем сертификат сервера.  
  
    ```  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
     Переменная %SERVER_NAME% задает имя сервера. Сертификат хранится в хранилище LocalMachine. Если пакетный файл Setup.bat запускается с аргументом service (например, `setup.bat service`), переменная %SERVER_NAME% содержит полное имя домена компьютера.  В противном случае по умолчанию используется значение localhost.  
  
-   Установка сертификата сервера в хранилище доверенных сертификатов клиента  
  
     Следующая строка копирует сертификат сервера в хранилище доверенных лиц клиента. Этот шаг является обязательным, поскольку сертификаты, созданные с помощью программы Makecert.exe, не получают неявного доверия со стороны клиентской системы. Если уже имеется сертификат, имеющий доверенный корневой сертификат клиента, например сертификат, выпущенный корпорацией Майкрософт, выполнять этот шаг по добавлению сертификата сервера в хранилище сертификатов клиента не требуется.  
  
    ```  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
-   Предоставление разрешений в закрытом ключе сертификата  
  
     Следующие строки файла Setup.bat открывают доступ к сертификату сервера, расположенному в хранилище LocalMachine, для учетной записи рабочего процесса [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].  
  
    ```  
    echo ************  
    echo setting privileges on server certificates  
    echo ************  
    for /F "delims=" %%i in ('"%ProgramFiles%\ServiceModelSampleTools\FindPrivateKey.exe" My LocalMachine -n CN^=%SERVER_NAME% -a') do set PRIVATE_KEY_FILE=%%i  
    set WP_ACCOUNT=NT AUTHORITY\NETWORK SERVICE  
    (ver | findstr /C:"5.1") && set WP_ACCOUNT=%COMPUTERNAME%\ASPNET  
    echo Y|cacls.exe "%PRIVATE_KEY_FILE%" /E /G "%WP_ACCOUNT%":R  
    iisreset  
    ```  
  
    > [!NOTE]
    >  Если используется в англоязычном (не американском) выпуске Windows, необходимо изменить файл Setup.bat и заменить имя учетной записи `NT AUTHORITY\NETWORK SERVICE` своим региональным эквивалентом.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
### <a name="to-run-the-sample-on-the-same-computer"></a>Запуск образца на одном компьютере  
  
1.  Убедитесь, что путь включает папку, в которой хранятся файлы Makecert.exe и FindPrivateKey.exe.  
  
2.  Из командной строки Visual Studio, открытой с правами администратора, запустите файл Setup.bat из папки установки образца. При этом устанавливаются все сертификаты, необходимые для выполнения образца.  
  
    > [!NOTE]
    >  Пакетный файл Setup.bat предназначен для запуска из командной строки Visual Studio. Необходимо, чтобы переменная среды path указывала на каталог, в котором установлен пакет SDK. Эта переменная среды автоматически устанавливается в командной строке Visual Studio.  
  
3.  Проверьте доступ к службе с помощью браузера путем ввода адреса http://localhost/servicemodelsamples/service.svc.  
  
4.  Запустите программу Client.exe из каталога \client\bin. Действия клиента отображаются в консольном приложении клиента.  
  
5.  Если клиенту и службе не удается взаимодействовать, см. раздел [советы по устранению неполадок](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).  
  
### <a name="to-run-the-sample-across-computers"></a>Запуск образца на нескольких компьютерах  
  
1.  Создайте каталог на компьютере службы. Создайте для этого каталога виртуальное приложение servicemodelsamples, воспользовавшись для этого средством управления службами IIS.  
  
2.  Скопируйте файлы служебной программы из каталога «\inetpub\wwwroot\servicemodelsamples» в виртуальный каталог на компьютере службы. Убедитесь, что скопированы все файлы из подкаталога \bin. Кроме того, скопируйте файлы Setup.bat и Cleanup.bat на компьютер службы.  
  
3.  Создайте на клиентском компьютере каталог для двоичных файлов клиента.  
  
4.  Скопируйте в клиентский каталог на клиентском компьютере файлы программы клиента. Кроме того, скопируйте на клиент файлы Setup.bat, Cleanup.bat и ImportServiceCert.bat.  
  
5.  На сервере откройте командную строку Visual Studio с правами администратора и запустите `setup.bat service`. Под управлением `setup.bat` с `service` аргумент создается сертификат службы с полным доменным именем компьютера и экспортируется в файл с именем Service.cer.  
  
6.  Внесите в файл Web.config изменения в соответствии с новым именем сертификата (в атрибуте findValue в элементе serviceCertificate), которое совпадает с полным именем домена компьютера`.`  
  
7.  Скопируйте файл Service.cer из каталога службы в клиентский каталог на клиентском компьютере.  
  
8.  В файле Client.exe.config на клиентском компьютере измените значение адреса конечной точки, чтобы оно соответствовало новому адресу службы.  
  
9. На клиентском компьютере откройте командную строку Visual Studio с правами администратора и запустите файл ImportServiceCert.bat. Он импортирует сертификат службы из файла Service.cer в хранилище CurrentUser - TrustedPeople.  
  
10. На клиентском компьютере из командной строки запустите программу Client.exe. Если клиенту и службе не удается взаимодействовать, см. раздел [советы по устранению неполадок](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).  
  
### <a name="to-clean-up-after-the-sample"></a>Очистка после образца  
  
-   После завершения работы образца запустите в папке образцов файл Cleanup.bat.  
  
    > [!NOTE]
    >  Этот скрипт не удаляет сертификаты службы на клиенте при запуске образца на нескольких компьютерах. Если образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], в которых использовались сертификаты, запускались на нескольких компьютерах, обязательно удалите сертификаты службы, которые были установлены в хранилище «CurrentUser - TrustedPeople». Для этого воспользуйтесь следующей командой: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`. Например: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.  
  
## <a name="see-also"></a>См. также
