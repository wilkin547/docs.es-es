---
description: 'Más información sobre: ICorProfilerCallback4:: Movedreferences2 ((método)'
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
ms.openlocfilehash: 37bd1c91866a583bf4ba04e3e532d0efe5a11fc9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788740"
---
# <a name="icorprofilercallback4movedreferences2-method"></a><span data-ttu-id="bfaaf-103">ICorProfilerCallback4::MovedReferences2 (Método)</span><span class="sxs-lookup"><span data-stu-id="bfaaf-103">ICorProfilerCallback4::MovedReferences2 Method</span></span>

<span data-ttu-id="bfaaf-104">Se le llama para informar de la nueva distribución de los objetos del montón como resultado de una recolección de elementos no utilizados con compactación.</span><span class="sxs-lookup"><span data-stu-id="bfaaf-104">Called to report the new layout of objects in the heap as a result of a compacting garbage collection.</span></span> <span data-ttu-id="bfaaf-105">Se llama a este método si el generador de perfiles ha implementado la interfaz [ICorProfilerCallback4](icorprofilercallback4-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="bfaaf-105">This method is called if the profiler has implemented the [ICorProfilerCallback4](icorprofilercallback4-interface.md) interface.</span></span> <span data-ttu-id="bfaaf-106">Esta devolución de llamada reemplaza el método [ICorProfilerCallback:: MovedReferences](icorprofilercallback-movedreferences-method.md) , ya que puede informar de intervalos de objetos mayores cuyas longitudes superen lo que se puede expresar en un ulong.</span><span class="sxs-lookup"><span data-stu-id="bfaaf-106">This callback replaces the [ICorProfilerCallback::MovedReferences](icorprofilercallback-movedreferences-method.md) method, because it can report larger ranges of objects whose lengths exceed what can be expressed in a ULONG.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfaaf-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bfaaf-107">Syntax</span></span>  
  
```cpp  
HRESULT MovedReferences2(  
    [in]  ULONG  cMovedObjectIDRanges,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID oldObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID newObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] SIZE_T    cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="bfaaf-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bfaaf-108">Parameters</span></span>  

 `cMovedObjectIDRanges`  
 <span data-ttu-id="bfaaf-109">[in] Número de bloques de objetos contiguos que se movieron como resultado de la recolección de elementos no utilizados con compactación.</span><span class="sxs-lookup"><span data-stu-id="bfaaf-109">[in] The number of blocks of contiguous objects that moved as the result of the compacting garbage collection.</span></span> <span data-ttu-id="bfaaf-110">Es decir, el valor de `cMovedObjectIDRanges` es el tamaño total de las matrices `oldObjectIDRangeStart`, `newObjectIDRangeStart` y `cObjectIDRangeLength`.</span><span class="sxs-lookup"><span data-stu-id="bfaaf-110">That is, the value of `cMovedObjectIDRanges` is the total size of the `oldObjectIDRangeStart`, `newObjectIDRangeStart`, and `cObjectIDRangeLength` arrays.</span></span>  
  
 <span data-ttu-id="bfaaf-111">Los tres argumentos siguientes de `MovedReferences2` son matrices paralelas.</span><span class="sxs-lookup"><span data-stu-id="bfaaf-111">The next three arguments of `MovedReferences2` are parallel arrays.</span></span> <span data-ttu-id="bfaaf-112">En otras palabras, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]` y `cObjectIDRangeLength[i]` hacen referencia a un único bloque de objetos contiguos.</span><span class="sxs-lookup"><span data-stu-id="bfaaf-112">In other words, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]`, and `cObjectIDRangeLength[i]` all concern a single block of contiguous objects.</span></span>  
  
 `oldObjectIDRangeStart`  
 <span data-ttu-id="bfaaf-113">[in] Matriz de valores `ObjectID`, cada uno de los cuales es la dirección inicial antigua (antes de la recolección de elementos no utilizados) de un bloque de objetos contiguos activos en la memoria.</span><span class="sxs-lookup"><span data-stu-id="bfaaf-113">[in] An array of `ObjectID` values, each of which is the old (pre-garbage collection) starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `newObjectIDRangeStart`  
 <span data-ttu-id="bfaaf-114">[in] Matriz de valores `ObjectID`, cada uno de los cuales es la dirección inicial nueva (después de la recolección de elementos no utilizados) de un bloque de objetos contiguos activos en la memoria.</span><span class="sxs-lookup"><span data-stu-id="bfaaf-114">[in] An array of `ObjectID` values, each of which is the new (post-garbage collection) starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `cObjectIDRangeLength`  
 <span data-ttu-id="bfaaf-115">[in] Matriz de enteros, cada uno de los cuales es el tamaño de un bloque de objetos contiguos en la memoria.</span><span class="sxs-lookup"><span data-stu-id="bfaaf-115">[in] An array of integers, each of which is the size of a block of contiguous objects in memory.</span></span>  
  
 <span data-ttu-id="bfaaf-116">Se especifica un tamaño para cada bloque al que se hace referencia en las matrices `oldObjectIDRangeStart` y `newObjectIDRangeStart`.</span><span class="sxs-lookup"><span data-stu-id="bfaaf-116">A size is specified for each block that is referenced in the `oldObjectIDRangeStart` and `newObjectIDRangeStart` arrays.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bfaaf-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bfaaf-117">Remarks</span></span>  

 <span data-ttu-id="bfaaf-118">Un recolector de elementos no utilizados con compactación recupera la memoria ocupada por los objetos inactivos y compacta ese espacio liberado.</span><span class="sxs-lookup"><span data-stu-id="bfaaf-118">A compacting garbage collector reclaims the memory occupied by dead objects and compacts that freed space.</span></span> <span data-ttu-id="bfaaf-119">Como resultado, los objetos activos podrían moverse dentro del montón y los valores de `ObjectID` distribuidos por notificaciones anteriores podrían cambiar.</span><span class="sxs-lookup"><span data-stu-id="bfaaf-119">As a result, live objects might be moved within the heap, and `ObjectID` values distributed by previous notifications might change.</span></span>  
  
 <span data-ttu-id="bfaaf-120">Supongamos que un valor `ObjectID` existente (`oldObjectID`) se encuentra dentro del intervalo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bfaaf-120">Assume that an existing `ObjectID` value (`oldObjectID`) lies within the following range:</span></span>  
  
 `oldObjectIDRangeStart[i]` <= `oldObjectID` < `oldObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 <span data-ttu-id="bfaaf-121">En este caso, el desplazamiento desde el inicio del intervalo al inicio del objeto es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="bfaaf-121">In this case, the offset from the start of the range to the start of the object is as follows:</span></span>  
  
 `oldObjectID` - `oldObjectRangeStart[i]`  
  
 <span data-ttu-id="bfaaf-122">Para cualquier valor de `i` que esté en el intervalo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bfaaf-122">For any value of `i` that is in the following range:</span></span>  
  
 <span data-ttu-id="bfaaf-123">0 <= `i` < `cMovedObjectIDRanges`</span><span class="sxs-lookup"><span data-stu-id="bfaaf-123">0 <= `i` < `cMovedObjectIDRanges`</span></span>  
  
 <span data-ttu-id="bfaaf-124">puede calcular el nuevo `ObjectID` de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="bfaaf-124">you can calculate the new `ObjectID` as follows:</span></span>  
  
 <span data-ttu-id="bfaaf-125">`newObjectID` = `newObjectIDRangeStart[i]` + ( `oldObjectID` – `oldObjectIDRangeStart[i]` )</span><span class="sxs-lookup"><span data-stu-id="bfaaf-125">`newObjectID` = `newObjectIDRangeStart[i]` + (`oldObjectID` – `oldObjectIDRangeStart[i]`)</span></span>  
  
 <span data-ttu-id="bfaaf-126">Ninguno de los valores `ObjectID` pasados por `MovedReferences2` son válidos durante la devolución de llamada en sí porque el recolector de elementos no utilizados puede estar en pleno proceso de mover objetos desde ubicaciones anteriores a ubicaciones nuevas.</span><span class="sxs-lookup"><span data-stu-id="bfaaf-126">None of the `ObjectID` values passed by `MovedReferences2` are valid during the callback itself, because the garbage collector might be in the middle of moving objects from old locations to new locations.</span></span> <span data-ttu-id="bfaaf-127">Por lo tanto, los generadores de perfiles no deben intentar inspeccionar objetos durante una llamada a `MovedReferences2`.</span><span class="sxs-lookup"><span data-stu-id="bfaaf-127">Therefore, profilers should not attempt to inspect objects during a `MovedReferences2` call.</span></span> <span data-ttu-id="bfaaf-128">Una devolución de llamada [ICorProfilerCallback2:: garbagecollectionfinished (](icorprofilercallback2-garbagecollectionfinished-method.md) indica que todos los objetos se movieron a sus nuevas ubicaciones y se puede realizar la inspección.</span><span class="sxs-lookup"><span data-stu-id="bfaaf-128">A [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) callback indicates that all objects have been moved to their new locations and inspection can be performed.</span></span>  
  
 <span data-ttu-id="bfaaf-129">Si el generador de perfiles implementa las interfaces [ICorProfilerCallback](icorprofilercallback-interface.md) y [ICorProfilerCallback4](icorprofilercallback4-interface.md) , `MovedReferences2` se llama al método antes que al método [ICorProfilerCallback:: MovedReferences](icorprofilercallback-movedreferences-method.md) , pero solo si el `MovedReferences2` método se devuelve correctamente.</span><span class="sxs-lookup"><span data-stu-id="bfaaf-129">If the profiler implements both the [ICorProfilerCallback](icorprofilercallback-interface.md) and the [ICorProfilerCallback4](icorprofilercallback4-interface.md) interfaces, the `MovedReferences2` method is called before the [ICorProfilerCallback::MovedReferences](icorprofilercallback-movedreferences-method.md) method, but only if the `MovedReferences2` method returns successfully.</span></span> <span data-ttu-id="bfaaf-130">Los generadores de perfiles pueden devolver un HRESULT que indica un error del método `MovedReferences2` para evitar llamar al segundo método.</span><span class="sxs-lookup"><span data-stu-id="bfaaf-130">Profilers can return an HRESULT that indicates failure from the `MovedReferences2` method, to avoid calling the second method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfaaf-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bfaaf-131">Requirements</span></span>  

 <span data-ttu-id="bfaaf-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bfaaf-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfaaf-133">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bfaaf-133">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bfaaf-134">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bfaaf-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bfaaf-135">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfaaf-135">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfaaf-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="bfaaf-136">See also</span></span>

- [<span data-ttu-id="bfaaf-137">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bfaaf-137">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="bfaaf-138">Método MovedReferences</span><span class="sxs-lookup"><span data-stu-id="bfaaf-138">MovedReferences Method</span></span>](icorprofilercallback-movedreferences-method.md)
- [<span data-ttu-id="bfaaf-139">ICorProfilerCallback4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bfaaf-139">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
- [<span data-ttu-id="bfaaf-140">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="bfaaf-140">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="bfaaf-141">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="bfaaf-141">Profiling</span></span>](index.md)
