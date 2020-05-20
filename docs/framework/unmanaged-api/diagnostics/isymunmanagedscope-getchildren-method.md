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
ms.openlocfilehash: c6d21f40c260890c9c88dcdfccd7e31161024ba3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614869"
---
# <a name="isymunmanagedscopegetchildren-method"></a><span data-ttu-id="d9f36-102">ISymUnmanagedScope::GetChildren (Método)</span><span class="sxs-lookup"><span data-stu-id="d9f36-102">ISymUnmanagedScope::GetChildren Method</span></span>
<span data-ttu-id="d9f36-103">Obtiene los elementos secundarios de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="d9f36-103">Gets the children of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9f36-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9f36-104">Syntax</span></span>  
  
```cpp  
HRESULT GetChildren(  
    [in]  ULONG32  cChildren,  
    [out] ULONG32  *pcChildren,  
    [out, size_is(cChildren),  
        length_is(*pcChildren)] ISymUnmanagedScope* children[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9f36-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d9f36-105">Parameters</span></span>  
 `cChildren`  
 <span data-ttu-id="d9f36-106">de `ULONG32`Que indica el tamaño de la `children` matriz.</span><span class="sxs-lookup"><span data-stu-id="d9f36-106">[in] A `ULONG32` that indicates the size of the `children` array.</span></span>  
  
 `pcChildren`  
 <span data-ttu-id="d9f36-107">enuncia Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="d9f36-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the children.</span></span>  
  
 `children`  
 <span data-ttu-id="d9f36-108">enuncia Matriz de elementos secundarios devuelta.</span><span class="sxs-lookup"><span data-stu-id="d9f36-108">[out] The returned array of children.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9f36-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d9f36-109">Return Value</span></span>  
 <span data-ttu-id="d9f36-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="d9f36-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9f36-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d9f36-111">Requirements</span></span>  
 <span data-ttu-id="d9f36-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="d9f36-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9f36-113">Consulta también</span><span class="sxs-lookup"><span data-stu-id="d9f36-113">See also</span></span>

- [<span data-ttu-id="d9f36-114">ISymUnmanagedScope (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d9f36-114">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="d9f36-115">Método GetParent</span><span class="sxs-lookup"><span data-stu-id="d9f36-115">GetParent Method</span></span>](isymunmanagedscope-getparent-method.md)
