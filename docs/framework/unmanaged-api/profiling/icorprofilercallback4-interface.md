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
ms.openlocfilehash: 3eb1f46900199db65be5d14c56bfc0b6f55bf269
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59205139"
---
# <a name="icorprofilercallback4-interface"></a><span data-ttu-id="95c0c-102">ICorProfilerCallback4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="95c0c-102">ICorProfilerCallback4 Interface</span></span>
<span data-ttu-id="95c0c-103">Proporciona métodos de devolución de llamada que common language runtime (CLR) se usa para comunicar información al generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="95c0c-103">Provides callback methods that the common language runtime (CLR) uses to communicate information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="95c0c-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="95c0c-104">Methods</span></span>  
  
|<span data-ttu-id="95c0c-105">Método</span><span class="sxs-lookup"><span data-stu-id="95c0c-105">Method</span></span>|<span data-ttu-id="95c0c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="95c0c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="95c0c-107">Método GetReJITParameters</span><span class="sxs-lookup"><span data-stu-id="95c0c-107">GetReJITParameters Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md)|<span data-ttu-id="95c0c-108">Permite al analizador de código establecer las marcas de generación de código alternativa para un nuevo cuerpo de método ha vuelto a compilar.</span><span class="sxs-lookup"><span data-stu-id="95c0c-108">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>|  
|[<span data-ttu-id="95c0c-109">Método MovedReferences2</span><span class="sxs-lookup"><span data-stu-id="95c0c-109">MovedReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)|<span data-ttu-id="95c0c-110">Informa de la nueva disposición de los objetos del montón como resultado de una recolección de elementos no utilizados con compactación.</span><span class="sxs-lookup"><span data-stu-id="95c0c-110">Reports the new layout of objects in the heap as a result of a compacting garbage collection.</span></span>|  
|[<span data-ttu-id="95c0c-111">Método ReJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="95c0c-111">ReJITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)|<span data-ttu-id="95c0c-112">Notifica al generador de perfiles que el compilador de just-in-time (JIT) ha terminado la recompilación de una función.</span><span class="sxs-lookup"><span data-stu-id="95c0c-112">Notifies the profiler that the just-in-time (JIT) compiler has finished the recompilation of a function.</span></span>|  
|[<span data-ttu-id="95c0c-113">Método ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="95c0c-113">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)|<span data-ttu-id="95c0c-114">Notifica al generador de perfiles que se ha iniciado el compilador de just-in-time (JIT) volver a compilar una función.</span><span class="sxs-lookup"><span data-stu-id="95c0c-114">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>|  
|[<span data-ttu-id="95c0c-115">Método ReJITError</span><span class="sxs-lookup"><span data-stu-id="95c0c-115">ReJITError Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md)|<span data-ttu-id="95c0c-116">Notifica un error al procesar una solicitud de recompilación.</span><span class="sxs-lookup"><span data-stu-id="95c0c-116">Reports an error encountered while processing a recompile request.</span></span>|  
|[<span data-ttu-id="95c0c-117">Método SurvivingReferences2</span><span class="sxs-lookup"><span data-stu-id="95c0c-117">SurvivingReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md)|<span data-ttu-id="95c0c-118">Informa del diseño de objetos del montón como resultado de una recolección de elementos no utilizados sin compactación.</span><span class="sxs-lookup"><span data-stu-id="95c0c-118">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95c0c-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="95c0c-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95c0c-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="95c0c-120">Requirements</span></span>  
 <span data-ttu-id="95c0c-121">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95c0c-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95c0c-122">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="95c0c-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="95c0c-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95c0c-123">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="95c0c-124">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="95c0c-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="95c0c-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="95c0c-125">See also</span></span>

- [<span data-ttu-id="95c0c-126">ICorProfilerCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="95c0c-126">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [<span data-ttu-id="95c0c-127">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="95c0c-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="95c0c-128">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="95c0c-128">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
