---
title: ICorProfilerCallback2::SurvivingReferences (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.SurvivingReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::SurvivingReferences
helpviewer_keywords:
- ICorProfilerCallback2::SurvivingReferences method [.NET Framework profiling]
- SurvivingReferences method [.NET Framework profiling]
ms.assetid: f165200e-3a91-47f7-88fc-13ff10c8babc
topic_type:
- apiref
ms.openlocfilehash: 3681106bca94f1fefb2f24a1aa4254eb2b1b0531
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499745"
---
# <a name="icorprofilercallback2survivingreferences-method"></a><span data-ttu-id="37258-102">ICorProfilerCallback2::SurvivingReferences (Método)</span><span class="sxs-lookup"><span data-stu-id="37258-102">ICorProfilerCallback2::SurvivingReferences Method</span></span>
<span data-ttu-id="37258-103">Informa del diseño de objetos del montón como resultado de una recolección de elementos no utilizados sin compactación.</span><span class="sxs-lookup"><span data-stu-id="37258-103">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37258-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37258-104">Syntax</span></span>  
  
```cpp  
HRESULT SurvivingReferences(  
    [in] ULONG  cSurvivingObjectIDRanges,  
    [in, size_is(cSurvivingObjectIDRanges)] ObjectID  
                objectIDRangeStart[] ,  
    [in, size_is(cSurvivingObjectIDRanges)] ULONG  
                cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="37258-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="37258-105">Parameters</span></span>  
 `cSurvivingObjectIDRanges`  
 <span data-ttu-id="37258-106">[in] Número de bloques de objetos contiguos que sobrevivieron como resultado de la recolección de elementos no utilizados sin compactación.</span><span class="sxs-lookup"><span data-stu-id="37258-106">[in] The number of blocks of contiguous objects that survived as the result of the non-compacting garbage collection.</span></span> <span data-ttu-id="37258-107">Es decir, el valor de `cSurvivingObjectIDRanges` es el tamaño de las matrices `objectIDRangeStart` y `cObjectIDRangeLength`, que almacenan un `ObjectID` y una longitud, respectivamente, para cada bloque de objetos.</span><span class="sxs-lookup"><span data-stu-id="37258-107">That is, the value of `cSurvivingObjectIDRanges` is the size of the `objectIDRangeStart` and `cObjectIDRangeLength` arrays, which store an `ObjectID` and a length, respectively, for each block of objects.</span></span>  
  
 <span data-ttu-id="37258-108">Los dos argumentos siguientes de `SurvivingReferences` son matrices paralelas.</span><span class="sxs-lookup"><span data-stu-id="37258-108">The next two arguments of `SurvivingReferences` are parallel arrays.</span></span> <span data-ttu-id="37258-109">En otras palabras, `objectIDRangeStart` y `cObjectIDRangeLength` hacen referencia al mismo bloque de objetos contiguos.</span><span class="sxs-lookup"><span data-stu-id="37258-109">In other words, `objectIDRangeStart` and `cObjectIDRangeLength` concern the same block of contiguous objects.</span></span>  
  
 `objectIDRangeStart`  
 <span data-ttu-id="37258-110">[in] Matriz de valores `ObjectID`, cada uno de los cuales es la dirección inicial de un bloque de objetos activos y contiguos en la memoria.</span><span class="sxs-lookup"><span data-stu-id="37258-110">[in] An array of `ObjectID` values, each of which is the starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `cObjectIDRangeLength`  
 <span data-ttu-id="37258-111">[in] Matriz de enteros, cada uno de los cuales es el tamaño de un bloque superviviente de objetos contiguos en la memoria.</span><span class="sxs-lookup"><span data-stu-id="37258-111">[in] An array of integers, each of which is the size of a surviving block of contiguous objects in memory.</span></span>  
  
 <span data-ttu-id="37258-112">Se especifica un tamaño para cada bloque al que se hace referencia en la matriz `objectIDRangeStart`.</span><span class="sxs-lookup"><span data-stu-id="37258-112">A size is specified for each block that is referenced in the `objectIDRangeStart` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37258-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="37258-113">Remarks</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="37258-114">Este método notifica tamaños como `MAX_ULONG` para objetos de más de 4 GB en plataformas de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="37258-114">This method reports sizes as `MAX_ULONG` for objects that are greater than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="37258-115">En el caso de objetos mayores de 4 GB, use el método [ICorProfilerCallback4:: survivingreferences2 (](icorprofilercallback4-survivingreferences2-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="37258-115">For objects that are larger than 4 GB, use the [ICorProfilerCallback4::SurvivingReferences2](icorprofilercallback4-survivingreferences2-method.md) method instead.</span></span>  
  
 <span data-ttu-id="37258-116">Los elementos de las matrices `objectIDRangeStart` y `cObjectIDRangeLength` deben interpretarse del siguiente modo para determinar si un objeto ha sobrevivido a la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="37258-116">The elements of the `objectIDRangeStart` and `cObjectIDRangeLength` arrays should be interpreted as follows to determine whether an object survived the garbage collection.</span></span> <span data-ttu-id="37258-117">Supongamos que un valor `ObjectID` (`ObjectID`) se encuentra dentro del intervalo siguiente:</span><span class="sxs-lookup"><span data-stu-id="37258-117">Assume that an `ObjectID` value (`ObjectID`) lies within the following range:</span></span>  
  
 `ObjectIDRangeStart[i]` <= `ObjectID` < `ObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 <span data-ttu-id="37258-118">Para cualquier valor `i` que esté en el intervalo siguiente, el objeto sobrevivió a la recolección de elementos no utilizados:</span><span class="sxs-lookup"><span data-stu-id="37258-118">For any value of `i` that is in the following range, the object has survived the garbage collection:</span></span>  
  
 <span data-ttu-id="37258-119">0 <=`i` < `cSurvivingObjectIDRanges`</span><span class="sxs-lookup"><span data-stu-id="37258-119">0 <= `i` < `cSurvivingObjectIDRanges`</span></span>  
  
 <span data-ttu-id="37258-120">Una recolección de elementos no utilizados sin compactación recupera la memoria ocupada por objetos "inactivos", pero no compacta ese espacio liberado.</span><span class="sxs-lookup"><span data-stu-id="37258-120">A non-compacting garbage collection reclaims the memory occupied by "dead" objects, but does not compact that freed space.</span></span> <span data-ttu-id="37258-121">Como consecuencia, la memoria se devuelve al montón pero no se mueve ningún objeto "activo".</span><span class="sxs-lookup"><span data-stu-id="37258-121">As a result, memory is returned to the heap, but no "live" objects are moved.</span></span>  
  
 <span data-ttu-id="37258-122">Common Language Runtime (CLR) llama a `SurvivingReferences` para las recolecciones de elementos no utilizados sin compactación.</span><span class="sxs-lookup"><span data-stu-id="37258-122">The common language runtime (CLR) calls `SurvivingReferences` for non-compacting garbage collections.</span></span> <span data-ttu-id="37258-123">Para compactar las recolecciones de elementos no utilizados, se llama a [ICorProfilerCallback:: MovedReferences](icorprofilercallback-movedreferences-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="37258-123">For compacting garbage collections, [ICorProfilerCallback::MovedReferences](icorprofilercallback-movedreferences-method.md) is called instead.</span></span> <span data-ttu-id="37258-124">Se puede compactar una única recolección de elementos no utilizados para una generación y no compactar para otra.</span><span class="sxs-lookup"><span data-stu-id="37258-124">A single garbage collection can be compacting for one generation and non-compacting for another.</span></span> <span data-ttu-id="37258-125">Para una recolección de elementos no utilizados en una generación determinada, el generador de perfiles recibirá una devolución de llamada `SurvivingReferences` o una devolución de llamada `MovedReferences`, pero no ambas.</span><span class="sxs-lookup"><span data-stu-id="37258-125">For a garbage collection on any particular generation, the profiler will receive either a `SurvivingReferences` callback or a `MovedReferences` callback, but not both.</span></span>  
  
 <span data-ttu-id="37258-126">Se pueden recibir varias devoluciones de llamada `SurvivingReferences` durante una recolección de elementos no utilizados determinada debido a un almacenamiento en búfer interno limitado, a la notificación de varios subprocesos en el caso de la recolección de elementos no utilizados de servidor, y a otros motivos.</span><span class="sxs-lookup"><span data-stu-id="37258-126">Multiple `SurvivingReferences` callbacks might be received during a particular garbage collection, due to limited internal buffering, multiple threads reporting in the case of server garbage collection, and other reasons.</span></span> <span data-ttu-id="37258-127">En el caso de varias devoluciones de llamada durante una recolección de elementos no utilizados, la información es acumulativa. Todas las referencias que se notifican en cualquier devolución de llamada `SurvivingReferences` sobreviven a la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="37258-127">In the case of multiple callbacks during a garbage collection, the information is cumulative — all references that are reported in any `SurvivingReferences` callback survive the garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37258-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="37258-128">Requirements</span></span>  
 <span data-ttu-id="37258-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37258-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37258-130">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="37258-130">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="37258-131">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37258-131">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37258-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37258-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37258-133">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="37258-133">See also</span></span>

- [<span data-ttu-id="37258-134">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="37258-134">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="37258-135">ICorProfilerCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="37258-135">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
- [<span data-ttu-id="37258-136">Método SurvivingReferences2</span><span class="sxs-lookup"><span data-stu-id="37258-136">SurvivingReferences2 Method</span></span>](icorprofilercallback4-survivingreferences2-method.md)
