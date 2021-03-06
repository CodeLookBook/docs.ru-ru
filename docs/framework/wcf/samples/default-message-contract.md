---
title: "Контракт сообщения по умолчанию"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Message Contract
ms.assetid: 5a200b78-1a46-4104-b7fb-da6dbab33893
caps.latest.revision: "35"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d1219f2c1a173f454827c7450e66d90a500d87e6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="default-message-contract"></a>Контракт сообщения по умолчанию
Образец контракта сообщения по умолчанию демонстрирует службу, в которой пользовательское сообщение, определенное пользователем, передается в операции службы и из операций службы. Этот пример построен на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md) , реализующий интерфейс калькулятора как типизированные службы. Вместо отдельные операции служб для сложения, вычитания, умножения и деления, используемых в [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md), в этом примере передает пользовательское сообщение, содержащее операнды и оператор и возвращает результат арифметические операции.  
  
 Клиентом является консольное приложение (EXE), а библиотека службы (DLL) размещается в службах Internet Information Services (IIS). Действия клиента отображаются в окне консоли.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 В этой службе определена единственная операция службы, которая принимает и возвращает пользовательские сообщения типа `MyMessage`. Хотя в этом образце сообщения запроса и ответа имеют одинаковый тип, при необходимости они, конечно, могут быть различными контрактами сообщений.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract(Action="http://test/MyMessage_action",  
                  ReplyAction="http://test/MyMessage_action")]  
    MyMessage Calculate(MyMessage request);  
}  
```  
  
 Пользовательское сообщение `MyMessage` определено в классе, аннотированном атрибутами <xref:System.ServiceModel.MessageContractAttribute>, <xref:System.ServiceModel.MessageHeaderAttribute> и <xref:System.ServiceModel.MessageBodyMemberAttribute>. В этом образце используется только третий конструктор. Использование контрактов сообщений обеспечивает полное управление сообщением SOAP. В этом образце атрибут <xref:System.ServiceModel.MessageHeaderAttribute> используется для помещения параметра `Operation` в заголовок SOAP. Операнды `N1`, `N2` и `Result` помещаются в тело сообщения SOAP, так как к ним применен атрибут <xref:System.ServiceModel.MessageBodyMemberAttribute>.  
  
```  
[MessageContract]  
public class MyMessage  
{  
    private string operation;  
    private double n1;  
    private double n2;  
    private double result;  
  
    //Constructor - create an empty message.  
  
    public MyMessage() {}  
  
    //Constructor - create a message and populate its members.  
  
    public MyMessage(double n1, double n2, string operation,   
                     double result)  
    {  
        this.n1 = n1;  
        this.n2 = n2;  
        this.operation = operation;  
        this.result = result;  
    }  
  
    //Constructor - create a message from another message.  
  
    public MyMessage(MyMessage message)  
    {  
        this.n1 = message.n1;  
        this.n2 = message.n2;  
        this.operation = message.operation;  
        this.result = message.result;  
    }  
  
    [MessageHeader]  
    public string Operation  
    {  
        get { return operation; }  
        set { operation = value; }  
    }  
  
    [MessageBodyMember]  
    public double N1  
    {  
        get { return n1; }  
        set { n1 = value; }  
    }  
  
    [MessageBodyMember]  
    public double N2  
    {  
        get { return n2; }  
        set { n2 = value; }  
    }  
  
    [MessageBodyMember]  
    public double Result  
    {  
        get { return result; }  
        set { result = value; }  
    }  
}  
```  
  
 Класс реализации содержит код для операции службы `Calculate`. Класс `CalculateService` получает операнды и оператор из сообщения запроса и создает ответное сообщение, содержащее результаты запрошенного вычисления, как показано в следующем образце кода.  
  
```  
// Service class which implements the service contract.  
public class CalculatorService : ICalculator  
{  
    // Perform a calculation.  
  
    public MyMessage Calculate(MyMessage request)  
    {  
        MyMessage response = new MyMessage(request);  
        switch (request.Operation)  
        {  
            case "+":  
                response.Result = request.N1 + request.N2;  
                break;  
            case "-":  
                response.Result = request.N1 - request.N2;  
                break;  
            case "*":  
                response.Result = request.N1 * request.N2;  
                break;  
            case "/":  
                response.Result = request.N1 / request.N2;  
                break;  
            default:  
                response.Result = 0.0D;  
                break;  
        }  
        return response;  
    }  
}  
```  
  
 Созданный код клиента для клиента был создан с [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) средства. При необходимости это средство автоматически создает типы контрактов сообщений в создаваемом коде клиента. Можно указать параметр команды `/messageContract`, чтобы принудительно создавать контракты сообщений.  
  
```  
svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" /o:client\generatedClient.cs http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 В следующем образце кода показан клиент, использующий сообщение `MyMessage`.  
  
```  
// Create a client with given client endpoint configuration  
CalculatorClient client = new CalculatorClient();  
  
// Perform addition using a typed message.  
  
MyMessage request = new MyMessage();  
request.N1 = 100D;  
request.N2 = 15.99D;  
request.Operation = "+";  
MyMessage response = ((ICalculator)client).Calculate(request);  
Console.WriteLine("Add({0},{1}) = {2}", request.N1, request.N2, response.Result);  
```  
  
 При выполнении образца ход вычислений отображается в окне консоли клиента. Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
 На этом этапе пользовательские сообщения, определенные пользователем, передаются между клиентом и операцией службы. Контракт сообщений определяет, что операнды и результаты находятся в теле сообщения, а оператор - в заголовке сообщения. Для наблюдения за этой структурой сообщений можно настроить ведение журнала сообщений.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Message\Default`  
  
## <a name="see-also"></a>См. также
