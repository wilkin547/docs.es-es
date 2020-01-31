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
ms.openlocfilehash: c90c790c519cc0c422657e6e2d8040a365fbf48c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865784"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a><span data-ttu-id="94fe2-102">ICorProfilerCallback2::GarbageCollectionStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="94fe2-102">ICorProfilerCallback2::GarbageCollectionStarted Method</span></span>
<span data-ttu-id="94fe2-103">Notifica al generador de perfiles de código que se ha iniciado la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="94fe2-103">Notifies the code profiler that garbage collection has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94fe2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="94fe2-104">Syntax</span></span>  
  
```cpp  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94fe2-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="94fe2-105">Parameters</span></span>  
 `cGenerations`  
 <span data-ttu-id="94fe2-106">de Número total de entradas de la matriz de `generationCollected`.</span><span class="sxs-lookup"><span data-stu-id="94fe2-106">[in] The total number of entries in the `generationCollected` array.</span></span>  
  
 `generationCollected`  
 <span data-ttu-id="94fe2-107">de Matriz de valores booleanos, que se `true` si la generación que corresponde al índice de la matriz se va a recopilar mediante esta recolección de elementos no utilizados; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="94fe2-107">[in] An array of Boolean values, which are `true` if the generation that corresponds to the array index is being collected by this garbage collection; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="94fe2-108">La matriz se indiza mediante un valor de la enumeración [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) , que indica la generación.</span><span class="sxs-lookup"><span data-stu-id="94fe2-108">The array is indexed by a value of the [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) enumeration, which indicates the generation.</span></span>  
  
 `reason`  
 <span data-ttu-id="94fe2-109">de Un valor de la enumeración [COR_PRF_GC_REASON](cor-prf-gc-reason-enumeration.md) que indica la razón por la que se indujo la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="94fe2-109">[in] A value of the [COR_PRF_GC_REASON](cor-prf-gc-reason-enumeration.md) enumeration that indicates the reason the garbage collection was induced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94fe2-110">Notas</span><span class="sxs-lookup"><span data-stu-id="94fe2-110">Remarks</span></span>  
 <span data-ttu-id="94fe2-111">Todas las devoluciones de llamada que pertenecen a esta recolección de elementos no utilizados se producirán entre la `GarbageCollectionStarted` devolución de llamada y la devolución de llamada [ICorProfilerCallback2:: garbagecollectionfinished (](icorprofilercallback2-garbagecollectionfinished-method.md) correspondiente.</span><span class="sxs-lookup"><span data-stu-id="94fe2-111">All callbacks that pertain to this garbage collection will occur between the `GarbageCollectionStarted` callback and the corresponding [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) callback.</span></span> <span data-ttu-id="94fe2-112">No es necesario que estas devoluciones de llamada se realicen en el mismo subproceso.</span><span class="sxs-lookup"><span data-stu-id="94fe2-112">These callbacks need not occur on the same thread.</span></span>  
  
 <span data-ttu-id="94fe2-113">Es seguro que el generador de perfiles Inspeccione los objetos en sus ubicaciones originales durante la devolución de llamada de `GarbageCollectionStarted`.</span><span class="sxs-lookup"><span data-stu-id="94fe2-113">It is safe for the profiler to inspect objects in their original locations during the `GarbageCollectionStarted` callback.</span></span> <span data-ttu-id="94fe2-114">El recolector de elementos no utilizados comenzará a mover objetos después del retorno de `GarbageCollectionStarted`.</span><span class="sxs-lookup"><span data-stu-id="94fe2-114">The garbage collector will begin moving objects after the return from `GarbageCollectionStarted`.</span></span> <span data-ttu-id="94fe2-115">Una vez que el generador de perfiles ha devuelto desde esta devolución de llamada, el generador de perfiles debe considerar que todos los identificadores de objeto no son válidos hasta recibir una devolución de llamada de `ICorProfilerCallback2::GarbageCollectionFinished`.</span><span class="sxs-lookup"><span data-stu-id="94fe2-115">After the profiler has returned from this callback, the profiler should consider all object IDs to be invalid until it receives a `ICorProfilerCallback2::GarbageCollectionFinished` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94fe2-116">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="94fe2-116">Requirements</span></span>  
 <span data-ttu-id="94fe2-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94fe2-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94fe2-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="94fe2-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="94fe2-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94fe2-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94fe2-120">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94fe2-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94fe2-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="94fe2-121">See also</span></span>

- [<span data-ttu-id="94fe2-122">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="94fe2-122">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="94fe2-123">ICorProfilerCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="94fe2-123">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
