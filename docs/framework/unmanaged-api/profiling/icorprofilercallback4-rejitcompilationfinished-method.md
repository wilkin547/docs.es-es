---
title: "ICorProfilerCallback4::ReJITCompilationFinished (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback4.ReJITCompilationFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback4::ReJITCompilationFinished
helpviewer_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished method [.NET Framework profiling]
- ReJITCompilationFinished method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 3b5cff02-2005-44eb-a2bc-50214c4b0e1d
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1aab8fd836da5238fa939b4d20d019f7bd581213
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback4rejitcompilationfinished-method"></a><span data-ttu-id="f41e9-102">ICorProfilerCallback4::ReJITCompilationFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="f41e9-102">ICorProfilerCallback4::ReJITCompilationFinished Method</span></span>
<span data-ttu-id="f41e9-103">Notifica al generador de perfiles que el compilador de just-in-time (JIT) ha terminado de volver a compilar una función.</span><span class="sxs-lookup"><span data-stu-id="f41e9-103">Notifies the profiler that the just-in-time (JIT) compiler has finished recompiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f41e9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f41e9-104">Syntax</span></span>  
  
```  
HRESULT ReJITCompilationFinished(  
    [in] FunctionID functionId,    [in] ReJITID rejitId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f41e9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f41e9-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="f41e9-106">[in] El identificador de la función que se vuelven a compilar.</span><span class="sxs-lookup"><span data-stu-id="f41e9-106">[in] The ID of the function that was recompiled.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="f41e9-107">[in] Identidad de la función recompilada con JIT.</span><span class="sxs-lookup"><span data-stu-id="f41e9-107">[in] The identity of the JIT-recompiled function.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="f41e9-108">[in] Un valor que indica si la recompilación con JIT se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="f41e9-108">[in] A value that indicates whether the JIT recompilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="f41e9-109">[in] `true` para indicar que el bloqueo puede causar el tiempo de ejecución esperar el subproceso de llamada devolver desde esta devolución de llamada; `false` para indicar que el bloqueo no afectará al funcionamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f41e9-109">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  
  
 <span data-ttu-id="f41e9-110">Un valor de `true` no dañar el tiempo de ejecución, pero puede afectar a los resultados de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="f41e9-110">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f41e9-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f41e9-111">Requirements</span></span>  
 <span data-ttu-id="f41e9-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f41e9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f41e9-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f41e9-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f41e9-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f41e9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f41e9-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f41e9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f41e9-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f41e9-116">See Also</span></span>  
 [<span data-ttu-id="f41e9-117">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f41e9-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="f41e9-118">ICorProfilerCallback4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f41e9-118">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 [<span data-ttu-id="f41e9-119">JITCompilationStarted (método)</span><span class="sxs-lookup"><span data-stu-id="f41e9-119">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)  
 [<span data-ttu-id="f41e9-120">ReJITCompilationStarted (método)</span><span class="sxs-lookup"><span data-stu-id="f41e9-120">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)
