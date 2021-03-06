---
title: "Перечисление CorDebugUserState"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugUserState
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugUserState
helpviewer_keywords: CorDebugUserState enumeration [.NET Framework debugging]
ms.assetid: 5f6c2bcd-8102-4e3b-abc5-86ab0bd62def
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 57fd9df27b1911c90bd11712b67e6e64588c2b5f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="cordebuguserstate-enumeration"></a>Перечисление CorDebugUserState
Указывает состояние пользователя потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum CorDebugUserState {  
    USER_STOP_REQUESTED     =  0x01,  
    USER_SUSPEND_REQUESTED  =  0x02,  
    USER_BACKGROUND         =  0x04,  
    USER_UNSTARTED          =  0x08,  
    USER_STOPPED            =  0x10,  
    USER_WAIT_SLEEP_JOIN    =  0x20,  
    USER_SUSPENDED          =  0x40,  
    USER_UNSAFE_POINT       =  0x80,  
    USER_THREADPOOL         = 0x100  
} CorDebugUserState;  
```  
  
## <a name="members"></a>Участники  
  
|Значение|Описание:|  
|-----------|-----------------|  
|`USER_STOP_REQUESTED`|Запрошено завершение выполнения потока.|  
|`USER_SUSPEND_REQUESTED`|Приостановка потока был запрошен.|  
|`USER_BACKGROUND`|Поток выполняется в фоновом режиме.|  
|`USER_UNSTARTED`|Поток не запущен выполнения.|  
|`USER_STOPPED`|Поток был завершен.|  
|`USER_WAIT_SLEEP_JOIN`|Поток ожидает другого потока до завершения задачи.|  
|`USER_SUSPENDED`|Этот поток был приостановлен.|  
|`USER_UNSAFE_POINT`|Поток находится в небезопасной точке. То есть поток находится в точке выполнения, в которой он может блокировать сборку мусора.<br /><br /> Отладка событий могут доставляться в небезопасных точках, но приостановка потока в небезопасной точке вероятнее всего вызовет взаимоблокировку до возобновления потока. Безопасные и небезопасные точки определяются just-in-time (JIT) и реализацию сбора мусора.|  
|`USER_THREADPOOL`|Поток находится в пуле потоков.|  
  
## <a name="remarks"></a>Примечания  
 Пользовательское состояние потока — используется состояние потока при его анализа отладчиком. Для потока может быть сочетание пользовательских состояний.  
  
 Используйте [ICorDebugThread::GetUserState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md) метод, чтобы получить состояние пользователя потока.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
