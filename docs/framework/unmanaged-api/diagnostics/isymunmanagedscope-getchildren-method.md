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
ms.openlocfilehash: f9bd6ae34903798a29f8666dfdba3e102fae28db
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54584563"
---
# <a name="isymunmanagedscopegetchildren-method"></a><span data-ttu-id="8e9a5-102">ISymUnmanagedScope::GetChildren (Método)</span><span class="sxs-lookup"><span data-stu-id="8e9a5-102">ISymUnmanagedScope::GetChildren Method</span></span>
<span data-ttu-id="8e9a5-103">Obtiene a los elementos secundarios de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="8e9a5-103">Gets the children of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e9a5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8e9a5-104">Syntax</span></span>  
  
```  
HRESULT GetChildren(  
    [in]  ULONG32  cChildren,  
    [out] ULONG32  *pcChildren,  
    [out, size_is(cChildren),  
        length_is(*pcChildren)] ISymUnmanagedScope* children[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8e9a5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8e9a5-105">Parameters</span></span>  
 `cChildren`  
 <span data-ttu-id="8e9a5-106">[in] Un `ULONG32` que indica el tamaño de la `children` matriz.</span><span class="sxs-lookup"><span data-stu-id="8e9a5-106">[in] A `ULONG32` that indicates the size of the `children` array.</span></span>  
  
 `pcChildren`  
 <span data-ttu-id="8e9a5-107">[out] Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="8e9a5-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the children.</span></span>  
  
 `children`  
 <span data-ttu-id="8e9a5-108">[out] La matriz devuelta de los elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="8e9a5-108">[out] The returned array of children.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8e9a5-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8e9a5-109">Return Value</span></span>  
 <span data-ttu-id="8e9a5-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="8e9a5-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e9a5-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8e9a5-111">Requirements</span></span>  
 <span data-ttu-id="8e9a5-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8e9a5-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e9a5-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e9a5-113">See also</span></span>
- [<span data-ttu-id="8e9a5-114">ISymUnmanagedScope (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8e9a5-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="8e9a5-115">GetParent (método)</span><span class="sxs-lookup"><span data-stu-id="8e9a5-115">GetParent Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)
