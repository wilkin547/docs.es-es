---
description: 'Más información acerca de: ICorProfilerCallback:: MovedReferences (método)'
title: ICorProfilerCallback::MovedReferences (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.MovedReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::MovedReferences
helpviewer_keywords:
- MovedReferences method [.NET Framework profiling]
- ICorProfilerCallback::MovedReferences method [.NET Framework profiling]
ms.assetid: 996c71ae-0676-4616-a085-84ebf507649d
topic_type:
- apiref
ms.openlocfilehash: da77ace52e19540e30488d3304d2822500c90391
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745195"
---
# <a name="icorprofilercallbackmovedreferences-method"></a><span data-ttu-id="1dad2-103">ICorProfilerCallback::MovedReferences (Método)</span><span class="sxs-lookup"><span data-stu-id="1dad2-103">ICorProfilerCallback::MovedReferences Method</span></span>

<span data-ttu-id="1dad2-104">Se le llama para informar de la nueva distribución de los objetos del montón como resultado de una recolección de elementos no utilizados con compactación.</span><span class="sxs-lookup"><span data-stu-id="1dad2-104">Called to report the new layout of objects in the heap as a result of a compacting garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dad2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1dad2-105">Syntax</span></span>  
  
```cpp  
HRESULT MovedReferences(  
    [in]  ULONG  cMovedObjectIDRanges,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID oldObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID newObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ULONG    cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="1dad2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1dad2-106">Parameters</span></span>  

 `cMovedObjectIDRanges`  
 <span data-ttu-id="1dad2-107">[in] Número de bloques de objetos contiguos que se movieron como resultado de la recolección de elementos no utilizados con compactación.</span><span class="sxs-lookup"><span data-stu-id="1dad2-107">[in] The number of blocks of contiguous objects that moved as the result of the compacting garbage collection.</span></span> <span data-ttu-id="1dad2-108">Es decir, el valor de `cMovedObjectIDRanges` es el tamaño total de las matrices `oldObjectIDRangeStart`, `newObjectIDRangeStart` y `cObjectIDRangeLength`.</span><span class="sxs-lookup"><span data-stu-id="1dad2-108">That is, the value of `cMovedObjectIDRanges` is the total size of the `oldObjectIDRangeStart`, `newObjectIDRangeStart`, and `cObjectIDRangeLength` arrays.</span></span>  
  
 <span data-ttu-id="1dad2-109">Los tres argumentos siguientes de `MovedReferences` son matrices paralelas.</span><span class="sxs-lookup"><span data-stu-id="1dad2-109">The next three arguments of `MovedReferences` are parallel arrays.</span></span> <span data-ttu-id="1dad2-110">En otras palabras, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]` y `cObjectIDRangeLength[i]` hacen referencia a un único bloque de objetos contiguos.</span><span class="sxs-lookup"><span data-stu-id="1dad2-110">In other words, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]`, and `cObjectIDRangeLength[i]` all concern a single block of contiguous objects.</span></span>  
  
 `oldObjectIDRangeStart`  
 <span data-ttu-id="1dad2-111">[in] Matriz de valores `ObjectID`, cada uno de los cuales es la dirección inicial antigua (antes de la recolección de elementos no utilizados) de un bloque de objetos contiguos activos en la memoria.</span><span class="sxs-lookup"><span data-stu-id="1dad2-111">[in] An array of `ObjectID` values, each of which is the old (pre-garbage collection) starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `newObjectIDRangeStart`  
 <span data-ttu-id="1dad2-112">[in] Matriz de valores `ObjectID`, cada uno de los cuales es la dirección inicial nueva (después de la recolección de elementos no utilizados) de un bloque de objetos contiguos activos en la memoria.</span><span class="sxs-lookup"><span data-stu-id="1dad2-112">[in] An array of `ObjectID` values, each of which is the new (post-garbage collection) starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `cObjectIDRangeLength`  
 <span data-ttu-id="1dad2-113">[in] Matriz de enteros, cada uno de los cuales es el tamaño de un bloque de objetos contiguos en la memoria.</span><span class="sxs-lookup"><span data-stu-id="1dad2-113">[in] An array of integers, each of which is the size of a block of contiguous objects in memory.</span></span>  
  
 <span data-ttu-id="1dad2-114">Se especifica un tamaño para cada bloque al que se hace referencia en las matrices `oldObjectIDRangeStart` y `newObjectIDRangeStart`.</span><span class="sxs-lookup"><span data-stu-id="1dad2-114">A size is specified for each block that is referenced in the `oldObjectIDRangeStart` and `newObjectIDRangeStart` arrays.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1dad2-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1dad2-115">Remarks</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1dad2-116">Este método notifica tamaños como `MAX_ULONG` para objetos de más de 4 GB en plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="1dad2-116">This method reports sizes as `MAX_ULONG` for objects that are greater than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="1dad2-117">Para obtener el tamaño de objetos mayores de 4 GB, use el método [ICorProfilerCallback4:: movedreferences2 (](icorprofilercallback4-movedreferences2-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="1dad2-117">To get the size of objects that are larger than 4 GB, use the [ICorProfilerCallback4::MovedReferences2](icorprofilercallback4-movedreferences2-method.md) method instead.</span></span>  
  
 <span data-ttu-id="1dad2-118">Un recolector de elementos no utilizados con compactación recupera la memoria ocupada por los objetos inactivos y compacta ese espacio liberado.</span><span class="sxs-lookup"><span data-stu-id="1dad2-118">A compacting garbage collector reclaims the memory occupied by dead objects and compacts that freed space.</span></span> <span data-ttu-id="1dad2-119">Como resultado, los objetos activos podrían moverse dentro del montón y los valores de `ObjectID` distribuidos por notificaciones anteriores podrían cambiar.</span><span class="sxs-lookup"><span data-stu-id="1dad2-119">As a result, live objects might be moved within the heap, and `ObjectID` values distributed by previous notifications might change.</span></span>  
  
 <span data-ttu-id="1dad2-120">Supongamos que un valor `ObjectID` existente (`oldObjectID`) se encuentra dentro del intervalo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1dad2-120">Assume that an existing `ObjectID` value (`oldObjectID`) lies within the following range:</span></span>  
  
 `oldObjectIDRangeStart[i]` <= `oldObjectID` < `oldObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 <span data-ttu-id="1dad2-121">En este caso, el desplazamiento desde el inicio del intervalo al inicio del objeto es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="1dad2-121">In this case, the offset from the start of the range to the start of the object is as follows:</span></span>  
  
 `oldObjectID` - `oldObjectRangeStart[i]`  
  
 <span data-ttu-id="1dad2-122">Para cualquier valor de `i` que esté en el intervalo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1dad2-122">For any value of `i` that is in the following range:</span></span>  
  
 <span data-ttu-id="1dad2-123">0 <= `i` < `cMovedObjectIDRanges`</span><span class="sxs-lookup"><span data-stu-id="1dad2-123">0 <= `i` < `cMovedObjectIDRanges`</span></span>  
  
 <span data-ttu-id="1dad2-124">puede calcular el nuevo `ObjectID` de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="1dad2-124">you can calculate the new `ObjectID` as follows:</span></span>  
  
 <span data-ttu-id="1dad2-125">`newObjectID` = `newObjectIDRangeStart[i]` + ( `oldObjectID` – `oldObjectIDRangeStart[i]` )</span><span class="sxs-lookup"><span data-stu-id="1dad2-125">`newObjectID` = `newObjectIDRangeStart[i]` + (`oldObjectID` – `oldObjectIDRangeStart[i]`)</span></span>  
  
 <span data-ttu-id="1dad2-126">Ninguno de los valores `ObjectID` pasados por `MovedReferences` son válidos durante la devolución de llamada en sí porque el recolector de elementos no utilizados puede estar en proceso de mover objetos de ubicaciones anteriores a nuevas.</span><span class="sxs-lookup"><span data-stu-id="1dad2-126">None of the `ObjectID` values passed by `MovedReferences` are valid during the callback itself, because the garbage collection might be in the middle of moving objects from old locations to new locations.</span></span> <span data-ttu-id="1dad2-127">Por lo tanto, los generadores de perfiles no deben intentar inspeccionar objetos durante una llamada a `MovedReferences`.</span><span class="sxs-lookup"><span data-stu-id="1dad2-127">Therefore, profilers should not attempt to inspect objects during a `MovedReferences` call.</span></span> <span data-ttu-id="1dad2-128">Una devolución de llamada [ICorProfilerCallback2:: garbagecollectionfinished (](icorprofilercallback2-garbagecollectionfinished-method.md) indica que todos los objetos se movieron a sus nuevas ubicaciones y se puede realizar la inspección.</span><span class="sxs-lookup"><span data-stu-id="1dad2-128">A [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) callback indicates that all objects have been moved to their new locations and inspection can be performed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1dad2-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1dad2-129">Requirements</span></span>  

 <span data-ttu-id="1dad2-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1dad2-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1dad2-131">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1dad2-131">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1dad2-132">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1dad2-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1dad2-133">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1dad2-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dad2-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="1dad2-134">See also</span></span>

- [<span data-ttu-id="1dad2-135">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1dad2-135">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="1dad2-136">Método MovedReferences2</span><span class="sxs-lookup"><span data-stu-id="1dad2-136">MovedReferences2 Method</span></span>](icorprofilercallback4-movedreferences2-method.md)
- [<span data-ttu-id="1dad2-137">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="1dad2-137">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="1dad2-138">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="1dad2-138">Profiling</span></span>](index.md)
