---
title: "Метод ICLRStrongName::StrongNameSignatureSize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameSignatureSize
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameSignatureSize
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureSize method [.NET Framework hosting]
- StrongNameSignatureSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 76d4f93a-5e25-4399-abcc-a1389549481d
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 91a420e520a48f3a33c4ac8c127ccefc064c23bb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="iclrstrongnamestrongnamesignaturesize-method"></a><span data-ttu-id="509e0-102">Метод ICLRStrongName::StrongNameSignatureSize</span><span class="sxs-lookup"><span data-stu-id="509e0-102">ICLRStrongName::StrongNameSignatureSize Method</span></span>
<span data-ttu-id="509e0-103">Возвращает размер подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="509e0-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="509e0-104">Этот метод обычно используется компиляторами, чтобы определить, сколько места для резервирования в файле, при создании сборки с отложенной подписью.</span><span class="sxs-lookup"><span data-stu-id="509e0-104">This method is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="509e0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="509e0-105">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="509e0-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="509e0-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="509e0-107">[in] Структура типа [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) , содержащая открытую часть пары ключей, используемой для создания подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="509e0-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="509e0-108">[in] Размер в байтах для `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="509e0-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="509e0-109">[in] Число байтов, необходимое для хранения подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="509e0-109">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="509e0-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="509e0-110">Return Value</span></span>  
 <span data-ttu-id="509e0-111">`S_OK`Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (в разделе [часто встречающихся значений HRESULT](http://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="509e0-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="509e0-112">Требования</span><span class="sxs-lookup"><span data-stu-id="509e0-112">Requirements</span></span>  
 <span data-ttu-id="509e0-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="509e0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="509e0-114">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="509e0-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="509e0-115">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="509e0-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="509e0-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="509e0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="509e0-117">См. также</span><span class="sxs-lookup"><span data-stu-id="509e0-117">See Also</span></span>  
 [<span data-ttu-id="509e0-118">Iclrstrongname-интерфейс</span><span class="sxs-lookup"><span data-stu-id="509e0-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)