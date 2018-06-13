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
ms.openlocfilehash: c786cd43a25aa0c69c19e57452a3b190c7bfb167
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426846"
---
# <a name="isymunmanagedscopegetnamespaces-method"></a><span data-ttu-id="803b0-102">ISymUnmanagedScope::GetNamespaces (Método)</span><span class="sxs-lookup"><span data-stu-id="803b0-102">ISymUnmanagedScope::GetNamespaces Method</span></span>
<span data-ttu-id="803b0-103">Obtiene los espacios de nombres que se utilizan dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="803b0-103">Gets the namespaces that are being used within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="803b0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="803b0-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces),  
        length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="803b0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="803b0-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="803b0-106">[in] Tamaño de la matriz `namespaces`.</span><span class="sxs-lookup"><span data-stu-id="803b0-106">[in] The size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="803b0-107">[out] Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="803b0-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="803b0-108">[out] Matriz que recibe los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="803b0-108">[out] The array that receives the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="803b0-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="803b0-109">Return Value</span></span>  
 <span data-ttu-id="803b0-110">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="803b0-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="803b0-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="803b0-111">Requirements</span></span>  
 <span data-ttu-id="803b0-112">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="803b0-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="803b0-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="803b0-113">See Also</span></span>  
 [<span data-ttu-id="803b0-114">ISymUnmanagedScope (interfaz)</span><span class="sxs-lookup"><span data-stu-id="803b0-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
