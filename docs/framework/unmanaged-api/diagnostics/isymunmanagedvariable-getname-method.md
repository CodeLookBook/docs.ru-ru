---
title: "Метод ISymUnmanagedVariable::GetName"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable.GetName
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable::GetName
helpviewer_keywords:
- GetName method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetName method [.NET Framework debugging]
ms.assetid: eedf1ef0-9d4a-4847-a201-4e99572dfe5e
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a86a93db6058a8fda42e837388f7fa4cf5c765c0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedvariablegetname-method"></a><span data-ttu-id="a576c-102">Метод ISymUnmanagedVariable::GetName</span><span class="sxs-lookup"><span data-stu-id="a576c-102">ISymUnmanagedVariable::GetName Method</span></span>
<span data-ttu-id="a576c-103">Получает имя этой переменной.</span><span class="sxs-lookup"><span data-stu-id="a576c-103">Gets the name of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a576c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a576c-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a576c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a576c-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="a576c-106">[in] Длина буфера, `pcchName` указывает параметр.</span><span class="sxs-lookup"><span data-stu-id="a576c-106">[in] The length of the buffer that the `pcchName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="a576c-107">[out] Указатель на `ULONG32` , получающий размер в символах, буфера, должны содержать имя, включая нулем.</span><span class="sxs-lookup"><span data-stu-id="a576c-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="a576c-108">[out] Буфер, в которой хранится имя.</span><span class="sxs-lookup"><span data-stu-id="a576c-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a576c-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a576c-109">Return Value</span></span>  
 <span data-ttu-id="a576c-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="a576c-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a576c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="a576c-111">Requirements</span></span>  
 <span data-ttu-id="a576c-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a576c-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a576c-113">См. также</span><span class="sxs-lookup"><span data-stu-id="a576c-113">See Also</span></span>  
 [<span data-ttu-id="a576c-114">ISymUnmanagedVariable-интерфейс</span><span class="sxs-lookup"><span data-stu-id="a576c-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)