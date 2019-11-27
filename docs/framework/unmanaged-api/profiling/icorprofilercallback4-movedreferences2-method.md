---
title: ICorProfilerCallback4::MovedReferences2 (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.MovedReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::MovedReferences2
helpviewer_keywords:
- MovedReferences2 method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::MovedReferences2 method [.NET Framework profiling]
ms.assetid: d17a065b-5bc6-4817-b3e1-1e413fcb33a8
topic_type:
- apiref
ms.openlocfilehash: 37d5f5e8294bb87a8796d6dcae046864904b096b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439371"
---
# <a name="icorprofilercallback4movedreferences2-method"></a><span data-ttu-id="a9486-102">ICorProfilerCallback4::MovedReferences2 (Método)</span><span class="sxs-lookup"><span data-stu-id="a9486-102">ICorProfilerCallback4::MovedReferences2 Method</span></span>
<span data-ttu-id="a9486-103">Se le llama para informar de la nueva distribución de los objetos del montón como resultado de una recolección de elementos no utilizados con compactación.</span><span class="sxs-lookup"><span data-stu-id="a9486-103">Called to report the new layout of objects in the heap as a result of a compacting garbage collection.</span></span> <span data-ttu-id="a9486-104">Se llama a este método si el generador de perfiles ha implementado la interfaz [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="a9486-104">This method is called if the profiler has implemented the [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interface.</span></span> <span data-ttu-id="a9486-105">Esta devolución de llamada reemplaza el método [ICorProfilerCallback:: MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md) , ya que puede informar de intervalos de objetos mayores cuyas longitudes superen lo que se puede expresar en un ulong.</span><span class="sxs-lookup"><span data-stu-id="a9486-105">This callback replaces the [ICorProfilerCallback::MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md) method, because it can report larger ranges of objects whose lengths exceed what can be expressed in a ULONG.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9486-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9486-106">Syntax</span></span>  
  
```cpp  
HRESULT MovedReferences2(  
    [in]  ULONG  cMovedObjectIDRanges,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID oldObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID newObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] SIZE_T    cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9486-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a9486-107">Parameters</span></span>  
 `cMovedObjectIDRanges`  
 <span data-ttu-id="a9486-108">[in] Número de bloques de objetos contiguos que se movieron como resultado de la recolección de elementos no utilizados con compactación.</span><span class="sxs-lookup"><span data-stu-id="a9486-108">[in] The number of blocks of contiguous objects that moved as the result of the compacting garbage collection.</span></span> <span data-ttu-id="a9486-109">Es decir, el valor de `cMovedObjectIDRanges` es el tamaño total de las matrices `oldObjectIDRangeStart`, `newObjectIDRangeStart` y `cObjectIDRangeLength`.</span><span class="sxs-lookup"><span data-stu-id="a9486-109">That is, the value of `cMovedObjectIDRanges` is the total size of the `oldObjectIDRangeStart`, `newObjectIDRangeStart`, and `cObjectIDRangeLength` arrays.</span></span>  
  
 <span data-ttu-id="a9486-110">Los tres argumentos siguientes de `MovedReferences2` son matrices paralelas.</span><span class="sxs-lookup"><span data-stu-id="a9486-110">The next three arguments of `MovedReferences2` are parallel arrays.</span></span> <span data-ttu-id="a9486-111">En otras palabras, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]` y `cObjectIDRangeLength[i]` hacen referencia a un único bloque de objetos contiguos.</span><span class="sxs-lookup"><span data-stu-id="a9486-111">In other words, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]`, and `cObjectIDRangeLength[i]` all concern a single block of contiguous objects.</span></span>  
  
 `oldObjectIDRangeStart`  
 <span data-ttu-id="a9486-112">[in] Matriz de valores `ObjectID`, cada uno de los cuales es la dirección inicial antigua (antes de la recolección de elementos no utilizados) de un bloque de objetos contiguos activos en la memoria.</span><span class="sxs-lookup"><span data-stu-id="a9486-112">[in] An array of `ObjectID` values, each of which is the old (pre-garbage collection) starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `newObjectIDRangeStart`  
 <span data-ttu-id="a9486-113">[in] Matriz de valores `ObjectID`, cada uno de los cuales es la dirección inicial nueva (después de la recolección de elementos no utilizados) de un bloque de objetos contiguos activos en la memoria.</span><span class="sxs-lookup"><span data-stu-id="a9486-113">[in] An array of `ObjectID` values, each of which is the new (post-garbage collection) starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `cObjectIDRangeLength`  
 <span data-ttu-id="a9486-114">[in] Matriz de enteros, cada uno de los cuales es el tamaño de un bloque de objetos contiguos en la memoria.</span><span class="sxs-lookup"><span data-stu-id="a9486-114">[in] An array of integers, each of which is the size of a block of contiguous objects in memory.</span></span>  
  
 <span data-ttu-id="a9486-115">Se especifica un tamaño para cada bloque al que se hace referencia en las matrices `oldObjectIDRangeStart` y `newObjectIDRangeStart`.</span><span class="sxs-lookup"><span data-stu-id="a9486-115">A size is specified for each block that is referenced in the `oldObjectIDRangeStart` and `newObjectIDRangeStart` arrays.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9486-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a9486-116">Remarks</span></span>  
 <span data-ttu-id="a9486-117">Un recolector de elementos no utilizados con compactación recupera la memoria ocupada por los objetos inactivos y compacta ese espacio liberado.</span><span class="sxs-lookup"><span data-stu-id="a9486-117">A compacting garbage collector reclaims the memory occupied by dead objects and compacts that freed space.</span></span> <span data-ttu-id="a9486-118">Como resultado, los objetos activos podrían moverse dentro del montón y los valores de `ObjectID` distribuidos por notificaciones anteriores podrían cambiar.</span><span class="sxs-lookup"><span data-stu-id="a9486-118">As a result, live objects might be moved within the heap, and `ObjectID` values distributed by previous notifications might change.</span></span>  
  
 <span data-ttu-id="a9486-119">Supongamos que un valor `ObjectID` existente (`oldObjectID`) se encuentra dentro del intervalo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a9486-119">Assume that an existing `ObjectID` value (`oldObjectID`) lies within the following range:</span></span>  
  
 `oldObjectIDRangeStart[i]` <= `oldObjectID` < `oldObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 <span data-ttu-id="a9486-120">En este caso, el desplazamiento desde el inicio del intervalo al inicio del objeto es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="a9486-120">In this case, the offset from the start of the range to the start of the object is as follows:</span></span>  
  
 `oldObjectID` - `oldObjectRangeStart[i]`  
  
 <span data-ttu-id="a9486-121">Para cualquier valor de `i` que esté en el intervalo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a9486-121">For any value of `i` that is in the following range:</span></span>  
  
 <span data-ttu-id="a9486-122">0 < = `i` < `cMovedObjectIDRanges`</span><span class="sxs-lookup"><span data-stu-id="a9486-122">0 <= `i` < `cMovedObjectIDRanges`</span></span>  
  
 <span data-ttu-id="a9486-123">puede calcular el nuevo `ObjectID` de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="a9486-123">you can calculate the new `ObjectID` as follows:</span></span>  
  
 <span data-ttu-id="a9486-124">`newObjectID` = `newObjectIDRangeStart[i]` + (`oldObjectID` – `oldObjectIDRangeStart[i]`)</span><span class="sxs-lookup"><span data-stu-id="a9486-124">`newObjectID` = `newObjectIDRangeStart[i]` + (`oldObjectID` – `oldObjectIDRangeStart[i]`)</span></span>  
  
 <span data-ttu-id="a9486-125">Ninguno de los valores `ObjectID` pasados por `MovedReferences2` son válidos durante la devolución de llamada en sí porque el recolector de elementos no utilizados puede estar en pleno proceso de mover objetos desde ubicaciones anteriores a ubicaciones nuevas.</span><span class="sxs-lookup"><span data-stu-id="a9486-125">None of the `ObjectID` values passed by `MovedReferences2` are valid during the callback itself, because the garbage collector might be in the middle of moving objects from old locations to new locations.</span></span> <span data-ttu-id="a9486-126">Por lo tanto, los generadores de perfiles no deben intentar inspeccionar objetos durante una llamada a `MovedReferences2`.</span><span class="sxs-lookup"><span data-stu-id="a9486-126">Therefore, profilers should not attempt to inspect objects during a `MovedReferences2` call.</span></span> <span data-ttu-id="a9486-127">Una devolución de llamada [ICorProfilerCallback2:: garbagecollectionfinished (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) indica que todos los objetos se movieron a sus nuevas ubicaciones y se puede realizar la inspección.</span><span class="sxs-lookup"><span data-stu-id="a9486-127">A [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback indicates that all objects have been moved to their new locations and inspection can be performed.</span></span>  
  
 <span data-ttu-id="a9486-128">Si el generador de perfiles implementa las interfaces [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) y [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) , se llama al método `MovedReferences2` antes que al método [ICorProfilerCallback:: MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md) , pero solo si el método `MovedReferences2` se devuelve correctamente.</span><span class="sxs-lookup"><span data-stu-id="a9486-128">If the profiler implements both the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) and the [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interfaces, the `MovedReferences2` method is called before the [ICorProfilerCallback::MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md) method, but only if the `MovedReferences2` method returns successfully.</span></span> <span data-ttu-id="a9486-129">Los generadores de perfiles pueden devolver un HRESULT que indica un error del método `MovedReferences2` para evitar llamar al segundo método.</span><span class="sxs-lookup"><span data-stu-id="a9486-129">Profilers can return an HRESULT that indicates failure from the `MovedReferences2` method, to avoid calling the second method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9486-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9486-130">Requirements</span></span>  
 <span data-ttu-id="a9486-131">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9486-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9486-132">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a9486-132">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a9486-133">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9486-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9486-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9486-134">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9486-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9486-135">See also</span></span>

- [<span data-ttu-id="a9486-136">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9486-136">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="a9486-137">MovedReferences (método)</span><span class="sxs-lookup"><span data-stu-id="a9486-137">MovedReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)
- [<span data-ttu-id="a9486-138">ICorProfilerCallback4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9486-138">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [<span data-ttu-id="a9486-139">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a9486-139">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="a9486-140">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a9486-140">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
