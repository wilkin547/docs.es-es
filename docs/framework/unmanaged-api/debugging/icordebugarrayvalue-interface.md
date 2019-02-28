---
title: ICorDebugArrayValue (Interfaz)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73898bf5f4303d677787bae587a16f2f325dee9e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970849"
---
# <a name="icordebugarrayvalue-interface"></a><span data-ttu-id="4eafa-102">ICorDebugArrayValue (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4eafa-102">ICorDebugArrayValue Interface</span></span>

<span data-ttu-id="4eafa-103">Una subclase del ICorDebugHeapValue que representa una matriz unidimensional o multidimensional.</span><span class="sxs-lookup"><span data-stu-id="4eafa-103">A subclass of ICorDebugHeapValue that represents a single-dimensional or multi-dimensional array.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4eafa-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="4eafa-104">Methods</span></span>  
  
|<span data-ttu-id="4eafa-105">Método</span><span class="sxs-lookup"><span data-stu-id="4eafa-105">Method</span></span>|<span data-ttu-id="4eafa-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="4eafa-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4eafa-107">GetBaseIndicies (método)</span><span class="sxs-lookup"><span data-stu-id="4eafa-107">GetBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getbaseindicies-method.md)|<span data-ttu-id="4eafa-108">Obtiene el índice de base de cada dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="4eafa-108">Gets the base index of each dimension in the array.</span></span>|  
|[<span data-ttu-id="4eafa-109">GetCount (método)</span><span class="sxs-lookup"><span data-stu-id="4eafa-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getcount-method.md)|<span data-ttu-id="4eafa-110">Obtiene el número total de elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="4eafa-110">Gets the total number of elements in the array.</span></span>|  
|[<span data-ttu-id="4eafa-111">GetDimensions (método)</span><span class="sxs-lookup"><span data-stu-id="4eafa-111">GetDimensions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getdimensions-method.md)|<span data-ttu-id="4eafa-112">Obtiene las dimensiones de la matriz.</span><span class="sxs-lookup"><span data-stu-id="4eafa-112">Gets the dimensions of the array.</span></span>|  
|[<span data-ttu-id="4eafa-113">GetElement (método)</span><span class="sxs-lookup"><span data-stu-id="4eafa-113">GetElement Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelement-method.md)|<span data-ttu-id="4eafa-114">Obtiene un valor que representa el elemento especificado de la matriz.</span><span class="sxs-lookup"><span data-stu-id="4eafa-114">Gets a value representing the given element in the array.</span></span>|  
|[<span data-ttu-id="4eafa-115">GetElementAtPosition (método)</span><span class="sxs-lookup"><span data-stu-id="4eafa-115">GetElementAtPosition Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementatposition-method.md)|<span data-ttu-id="4eafa-116">Obtiene el elemento en la posición dada, tratando la matriz como una matriz unidimensional de base cero.</span><span class="sxs-lookup"><span data-stu-id="4eafa-116">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>|  
|[<span data-ttu-id="4eafa-117">GetElementType (método)</span><span class="sxs-lookup"><span data-stu-id="4eafa-117">GetElementType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementtype-method.md)|<span data-ttu-id="4eafa-118">Obtiene el tipo simple de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="4eafa-118">Gets the simple type of the elements in the array.</span></span>|  
|[<span data-ttu-id="4eafa-119">GetRank (método)</span><span class="sxs-lookup"><span data-stu-id="4eafa-119">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getrank-method.md)|<span data-ttu-id="4eafa-120">Obtiene el número de dimensiones de la matriz.</span><span class="sxs-lookup"><span data-stu-id="4eafa-120">Gets the number of dimensions in the array.</span></span>|  
|[<span data-ttu-id="4eafa-121">HasBaseIndicies (método)</span><span class="sxs-lookup"><span data-stu-id="4eafa-121">HasBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-hasbaseindicies-method.md)|<span data-ttu-id="4eafa-122">Determina si la matriz tiene índices de base.</span><span class="sxs-lookup"><span data-stu-id="4eafa-122">Determines whether the array has base indexes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4eafa-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4eafa-123">Remarks</span></span>  
 <span data-ttu-id="4eafa-124">`ICorDebugArrayValue` admite matrices unidimensionales y multidimensionales.</span><span class="sxs-lookup"><span data-stu-id="4eafa-124">`ICorDebugArrayValue` supports both single-dimensional and multi-dimensional arrays.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4eafa-125">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="4eafa-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4eafa-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4eafa-126">Requirements</span></span>  
 <span data-ttu-id="4eafa-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4eafa-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4eafa-128">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4eafa-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4eafa-129">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4eafa-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4eafa-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4eafa-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4eafa-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="4eafa-131">See also</span></span>
- [<span data-ttu-id="4eafa-132">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="4eafa-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
