---
title: "ISymUnmanagedScope::GetStartOffset (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope.GetStartOffset
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetStartOffset method [.NET Framework debugging]
ms.assetid: da6bbc75-94d1-4354-9722-0d455b4428fb
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9e0328af628eec062dc9efa7012bbeff213f1b86
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedscopegetstartoffset-method"></a><span data-ttu-id="921e5-102">ISymUnmanagedScope::GetStartOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="921e5-102">ISymUnmanagedScope::GetStartOffset Method</span></span>
<span data-ttu-id="921e5-103">Obtiene el desplazamiento inicial de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="921e5-103">Gets the start offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="921e5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="921e5-104">Syntax</span></span>  
  
```  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="921e5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="921e5-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="921e5-106">[out] Un puntero a un `ULONG32` que contiene el desplazamiento inicial.</span><span class="sxs-lookup"><span data-stu-id="921e5-106">[out] A pointer to a `ULONG32` that contains the starting offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="921e5-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="921e5-107">Return Value</span></span>  
 <span data-ttu-id="921e5-108">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="921e5-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="921e5-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="921e5-109">Requirements</span></span>  
 <span data-ttu-id="921e5-110">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="921e5-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="921e5-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="921e5-111">See Also</span></span>  
 [<span data-ttu-id="921e5-112">ISymUnmanagedScope (interfaz)</span><span class="sxs-lookup"><span data-stu-id="921e5-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 [<span data-ttu-id="921e5-113">GetEndOffset (método)</span><span class="sxs-lookup"><span data-stu-id="921e5-113">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)
