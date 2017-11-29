---
title: "Метод ISymUnmanagedWriter::UsingNamespace"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.UsingNamespace
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::UsingNamespace
helpviewer_keywords:
- UsingNamespace method [.NET Framework debugging]
- ISymUnmanagedWriter::UsingNamespace method [.NET Framework debugging]
ms.assetid: 8d746e0a-d158-4983-88da-db0a0856bc0b
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b9bfd5ca0c22a9b4da1acb1f93b29150beba865a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriterusingnamespace-method"></a><span data-ttu-id="c82f1-102">Метод ISymUnmanagedWriter::UsingNamespace</span><span class="sxs-lookup"><span data-stu-id="c82f1-102">ISymUnmanagedWriter::UsingNamespace Method</span></span>
<span data-ttu-id="c82f1-103">Указывает, что данный полным именем пространства имен используется в текущей открытой лексической области.</span><span class="sxs-lookup"><span data-stu-id="c82f1-103">Specifies that the given fully qualified namespace name is being used within the currently open lexical scope.</span></span> <span data-ttu-id="c82f1-104">Пространство имен будет использоваться во всех областях, наследуемых от открытых области.</span><span class="sxs-lookup"><span data-stu-id="c82f1-104">The namespace will be used within all scopes that inherit from the currently open scope.</span></span> <span data-ttu-id="c82f1-105">Использование пространства имен также прекращается, закрытие текущей области.</span><span class="sxs-lookup"><span data-stu-id="c82f1-105">Closing the current scope will also stop the use of the namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c82f1-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c82f1-106">Syntax</span></span>  
  
```  
HRESULT UsingNamespace(  
    [in] const WCHAR *fullName);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c82f1-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="c82f1-107">Parameters</span></span>  
 `fullName`  
 <span data-ttu-id="c82f1-108">[in] Указатель на полное имя пространства имен.</span><span class="sxs-lookup"><span data-stu-id="c82f1-108">[in] A pointer to the fully qualified name of the namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c82f1-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c82f1-109">Return Value</span></span>  
 <span data-ttu-id="c82f1-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="c82f1-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c82f1-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c82f1-111">Requirements</span></span>  
 <span data-ttu-id="c82f1-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c82f1-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c82f1-113">См. также</span><span class="sxs-lookup"><span data-stu-id="c82f1-113">See Also</span></span>  
 [<span data-ttu-id="c82f1-114">ISymUnmanagedWriter-интерфейс</span><span class="sxs-lookup"><span data-stu-id="c82f1-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)