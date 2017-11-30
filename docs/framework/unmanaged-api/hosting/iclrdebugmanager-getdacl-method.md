---
title: "Метод ICLRDebugManager::GetDacl"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager.GetDacl
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager::GetDacl
helpviewer_keywords:
- GetDacl method [.NET Framework hosting]
- ICLRDebugManager::GetDacl method [.NET Framework hosting]
ms.assetid: 7115e920-aaff-440a-824e-39497139c6f6
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b3f53c539e73bae9676dc40f128ea6c200dfe7d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdebugmanagergetdacl-method"></a><span data-ttu-id="03763-102">Метод ICLRDebugManager::GetDacl</span><span class="sxs-lookup"><span data-stu-id="03763-102">ICLRDebugManager::GetDacl Method</span></span>
<span data-ttu-id="03763-103">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="03763-103">This method is not implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03763-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="03763-104">Syntax</span></span>  
  
```  
HRESULT GetDacl (  
    [out] PACL* ppacl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="03763-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="03763-105">Parameters</span></span>  
 `ppacl`  
 <span data-ttu-id="03763-106">[out] Указатель на интерфейс в список управления доступом (ACL).</span><span class="sxs-lookup"><span data-stu-id="03763-106">[out] An interface pointer to the Access Control List (ACL).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="03763-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="03763-107">Return Value</span></span>  
  
|<span data-ttu-id="03763-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="03763-108">HRESULT</span></span>|<span data-ttu-id="03763-109">Описание</span><span class="sxs-lookup"><span data-stu-id="03763-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="03763-110">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="03763-110">E_NOTIMPL</span></span>|<span data-ttu-id="03763-111">Метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="03763-111">The method is not implemented.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="03763-112">Требования</span><span class="sxs-lookup"><span data-stu-id="03763-112">Requirements</span></span>  
 <span data-ttu-id="03763-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03763-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03763-114">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="03763-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="03763-115">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="03763-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="03763-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03763-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03763-117">См. также</span><span class="sxs-lookup"><span data-stu-id="03763-117">See Also</span></span>  
 [<span data-ttu-id="03763-118">ICLRControl-интерфейс</span><span class="sxs-lookup"><span data-stu-id="03763-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="03763-119">Iclrdebugmanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="03763-119">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="03763-120">Setdacl-метод</span><span class="sxs-lookup"><span data-stu-id="03763-120">SetDacl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)  
 [<span data-ttu-id="03763-121">IHostControl-интерфейс</span><span class="sxs-lookup"><span data-stu-id="03763-121">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)