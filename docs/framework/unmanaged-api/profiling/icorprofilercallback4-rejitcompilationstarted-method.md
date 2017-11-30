---
title: "ICorProfilerCallback4::ReJITCompilationStarted (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback4.ReJITCompilationStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback4::ReJITCompilationStarted
helpviewer_keywords:
- ReJITCompilationStarted method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITCompilationStarted method [.NET Framework profiling]
ms.assetid: 512fdd00-262a-4456-a075-365ef4133c4d
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ddcacf72d21ec076fe74a1c069311ef3f73a20c2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a><span data-ttu-id="c6ebe-102">ICorProfilerCallback4::ReJITCompilationStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="c6ebe-102">ICorProfilerCallback4::ReJITCompilationStarted Method</span></span>
<span data-ttu-id="c6ebe-103">Notifica al generador de perfiles que se ha iniciado el compilador de just-in-time (JIT) para volver a compilar una función.</span><span class="sxs-lookup"><span data-stu-id="c6ebe-103">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6ebe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c6ebe-104">Syntax</span></span>  
  
```  
HRESULT ReJITCompilationStarted(    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c6ebe-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c6ebe-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="c6ebe-106">[in] El identificador de la función que se ha iniciado el compilador JIT para volver a compilar.</span><span class="sxs-lookup"><span data-stu-id="c6ebe-106">[in] The ID of the function that the JIT compiler has started to recompile.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="c6ebe-107">[in] El identificador de la recompilación de la nueva versión de la función.</span><span class="sxs-lookup"><span data-stu-id="c6ebe-107">[in] The recompilation ID of the new version of the function.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="c6ebe-108">[in] `true` para indicar que el bloqueo puede causar el tiempo de ejecución esperar el subproceso de llamada devolver desde esta devolución de llamada; `false` para indicar que el bloqueo no afectará al funcionamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c6ebe-108">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span> <span data-ttu-id="c6ebe-109">Un valor de `true` no dañar el tiempo de ejecución, pero puede afectar a los resultados de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="c6ebe-109">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6ebe-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c6ebe-110">Remarks</span></span>  
 <span data-ttu-id="c6ebe-111">Es posible recibir más de un par de `ReJITCompilationStarted` y [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) método llama para cada función debido al modo en el tiempo de ejecución de los constructores de clases de identificadores.</span><span class="sxs-lookup"><span data-stu-id="c6ebe-111">It is possible to receive more than one pair of `ReJITCompilationStarted` and [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) method calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="c6ebe-112">Por ejemplo, el tiempo de ejecución se inicia para volver a compilar un método, pero el constructor de la clase B es necesario ejecutar.</span><span class="sxs-lookup"><span data-stu-id="c6ebe-112">For example, the runtime starts to recompile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="c6ebe-113">Por lo tanto, el tiempo de ejecución vuelve a compilar el constructor de clase B y lo ejecuta.</span><span class="sxs-lookup"><span data-stu-id="c6ebe-113">Therefore, the runtime recompiles the constructor for class B and runs it.</span></span> <span data-ttu-id="c6ebe-114">Cuando se está ejecutando el constructor, se hace una llamada a método A, que hace que el método A volver a compilar de nuevo.</span><span class="sxs-lookup"><span data-stu-id="c6ebe-114">While the constructor is running, it makes a call to method A, which causes method A to be recompiled again.</span></span> <span data-ttu-id="c6ebe-115">En este escenario, se detiene la primera recompilación de un método.</span><span class="sxs-lookup"><span data-stu-id="c6ebe-115">In this scenario, the first recompilation of method A is halted.</span></span> <span data-ttu-id="c6ebe-116">Sin embargo, ambas intenta volver a compilar método notificado A son eventos de recompilación JIT.</span><span class="sxs-lookup"><span data-stu-id="c6ebe-116">However, both attempts to recompile method A are reported with JIT recompilation events.</span></span>  
  
 <span data-ttu-id="c6ebe-117">Los generadores de perfiles deben admitir la secuencia de devoluciones de llamada de recompilación JIT en casos donde dos subprocesos están realizando simultáneamente devoluciones de llamada.</span><span class="sxs-lookup"><span data-stu-id="c6ebe-117">Profilers must support the sequence of JIT recompilation callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="c6ebe-118">Por ejemplo, un subproceso llama a `ReJITCompilationStarted`; sin embargo, antes de llamadas de subprocesos A [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), el subproceso B llama [ICorProfilerCallback:: ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) con el identificador de función desde el `ReJITCompilationStarted` devolución de llamada para el subproceso A. Podría parecer que el identificador de función no debe encontrarse aún válido porque una llamada a [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) tenía no se han recibido por el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="c6ebe-118">For example, thread A calls `ReJITCompilationStarted`; however, before thread A calls [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from the `ReJITCompilationStarted` callback for thread A. It might appear that the function ID should not yet be valid because a call to [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) had not yet been received by the profiler.</span></span> <span data-ttu-id="c6ebe-119">Sin embargo, en este caso, el identificador de función es válido.</span><span class="sxs-lookup"><span data-stu-id="c6ebe-119">However, in this case, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6ebe-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c6ebe-120">Requirements</span></span>  
 <span data-ttu-id="c6ebe-121">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6ebe-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6ebe-122">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c6ebe-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c6ebe-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6ebe-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6ebe-124">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6ebe-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6ebe-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6ebe-125">See Also</span></span>  
 [<span data-ttu-id="c6ebe-126">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c6ebe-126">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="c6ebe-127">ICorProfilerCallback4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c6ebe-127">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 [<span data-ttu-id="c6ebe-128">JITCompilationFinished (método)</span><span class="sxs-lookup"><span data-stu-id="c6ebe-128">JITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)  
 [<span data-ttu-id="c6ebe-129">ReJITCompilationFinished (método)</span><span class="sxs-lookup"><span data-stu-id="c6ebe-129">ReJITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)
