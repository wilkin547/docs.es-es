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
ms.openlocfilehash: 0944f3379c18cba56ab65fe40a5b94a64d8a8991
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778202"
---
# <a name="icordebugarrayvalue-interface"></a><span data-ttu-id="2f110-102">Interfaz ICorDebugArrayValue</span><span class="sxs-lookup"><span data-stu-id="2f110-102">ICorDebugArrayValue Interface</span></span>

<span data-ttu-id="2f110-103">Subclase de ICorDebugHeapValue que representa una matriz unidimensional o multidimensional.</span><span class="sxs-lookup"><span data-stu-id="2f110-103">A subclass of ICorDebugHeapValue that represents a single-dimensional or multi-dimensional array.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2f110-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="2f110-104">Methods</span></span>  
  
|<span data-ttu-id="2f110-105">Método</span><span class="sxs-lookup"><span data-stu-id="2f110-105">Method</span></span>|<span data-ttu-id="2f110-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f110-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2f110-107">GetBaseIndicies (método)</span><span class="sxs-lookup"><span data-stu-id="2f110-107">GetBaseIndicies Method</span></span>](icordebugarrayvalue-getbaseindicies-method.md)|<span data-ttu-id="2f110-108">Obtiene el índice base de cada dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="2f110-108">Gets the base index of each dimension in the array.</span></span>|  
|[<span data-ttu-id="2f110-109">GetCount (método)</span><span class="sxs-lookup"><span data-stu-id="2f110-109">GetCount Method</span></span>](icordebugarrayvalue-getcount-method.md)|<span data-ttu-id="2f110-110">Obtiene el número total de elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="2f110-110">Gets the total number of elements in the array.</span></span>|  
|[<span data-ttu-id="2f110-111">GetDimensions (método)</span><span class="sxs-lookup"><span data-stu-id="2f110-111">GetDimensions Method</span></span>](icordebugarrayvalue-getdimensions-method.md)|<span data-ttu-id="2f110-112">Obtiene las dimensiones de la matriz.</span><span class="sxs-lookup"><span data-stu-id="2f110-112">Gets the dimensions of the array.</span></span>|  
|[<span data-ttu-id="2f110-113">GetElement (método)</span><span class="sxs-lookup"><span data-stu-id="2f110-113">GetElement Method</span></span>](icordebugarrayvalue-getelement-method.md)|<span data-ttu-id="2f110-114">Obtiene un valor que representa el elemento especificado en la matriz.</span><span class="sxs-lookup"><span data-stu-id="2f110-114">Gets a value representing the given element in the array.</span></span>|  
|[<span data-ttu-id="2f110-115">GetElementAtPosition (método)</span><span class="sxs-lookup"><span data-stu-id="2f110-115">GetElementAtPosition Method</span></span>](icordebugarrayvalue-getelementatposition-method.md)|<span data-ttu-id="2f110-116">Obtiene el elemento en la posición especificada y trata la matriz como una matriz unidimensional de base cero.</span><span class="sxs-lookup"><span data-stu-id="2f110-116">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>|  
|[<span data-ttu-id="2f110-117">GetElementType (método)</span><span class="sxs-lookup"><span data-stu-id="2f110-117">GetElementType Method</span></span>](icordebugarrayvalue-getelementtype-method.md)|<span data-ttu-id="2f110-118">Obtiene el tipo simple de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="2f110-118">Gets the simple type of the elements in the array.</span></span>|  
|[<span data-ttu-id="2f110-119">GetRank (método)</span><span class="sxs-lookup"><span data-stu-id="2f110-119">GetRank Method</span></span>](icordebugarrayvalue-getrank-method.md)|<span data-ttu-id="2f110-120">Obtiene el número de dimensiones de la matriz.</span><span class="sxs-lookup"><span data-stu-id="2f110-120">Gets the number of dimensions in the array.</span></span>|  
|[<span data-ttu-id="2f110-121">HasBaseIndicies (método)</span><span class="sxs-lookup"><span data-stu-id="2f110-121">HasBaseIndicies Method</span></span>](icordebugarrayvalue-hasbaseindicies-method.md)|<span data-ttu-id="2f110-122">Determina si la matriz tiene índices base.</span><span class="sxs-lookup"><span data-stu-id="2f110-122">Determines whether the array has base indexes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f110-123">Notas</span><span class="sxs-lookup"><span data-stu-id="2f110-123">Remarks</span></span>  
 <span data-ttu-id="2f110-124">`ICorDebugArrayValue` admite Matrices unidimensionales y multidimensionales.</span><span class="sxs-lookup"><span data-stu-id="2f110-124">`ICorDebugArrayValue` supports both single-dimensional and multi-dimensional arrays.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2f110-125">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="2f110-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f110-126">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="2f110-126">Requirements</span></span>  
 <span data-ttu-id="2f110-127">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f110-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f110-128">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f110-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f110-129">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f110-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f110-130">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f110-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f110-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f110-131">See also</span></span>

- [<span data-ttu-id="2f110-132">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="2f110-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
