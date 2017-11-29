---
title: "Метод ICorRuntimeHost::CreateDomainSetup"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.CreateDomainSetup
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::CreateDomainSetup
helpviewer_keywords:
- CreateDomainSetup method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomainSetup method [.NET Framework hosting]
ms.assetid: c21dab60-fb65-47d9-8a94-7fd47ca53b48
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ca09788ea403e2a60d6de0cb6834fdc90261b770
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorruntimehostcreatedomainsetup-method"></a><span data-ttu-id="a1755-102">Метод ICorRuntimeHost::CreateDomainSetup</span><span class="sxs-lookup"><span data-stu-id="a1755-102">ICorRuntimeHost::CreateDomainSetup Method</span></span>
<span data-ttu-id="a1755-103">Возвращает указатель интерфейса типа IAppDomainSetup для <xref:System.AppDomainSetup?displayProperty=nameWithType> экземпляра.</span><span class="sxs-lookup"><span data-stu-id="a1755-103">Gets an interface pointer of type IAppDomainSetup to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="a1755-104">`IAppDomainSetup`Предоставляет методы для настройки аспектов домена приложения перед его созданием.</span><span class="sxs-lookup"><span data-stu-id="a1755-104">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1755-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a1755-105">Syntax</span></span>  
  
```  
HRESULT CreateDomainSetup (  
    [out] IUnknown** pAppDomainSetup  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a1755-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a1755-106">Parameters</span></span>  
 `pAppDomainSetup`  
 <span data-ttu-id="a1755-107">[out] Указатель интерфейса <xref:System.AppDomainSetup?displayProperty=nameWithType> экземпляра.</span><span class="sxs-lookup"><span data-stu-id="a1755-107">[out] An interface pointer to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="a1755-108">Этот параметр типизируется как `IUnknown`, поэтому обычно следует вызывать вызывающим объектам `QueryInterface` на этот указатель для получения указателя на интерфейс типа `IAppDomainSetup`.</span><span class="sxs-lookup"><span data-stu-id="a1755-108">This parameter is typed as `IUnknown`, so callers should generally call `QueryInterface` on this pointer to obtain an interface pointer of type `IAppDomainSetup`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1755-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a1755-109">Return Value</span></span>  
  
|<span data-ttu-id="a1755-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a1755-110">HRESULT</span></span>|<span data-ttu-id="a1755-111">Описание</span><span class="sxs-lookup"><span data-stu-id="a1755-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a1755-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="a1755-112">S_OK</span></span>|<span data-ttu-id="a1755-113">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="a1755-113">The operation was successful.</span></span>|  
|<span data-ttu-id="a1755-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a1755-114">S_FALSE</span></span>|<span data-ttu-id="a1755-115">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="a1755-115">The operation failed to complete.</span></span>|  
|<span data-ttu-id="a1755-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a1755-116">E_FAIL</span></span>|<span data-ttu-id="a1755-117">Неизвестный, Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="a1755-117">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="a1755-118">Если метод вернет значение E_FAIL, общеязыковой среды выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="a1755-118">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="a1755-119">Последующие вызовы любых размещающих интерфейсов API, возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a1755-119">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a1755-120">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a1755-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a1755-121">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="a1755-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1755-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="a1755-122">Remarks</span></span>  
 <span data-ttu-id="a1755-123">Указатель, возвращаемый этим методом обычно передается как параметр [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="a1755-123">The pointer returned from this method is typically passed as a parameter to the [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1755-124">Требования</span><span class="sxs-lookup"><span data-stu-id="a1755-124">Requirements</span></span>  
 <span data-ttu-id="a1755-125">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1755-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1755-126">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a1755-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a1755-127">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a1755-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a1755-128">**Версия платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="a1755-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1755-129">См. также</span><span class="sxs-lookup"><span data-stu-id="a1755-129">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 <xref:System.AppDomainSetup>  
 <xref:System.IAppDomainSetup?displayProperty=nameWithType>  
 [<span data-ttu-id="a1755-130">ICorRuntimeHost-интерфейс</span><span class="sxs-lookup"><span data-stu-id="a1755-130">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)