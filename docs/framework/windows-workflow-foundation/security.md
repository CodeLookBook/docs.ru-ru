---
title: "Безопасность | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 737ec121-bfc5-4b75-a504-2d53c2c8af39
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Безопасность
Хранилище экземпляров рабочих процессов SQL использует следующие роли безопасности базы данных для обеспечения безопасного доступа к сведениям о состоянии экземпляров в базе данных сохраняемости.  
  
-   **System.Activities.DurableInstancing.InstanceStoreUsers**.Эта роль имеет доступ на чтение и запись для всех открытых представлений и права на выполнение хранимых процедур, участвующих в создании, загрузке и сохранении экземпляров.  
  
-   **System.Activities.DurableInstancing.InstanceStoreObservers**.Эта роль имеет доступ только для чтения открытых представлений.  
  
-   **System.Activities.DurableInstancing.WorkflowActivationUsers**.Эта роль имеет права на выполнение хранимых процедур, участвующих в процессе активации экземпляра.Дополнительные сведения об активации экземпляров см. в разделе [Активация экземпляров](../../../docs/framework/windows-workflow-foundation//instance-activation.md).Учетная запись пользователя, в которой выполняется универсальное ведущее приложение \(например, служба управления рабочего процесса для [!INCLUDE[dublin](../../../includes/dublin-md.md)]\), должна быть добавлена к этой роли базы данных.  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)] безопасности постоянных хранилищ с Windows Server App Fabric см. в разделе [Конфигурация безопасности для постоянных хранилищ в App Fabric](http://go.microsoft.com/fwlink/?LinkId=201208)  
  
> [!CAUTION]
>  Клиент, имеющий доступ к данным собственного экземпляра в хранилище экземпляров, также получает доступ и ко всем другим экземплярам в этом хранилище экземпляров.Хранилище экземпляров не поддерживает указание прав доступа на уровне экземпляра.Для обеспечения доступа к различным хранилищам экземпляров необходимо создать отдельные хранилища экземпляров и настроить доступ к ним различных групп и пользователей.