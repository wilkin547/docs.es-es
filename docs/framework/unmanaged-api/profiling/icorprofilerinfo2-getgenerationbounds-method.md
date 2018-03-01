---
title: "ICorProfilerInfo2::GetGenerationBounds (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo2.GetGenerationBounds
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetGenerationBounds
helpviewer_keywords:
- ICorProfilerInfo2::GetGenerationBounds method [.NET Framework profiling]
- GetGenerationBounds method [.NET Framework profiling]
ms.assetid: 9c37185f-d1e0-4a6e-8b99-707f7df61d88
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c84be5d7e78c348c0368e9639a470a8fc60e2ca7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getgenerationbounds-method"></a><span data-ttu-id="d5892-102">ICorProfilerInfo2::GetGenerationBounds (Método)</span><span class="sxs-lookup"><span data-stu-id="d5892-102">ICorProfilerInfo2::GetGenerationBounds Method</span></span>
<span data-ttu-id="d5892-103">Obtiene las regiones de memoria, que son segmentos del montón, que componen las distintas generaciones de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="d5892-103">Gets the memory regions, which are segments of the heap, that make up the various garbage collection generations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5892-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d5892-104">Syntax</span></span>  
  
```  
HRESULT GetGenerationBounds(  
    [in]  ULONG cObjectRanges,  
    [out] ULONG *pcObjectRanges,  
    [out, size_is(cObjectRanges), length_is(*pcObjectRanges)] COR_PRF_GC_GENERATION_RANGE ranges[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d5892-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d5892-105">Parameters</span></span>  
 `cObjectRanges`  
 <span data-ttu-id="d5892-106">[in] Número de elementos asignado por el llamador para la matriz `ranges`.</span><span class="sxs-lookup"><span data-stu-id="d5892-106">[in] The number of elements allocated by the caller for the `ranges` array.</span></span>  
  
 `pcObjectRanges`  
 <span data-ttu-id="d5892-107">[out] Puntero a un entero que especifica el número total de intervalos, de los que algunos o todos se devolverán en la matriz `ranges`.</span><span class="sxs-lookup"><span data-stu-id="d5892-107">[out] A pointer to an integer that specifies the total number of ranges, some or all of which will be returned in the `ranges` array.</span></span>  
  
 `ranges`  
 <span data-ttu-id="d5892-108">[out] Una matriz de [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) estructuras, cada uno de los cuales describe un intervalo (es decir, un bloque) de memoria en la generación que se está sometiendo a la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="d5892-108">[out] An array of [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structures, each of which describes a range (that is, block) of memory within the generation that is undergoing garbage collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5892-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d5892-109">Remarks</span></span>  
 <span data-ttu-id="d5892-110">Se puede llamar al método `GetGenerationBounds` desde cualquier devolución de llamada del generador de perfiles, siempre que la recolección de elementos no utilizados no esté en curso.</span><span class="sxs-lookup"><span data-stu-id="d5892-110">The `GetGenerationBounds` method can be called from any profiler callback, provided that garbage collection is not in progress.</span></span> <span data-ttu-id="d5892-111">Es decir, se puede llamar desde cualquier devolución de llamada excepto las que se producen entre [ICorProfilerCallback2:: GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) y [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="d5892-111">That is, it can be called from any callback except those that occur between [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) and [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).</span></span>  
  
 <span data-ttu-id="d5892-112">La mayoría de los cambios de generación tienen lugar durante las recolecciones de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="d5892-112">Most shifting of generations takes place during garbage collections.</span></span> <span data-ttu-id="d5892-113">Las generaciones pueden crecer de una recolección a otra, pero por lo general no se mueven.</span><span class="sxs-lookup"><span data-stu-id="d5892-113">Generations might grow between collections but generally do not move around.</span></span> <span data-ttu-id="d5892-114">Por este motivo, los lugares más interesantes para llamar a `GetGenerationBounds` están en `ICorProfilerCallback2::GarbageCollectionStarted` y `ICorProfilerCallback2::GarbageCollectionFinished`.</span><span class="sxs-lookup"><span data-stu-id="d5892-114">Therefore, the most interesting places to call `GetGenerationBounds` are in `ICorProfilerCallback2::GarbageCollectionStarted` and `ICorProfilerCallback2::GarbageCollectionFinished`.</span></span>  
  
 <span data-ttu-id="d5892-115">Durante el inicio del programa, algunos objetos son asignados por el propio Common Language Runtime (CLR), por lo general en las generaciones 3 y 0.</span><span class="sxs-lookup"><span data-stu-id="d5892-115">During program startup, some objects are allocated by the common language runtime (CLR) itself, generally in generations 3 and 0.</span></span> <span data-ttu-id="d5892-116">Por lo tanto, en el momento en que se inicia la ejecución del código administrado, estas generaciones ya contendrán objetos.</span><span class="sxs-lookup"><span data-stu-id="d5892-116">Thus, by the time managed code starts executing, these generations will already contain objects.</span></span> <span data-ttu-id="d5892-117">Las generaciones 1 y 2 normalmente estarán vacías, salvo por los objetos ficticios generados por el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="d5892-117">Generations 1 and 2 will normally be empty, except for dummy objects that are generated by the garbage collector.</span></span> <span data-ttu-id="d5892-118">(El tamaño de los objetos ficticios es de 12 bytes en las implementaciones de 32 bits de CLR; el tamaño es mayor en las implementaciones de 64 bits). Puede que también vea intervalos de generación 2 dentro de los módulos producidos por el generador de imágenes nativas (NGen.exe).</span><span class="sxs-lookup"><span data-stu-id="d5892-118">(The size of dummy objects is 12 bytes in 32-bit implementations of the CLR; the size is larger in 64-bit implementations.) You might also see generation 2 ranges that are inside modules produced by the Native Image Generator (NGen.exe).</span></span> <span data-ttu-id="d5892-119">En este caso, los objetos de la generación 2 son *objetos inmovilizados*, que se asignan cuando se ejecuta NGen.exe en lugar de por el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="d5892-119">In this case, the objects in generation 2 are *frozen objects*, which are allocated when NGen.exe runs rather than by the garbage collector.</span></span>  
  
 <span data-ttu-id="d5892-120">Esta función usa búferes asignados por el llamador.</span><span class="sxs-lookup"><span data-stu-id="d5892-120">This function uses caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5892-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d5892-121">Requirements</span></span>  
 <span data-ttu-id="d5892-122">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5892-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5892-123">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d5892-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d5892-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5892-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5892-125">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5892-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5892-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5892-126">See Also</span></span>  
 [<span data-ttu-id="d5892-127">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d5892-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="d5892-128">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d5892-128">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 [<span data-ttu-id="d5892-129">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="d5892-129">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="d5892-130">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="d5892-130">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
