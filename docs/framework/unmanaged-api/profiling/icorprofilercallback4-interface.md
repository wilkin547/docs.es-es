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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a96aadcec6cb3c4f4680499585bf1c950bc5ddd4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54525315"
---
# <a name="icorprofilercallback4-interface"></a><span data-ttu-id="d73e4-102">ICorProfilerCallback4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d73e4-102">ICorProfilerCallback4 Interface</span></span>
<span data-ttu-id="d73e4-103">Proporciona métodos de devolución de llamada que common language runtime (CLR) se usa para comunicar información al generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="d73e4-103">Provides callback methods that the common language runtime (CLR) uses to communicate information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d73e4-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="d73e4-104">Methods</span></span>  
  
|<span data-ttu-id="d73e4-105">Método</span><span class="sxs-lookup"><span data-stu-id="d73e4-105">Method</span></span>|<span data-ttu-id="d73e4-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="d73e4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d73e4-107">GetReJITParameters (método)</span><span class="sxs-lookup"><span data-stu-id="d73e4-107">GetReJITParameters Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md)|<span data-ttu-id="d73e4-108">Permite al analizador de código establecer las marcas de generación de código alternativa para un nuevo cuerpo de método ha vuelto a compilar.</span><span class="sxs-lookup"><span data-stu-id="d73e4-108">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>|  
|[<span data-ttu-id="d73e4-109">MovedReferences2 (método)</span><span class="sxs-lookup"><span data-stu-id="d73e4-109">MovedReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)|<span data-ttu-id="d73e4-110">Informa de la nueva disposición de los objetos del montón como resultado de una recolección de elementos no utilizados con compactación.</span><span class="sxs-lookup"><span data-stu-id="d73e4-110">Reports the new layout of objects in the heap as a result of a compacting garbage collection.</span></span>|  
|[<span data-ttu-id="d73e4-111">ReJITCompilationFinished (método)</span><span class="sxs-lookup"><span data-stu-id="d73e4-111">ReJITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)|<span data-ttu-id="d73e4-112">Notifica al generador de perfiles que el compilador de just-in-time (JIT) ha terminado la recompilación de una función.</span><span class="sxs-lookup"><span data-stu-id="d73e4-112">Notifies the profiler that the just-in-time (JIT) compiler has finished the recompilation of a function.</span></span>|  
|[<span data-ttu-id="d73e4-113">ReJITCompilationStarted (método)</span><span class="sxs-lookup"><span data-stu-id="d73e4-113">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)|<span data-ttu-id="d73e4-114">Notifica al generador de perfiles que se ha iniciado el compilador de just-in-time (JIT) volver a compilar una función.</span><span class="sxs-lookup"><span data-stu-id="d73e4-114">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>|  
|[<span data-ttu-id="d73e4-115">ReJITError (método)</span><span class="sxs-lookup"><span data-stu-id="d73e4-115">ReJITError Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md)|<span data-ttu-id="d73e4-116">Notifica un error al procesar una solicitud de recompilación.</span><span class="sxs-lookup"><span data-stu-id="d73e4-116">Reports an error encountered while processing a recompile request.</span></span>|  
|[<span data-ttu-id="d73e4-117">SurvivingReferences2 (método)</span><span class="sxs-lookup"><span data-stu-id="d73e4-117">SurvivingReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md)|<span data-ttu-id="d73e4-118">Informa de la distribución de los objetos del montón como resultado de una recolección de elementos no utilizados sin compactación.</span><span class="sxs-lookup"><span data-stu-id="d73e4-118">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d73e4-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d73e4-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d73e4-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d73e4-120">Requirements</span></span>  
 <span data-ttu-id="d73e4-121">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d73e4-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d73e4-122">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d73e4-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d73e4-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d73e4-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d73e4-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d73e4-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d73e4-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="d73e4-125">See also</span></span>
- [<span data-ttu-id="d73e4-126">ICorProfilerCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d73e4-126">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [<span data-ttu-id="d73e4-127">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="d73e4-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="d73e4-128">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d73e4-128">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
