---
title: ICorProfilerCallback4 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4
helpviewer_keywords:
- ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 665f3cfc-cd6f-4880-906c-ea65ad384783
topic_type:
- apiref
ms.openlocfilehash: 942ee8234b79c6579acc009960f4571801fc3185
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730297"
---
# <a name="icorprofilercallback4-interface"></a><span data-ttu-id="62f15-102">ICorProfilerCallback4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="62f15-102">ICorProfilerCallback4 Interface</span></span>

<span data-ttu-id="62f15-103">Proporciona métodos de devolución de llamada que el Common Language Runtime (CLR) utiliza para comunicar información al generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="62f15-103">Provides callback methods that the common language runtime (CLR) uses to communicate information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="62f15-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="62f15-104">Methods</span></span>  
  
|<span data-ttu-id="62f15-105">Método</span><span class="sxs-lookup"><span data-stu-id="62f15-105">Method</span></span>|<span data-ttu-id="62f15-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="62f15-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="62f15-107">Método GetReJITParameters</span><span class="sxs-lookup"><span data-stu-id="62f15-107">GetReJITParameters Method</span></span>](icorprofilercallback4-getrejitparameters-method.md)|<span data-ttu-id="62f15-108">Permite que el generador de perfiles de código establezca marcas de generación de código alternativas para un nuevo cuerpo de método recompilado.</span><span class="sxs-lookup"><span data-stu-id="62f15-108">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>|  
|[<span data-ttu-id="62f15-109">Método MovedReferences2</span><span class="sxs-lookup"><span data-stu-id="62f15-109">MovedReferences2 Method</span></span>](icorprofilercallback4-movedreferences2-method.md)|<span data-ttu-id="62f15-110">Informa del nuevo diseño de objetos del montón como resultado de una recolección de elementos no utilizados de compactación.</span><span class="sxs-lookup"><span data-stu-id="62f15-110">Reports the new layout of objects in the heap as a result of a compacting garbage collection.</span></span>|  
|[<span data-ttu-id="62f15-111">Método ReJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="62f15-111">ReJITCompilationFinished Method</span></span>](icorprofilercallback4-rejitcompilationfinished-method.md)|<span data-ttu-id="62f15-112">Notifica al generador de perfiles que el compilador Just-in-Time (JIT) ha terminado de volver a compilar una función.</span><span class="sxs-lookup"><span data-stu-id="62f15-112">Notifies the profiler that the just-in-time (JIT) compiler has finished the recompilation of a function.</span></span>|  
|[<span data-ttu-id="62f15-113">Método ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="62f15-113">ReJITCompilationStarted Method</span></span>](icorprofilercallback4-rejitcompilationstarted-method.md)|<span data-ttu-id="62f15-114">Notifica al generador de perfiles que el compilador Just-in-Time (JIT) ha empezado a volver a compilar una función.</span><span class="sxs-lookup"><span data-stu-id="62f15-114">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>|  
|[<span data-ttu-id="62f15-115">Método ReJITError</span><span class="sxs-lookup"><span data-stu-id="62f15-115">ReJITError Method</span></span>](icorprofilercallback4-rejiterror-method.md)|<span data-ttu-id="62f15-116">Informa de un error detectado durante el procesamiento de una solicitud de recompilación.</span><span class="sxs-lookup"><span data-stu-id="62f15-116">Reports an error encountered while processing a recompile request.</span></span>|  
|[<span data-ttu-id="62f15-117">Método SurvivingReferences2</span><span class="sxs-lookup"><span data-stu-id="62f15-117">SurvivingReferences2 Method</span></span>](icorprofilercallback4-survivingreferences2-method.md)|<span data-ttu-id="62f15-118">Informa del diseño de objetos del montón como resultado de una recolección de elementos no utilizados sin compactación.</span><span class="sxs-lookup"><span data-stu-id="62f15-118">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62f15-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="62f15-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62f15-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="62f15-120">Requirements</span></span>  

 <span data-ttu-id="62f15-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62f15-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62f15-122">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="62f15-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="62f15-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62f15-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62f15-124">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62f15-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62f15-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="62f15-125">See also</span></span>

- [<span data-ttu-id="62f15-126">ICorProfilerCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="62f15-126">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
- [<span data-ttu-id="62f15-127">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="62f15-127">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="62f15-128">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="62f15-128">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
