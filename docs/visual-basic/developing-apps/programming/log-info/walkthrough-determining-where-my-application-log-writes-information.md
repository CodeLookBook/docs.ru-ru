---
title: "Определение места записи информации для My.Application.Log (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.Log object, output location
- output, application log location
- My.Application.Log object, outpout location
- event logs, determining output location
- application event logs, output location
- applications [Visual Basic], output location
ms.assetid: 5b70143a-7741-45f2-ae1d-03324a3a4189
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f35a850a262e96762b4ada3fdff1f14634f77317
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-determining-where-myapplicationlog-writes-information-visual-basic"></a>Пошаговое руководство. Определение места записи информации для My.Application.Log (Visual Basic)
Объект `My.Application.Log` может записывать информацию в несколько прослушивателей журналов. Прослушиватели журнала настраиваются в файле конфигурации компьютера и могут переопределяться в файле конфигурации приложения. В этом разделе описаны параметры по умолчанию и способ определения параметров для приложения.  
  
 Дополнительные сведения о расположении выходных данных по умолчанию см. в разделе [Работа с журналами приложения](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).  
  
### <a name="to-determine-the-listeners-for-myapplicationlog"></a>Определение прослушивателей для объекта My.Application.Log  
  
1.  Найдите файл конфигурации сборки. Во время разработки сборки доступ к файлу app.config в [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] можно получить в **обозревателе решений**. В противном случае имя файла конфигурации — это имя сборки с расширением .config, а расположен он в том же каталоге, что и сборка.  
  
    > [!NOTE]
    >  Не каждая сборка имеет файл конфигурации.  
  
     Файл конфигурации является XML-файлом.  
  
2.  Найдите раздел `<listeners>` в разделе `<source>` с атрибутом `name` , равным DefaultSource, в разделе `<sources>` . Раздел `<sources>` находится в разделе `<system.diagnostics>` в разделе `<configuration>` верхнего уровня.  
  
     Если эти разделы не существуют, то настройка прослушивателей журнала `My.Application.Log` может быть задана в файле конфигурации компьютера. Далее описано, как выяснить, что определяется в файле конфигурации компьютера.  
  
    1.  Найдите файл machine.config компьютера. Как правило, он находится в каталоге *SystemRoot\Microsoft.NET\Framework\frameworkVersion\CONFIG* , где `SystemRoot` — каталог операционной системы, а `frameworkVersion` — версия [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].  
  
         Параметры в файле machine.config могут быть переопределены файлом конфигурации приложения.  
  
         Если необязательные элементы, перечисленные ниже, отсутствуют, их можно создать.  
  
    2.  Найдите раздел `<listeners>` в разделе `<source>` с атрибутом `name` , равным DefaultSource, в разделе `<sources>` раздела `<system.diagnostics>` в разделе `<configuration>` верхнего уровня.  
  
         Если эти разделы не существуют, то в объекте `My.Application.Log` имеются только прослушиватели журнала по умолчанию.  
  
3.  Найдите элементы <`add>` в разделе <`listeners>`.  
  
     Эти элементы добавляют именованные прослушиватели журнала в источник `My.Application.Log` .  
  
4.  Найдите элементы `<add>` с именами прослушивателей журнала в разделе `<sharedListeners>` раздела `<system.diagnostics>` в разделе `<configuration>` верхнего уровня.  
  
5.  Данные инициализации для многих типов общих прослушивателей включают описание того, куда прослушиватель направляет данные.  
  
    -   Прослушиватель <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType> записывает данные в файловый журнал, как описано во введении.  
  
    -   Прослушиватель <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType> записывает данные в журнал событий компьютера, указанный в параметре `initializeData`. Для просмотра журнала событий можно использовать **обозреватель сервера** или **средство просмотра событий Windows**. Дополнительные сведения см. в разделе [ETW Events in the .NET Framework](../../../../framework/performance/etw-events.md).  
  
    -   Прослушиватели <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType> и <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> записывают данные в файл, указанный в параметре `initializeData`.  
  
    -   Прослушиватель <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType> выводит данные в консоль командной строки.  
  
    -   Сведения о том, куда записывают информацию другие типы прослушивателей журналов, приведены в документации по этим типам.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 <xref:System.Diagnostics.DelimitedListTraceListener>  
 <xref:System.Diagnostics.XmlWriterTraceListener>  
 <xref:System.Diagnostics.ConsoleTraceListener>  
 <xref:System.Diagnostics>  
 [Работа с журналами приложения](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)  
 [Практическое руководство. Запись в журнал сведений об исключениях](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)  
 [Практическое руководство. Запись сообщений в журнал](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)  
 [Пошаговое руководство. Изменение места записи сведений для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)  
 [События трассировки событий Windows в .NET Framework](../../../../framework/performance/etw-events.md)  
 [Устранение неполадок, связанных с прослушивателями журнала](../../../../visual-basic/developing-apps/programming/log-info/troubleshooting-log-listeners.md)
