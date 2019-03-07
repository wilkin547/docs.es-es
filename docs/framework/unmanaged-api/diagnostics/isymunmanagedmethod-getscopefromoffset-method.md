---
title: ISymUnmanagedMethod::GetScopeFromOffset (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetScopeFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetScopeFromOffset
helpviewer_keywords:
- GetScopeFromOffset method [.NET Framework debugging]
- ISymUnmanagedMethod::GetScopeFromOffset method [.NET Framework debugging]
ms.assetid: d14cf210-81f8-46e1-8b19-6ddec0ba8b11
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b036c5cff5300377580fe22dc254911fbdd79715
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57503130"
---
# <a name="isymunmanagedmethodgetscopefromoffset-method"></a><span data-ttu-id="1e8d7-102">ISymUnmanagedMethod::GetScopeFromOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="1e8d7-102">ISymUnmanagedMethod::GetScopeFromOffset Method</span></span>
<span data-ttu-id="1e8d7-103">Obtiene el ámbito léxico más envolvente dentro de este método que contiene el desplazamiento especificado.</span><span class="sxs-lookup"><span data-stu-id="1e8d7-103">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span> <span data-ttu-id="1e8d7-104">Esto puede usarse para iniciar búsquedas de variables locales.</span><span class="sxs-lookup"><span data-stu-id="1e8d7-104">This can be used to start local variable searches.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e8d7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1e8d7-105">Syntax</span></span>  
  
```  
HRESULT GetScopeFromOffset(  
    [in]  ULONG32 offset,  
    [out, retval] ISymUnmanagedScope**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e8d7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1e8d7-106">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="1e8d7-107">[in] Un `ULONG` que contiene el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="1e8d7-107">[in] A `ULONG` that contains the offset.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="1e8d7-108">[out] Un puntero que se establece en el valor devuelto [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="1e8d7-108">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1e8d7-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1e8d7-109">Return Value</span></span>  
 <span data-ttu-id="1e8d7-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="1e8d7-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e8d7-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1e8d7-111">Requirements</span></span>  
 <span data-ttu-id="1e8d7-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1e8d7-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e8d7-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e8d7-113">See also</span></span>
- [<span data-ttu-id="1e8d7-114">ISymUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1e8d7-114">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
