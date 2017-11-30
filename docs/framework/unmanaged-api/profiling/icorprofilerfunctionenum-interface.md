---
title: ICorProfilerFunctionEnum (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionEnum
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionEnum
helpviewer_keywords: ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0a1d4a38-cd0b-4231-91df-13646218ae72
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1067fa6738b23492b3a58500b4cb6ba1d030304f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerfunctionenum-interface"></a><span data-ttu-id="1cdf6-102">ICorProfilerFunctionEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1cdf6-102">ICorProfilerFunctionEnum Interface</span></span>
<span data-ttu-id="1cdf6-103">Proporciona métodos para iterar secuencialmente por una colección de funciones en Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="1cdf6-103">Provides methods to sequentially iterate through a collection of functions in the common language runtime.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1cdf6-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="1cdf6-104">Methods</span></span>  
  
|<span data-ttu-id="1cdf6-105">Método</span><span class="sxs-lookup"><span data-stu-id="1cdf6-105">Method</span></span>|<span data-ttu-id="1cdf6-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="1cdf6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1cdf6-107">Clone (método)</span><span class="sxs-lookup"><span data-stu-id="1cdf6-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-clone-method.md)|<span data-ttu-id="1cdf6-108">Obtiene un puntero de interfaz a una copia de esta interfaz `ICorProfilerFunctionEnum`.</span><span class="sxs-lookup"><span data-stu-id="1cdf6-108">Gets an interface pointer to a copy of this `ICorProfilerFunctionEnum` interface.</span></span>|  
|[<span data-ttu-id="1cdf6-109">GetCount (método)</span><span class="sxs-lookup"><span data-stu-id="1cdf6-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-getcount-method.md)|<span data-ttu-id="1cdf6-110">Obtiene el número de funciones que la aplicación cargó o que el generador de perfiles cargó forzosamente.</span><span class="sxs-lookup"><span data-stu-id="1cdf6-110">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>|  
|[<span data-ttu-id="1cdf6-111">Next (método)</span><span class="sxs-lookup"><span data-stu-id="1cdf6-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-next-method.md)|<span data-ttu-id="1cdf6-112">Obtiene el número especificado de funciones contiguas de una colección secuencial de funciones, comenzando en la posición actual del enumerador en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="1cdf6-112">Gets the specified number of contiguous functions from a sequential collection of functions, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="1cdf6-113">Reset (método)</span><span class="sxs-lookup"><span data-stu-id="1cdf6-113">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-reset-method.md)|<span data-ttu-id="1cdf6-114">Mueve el cursor del enumerador a la posición inicial de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="1cdf6-114">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="1cdf6-115">Skip (método)</span><span class="sxs-lookup"><span data-stu-id="1cdf6-115">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-skip-method.md)|<span data-ttu-id="1cdf6-116">Desplaza el cursor del enumerador desde su posición actual de manera que se omita el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="1cdf6-116">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1cdf6-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1cdf6-117">Remarks</span></span>  
 <span data-ttu-id="1cdf6-118">La interfaz `ICorProfilerFunctionEnum` es un enumerador.</span><span class="sxs-lookup"><span data-stu-id="1cdf6-118">The `ICorProfilerFunctionEnum` interface is an enumerator.</span></span> <span data-ttu-id="1cdf6-119">Permite al receptor de una matriz extraer los elementos del remitente a una velocidad que sea adecuada para el receptor.</span><span class="sxs-lookup"><span data-stu-id="1cdf6-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="1cdf6-120">En otras palabras, el receptor es capaz de controlar explícitamente el flujo de elementos de matriz, lo que evita los problemas asociados con pasar matrices de gran tamaño como parámetros de método.</span><span class="sxs-lookup"><span data-stu-id="1cdf6-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
 <span data-ttu-id="1cdf6-121">`ICorProfilerFunctionEnum` enumera las funciones que ya se han compilado con JIT, pero no incluye las funciones que se cargan desde imágenes nativas generadas con Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="1cdf6-121">`ICorProfilerFunctionEnum` enumerates over functions that have already been JIT-compiled, but does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cdf6-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1cdf6-122">Requirements</span></span>  
 <span data-ttu-id="1cdf6-123">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1cdf6-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cdf6-124">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1cdf6-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1cdf6-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1cdf6-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1cdf6-126">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1cdf6-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cdf6-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="1cdf6-127">See Also</span></span>  
 [<span data-ttu-id="1cdf6-128">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1cdf6-128">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="1cdf6-129">Interfaces de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="1cdf6-129">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="1cdf6-130">EnumJITedFunctions (método)</span><span class="sxs-lookup"><span data-stu-id="1cdf6-130">EnumJITedFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)
