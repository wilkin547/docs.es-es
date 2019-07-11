---
title: ISymUnmanagedScope::GetChildren (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetChildren
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetChildren
helpviewer_keywords:
- ISymUnmanagedScope::GetChildren method [.NET Framework debugging]
- GetChildren method [.NET Framework debugging]
ms.assetid: 0bed524e-cc48-4bf0-b9fa-25d665e63ddb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ffc4d5a1e6b8f1acc7603e9c2e01216e3188989e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751306"
---
# <a name="isymunmanagedscopegetchildren-method"></a><span data-ttu-id="e94a4-102">ISymUnmanagedScope::GetChildren (Método)</span><span class="sxs-lookup"><span data-stu-id="e94a4-102">ISymUnmanagedScope::GetChildren Method</span></span>
<span data-ttu-id="e94a4-103">Obtiene a los elementos secundarios de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="e94a4-103">Gets the children of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e94a4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e94a4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetChildren(  
    [in]  ULONG32  cChildren,  
    [out] ULONG32  *pcChildren,  
    [out, size_is(cChildren),  
        length_is(*pcChildren)] ISymUnmanagedScope* children[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e94a4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e94a4-105">Parameters</span></span>  
 `cChildren`  
 <span data-ttu-id="e94a4-106">[in] Un `ULONG32` que indica el tamaño de la `children` matriz.</span><span class="sxs-lookup"><span data-stu-id="e94a4-106">[in] A `ULONG32` that indicates the size of the `children` array.</span></span>  
  
 `pcChildren`  
 <span data-ttu-id="e94a4-107">[out] Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="e94a4-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the children.</span></span>  
  
 `children`  
 <span data-ttu-id="e94a4-108">[out] La matriz devuelta de los elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="e94a4-108">[out] The returned array of children.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e94a4-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e94a4-109">Return Value</span></span>  
 <span data-ttu-id="e94a4-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="e94a4-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e94a4-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e94a4-111">Requirements</span></span>  
 <span data-ttu-id="e94a4-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e94a4-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e94a4-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="e94a4-113">See also</span></span>

- [<span data-ttu-id="e94a4-114">ISymUnmanagedScope (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e94a4-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="e94a4-115">GetParent (método)</span><span class="sxs-lookup"><span data-stu-id="e94a4-115">GetParent Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)
