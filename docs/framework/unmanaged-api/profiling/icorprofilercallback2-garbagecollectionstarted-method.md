---
title: "ICorProfilerCallback2::GarbageCollectionStarted (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback2.GarbageCollectionStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback2::GarbageCollectionStarted
helpviewer_keywords:
- GarbageCollectionStarted method [.NET Framework profiling]
- ICorProfilerCallback2::GarbageCollectionStarted method [.NET Framework profiling]
ms.assetid: 44eef087-f21f-4fe2-b481-f8a0ee022e7d
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1e79eea059fab4810ece12dbc264f3d3b08b7ff4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a><span data-ttu-id="0a263-102">ICorProfilerCallback2::GarbageCollectionStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="0a263-102">ICorProfilerCallback2::GarbageCollectionStarted Method</span></span>
<span data-ttu-id="0a263-103">Notifica al generador de perfiles de código que ha iniciado la recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="0a263-103">Notifies the code profiler that garbage collection has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a263-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0a263-104">Syntax</span></span>  
  
```  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0a263-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a263-105">Parameters</span></span>  
 `cGenerations`  
 <span data-ttu-id="0a263-106">[in] El número total de entradas en la `generationCollected` matriz.</span><span class="sxs-lookup"><span data-stu-id="0a263-106">[in] The total number of entries in the `generationCollected` array.</span></span>  
  
 `generationCollected`  
 <span data-ttu-id="0a263-107">[in] Una matriz de valores booleanos, que son `true` si la generación que se corresponde con el índice de matriz se está recopilados por esta colección de elementos no utilizados; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="0a263-107">[in] An array of Boolean values, which are `true` if the generation that corresponds to the array index is being collected by this garbage collection; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="0a263-108">La matriz está indizada por un valor de la [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeración, que indica la generación.</span><span class="sxs-lookup"><span data-stu-id="0a263-108">The array is indexed by a value of the [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeration, which indicates the generation.</span></span>  
  
 `reason`  
 <span data-ttu-id="0a263-109">[in] Un valor de la [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) indujo enumeración que indica el motivo de la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="0a263-109">[in] A value of the [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) enumeration that indicates the reason the garbage collection was induced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a263-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0a263-110">Remarks</span></span>  
 <span data-ttu-id="0a263-111">Todas las devoluciones de llamada que pertenecen a esta colección de elementos no utilizados se producirán entre el `GarbageCollectionStarted` devolución de llamada y el correspondiente [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="0a263-111">All callbacks that pertain to this garbage collection will occur between the `GarbageCollectionStarted` callback and the corresponding [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback.</span></span> <span data-ttu-id="0a263-112">No es necesitan que estas devoluciones de llamada se produzca en el mismo subproceso.</span><span class="sxs-lookup"><span data-stu-id="0a263-112">These callbacks need not occur on the same thread.</span></span>  
  
 <span data-ttu-id="0a263-113">Es seguro para el generador de perfiles inspeccionar los objetos en sus ubicaciones originales durante la `GarbageCollectionStarted` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="0a263-113">It is safe for the profiler to inspect objects in their original locations during the `GarbageCollectionStarted` callback.</span></span> <span data-ttu-id="0a263-114">El recolector de elementos no utilizados se iniciará el movimiento de objetos después de la devolución de `GarbageCollectionStarted`.</span><span class="sxs-lookup"><span data-stu-id="0a263-114">The garbage collector will begin moving objects after the return from `GarbageCollectionStarted`.</span></span> <span data-ttu-id="0a263-115">Después de que el generador de perfiles ha devuelto por esta devolución de llamada, el generador de perfiles debe tener en cuenta todos los identificadores de objeto son válidos hasta que recibe un `ICorProfilerCallback2::GarbageCollectionFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="0a263-115">After the profiler has returned from this callback, the profiler should consider all object IDs to be invalid until it receives a `ICorProfilerCallback2::GarbageCollectionFinished` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a263-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0a263-116">Requirements</span></span>  
 <span data-ttu-id="0a263-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a263-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a263-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0a263-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0a263-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a263-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a263-120">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a263-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a263-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a263-121">See Also</span></span>  
 [<span data-ttu-id="0a263-122">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0a263-122">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="0a263-123">ICorProfilerCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0a263-123">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
