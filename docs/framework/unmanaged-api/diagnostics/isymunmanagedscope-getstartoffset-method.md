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
ms.openlocfilehash: faab55199a3b921ea8b995e2a0f9823fb4da9cc7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761626"
---
# <a name="isymunmanagedscopegetstartoffset-method"></a><span data-ttu-id="69499-102">ISymUnmanagedScope::GetStartOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="69499-102">ISymUnmanagedScope::GetStartOffset Method</span></span>
<span data-ttu-id="69499-103">Obtiene el desplazamiento inicial de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="69499-103">Gets the start offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69499-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69499-104">Syntax</span></span>  
  
```  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69499-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="69499-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="69499-106">[out] Un puntero a un `ULONG32` que contiene el desplazamiento inicial.</span><span class="sxs-lookup"><span data-stu-id="69499-106">[out] A pointer to a `ULONG32` that contains the starting offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="69499-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="69499-107">Return Value</span></span>  
 <span data-ttu-id="69499-108">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="69499-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69499-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="69499-109">Requirements</span></span>  
 <span data-ttu-id="69499-110">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="69499-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69499-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="69499-111">See also</span></span>

- [<span data-ttu-id="69499-112">ISymUnmanagedScope (interfaz)</span><span class="sxs-lookup"><span data-stu-id="69499-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="69499-113">GetEndOffset (método)</span><span class="sxs-lookup"><span data-stu-id="69499-113">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)
