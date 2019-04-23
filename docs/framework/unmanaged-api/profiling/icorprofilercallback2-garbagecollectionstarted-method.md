---
title: ICorProfilerCallback2::GarbageCollectionStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.GarbageCollectionStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::GarbageCollectionStarted
helpviewer_keywords:
- GarbageCollectionStarted method [.NET Framework profiling]
- ICorProfilerCallback2::GarbageCollectionStarted method [.NET Framework profiling]
ms.assetid: 44eef087-f21f-4fe2-b481-f8a0ee022e7d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f5f9104dded44540c47c955c15354d8d76a27650
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183078"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a><span data-ttu-id="08d5a-102">ICorProfilerCallback2::GarbageCollectionStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="08d5a-102">ICorProfilerCallback2::GarbageCollectionStarted Method</span></span>
<span data-ttu-id="08d5a-103">Notifica al generador de perfiles de código que ha iniciado la recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="08d5a-103">Notifies the code profiler that garbage collection has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08d5a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="08d5a-104">Syntax</span></span>  
  
```  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08d5a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="08d5a-105">Parameters</span></span>  
 `cGenerations`  
 <span data-ttu-id="08d5a-106">[in] El número total de entradas en el `generationCollected` matriz.</span><span class="sxs-lookup"><span data-stu-id="08d5a-106">[in] The total number of entries in the `generationCollected` array.</span></span>  
  
 `generationCollected`  
 <span data-ttu-id="08d5a-107">[in] Una matriz de valores booleanos, que son `true` si la generación que se corresponde con el índice de matriz está siendo recopilados por esta colección de elementos no utilizados; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="08d5a-107">[in] An array of Boolean values, which are `true` if the generation that corresponds to the array index is being collected by this garbage collection; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="08d5a-108">La matriz se indiza por un valor de la [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeración, que indica la generación.</span><span class="sxs-lookup"><span data-stu-id="08d5a-108">The array is indexed by a value of the [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeration, which indicates the generation.</span></span>  
  
 `reason`  
 <span data-ttu-id="08d5a-109">[in] Un valor de la [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) indujo la enumeración que indica la razón por la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="08d5a-109">[in] A value of the [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) enumeration that indicates the reason the garbage collection was induced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08d5a-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="08d5a-110">Remarks</span></span>  
 <span data-ttu-id="08d5a-111">Todas las devoluciones de llamada que pertenecen a esta colección de elementos no utilizados se producirán entre el `GarbageCollectionStarted` devolución de llamada y el correspondiente [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="08d5a-111">All callbacks that pertain to this garbage collection will occur between the `GarbageCollectionStarted` callback and the corresponding [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback.</span></span> <span data-ttu-id="08d5a-112">No es necesitan que estas devoluciones de llamada se produzca en el mismo subproceso.</span><span class="sxs-lookup"><span data-stu-id="08d5a-112">These callbacks need not occur on the same thread.</span></span>  
  
 <span data-ttu-id="08d5a-113">Es seguro para el generador de perfiles inspeccionar los objetos en sus ubicaciones originales durante la `GarbageCollectionStarted` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="08d5a-113">It is safe for the profiler to inspect objects in their original locations during the `GarbageCollectionStarted` callback.</span></span> <span data-ttu-id="08d5a-114">El recolector de elementos no utilizados se iniciará el movimiento de objetos después de la devolución de `GarbageCollectionStarted`.</span><span class="sxs-lookup"><span data-stu-id="08d5a-114">The garbage collector will begin moving objects after the return from `GarbageCollectionStarted`.</span></span> <span data-ttu-id="08d5a-115">Después de que el generador de perfiles ha devuelto desde esta devolución de llamada, el generador de perfiles debe tener en cuenta todos los identificadores de objeto son válidos hasta que reciba un `ICorProfilerCallback2::GarbageCollectionFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="08d5a-115">After the profiler has returned from this callback, the profiler should consider all object IDs to be invalid until it receives a `ICorProfilerCallback2::GarbageCollectionFinished` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08d5a-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="08d5a-116">Requirements</span></span>  
 <span data-ttu-id="08d5a-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08d5a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08d5a-118">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="08d5a-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="08d5a-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08d5a-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08d5a-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08d5a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08d5a-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="08d5a-121">See also</span></span>

- [<span data-ttu-id="08d5a-122">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="08d5a-122">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="08d5a-123">ICorProfilerCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="08d5a-123">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
