---
title: ISymUnmanagedScope::GetNamespaces (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetNamespaces
helpviewer_keywords:
- GetNamespaces method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetNamespaces method [.NET Framework debugging]
ms.assetid: c44b0440-04bd-460a-84fb-41afecf44503
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ab3e64911e3d64409e5fc93fe8ded995a333fcbb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471961"
---
# <a name="isymunmanagedscopegetnamespaces-method"></a><span data-ttu-id="03829-102">ISymUnmanagedScope::GetNamespaces (Método)</span><span class="sxs-lookup"><span data-stu-id="03829-102">ISymUnmanagedScope::GetNamespaces Method</span></span>
<span data-ttu-id="03829-103">Obtiene los espacios de nombres que se utilizan dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="03829-103">Gets the namespaces that are being used within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03829-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03829-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces),  
        length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03829-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="03829-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="03829-106">[in] Tamaño de la matriz `namespaces`.</span><span class="sxs-lookup"><span data-stu-id="03829-106">[in] The size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="03829-107">[out] Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="03829-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="03829-108">[out] Matriz que recibe los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="03829-108">[out] The array that receives the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="03829-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="03829-109">Return Value</span></span>  
 <span data-ttu-id="03829-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="03829-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03829-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="03829-111">Requirements</span></span>  
 <span data-ttu-id="03829-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="03829-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03829-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="03829-113">See also</span></span>
- [<span data-ttu-id="03829-114">ISymUnmanagedScope (interfaz)</span><span class="sxs-lookup"><span data-stu-id="03829-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
