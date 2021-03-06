---
title: "Использование средств разработки WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7d253f38fab21496dd305cc67e7b6e84846579f3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="using-the-wcf-development-tools"></a>Использование средств разработки WCF
В этом разделе описываются [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] средства разработки, которые могут помочь в разработке вашей [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]службы.  
  
 Можно использовать [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] шаблоны как основу для быстрого создания собственной службы, затем с помощью [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host и [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] тестовый клиент для отладки и тестирования службы. Оба этих инструмента обеспечивают быстрый и удобный цикл отладки и тестирования и исключают необходимость фиксации модели размещения на ранней стадии.  
  
## <a name="the-wcf-developer-tools"></a>Инструменты разработчика WCF  
 [Шаблоны WCF в Visual Studio](../../../docs/framework/wcf/wcf-vs-templates.md)  
  
 Можно использовать предопределенный [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] шаблонов проектов и элементов в [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] для быстрого создания [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] службы и окружающих приложений.  
  
 [Узел службы WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
 Средство Service Auto Host [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (WcfSvcHost.exe) позволяет запускать отладчик [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] (F5) для автоматического размещения и проверки реализованной службы. Затем службу можно проверить с помощью тестового клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (wcfTestClient.exe) или своего собственного клиента для поиска и устранения потенциальных ошибок.  
  
 [Тестовый клиент WCF (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)  
  
 Тестовый клиент [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (WcfTestClient.exe) представляет собой средство графического интерфейса пользователя, позволяющее вводить тестовые параметры произвольных типов, отправлять их в службу и просматривать ответную реакцию службы. При совместном использовании со средством Service Auto Host [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] это обеспечивает удобный способ тестирования служб.  
  
 [Формирование классов типов данных из XML](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md)  
  
 Данные XML, сохраненные в буфере обмена, можно вставить в кодовую страницу. Классы, определенные в данных, будут преобразованы в типы кода.  
  
## <a name="using-the-tools-without-administrator-privilege"></a>Использование инструментов без прав администратора  
 Чтобы позволить пользователю, у которого нет прав администратора, разрабатывать службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], для пространства имен "http://+:8731/Design_Time_Addresses" при установке [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] создается список управления доступом (ACL). Список управления доступом определяется пользовательским интерфейсом, который включает всех пользователей, выполнивших вход в систему. Администраторы могут добавлять или удалять пользователей из этого списка ACL или открыть дополнительные порты. Этот список ACL позволяет шаблонам WCF или WF отправлять и получать данные в их конфигурации по умолчанию. Он также позволяет пользователям использовать средство Service Auto Host [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (wcfSvcHost.exe) без предоставления им прав администратора.  
  
 Можно изменить доступ используя средство Netsh.exe в [!INCLUDE[wv](../../../includes/wv-md.md)] под учетной записью администратора. Ниже приведен пример использования средства Netsh.exe.  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)]Netsh.exe см. в разделе [способы использования средства Netsh.exe и переключателей командной строки](http://go.microsoft.com/fwlink/?LinkId=97877).  
  
## <a name="see-also"></a>См. также  
 [Шаблоны WCF в Visual Studio](../../../docs/framework/wcf/wcf-vs-templates.md)  
 [Узел службы WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
 [Тестовый клиент WCF (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
