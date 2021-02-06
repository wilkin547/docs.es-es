---
description: 'Más información sobre: método ICorProfilerCallback2:: Garbagecollectionstarted ('
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
ms.openlocfilehash: 2b57a21dc3a1751b5d4767ea940f64df61af4318
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647887"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a><span data-ttu-id="0e050-103">ICorProfilerCallback2::GarbageCollectionStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="0e050-103">ICorProfilerCallback2::GarbageCollectionStarted Method</span></span>

<span data-ttu-id="0e050-104">Notifica al generador de perfiles de código que se ha iniciado la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="0e050-104">Notifies the code profiler that garbage collection has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e050-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0e050-105">Syntax</span></span>  
  
```cpp  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e050-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0e050-106">Parameters</span></span>  

 `cGenerations`  
 <span data-ttu-id="0e050-107">de Número total de entradas de la `generationCollected` matriz.</span><span class="sxs-lookup"><span data-stu-id="0e050-107">[in] The total number of entries in the `generationCollected` array.</span></span>  
  
 `generationCollected`  
 <span data-ttu-id="0e050-108">de Matriz de valores booleanos, que es `true` si la generación que corresponde al índice de la matriz se está recopilando por esta recolección de elementos no utilizados; en caso contrario, es `false` .</span><span class="sxs-lookup"><span data-stu-id="0e050-108">[in] An array of Boolean values, which are `true` if the generation that corresponds to the array index is being collected by this garbage collection; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="0e050-109">La matriz se indiza mediante un valor de la enumeración [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) , que indica la generación.</span><span class="sxs-lookup"><span data-stu-id="0e050-109">The array is indexed by a value of the [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) enumeration, which indicates the generation.</span></span>  
  
 `reason`  
 <span data-ttu-id="0e050-110">de Un valor de la enumeración [COR_PRF_GC_REASON](cor-prf-gc-reason-enumeration.md) que indica la razón por la que se indujo la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="0e050-110">[in] A value of the [COR_PRF_GC_REASON](cor-prf-gc-reason-enumeration.md) enumeration that indicates the reason the garbage collection was induced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e050-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0e050-111">Remarks</span></span>  

 <span data-ttu-id="0e050-112">Todas las devoluciones de llamada que pertenecen a esta recolección de elementos no utilizados se producirán entre la `GarbageCollectionStarted` devolución de llamada y la devolución de llamada [ICorProfilerCallback2:: garbagecollectionfinished (](icorprofilercallback2-garbagecollectionfinished-method.md) correspondiente.</span><span class="sxs-lookup"><span data-stu-id="0e050-112">All callbacks that pertain to this garbage collection will occur between the `GarbageCollectionStarted` callback and the corresponding [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) callback.</span></span> <span data-ttu-id="0e050-113">No es necesario que estas devoluciones de llamada se realicen en el mismo subproceso.</span><span class="sxs-lookup"><span data-stu-id="0e050-113">These callbacks need not occur on the same thread.</span></span>  
  
 <span data-ttu-id="0e050-114">Es seguro que el generador de perfiles Inspeccione los objetos en sus ubicaciones originales durante la `GarbageCollectionStarted` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="0e050-114">It is safe for the profiler to inspect objects in their original locations during the `GarbageCollectionStarted` callback.</span></span> <span data-ttu-id="0e050-115">El recolector de elementos no utilizados comenzará a mover objetos después del retorno de `GarbageCollectionStarted` .</span><span class="sxs-lookup"><span data-stu-id="0e050-115">The garbage collector will begin moving objects after the return from `GarbageCollectionStarted`.</span></span> <span data-ttu-id="0e050-116">Una vez que el generador de perfiles ha devuelto desde esta devolución de llamada, el generador de perfiles debe considerar que todos los identificadores de objeto no son válidos hasta recibir una `ICorProfilerCallback2::GarbageCollectionFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="0e050-116">After the profiler has returned from this callback, the profiler should consider all object IDs to be invalid until it receives a `ICorProfilerCallback2::GarbageCollectionFinished` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e050-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0e050-117">Requirements</span></span>  

 <span data-ttu-id="0e050-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e050-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e050-119">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0e050-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0e050-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e050-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e050-121">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e050-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e050-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e050-122">See also</span></span>

- [<span data-ttu-id="0e050-123">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0e050-123">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="0e050-124">ICorProfilerCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0e050-124">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
