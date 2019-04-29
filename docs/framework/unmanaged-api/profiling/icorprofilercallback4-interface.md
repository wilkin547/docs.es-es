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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598200"
---
# <a name="icorprofilercallback4-interface"></a><span data-ttu-id="0b2c7-102">ICorProfilerCallback4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0b2c7-102">ICorProfilerCallback4 Interface</span></span>
<span data-ttu-id="0b2c7-103">Proporciona métodos de devolución de llamada que common language runtime (CLR) se usa para comunicar información al generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="0b2c7-103">Provides callback methods that the common language runtime (CLR) uses to communicate information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0b2c7-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="0b2c7-104">Methods</span></span>  
  
|<span data-ttu-id="0b2c7-105">Método</span><span class="sxs-lookup"><span data-stu-id="0b2c7-105">Method</span></span>|<span data-ttu-id="0b2c7-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="0b2c7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0b2c7-107">GetReJITParameters (método)</span><span class="sxs-lookup"><span data-stu-id="0b2c7-107">GetReJITParameters Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md)|<span data-ttu-id="0b2c7-108">Permite al analizador de código establecer las marcas de generación de código alternativa para un nuevo cuerpo de método ha vuelto a compilar.</span><span class="sxs-lookup"><span data-stu-id="0b2c7-108">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>|  
|[<span data-ttu-id="0b2c7-109">MovedReferences2 (método)</span><span class="sxs-lookup"><span data-stu-id="0b2c7-109">MovedReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)|<span data-ttu-id="0b2c7-110">Informa de la nueva disposición de los objetos del montón como resultado de una recolección de elementos no utilizados con compactación.</span><span class="sxs-lookup"><span data-stu-id="0b2c7-110">Reports the new layout of objects in the heap as a result of a compacting garbage collection.</span></span>|  
|[<span data-ttu-id="0b2c7-111">ReJITCompilationFinished (método)</span><span class="sxs-lookup"><span data-stu-id="0b2c7-111">ReJITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)|<span data-ttu-id="0b2c7-112">Notifica al generador de perfiles que el compilador de just-in-time (JIT) ha terminado la recompilación de una función.</span><span class="sxs-lookup"><span data-stu-id="0b2c7-112">Notifies the profiler that the just-in-time (JIT) compiler has finished the recompilation of a function.</span></span>|  
|[<span data-ttu-id="0b2c7-113">ReJITCompilationStarted (método)</span><span class="sxs-lookup"><span data-stu-id="0b2c7-113">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)|<span data-ttu-id="0b2c7-114">Notifica al generador de perfiles que se ha iniciado el compilador de just-in-time (JIT) volver a compilar una función.</span><span class="sxs-lookup"><span data-stu-id="0b2c7-114">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>|  
|[<span data-ttu-id="0b2c7-115">ReJITError (método)</span><span class="sxs-lookup"><span data-stu-id="0b2c7-115">ReJITError Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md)|<span data-ttu-id="0b2c7-116">Notifica un error al procesar una solicitud de recompilación.</span><span class="sxs-lookup"><span data-stu-id="0b2c7-116">Reports an error encountered while processing a recompile request.</span></span>|  
|[<span data-ttu-id="0b2c7-117">SurvivingReferences2 (método)</span><span class="sxs-lookup"><span data-stu-id="0b2c7-117">SurvivingReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md)|<span data-ttu-id="0b2c7-118">Informa del diseño de objetos del montón como resultado de una recolección de elementos no utilizados sin compactación.</span><span class="sxs-lookup"><span data-stu-id="0b2c7-118">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b2c7-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0b2c7-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b2c7-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0b2c7-120">Requirements</span></span>  
 <span data-ttu-id="0b2c7-121">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b2c7-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b2c7-122">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0b2c7-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0b2c7-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b2c7-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b2c7-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b2c7-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b2c7-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b2c7-125">See also</span></span>

- [<span data-ttu-id="0b2c7-126">ICorProfilerCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0b2c7-126">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [<span data-ttu-id="0b2c7-127">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="0b2c7-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="0b2c7-128">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0b2c7-128">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
