---
title: ICorProfilerCallback4 (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback4
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback4
helpviewer_keywords: ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 665f3cfc-cd6f-4880-906c-ea65ad384783
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: efcbc9adce9b5cfc39c5eb3e1649a35d458e99c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback4-interface"></a><span data-ttu-id="a0549-102">ICorProfilerCallback4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a0549-102">ICorProfilerCallback4 Interface</span></span>
<span data-ttu-id="a0549-103">Proporciona métodos de devolución de llamada que common language runtime (CLR) usa para comunicar información al generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="a0549-103">Provides callback methods that the common language runtime (CLR) uses to communicate information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a0549-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a0549-104">Methods</span></span>  
  
|<span data-ttu-id="a0549-105">Método</span><span class="sxs-lookup"><span data-stu-id="a0549-105">Method</span></span>|<span data-ttu-id="a0549-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0549-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a0549-107">GetReJITParameters (método)</span><span class="sxs-lookup"><span data-stu-id="a0549-107">GetReJITParameters Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md)|<span data-ttu-id="a0549-108">Permite que el generador de perfiles de código establecer las marcas de generación de código alternativo para un nuevo cuerpo de método ha vuelto a compilar.</span><span class="sxs-lookup"><span data-stu-id="a0549-108">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>|  
|[<span data-ttu-id="a0549-109">MovedReferences2 (método)</span><span class="sxs-lookup"><span data-stu-id="a0549-109">MovedReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)|<span data-ttu-id="a0549-110">Informa del diseño de objetos del montón como resultado de una colección de elementos no utilizados sin compactación.</span><span class="sxs-lookup"><span data-stu-id="a0549-110">Reports the new layout of objects in the heap as a result of a compacting garbage collection.</span></span>|  
|[<span data-ttu-id="a0549-111">ReJITCompilationFinished (método)</span><span class="sxs-lookup"><span data-stu-id="a0549-111">ReJITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)|<span data-ttu-id="a0549-112">Notifica al generador de perfiles que el compilador de just-in-time (JIT) ha terminado la recompilación de una función.</span><span class="sxs-lookup"><span data-stu-id="a0549-112">Notifies the profiler that the just-in-time (JIT) compiler has finished the recompilation of a function.</span></span>|  
|[<span data-ttu-id="a0549-113">ReJITCompilationStarted (método)</span><span class="sxs-lookup"><span data-stu-id="a0549-113">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)|<span data-ttu-id="a0549-114">Notifica al generador de perfiles que se ha iniciado el compilador de just-in-time (JIT) para volver a compilar una función.</span><span class="sxs-lookup"><span data-stu-id="a0549-114">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>|  
|[<span data-ttu-id="a0549-115">ReJITError (método)</span><span class="sxs-lookup"><span data-stu-id="a0549-115">ReJITError Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md)|<span data-ttu-id="a0549-116">Notifica un error al procesar una solicitud de nueva compilación.</span><span class="sxs-lookup"><span data-stu-id="a0549-116">Reports an error encountered while processing a recompile request.</span></span>|  
|[<span data-ttu-id="a0549-117">SurvivingReferences2 (método)</span><span class="sxs-lookup"><span data-stu-id="a0549-117">SurvivingReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md)|<span data-ttu-id="a0549-118">Informa de la distribución de los objetos del montón como resultado de una recolección de elementos no utilizados sin compactación.</span><span class="sxs-lookup"><span data-stu-id="a0549-118">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0549-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a0549-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0549-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a0549-120">Requirements</span></span>  
 <span data-ttu-id="a0549-121">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0549-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0549-122">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a0549-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a0549-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0549-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0549-124">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0549-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0549-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0549-125">See Also</span></span>  
 [<span data-ttu-id="a0549-126">ICorProfilerCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a0549-126">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [<span data-ttu-id="a0549-127">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a0549-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="a0549-128">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a0549-128">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
