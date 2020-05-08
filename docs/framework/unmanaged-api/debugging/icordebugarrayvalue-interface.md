---
title: Interfaz ICorDebugArrayValue
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue interface
helpviewer_keywords:
- ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: dc437751-7093-44e2-bfdc-191d9ce3c192
topic_type:
- apiref
ms.openlocfilehash: bd1e86b83c43af20604416f158ab9e74f399821b
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894965"
---
# <a name="icordebugarrayvalue-interface"></a><span data-ttu-id="cc557-102">Interfaz ICorDebugArrayValue</span><span class="sxs-lookup"><span data-stu-id="cc557-102">ICorDebugArrayValue Interface</span></span>

<span data-ttu-id="cc557-103">Subclase de ICorDebugHeapValue que representa una matriz unidimensional o multidimensional.</span><span class="sxs-lookup"><span data-stu-id="cc557-103">A subclass of ICorDebugHeapValue that represents a single-dimensional or multi-dimensional array.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cc557-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="cc557-104">Methods</span></span>  
  
|<span data-ttu-id="cc557-105">Método</span><span class="sxs-lookup"><span data-stu-id="cc557-105">Method</span></span>|<span data-ttu-id="cc557-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc557-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cc557-107">Método GetBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="cc557-107">GetBaseIndicies Method</span></span>](icordebugarrayvalue-getbaseindicies-method.md)|<span data-ttu-id="cc557-108">Obtiene el índice base de cada dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="cc557-108">Gets the base index of each dimension in the array.</span></span>|  
|[<span data-ttu-id="cc557-109">Método GetCount</span><span class="sxs-lookup"><span data-stu-id="cc557-109">GetCount Method</span></span>](icordebugarrayvalue-getcount-method.md)|<span data-ttu-id="cc557-110">Obtiene el número total de elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="cc557-110">Gets the total number of elements in the array.</span></span>|  
|[<span data-ttu-id="cc557-111">Método GetDimensions</span><span class="sxs-lookup"><span data-stu-id="cc557-111">GetDimensions Method</span></span>](icordebugarrayvalue-getdimensions-method.md)|<span data-ttu-id="cc557-112">Obtiene las dimensiones de la matriz.</span><span class="sxs-lookup"><span data-stu-id="cc557-112">Gets the dimensions of the array.</span></span>|  
|[<span data-ttu-id="cc557-113">Método GetElement</span><span class="sxs-lookup"><span data-stu-id="cc557-113">GetElement Method</span></span>](icordebugarrayvalue-getelement-method.md)|<span data-ttu-id="cc557-114">Obtiene un valor que representa el elemento especificado en la matriz.</span><span class="sxs-lookup"><span data-stu-id="cc557-114">Gets a value representing the given element in the array.</span></span>|  
|[<span data-ttu-id="cc557-115">Método GetElementAtPosition</span><span class="sxs-lookup"><span data-stu-id="cc557-115">GetElementAtPosition Method</span></span>](icordebugarrayvalue-getelementatposition-method.md)|<span data-ttu-id="cc557-116">Obtiene el elemento en la posición especificada y trata la matriz como una matriz unidimensional de base cero.</span><span class="sxs-lookup"><span data-stu-id="cc557-116">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>|  
|[<span data-ttu-id="cc557-117">Método GetElementType</span><span class="sxs-lookup"><span data-stu-id="cc557-117">GetElementType Method</span></span>](icordebugarrayvalue-getelementtype-method.md)|<span data-ttu-id="cc557-118">Obtiene el tipo simple de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="cc557-118">Gets the simple type of the elements in the array.</span></span>|  
|[<span data-ttu-id="cc557-119">Método GetRank</span><span class="sxs-lookup"><span data-stu-id="cc557-119">GetRank Method</span></span>](icordebugarrayvalue-getrank-method.md)|<span data-ttu-id="cc557-120">Obtiene el número de dimensiones de la matriz.</span><span class="sxs-lookup"><span data-stu-id="cc557-120">Gets the number of dimensions in the array.</span></span>|  
|[<span data-ttu-id="cc557-121">Método HasBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="cc557-121">HasBaseIndicies Method</span></span>](icordebugarrayvalue-hasbaseindicies-method.md)|<span data-ttu-id="cc557-122">Determina si la matriz tiene índices base.</span><span class="sxs-lookup"><span data-stu-id="cc557-122">Determines whether the array has base indexes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc557-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cc557-123">Remarks</span></span>  
 <span data-ttu-id="cc557-124">`ICorDebugArrayValue`admite Matrices unidimensionales y multidimensionales.</span><span class="sxs-lookup"><span data-stu-id="cc557-124">`ICorDebugArrayValue` supports both single-dimensional and multi-dimensional arrays.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cc557-125">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="cc557-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc557-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cc557-126">Requirements</span></span>  
 <span data-ttu-id="cc557-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc557-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc557-128">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc557-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc557-129">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc557-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc557-130">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc557-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc557-131">Consulta también</span><span class="sxs-lookup"><span data-stu-id="cc557-131">See also</span></span>

- [<span data-ttu-id="cc557-132">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="cc557-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
