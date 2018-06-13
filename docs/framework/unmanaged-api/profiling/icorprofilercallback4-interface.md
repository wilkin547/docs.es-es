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
ms.openlocfilehash: 8bcddc143cacc3df016e6b8dd7907a67354c4311
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455747"
---
# <a name="icorprofilercallback4-interface"></a><span data-ttu-id="2aafe-102">ICorProfilerCallback4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2aafe-102">ICorProfilerCallback4 Interface</span></span>
<span data-ttu-id="2aafe-103">Proporciona métodos de devolución de llamada que common language runtime (CLR) usa para comunicar información al generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="2aafe-103">Provides callback methods that the common language runtime (CLR) uses to communicate information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2aafe-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="2aafe-104">Methods</span></span>  
  
|<span data-ttu-id="2aafe-105">Método</span><span class="sxs-lookup"><span data-stu-id="2aafe-105">Method</span></span>|<span data-ttu-id="2aafe-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="2aafe-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2aafe-107">GetReJITParameters (método)</span><span class="sxs-lookup"><span data-stu-id="2aafe-107">GetReJITParameters Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md)|<span data-ttu-id="2aafe-108">Permite que el generador de perfiles de código establecer las marcas de generación de código alternativo para un nuevo cuerpo de método ha vuelto a compilar.</span><span class="sxs-lookup"><span data-stu-id="2aafe-108">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>|  
|[<span data-ttu-id="2aafe-109">MovedReferences2 (método)</span><span class="sxs-lookup"><span data-stu-id="2aafe-109">MovedReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)|<span data-ttu-id="2aafe-110">Informa del diseño de objetos del montón como resultado de una colección de elementos no utilizados sin compactación.</span><span class="sxs-lookup"><span data-stu-id="2aafe-110">Reports the new layout of objects in the heap as a result of a compacting garbage collection.</span></span>|  
|[<span data-ttu-id="2aafe-111">ReJITCompilationFinished (método)</span><span class="sxs-lookup"><span data-stu-id="2aafe-111">ReJITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)|<span data-ttu-id="2aafe-112">Notifica al generador de perfiles que el compilador de just-in-time (JIT) ha terminado la recompilación de una función.</span><span class="sxs-lookup"><span data-stu-id="2aafe-112">Notifies the profiler that the just-in-time (JIT) compiler has finished the recompilation of a function.</span></span>|  
|[<span data-ttu-id="2aafe-113">ReJITCompilationStarted (método)</span><span class="sxs-lookup"><span data-stu-id="2aafe-113">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)|<span data-ttu-id="2aafe-114">Notifica al generador de perfiles que se ha iniciado el compilador de just-in-time (JIT) para volver a compilar una función.</span><span class="sxs-lookup"><span data-stu-id="2aafe-114">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>|  
|[<span data-ttu-id="2aafe-115">ReJITError (método)</span><span class="sxs-lookup"><span data-stu-id="2aafe-115">ReJITError Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md)|<span data-ttu-id="2aafe-116">Notifica un error al procesar una solicitud de nueva compilación.</span><span class="sxs-lookup"><span data-stu-id="2aafe-116">Reports an error encountered while processing a recompile request.</span></span>|  
|[<span data-ttu-id="2aafe-117">SurvivingReferences2 (método)</span><span class="sxs-lookup"><span data-stu-id="2aafe-117">SurvivingReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md)|<span data-ttu-id="2aafe-118">Informa de la distribución de los objetos del montón como resultado de una recolección de elementos no utilizados sin compactación.</span><span class="sxs-lookup"><span data-stu-id="2aafe-118">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2aafe-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2aafe-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2aafe-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2aafe-120">Requirements</span></span>  
 <span data-ttu-id="2aafe-121">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2aafe-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2aafe-122">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2aafe-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2aafe-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2aafe-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2aafe-124">**Versiones de .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2aafe-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aafe-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="2aafe-125">See Also</span></span>  
 [<span data-ttu-id="2aafe-126">ICorProfilerCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2aafe-126">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [<span data-ttu-id="2aafe-127">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="2aafe-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="2aafe-128">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2aafe-128">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
