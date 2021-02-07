---
description: 'Más información acerca de: ISymUnmanagedScope:: GetChildren (método)'
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
ms.openlocfilehash: 55d72c98d34fcb30a479611895228fbc1b9f7f55
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763506"
---
# <a name="isymunmanagedscopegetchildren-method"></a><span data-ttu-id="11654-103">ISymUnmanagedScope::GetChildren (Método)</span><span class="sxs-lookup"><span data-stu-id="11654-103">ISymUnmanagedScope::GetChildren Method</span></span>

<span data-ttu-id="11654-104">Obtiene los elementos secundarios de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="11654-104">Gets the children of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11654-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11654-105">Syntax</span></span>  
  
```cpp  
HRESULT GetChildren(  
    [in]  ULONG32  cChildren,  
    [out] ULONG32  *pcChildren,  
    [out, size_is(cChildren),  
        length_is(*pcChildren)] ISymUnmanagedScope* children[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11654-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="11654-106">Parameters</span></span>  

 `cChildren`  
 <span data-ttu-id="11654-107">de `ULONG32` Que indica el tamaño de la `children` matriz.</span><span class="sxs-lookup"><span data-stu-id="11654-107">[in] A `ULONG32` that indicates the size of the `children` array.</span></span>  
  
 `pcChildren`  
 <span data-ttu-id="11654-108">enuncia Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="11654-108">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the children.</span></span>  
  
 `children`  
 <span data-ttu-id="11654-109">enuncia Matriz de elementos secundarios devuelta.</span><span class="sxs-lookup"><span data-stu-id="11654-109">[out] The returned array of children.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11654-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="11654-110">Return Value</span></span>  

 <span data-ttu-id="11654-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="11654-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11654-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="11654-112">Requirements</span></span>  

 <span data-ttu-id="11654-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="11654-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11654-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="11654-114">See also</span></span>

- [<span data-ttu-id="11654-115">ISymUnmanagedScope (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="11654-115">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="11654-116">Método GetParent</span><span class="sxs-lookup"><span data-stu-id="11654-116">GetParent Method</span></span>](isymunmanagedscope-getparent-method.md)
