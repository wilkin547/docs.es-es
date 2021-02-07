---
description: 'Más información acerca de: ICorProfilerInfo2:: Getgenerationbounds ((método)'
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
ms.openlocfilehash: 2f6fb9037be2722166653cceb4081a5ddcb81327
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753233"
---
# <a name="icorprofilerinfo2getgenerationbounds-method"></a><span data-ttu-id="7dfd0-103">ICorProfilerInfo2::GetGenerationBounds (Método)</span><span class="sxs-lookup"><span data-stu-id="7dfd0-103">ICorProfilerInfo2::GetGenerationBounds Method</span></span>

<span data-ttu-id="7dfd0-104">Obtiene las regiones de memoria, que son segmentos del montón, que componen las distintas generaciones de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="7dfd0-104">Gets the memory regions, which are segments of the heap, that make up the various garbage collection generations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dfd0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7dfd0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetGenerationBounds(  
    [in]  ULONG cObjectRanges,  
    [out] ULONG *pcObjectRanges,  
    [out, size_is(cObjectRanges), length_is(*pcObjectRanges)] COR_PRF_GC_GENERATION_RANGE ranges[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7dfd0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7dfd0-106">Parameters</span></span>  

 `cObjectRanges`  
 <span data-ttu-id="7dfd0-107">[in] Número de elementos asignado por el llamador para la matriz `ranges`.</span><span class="sxs-lookup"><span data-stu-id="7dfd0-107">[in] The number of elements allocated by the caller for the `ranges` array.</span></span>  
  
 `pcObjectRanges`  
 <span data-ttu-id="7dfd0-108">[out] Puntero a un entero que especifica el número total de intervalos, de los que algunos o todos se devolverán en la matriz `ranges`.</span><span class="sxs-lookup"><span data-stu-id="7dfd0-108">[out] A pointer to an integer that specifies the total number of ranges, some or all of which will be returned in the `ranges` array.</span></span>  
  
 `ranges`  
 <span data-ttu-id="7dfd0-109">enuncia Matriz de estructuras de [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) , cada una de las cuales describe un intervalo (es decir, un bloque) de memoria dentro de la generación que está en proceso de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="7dfd0-109">[out] An array of [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) structures, each of which describes a range (that is, block) of memory within the generation that is undergoing garbage collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7dfd0-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7dfd0-110">Remarks</span></span>  

 <span data-ttu-id="7dfd0-111">Se puede llamar al método `GetGenerationBounds` desde cualquier devolución de llamada del generador de perfiles, siempre que la recolección de elementos no utilizados no esté en curso.</span><span class="sxs-lookup"><span data-stu-id="7dfd0-111">The `GetGenerationBounds` method can be called from any profiler callback, provided that garbage collection is not in progress.</span></span>

 <span data-ttu-id="7dfd0-112">La mayoría de los cambios de generación tienen lugar durante las recolecciones de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="7dfd0-112">Most shifting of generations takes place during garbage collections.</span></span> <span data-ttu-id="7dfd0-113">Las generaciones pueden crecer de una recolección a otra, pero por lo general no se mueven.</span><span class="sxs-lookup"><span data-stu-id="7dfd0-113">Generations might grow between collections but generally do not move around.</span></span> <span data-ttu-id="7dfd0-114">Por este motivo, los lugares más interesantes para llamar a `GetGenerationBounds` están en `ICorProfilerCallback2::GarbageCollectionStarted` y `ICorProfilerCallback2::GarbageCollectionFinished`.</span><span class="sxs-lookup"><span data-stu-id="7dfd0-114">Therefore, the most interesting places to call `GetGenerationBounds` are in `ICorProfilerCallback2::GarbageCollectionStarted` and `ICorProfilerCallback2::GarbageCollectionFinished`.</span></span>  
  
 <span data-ttu-id="7dfd0-115">Durante el inicio del programa, algunos objetos son asignados por el propio Common Language Runtime (CLR), por lo general en las generaciones 3 y 0.</span><span class="sxs-lookup"><span data-stu-id="7dfd0-115">During program startup, some objects are allocated by the common language runtime (CLR) itself, generally in generations 3 and 0.</span></span> <span data-ttu-id="7dfd0-116">Por lo tanto, en el momento en que se inicia la ejecución del código administrado, estas generaciones ya contendrán objetos.</span><span class="sxs-lookup"><span data-stu-id="7dfd0-116">Thus, by the time managed code starts executing, these generations will already contain objects.</span></span> <span data-ttu-id="7dfd0-117">Las generaciones 1 y 2 normalmente estarán vacías, salvo por los objetos ficticios generados por el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="7dfd0-117">Generations 1 and 2 will normally be empty, except for dummy objects that are generated by the garbage collector.</span></span> <span data-ttu-id="7dfd0-118">(El tamaño de los objetos ficticios es de 12 bytes en las implementaciones de 32 bits de CLR; el tamaño es mayor en las implementaciones de 64 bits). También puede ver intervalos de generación 2 que se encuentran dentro de módulos generados por el generador de imágenes nativas (NGen.exe).</span><span class="sxs-lookup"><span data-stu-id="7dfd0-118">(The size of dummy objects is 12 bytes in 32-bit implementations of the CLR; the size is larger in 64-bit implementations.) You might also see generation 2 ranges that are inside modules produced by the Native Image Generator (NGen.exe).</span></span> <span data-ttu-id="7dfd0-119">En este caso, los objetos de la generación 2 son *objetos inmovilizados*, que se asignan cuando NGen.exe se ejecuta en lugar del recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="7dfd0-119">In this case, the objects in generation 2 are *frozen objects*, which are allocated when NGen.exe runs rather than by the garbage collector.</span></span>  
  
 <span data-ttu-id="7dfd0-120">Esta función usa búferes asignados por el llamador.</span><span class="sxs-lookup"><span data-stu-id="7dfd0-120">This function uses caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7dfd0-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7dfd0-121">Requirements</span></span>  

 <span data-ttu-id="7dfd0-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7dfd0-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7dfd0-123">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7dfd0-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7dfd0-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7dfd0-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7dfd0-125">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7dfd0-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dfd0-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="7dfd0-126">See also</span></span>

- [<span data-ttu-id="7dfd0-127">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7dfd0-127">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="7dfd0-128">ICorProfilerInfo2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7dfd0-128">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
- [<span data-ttu-id="7dfd0-129">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="7dfd0-129">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="7dfd0-130">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="7dfd0-130">Profiling</span></span>](index.md)
