---
title: "Перечисление CorGCReferenceType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorGCReferenceType
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorGCReferenceType
helpviewer_keywords: CorGCReferenceType
ms.assetid: d9f16439-5a36-4474-8ffd-4f0b2c2bb686
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b314580f7628eca68a3996aaafb362081c6ed705
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corgcreferencetype-enumeration"></a>Перечисление CorGCReferenceType
Идентифицирует источник объекта, в котором должна быть выполнена сборка мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum {  
    CorHandleStrong = 1,  
    CorHandleStrongPinning = 2,  
    CorHandleWeakShort = 4,  
    CorHandleWeakRefCount = 8,  
    CorHandleStrongRefCount = 32,  
    CorHandleStrongDependent = 64,  
    CorHandleStrongAsyncPinned = 128,  
    CorHandleStrongSizedByref = 256,  
  
    CorReferenceStack = 0x80000001,  
    CorReferenceFinalizer = 0x80000002,  
  
    CorHandleStrongOnly = 0x1E3,  
    CorHandleWeakOnly = 0xC,  
    CorHandleAll = 0x7FFFFFFF  
} CorGCReferenceType  
```  
  
## <a name="members"></a>Участники  
  
|Имя члена|Описание:|  
|-----------------|-----------------|  
|`CorHandleStrong`|Дескриптор строгой ссылки из таблицы дескрипторов объектов.|  
|`CorHandleStrongPinning`|Дескриптор закрепленная строгая ссылка из таблицы дескрипторов объектов.|  
|`CorHandleWeakShort`|Дескриптор слабая ссылка из таблицы дескрипторов объектов.|  
|`CorHandleWeakRefCount`|Дескриптор слабое объект с подсчетом ссылок из таблицы дескрипторов объектов.|  
|`CorHandleStrongRefCount`|Дескриптор объект с подсчетом ссылок из таблицы дескрипторов объектов.|  
|`CorHandleStrongDependent`|Дескриптор зависимого объекта из таблицы дескрипторов объектов.|  
|`CorHandleStrongAsyncPinned`|Асинхронный закрепленный объект из таблицы дескрипторов объектов.|  
|`CorHandleStrongSizedByref`|Строгая ссылка, хранящая приблизительный размер общего закрытия всех объектов и корневых объектов во время сборки мусора.|  
|`CorReferenceStack`|Ссылка из управляемого стека.|  
|`CorReferenceFinalizer`|Ссылка из очереди метода завершения.|  
|CorHandleStrongOnly|Возвращать только строгих ссылок из таблицы дескрипторов. Это значение используется [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) только метод.|  
|`CorHandleWeakOnly`|Возвращать только слабые ссылки из таблицы дескрипторов. Это значение используется [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) только метод.|  
|`CorHandleAll`|Возврат всех ссылок из таблицы дескрипторов. Это значение используется [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) только метод.|  
  
## <a name="remarks"></a>Примечания  
 `CorGCReferenceType` Перечисление используется следующим образом:  
  
-   В качестве значения `type` поле [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) структуры, он указывает на источник ссылки или дескриптора.  
  
-   Как `types` аргумент [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) метода, задает типы маркеров для включения в перечислении.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
