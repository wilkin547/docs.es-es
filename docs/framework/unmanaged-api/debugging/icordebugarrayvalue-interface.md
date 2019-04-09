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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 67fd1a9174b04e42b53f2b866a1dfdd504362aa9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168394"
---
# <a name="icordebugarrayvalue-interface"></a><span data-ttu-id="dd2fc-102">Interfaz ICorDebugArrayValue</span><span class="sxs-lookup"><span data-stu-id="dd2fc-102">ICorDebugArrayValue Interface</span></span>

<span data-ttu-id="dd2fc-103">Una subclase del ICorDebugHeapValue que representa una matriz unidimensional o multidimensional.</span><span class="sxs-lookup"><span data-stu-id="dd2fc-103">A subclass of ICorDebugHeapValue that represents a single-dimensional or multi-dimensional array.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dd2fc-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="dd2fc-104">Methods</span></span>  
  
|<span data-ttu-id="dd2fc-105">Método</span><span class="sxs-lookup"><span data-stu-id="dd2fc-105">Method</span></span>|<span data-ttu-id="dd2fc-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="dd2fc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dd2fc-107">Método GetBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="dd2fc-107">GetBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getbaseindicies-method.md)|<span data-ttu-id="dd2fc-108">Obtiene el índice de base de cada dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="dd2fc-108">Gets the base index of each dimension in the array.</span></span>|  
|[<span data-ttu-id="dd2fc-109">Método GetCount</span><span class="sxs-lookup"><span data-stu-id="dd2fc-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getcount-method.md)|<span data-ttu-id="dd2fc-110">Obtiene el número total de elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="dd2fc-110">Gets the total number of elements in the array.</span></span>|  
|[<span data-ttu-id="dd2fc-111">Método GetDimensions</span><span class="sxs-lookup"><span data-stu-id="dd2fc-111">GetDimensions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getdimensions-method.md)|<span data-ttu-id="dd2fc-112">Obtiene las dimensiones de la matriz.</span><span class="sxs-lookup"><span data-stu-id="dd2fc-112">Gets the dimensions of the array.</span></span>|  
|[<span data-ttu-id="dd2fc-113">Método GetElement</span><span class="sxs-lookup"><span data-stu-id="dd2fc-113">GetElement Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelement-method.md)|<span data-ttu-id="dd2fc-114">Obtiene un valor que representa el elemento especificado de la matriz.</span><span class="sxs-lookup"><span data-stu-id="dd2fc-114">Gets a value representing the given element in the array.</span></span>|  
|[<span data-ttu-id="dd2fc-115">Método GetElementAtPosition</span><span class="sxs-lookup"><span data-stu-id="dd2fc-115">GetElementAtPosition Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementatposition-method.md)|<span data-ttu-id="dd2fc-116">Obtiene el elemento en la posición dada, tratando la matriz como una matriz unidimensional de base cero.</span><span class="sxs-lookup"><span data-stu-id="dd2fc-116">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>|  
|[<span data-ttu-id="dd2fc-117">Método GetElementType</span><span class="sxs-lookup"><span data-stu-id="dd2fc-117">GetElementType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementtype-method.md)|<span data-ttu-id="dd2fc-118">Obtiene el tipo simple de los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="dd2fc-118">Gets the simple type of the elements in the array.</span></span>|  
|[<span data-ttu-id="dd2fc-119">Método GetRank</span><span class="sxs-lookup"><span data-stu-id="dd2fc-119">GetRank Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getrank-method.md)|<span data-ttu-id="dd2fc-120">Obtiene el número de dimensiones de la matriz.</span><span class="sxs-lookup"><span data-stu-id="dd2fc-120">Gets the number of dimensions in the array.</span></span>|  
|[<span data-ttu-id="dd2fc-121">Método HasBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="dd2fc-121">HasBaseIndicies Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-hasbaseindicies-method.md)|<span data-ttu-id="dd2fc-122">Determina si la matriz tiene índices de base.</span><span class="sxs-lookup"><span data-stu-id="dd2fc-122">Determines whether the array has base indexes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd2fc-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dd2fc-123">Remarks</span></span>  
 `ICorDebugArrayValue` <span data-ttu-id="dd2fc-124">admite matrices unidimensionales y multidimensionales.</span><span class="sxs-lookup"><span data-stu-id="dd2fc-124">supports both single-dimensional and multi-dimensional arrays.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd2fc-125">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="dd2fc-125">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd2fc-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dd2fc-126">Requirements</span></span>  
 <span data-ttu-id="dd2fc-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd2fc-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd2fc-128">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd2fc-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd2fc-129">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd2fc-129">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="dd2fc-130">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="dd2fc-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dd2fc-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd2fc-131">See also</span></span>

- [<span data-ttu-id="dd2fc-132">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="dd2fc-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
