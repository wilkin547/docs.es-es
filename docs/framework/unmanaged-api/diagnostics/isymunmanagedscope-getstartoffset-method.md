---
title: ISymUnmanagedScope::GetStartOffset (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetStartOffset method [.NET Framework debugging]
ms.assetid: da6bbc75-94d1-4354-9722-0d455b4428fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d34bcaf1ef00806e3883996804336bd22b9b634f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777842"
---
# <a name="isymunmanagedscopegetstartoffset-method"></a><span data-ttu-id="e65a8-102">ISymUnmanagedScope::GetStartOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="e65a8-102">ISymUnmanagedScope::GetStartOffset Method</span></span>
<span data-ttu-id="e65a8-103">Obtiene el desplazamiento inicial de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="e65a8-103">Gets the start offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e65a8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e65a8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e65a8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e65a8-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="e65a8-106">[out] Un puntero a un `ULONG32` que contiene el desplazamiento inicial.</span><span class="sxs-lookup"><span data-stu-id="e65a8-106">[out] A pointer to a `ULONG32` that contains the starting offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e65a8-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e65a8-107">Return Value</span></span>  
 <span data-ttu-id="e65a8-108">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="e65a8-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e65a8-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e65a8-109">Requirements</span></span>  
 <span data-ttu-id="e65a8-110">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e65a8-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e65a8-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="e65a8-111">See also</span></span>

- [<span data-ttu-id="e65a8-112">ISymUnmanagedScope (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e65a8-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="e65a8-113">GetEndOffset (método)</span><span class="sxs-lookup"><span data-stu-id="e65a8-113">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)
