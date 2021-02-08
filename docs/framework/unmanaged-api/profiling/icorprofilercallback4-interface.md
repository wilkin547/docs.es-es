---
description: 'Más información acerca de: interfaz ICorProfilerCallback4'
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
ms.openlocfilehash: 882f234cb94ccd65203b42ed213aab6355250af8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788753"
---
# <a name="icorprofilercallback4-interface"></a><span data-ttu-id="f1ffa-103">ICorProfilerCallback4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f1ffa-103">ICorProfilerCallback4 Interface</span></span>

<span data-ttu-id="f1ffa-104">Proporciona métodos de devolución de llamada que el Common Language Runtime (CLR) utiliza para comunicar información al generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="f1ffa-104">Provides callback methods that the common language runtime (CLR) uses to communicate information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f1ffa-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="f1ffa-105">Methods</span></span>  
  
|<span data-ttu-id="f1ffa-106">Método</span><span class="sxs-lookup"><span data-stu-id="f1ffa-106">Method</span></span>|<span data-ttu-id="f1ffa-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f1ffa-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f1ffa-108">Método GetReJITParameters</span><span class="sxs-lookup"><span data-stu-id="f1ffa-108">GetReJITParameters Method</span></span>](icorprofilercallback4-getrejitparameters-method.md)|<span data-ttu-id="f1ffa-109">Permite que el generador de perfiles de código establezca marcas de generación de código alternativas para un nuevo cuerpo de método recompilado.</span><span class="sxs-lookup"><span data-stu-id="f1ffa-109">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>|  
|[<span data-ttu-id="f1ffa-110">Método MovedReferences2</span><span class="sxs-lookup"><span data-stu-id="f1ffa-110">MovedReferences2 Method</span></span>](icorprofilercallback4-movedreferences2-method.md)|<span data-ttu-id="f1ffa-111">Informa del nuevo diseño de objetos del montón como resultado de una recolección de elementos no utilizados de compactación.</span><span class="sxs-lookup"><span data-stu-id="f1ffa-111">Reports the new layout of objects in the heap as a result of a compacting garbage collection.</span></span>|  
|[<span data-ttu-id="f1ffa-112">Método ReJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="f1ffa-112">ReJITCompilationFinished Method</span></span>](icorprofilercallback4-rejitcompilationfinished-method.md)|<span data-ttu-id="f1ffa-113">Notifica al generador de perfiles que el compilador Just-in-Time (JIT) ha terminado de volver a compilar una función.</span><span class="sxs-lookup"><span data-stu-id="f1ffa-113">Notifies the profiler that the just-in-time (JIT) compiler has finished the recompilation of a function.</span></span>|  
|[<span data-ttu-id="f1ffa-114">Método ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="f1ffa-114">ReJITCompilationStarted Method</span></span>](icorprofilercallback4-rejitcompilationstarted-method.md)|<span data-ttu-id="f1ffa-115">Notifica al generador de perfiles que el compilador Just-in-Time (JIT) ha empezado a volver a compilar una función.</span><span class="sxs-lookup"><span data-stu-id="f1ffa-115">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>|  
|[<span data-ttu-id="f1ffa-116">Método ReJITError</span><span class="sxs-lookup"><span data-stu-id="f1ffa-116">ReJITError Method</span></span>](icorprofilercallback4-rejiterror-method.md)|<span data-ttu-id="f1ffa-117">Informa de un error detectado durante el procesamiento de una solicitud de recompilación.</span><span class="sxs-lookup"><span data-stu-id="f1ffa-117">Reports an error encountered while processing a recompile request.</span></span>|  
|[<span data-ttu-id="f1ffa-118">Método SurvivingReferences2</span><span class="sxs-lookup"><span data-stu-id="f1ffa-118">SurvivingReferences2 Method</span></span>](icorprofilercallback4-survivingreferences2-method.md)|<span data-ttu-id="f1ffa-119">Informa del diseño de objetos del montón como resultado de una recolección de elementos no utilizados sin compactación.</span><span class="sxs-lookup"><span data-stu-id="f1ffa-119">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1ffa-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f1ffa-120">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1ffa-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f1ffa-121">Requirements</span></span>  

 <span data-ttu-id="f1ffa-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1ffa-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1ffa-123">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f1ffa-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f1ffa-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1ffa-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1ffa-125">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1ffa-125">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1ffa-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1ffa-126">See also</span></span>

- [<span data-ttu-id="f1ffa-127">ICorProfilerCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f1ffa-127">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
- [<span data-ttu-id="f1ffa-128">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="f1ffa-128">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="f1ffa-129">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f1ffa-129">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
