---
description: 'Más información acerca de: ICorDebugArrayValue (interfaz)'
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
ms.openlocfilehash: 2b91c910b9444b061b4a6bea715667bca6a4629c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722898"
---
# <a name="icordebugarrayvalue-interface"></a><span data-ttu-id="ad1e5-103">Interfaz ICorDebugArrayValue</span><span class="sxs-lookup"><span data-stu-id="ad1e5-103">ICorDebugArrayValue Interface</span></span>

<span data-ttu-id="ad1e5-104">Subclase de ICorDebugHeapValue que representa una matriz unidimensional o multidimensional.</span><span class="sxs-lookup"><span data-stu-id="ad1e5-104">A subclass of ICorDebugHeapValue that represents a single-dimensional or multi-dimensional array.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ad1e5-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="ad1e5-105">Methods</span></span>  
  
|<span data-ttu-id="ad1e5-106">Método</span><span class="sxs-lookup"><span data-stu-id="ad1e5-106">Method</span></span>|<span data-ttu-id="ad1e5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ad1e5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ad1e5-108">Método GetBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="ad1e5-108">GetBaseIndicies Method</span></span>](icordebugarrayvalue-getbaseindicies-method.md)|<span data-ttu-id="ad1e5-109">Obtiene el índice base de cada dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="ad1e5-109">Gets the base index of each dimension in the array.</span></span>|  
|[<span data-ttu-id="ad1e5-110">Método GetCount</span><span class="sxs-lookup"><span data-stu-id="ad1e5-110">GetCount Method</span></span>](icordebugarrayvalue-getcount-method.md)|<span data-ttu-id="ad1e5-111">Obtiene el número total de elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="ad1e5-111">Gets the total number of elements in the array.</span></span>|  
|[<span data-ttu-id="ad1e5-112">Método GetDimensions</span><span class="sxs-lookup"><span data-stu-id="ad1e5-112">GetDimensions Method</span></span>](icordebugarrayvalue-getdimensions-method.md)|<span data-ttu-id="ad1e5-113">Obtiene las dimensiones de la matriz.</span><span class="sxs-lookup"><span data-stu-id="ad1e5-113">Gets the dimensions of the array.</span></span>|  
|[<span data-ttu-id="ad1e5-114">Método GetElement</span><span class="sxs-lookup"><span data-stu-id="ad1e5-114">GetElement Method</span></span>](icordebugarrayvalue-getelement-method.md)|<span data-ttu-id="ad1e5-115">Obtiene un valor que representa el elemento especificado en la matriz.</span><span class="sxs-lookup"><span data-stu-id="ad1e5-115">Gets a value representing the given element in the array.</span></span>|  
|[<span data-ttu-id="ad1e5-116">Método GetElementAtPosition</span><span class="sxs-lookup"><span data-stu-id="ad1e5-116">GetElementAtPosition Method</span></span>](icordebugarrayvalue-getelementatposition-method.md)|<span data-ttu-id="ad1e5-117">Obtiene el elemento en la posición especificada y trata la matriz como una matriz unidimensional de base cero.</span><span class="sxs-lookup"><span data-stu-id="ad1e5-117">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>|  
|[<span data-ttu-id="ad1e5-118">Método GetElementType</span><span class="sxs-lookup"><span data-stu-id="ad1e5-118">GetElementType Method</span></span>](icordebugarrayvalue-getelementtype-method.md)|<span data-ttu-id="ad1e5-119">Obtiene el tipo simple de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="ad1e5-119">Gets the simple type of the elements in the array.</span></span>|  
|[<span data-ttu-id="ad1e5-120">Método GetRank</span><span class="sxs-lookup"><span data-stu-id="ad1e5-120">GetRank Method</span></span>](icordebugarrayvalue-getrank-method.md)|<span data-ttu-id="ad1e5-121">Obtiene el número de dimensiones de la matriz.</span><span class="sxs-lookup"><span data-stu-id="ad1e5-121">Gets the number of dimensions in the array.</span></span>|  
|[<span data-ttu-id="ad1e5-122">Método HasBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="ad1e5-122">HasBaseIndicies Method</span></span>](icordebugarrayvalue-hasbaseindicies-method.md)|<span data-ttu-id="ad1e5-123">Determina si la matriz tiene índices base.</span><span class="sxs-lookup"><span data-stu-id="ad1e5-123">Determines whether the array has base indexes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad1e5-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ad1e5-124">Remarks</span></span>  

 <span data-ttu-id="ad1e5-125">`ICorDebugArrayValue` admite Matrices unidimensionales y multidimensionales.</span><span class="sxs-lookup"><span data-stu-id="ad1e5-125">`ICorDebugArrayValue` supports both single-dimensional and multi-dimensional arrays.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ad1e5-126">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="ad1e5-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad1e5-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ad1e5-127">Requirements</span></span>  

 <span data-ttu-id="ad1e5-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad1e5-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad1e5-129">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ad1e5-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad1e5-130">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad1e5-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad1e5-131">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad1e5-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad1e5-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad1e5-132">See also</span></span>

- [<span data-ttu-id="ad1e5-133">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="ad1e5-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
