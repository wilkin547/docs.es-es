---
title: ISymUnmanagedNamespace::GetNamespaces (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedNamespace::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 0ea9d9af-8709-4a46-872b-f54d9e840088
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8284b23f5d36f7b3405bfff706e0ee7f0e32a042
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479940"
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a><span data-ttu-id="d1f79-102">ISymUnmanagedNamespace::GetNamespaces (Método)</span><span class="sxs-lookup"><span data-stu-id="d1f79-102">ISymUnmanagedNamespace::GetNamespaces Method</span></span>
<span data-ttu-id="d1f79-103">Obtiene a los elementos secundarios de este espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="d1f79-103">Gets the children of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1f79-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d1f79-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1f79-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d1f79-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="d1f79-106">[in] Un `ULONG32` que indica el tamaño de la `namespaces` matriz.</span><span class="sxs-lookup"><span data-stu-id="d1f79-106">[in] A `ULONG32` that indicates the size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="d1f79-107">[out] Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="d1f79-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="d1f79-108">[out] Un puntero al búfer que contiene los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="d1f79-108">[out] A pointer to the buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d1f79-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d1f79-109">Return Value</span></span>  
 <span data-ttu-id="d1f79-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="d1f79-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1f79-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d1f79-111">Requirements</span></span>  
 <span data-ttu-id="d1f79-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d1f79-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1f79-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1f79-113">See also</span></span>
- [<span data-ttu-id="d1f79-114">ISymUnmanagedNamespace (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d1f79-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
