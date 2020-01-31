---
title: ICorProfilerInfo2::GetGenerationBounds (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: 3cdc185408576f5679daacef4dde438d66e490ff
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862755"
---
# <a name="icorprofilerinfo2getgenerationbounds-method"></a><span data-ttu-id="006cd-102">ICorProfilerInfo2::GetGenerationBounds (Método)</span><span class="sxs-lookup"><span data-stu-id="006cd-102">ICorProfilerInfo2::GetGenerationBounds Method</span></span>
<span data-ttu-id="006cd-103">Obtiene las regiones de memoria, que son segmentos del montón, que componen las distintas generaciones de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="006cd-103">Gets the memory regions, which are segments of the heap, that make up the various garbage collection generations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="006cd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="006cd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGenerationBounds(  
    [in]  ULONG cObjectRanges,  
    [out] ULONG *pcObjectRanges,  
    [out, size_is(cObjectRanges), length_is(*pcObjectRanges)] COR_PRF_GC_GENERATION_RANGE ranges[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="006cd-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="006cd-105">Parameters</span></span>  
 `cObjectRanges`  
 <span data-ttu-id="006cd-106">[in] Número de elementos asignado por el llamador para la matriz `ranges`.</span><span class="sxs-lookup"><span data-stu-id="006cd-106">[in] The number of elements allocated by the caller for the `ranges` array.</span></span>  
  
 `pcObjectRanges`  
 <span data-ttu-id="006cd-107">[out] Puntero a un entero que especifica el número total de intervalos, de los que algunos o todos se devolverán en la matriz `ranges`.</span><span class="sxs-lookup"><span data-stu-id="006cd-107">[out] A pointer to an integer that specifies the total number of ranges, some or all of which will be returned in the `ranges` array.</span></span>  
  
 `ranges`  
 <span data-ttu-id="006cd-108">enuncia Matriz de estructuras de [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) , cada una de las cuales describe un intervalo (es decir, un bloque) de memoria dentro de la generación que está en proceso de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="006cd-108">[out] An array of [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) structures, each of which describes a range (that is, block) of memory within the generation that is undergoing garbage collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="006cd-109">Notas</span><span class="sxs-lookup"><span data-stu-id="006cd-109">Remarks</span></span>  
 <span data-ttu-id="006cd-110">Se puede llamar al método `GetGenerationBounds` desde cualquier devolución de llamada del generador de perfiles, siempre que la recolección de elementos no utilizados no esté en curso.</span><span class="sxs-lookup"><span data-stu-id="006cd-110">The `GetGenerationBounds` method can be called from any profiler callback, provided that garbage collection is not in progress.</span></span>

 <span data-ttu-id="006cd-111">La mayoría de los cambios de generación tienen lugar durante las recolecciones de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="006cd-111">Most shifting of generations takes place during garbage collections.</span></span> <span data-ttu-id="006cd-112">Las generaciones pueden crecer de una recolección a otra, pero por lo general no se mueven.</span><span class="sxs-lookup"><span data-stu-id="006cd-112">Generations might grow between collections but generally do not move around.</span></span> <span data-ttu-id="006cd-113">Por este motivo, los lugares más interesantes para llamar a `GetGenerationBounds` están en `ICorProfilerCallback2::GarbageCollectionStarted` y `ICorProfilerCallback2::GarbageCollectionFinished`.</span><span class="sxs-lookup"><span data-stu-id="006cd-113">Therefore, the most interesting places to call `GetGenerationBounds` are in `ICorProfilerCallback2::GarbageCollectionStarted` and `ICorProfilerCallback2::GarbageCollectionFinished`.</span></span>  
  
 <span data-ttu-id="006cd-114">Durante el inicio del programa, algunos objetos son asignados por el propio Common Language Runtime (CLR), por lo general en las generaciones 3 y 0.</span><span class="sxs-lookup"><span data-stu-id="006cd-114">During program startup, some objects are allocated by the common language runtime (CLR) itself, generally in generations 3 and 0.</span></span> <span data-ttu-id="006cd-115">Por lo tanto, en el momento en que se inicia la ejecución del código administrado, estas generaciones ya contendrán objetos.</span><span class="sxs-lookup"><span data-stu-id="006cd-115">Thus, by the time managed code starts executing, these generations will already contain objects.</span></span> <span data-ttu-id="006cd-116">Las generaciones 1 y 2 normalmente estarán vacías, salvo por los objetos ficticios generados por el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="006cd-116">Generations 1 and 2 will normally be empty, except for dummy objects that are generated by the garbage collector.</span></span> <span data-ttu-id="006cd-117">(El tamaño de los objetos ficticios es de 12 bytes en las implementaciones de 32 bits de CLR; el tamaño es mayor en las implementaciones de 64 bits). También puede ver intervalos de generación 2 que se encuentran dentro de módulos generados por el generador de imágenes nativas (NGen. exe).</span><span class="sxs-lookup"><span data-stu-id="006cd-117">(The size of dummy objects is 12 bytes in 32-bit implementations of the CLR; the size is larger in 64-bit implementations.) You might also see generation 2 ranges that are inside modules produced by the Native Image Generator (NGen.exe).</span></span> <span data-ttu-id="006cd-118">En este caso, los objetos de la generación 2 son *objetos inmovilizados*, que se asignan cuando se ejecuta Ngen. exe en lugar del recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="006cd-118">In this case, the objects in generation 2 are *frozen objects*, which are allocated when NGen.exe runs rather than by the garbage collector.</span></span>  
  
 <span data-ttu-id="006cd-119">Esta función usa búferes asignados por el llamador.</span><span class="sxs-lookup"><span data-stu-id="006cd-119">This function uses caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="006cd-120">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="006cd-120">Requirements</span></span>  
 <span data-ttu-id="006cd-121">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="006cd-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="006cd-122">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="006cd-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="006cd-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="006cd-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="006cd-124">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="006cd-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="006cd-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="006cd-125">See also</span></span>

- [<span data-ttu-id="006cd-126">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="006cd-126">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="006cd-127">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="006cd-127">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
- [<span data-ttu-id="006cd-128">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="006cd-128">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="006cd-129">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="006cd-129">Profiling</span></span>](index.md)
