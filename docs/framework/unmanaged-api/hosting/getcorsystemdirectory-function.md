---
title: "Функция GetCORSystemDirectory"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetCORSystemDirectory
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: GetCORSystemDirectory
helpviewer_keywords: GetCORSystemDirectory function [.NET Framework hosting]
ms.assetid: 3dcd16a7-dafc-4ca8-b5cd-20ffb37db91d
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 802e9a7bd4e6caedd657a8e8cf0132d75b4cbc2e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="getcorsystemdirectory-function"></a><span data-ttu-id="c430e-102">Функция GetCORSystemDirectory</span><span class="sxs-lookup"><span data-stu-id="c430e-102">GetCORSystemDirectory Function</span></span>
<span data-ttu-id="c430e-103">Возвращает каталог установки среды common language runtime (CLR), который загружается процесс.</span><span class="sxs-lookup"><span data-stu-id="c430e-103">Returns the installation directory of the common language runtime (CLR) that is loaded into the process.</span></span> <span data-ttu-id="c430e-104">Каталог установки — полное имя, например, «c:\windows\microsoft.net\framework\v1.0.3705».</span><span class="sxs-lookup"><span data-stu-id="c430e-104">The installation directory is fully qualified, for example, "c:\windows\microsoft.net\framework\v1.0.3705".</span></span>  
  
 <span data-ttu-id="c430e-105">Эта функция устарела.</span><span class="sxs-lookup"><span data-stu-id="c430e-105">This function is deprecated.</span></span> <span data-ttu-id="c430e-106">Он заменен [ICLRRuntimeInfo::GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) метода [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c430e-106">It is superseded by the [ICLRRuntimeInfo::GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) method provided in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c430e-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c430e-107">Syntax</span></span>  
  
```  
HRESULT GetCORSystemDirectory (   
    [out] LPWSTR  pbuffer,     
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="c430e-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="c430e-108">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="c430e-109">[out] Буфер, в котором среда выполнения возвращает строка, содержащая полное имя каталога установки для среды выполнения, который загружается в процесс.</span><span class="sxs-lookup"><span data-stu-id="c430e-109">[out] A buffer in which the runtime returns a string that contains the fully qualified name of the installation directory for the runtime that is loaded into the process.</span></span> <span data-ttu-id="c430e-110">Если среда выполнения еще не был загружен в процесс, функция возвращает сведения каталога, соответствующего последнюю версию среды выполнения, установленную на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c430e-110">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="c430e-111">[in] Размер в байтах для `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="c430e-111">[in] The size, in bytes, of `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="c430e-112">[out] Число символов, возвращаемых в `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="c430e-112">[out] The number of characters returned in `pbuffer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c430e-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="c430e-113">Remarks</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="c430e-114">Не используйте эту функцию в процессы, работающие в среде CLR версии 4.</span><span class="sxs-lookup"><span data-stu-id="c430e-114">Do not use this function in processes that are running version 4 of the CLR.</span></span> <span data-ttu-id="c430e-115">Если на компьютере установлена более ранняя версия среды CLR, эта функция возвращает каталог установки для этой версии.</span><span class="sxs-lookup"><span data-stu-id="c430e-115">If an earlier version of the CLR is installed on the computer, this function returns the installation directory for that version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c430e-116">Требования</span><span class="sxs-lookup"><span data-stu-id="c430e-116">Requirements</span></span>  
 <span data-ttu-id="c430e-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c430e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c430e-118">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c430e-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c430e-119">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c430e-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c430e-120">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c430e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c430e-121">См. также</span><span class="sxs-lookup"><span data-stu-id="c430e-121">See Also</span></span>  
 [<span data-ttu-id="c430e-122">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="c430e-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)