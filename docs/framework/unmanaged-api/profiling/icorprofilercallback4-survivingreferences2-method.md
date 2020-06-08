---
title: ICorProfilerCallback4::SurvivingReferences2 (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.SurvivingReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::SurvivingReferences2
helpviewer_keywords:
- ICorProfilerCallback4::SurvivingReferences2 method [.NET Framework profiling]
- SurvivingReferences2 method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 02b51888-5d89-4e50-a915-45b7e329aad9
topic_type:
- apiref
ms.openlocfilehash: 208ce1d7ef8a1eab4f18a6d488f0cc480b5713d8
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499342"
---
# <a name="icorprofilercallback4survivingreferences2-method"></a><span data-ttu-id="6d3a1-102">ICorProfilerCallback4::SurvivingReferences2 (Método)</span><span class="sxs-lookup"><span data-stu-id="6d3a1-102">ICorProfilerCallback4::SurvivingReferences2 Method</span></span>
<span data-ttu-id="6d3a1-103">Informa del diseño de objetos del montón como resultado de una recolección de elementos no utilizados sin compactación.</span><span class="sxs-lookup"><span data-stu-id="6d3a1-103">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span> <span data-ttu-id="6d3a1-104">Se llama a este método si el generador de perfiles ha implementado la interfaz [ICorProfilerCallback4](icorprofilercallback4-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="6d3a1-104">This method is called if the profiler has implemented the [ICorProfilerCallback4](icorprofilercallback4-interface.md) interface.</span></span> <span data-ttu-id="6d3a1-105">Esta devolución de llamada reemplaza el método [ICorProfilerCallback2:: SurvivingReferences (](icorprofilercallback2-survivingreferences-method.md) , ya que puede informar de intervalos de objetos mayores cuyas longitudes superen lo que se puede expresar en un ulong.</span><span class="sxs-lookup"><span data-stu-id="6d3a1-105">This callback replaces the [ICorProfilerCallback2::SurvivingReferences](icorprofilercallback2-survivingreferences-method.md) method, because it can report larger ranges of objects whose lengths exceed what can be expressed in a ULONG.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d3a1-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d3a1-106">Syntax</span></span>  
  
```cpp  
HRESULT SurvivingReferences2(  
    [in] ULONG  cSurvivingObjectIDRanges,  
    [in, size_is(cSurvivingObjectIDRanges)] ObjectID  
                objectIDRangeStart[] ,  
    [in, size_is(cSurvivingObjectIDRanges)] SIZE_T  
                cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d3a1-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6d3a1-107">Parameters</span></span>  
 `cSurvivingObjectIDRanges`  
 <span data-ttu-id="6d3a1-108">[in] Número de bloques de objetos contiguos que sobrevivieron como resultado de la recolección de elementos no utilizados sin compactación.</span><span class="sxs-lookup"><span data-stu-id="6d3a1-108">[in] The number of blocks of contiguous objects that survived as the result of the non-compacting garbage collection.</span></span> <span data-ttu-id="6d3a1-109">Es decir, el valor de `cSurvivingObjectIDRanges` es el tamaño de las matrices `objectIDRangeStart` y `cObjectIDRangeLength`, que almacenan un `ObjectID` y una longitud, respectivamente, para cada bloque de objetos.</span><span class="sxs-lookup"><span data-stu-id="6d3a1-109">That is, the value of `cSurvivingObjectIDRanges` is the size of the `objectIDRangeStart` and `cObjectIDRangeLength` arrays, which store an `ObjectID` and a length, respectively, for each block of objects.</span></span>  
  
 <span data-ttu-id="6d3a1-110">Los dos argumentos siguientes de `SurvivingReferences2` son matrices paralelas.</span><span class="sxs-lookup"><span data-stu-id="6d3a1-110">The next two arguments of `SurvivingReferences2` are parallel arrays.</span></span> <span data-ttu-id="6d3a1-111">En otras palabras, `objectIDRangeStart` y `cObjectIDRangeLength` hacen referencia al mismo bloque de objetos contiguos.</span><span class="sxs-lookup"><span data-stu-id="6d3a1-111">In other words, `objectIDRangeStart` and `cObjectIDRangeLength` concern the same block of contiguous objects.</span></span>  
  
 `objectIDRangeStart`  
 <span data-ttu-id="6d3a1-112">[in] Matriz de valores `ObjectID`, cada uno de los cuales es la dirección inicial de un bloque de objetos activos y contiguos en la memoria.</span><span class="sxs-lookup"><span data-stu-id="6d3a1-112">[in] An array of `ObjectID` values, each of which is the starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `cObjectIDRangeLength`  
 <span data-ttu-id="6d3a1-113">[in] Matriz de enteros, cada uno de los cuales es el tamaño de un bloque superviviente de objetos contiguos en la memoria.</span><span class="sxs-lookup"><span data-stu-id="6d3a1-113">[in] An array of integers, each of which is the size of a surviving block of contiguous objects in memory.</span></span>  
  
 <span data-ttu-id="6d3a1-114">Se especifica un tamaño para cada bloque al que se hace referencia en la matriz `objectIDRangeStart`.</span><span class="sxs-lookup"><span data-stu-id="6d3a1-114">A size is specified for each block that is referenced in the `objectIDRangeStart` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d3a1-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6d3a1-115">Remarks</span></span>  
 <span data-ttu-id="6d3a1-116">Los elementos de las matrices `objectIDRangeStart` y `cObjectIDRangeLength` deben interpretarse del siguiente modo para determinar si un objeto ha sobrevivido a la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="6d3a1-116">The elements of the `objectIDRangeStart` and `cObjectIDRangeLength` arrays should be interpreted as follows to determine whether an object survived the garbage collection.</span></span> <span data-ttu-id="6d3a1-117">Supongamos que un valor `ObjectID` (`ObjectID`) se encuentra dentro del intervalo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6d3a1-117">Assume that an `ObjectID` value (`ObjectID`) lies within the following range:</span></span>  
  
 `ObjectIDRangeStart[i]` <= `ObjectID` < `ObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 <span data-ttu-id="6d3a1-118">Para cualquier valor `i` que esté en el intervalo siguiente, el objeto sobrevivió a la recolección de elementos no utilizados:</span><span class="sxs-lookup"><span data-stu-id="6d3a1-118">For any value of `i` that is in the following range, the object has survived the garbage collection:</span></span>  
  
 <span data-ttu-id="6d3a1-119">0 <=`i` < `cSurvivingObjectIDRanges`</span><span class="sxs-lookup"><span data-stu-id="6d3a1-119">0 <= `i` < `cSurvivingObjectIDRanges`</span></span>  
  
 <span data-ttu-id="6d3a1-120">Una recolección de elementos no utilizados sin compactación recupera la memoria ocupada por objetos "inactivos", pero no compacta ese espacio liberado.</span><span class="sxs-lookup"><span data-stu-id="6d3a1-120">A non-compacting garbage collection reclaims the memory occupied by "dead" objects, but does not compact that freed space.</span></span> <span data-ttu-id="6d3a1-121">Como consecuencia, la memoria se devuelve al montón pero no se mueve ningún objeto "activo".</span><span class="sxs-lookup"><span data-stu-id="6d3a1-121">As a result, memory is returned to the heap, but no "live" objects are moved.</span></span>  
  
 <span data-ttu-id="6d3a1-122">Common Language Runtime (CLR) llama a `SurvivingReferences2` para las recolecciones de elementos no utilizados sin compactación.</span><span class="sxs-lookup"><span data-stu-id="6d3a1-122">The common language runtime (CLR) calls `SurvivingReferences2` for non-compacting garbage collections.</span></span> <span data-ttu-id="6d3a1-123">Para compactar las recolecciones de elementos no utilizados, se llama a [movedreferences2 (](icorprofilercallback4-movedreferences2-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="6d3a1-123">For compacting garbage collections, [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) is called instead.</span></span> <span data-ttu-id="6d3a1-124">Se puede compactar una única recolección de elementos no utilizados para una generación y no compactar para otra.</span><span class="sxs-lookup"><span data-stu-id="6d3a1-124">A single garbage collection can be compacting for one generation and non-compacting for another.</span></span> <span data-ttu-id="6d3a1-125">En el caso de una recolección de elementos no utilizados en una generación determinada, el generador de perfiles recibirá una devolución de llamada `SurvivingReferences2` o una devolución de llamada [movedreferences2 (](icorprofilercallback4-movedreferences2-method.md) , pero no ambos.</span><span class="sxs-lookup"><span data-stu-id="6d3a1-125">For a garbage collection on any particular generation, the profiler will receive either a `SurvivingReferences2` callback or a [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) callback, but not both.</span></span>  
  
 <span data-ttu-id="6d3a1-126">Se podrían recibir varias devoluciones de llamada `SurvivingReferences2` durante una recolección de elementos no utilizados determinada, a causa de un almacenamiento de búfer interno limitado, de varias devoluciones de llamada durante la recolección de elementos no utilizados del servidor o por otras razones.</span><span class="sxs-lookup"><span data-stu-id="6d3a1-126">Multiple `SurvivingReferences2` callbacks might be received during a particular garbage collection, because of limited internal buffering, multiple callbacks during server garbage collection, and other reasons.</span></span> <span data-ttu-id="6d3a1-127">En el caso de varias devoluciones de llamada durante una recolección de elementos no utilizados, la información es acumulativa. Todas las referencias que se notifican en cualquier devolución de llamada `SurvivingReferences2` sobreviven a la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="6d3a1-127">In the case of multiple callbacks during a garbage collection, the information is cumulative; all references that are reported in any `SurvivingReferences2` callback survive the garbage collection.</span></span>  
  
 <span data-ttu-id="6d3a1-128">Si el generador de perfiles implementa las interfaces [ICorProfilerCallback](icorprofilercallback-interface.md) y [ICorProfilerCallback4](icorprofilercallback4-interface.md) , `SurvivingReferences2` se llama al método antes que al método [ICorProfilerCallback2:: SurvivingReferences (](icorprofilercallback2-survivingreferences-method.md) , pero solo si se `SurvivingReferences2` devuelve correctamente.</span><span class="sxs-lookup"><span data-stu-id="6d3a1-128">If the profiler implements both the [ICorProfilerCallback](icorprofilercallback-interface.md) and the [ICorProfilerCallback4](icorprofilercallback4-interface.md) interfaces, the `SurvivingReferences2` method is called before the [ICorProfilerCallback2::SurvivingReferences](icorprofilercallback2-survivingreferences-method.md) method, but only if `SurvivingReferences2` returns successfully.</span></span> <span data-ttu-id="6d3a1-129">Los generadores de perfiles pueden devolver un valor HRESULT que indique un error del método `SurvivingReferences2` para evitar llamar al segundo método.</span><span class="sxs-lookup"><span data-stu-id="6d3a1-129">Profilers can return an HRESULT that indicates failure from the `SurvivingReferences2` method to avoid calling the second method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d3a1-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6d3a1-130">Requirements</span></span>  
 <span data-ttu-id="6d3a1-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d3a1-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d3a1-132">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6d3a1-132">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6d3a1-133">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d3a1-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d3a1-134">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d3a1-134">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d3a1-135">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="6d3a1-135">See also</span></span>

- [<span data-ttu-id="6d3a1-136">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6d3a1-136">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="6d3a1-137">ICorProfilerCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6d3a1-137">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
- [<span data-ttu-id="6d3a1-138">ICorProfilerCallback4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6d3a1-138">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
