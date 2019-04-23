---
title: ICorProfilerCallback4::ReJITCompilationStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITCompilationStarted
helpviewer_keywords:
- ReJITCompilationStarted method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITCompilationStarted method [.NET Framework profiling]
ms.assetid: 512fdd00-262a-4456-a075-365ef4133c4d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b8f2ada73686dfbe5629e21cfc6468becbd4ccc5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075904"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a><span data-ttu-id="e188b-102">ICorProfilerCallback4::ReJITCompilationStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="e188b-102">ICorProfilerCallback4::ReJITCompilationStarted Method</span></span>
<span data-ttu-id="e188b-103">Notifica al generador de perfiles que se ha iniciado el compilador de just-in-time (JIT) volver a compilar una función.</span><span class="sxs-lookup"><span data-stu-id="e188b-103">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e188b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e188b-104">Syntax</span></span>  
  
```  
HRESULT ReJITCompilationStarted(   
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e188b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e188b-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="e188b-106">[in] El identificador de la función que se ha iniciado el compilador JIT para volver a compilar.</span><span class="sxs-lookup"><span data-stu-id="e188b-106">[in] The ID of the function that the JIT compiler has started to recompile.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="e188b-107">[in] El identificador de la recompilación de la nueva versión de la función.</span><span class="sxs-lookup"><span data-stu-id="e188b-107">[in] The recompilation ID of the new version of the function.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="e188b-108">[in] `true` para indicar que el bloqueo puede causar el tiempo de ejecución esperar el subproceso de llamada devolver desde esta devolución de llamada; `false` para indicar que la de bloqueo no afectará al funcionamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e188b-108">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span> <span data-ttu-id="e188b-109">Un valor de `true` no daña el tiempo de ejecución, pero puede afectar a los resultados de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="e188b-109">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e188b-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e188b-110">Remarks</span></span>  
 <span data-ttu-id="e188b-111">Es posible recibir más de un par de `ReJITCompilationStarted` y [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) método llama para cada función debido al modo en el tiempo de ejecución controla los constructores de clase.</span><span class="sxs-lookup"><span data-stu-id="e188b-111">It is possible to receive more than one pair of `ReJITCompilationStarted` and [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) method calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="e188b-112">Por ejemplo, el tiempo de ejecución empieza a compilar un método, pero el constructor de la clase B debe ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="e188b-112">For example, the runtime starts to recompile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="e188b-113">Por lo tanto, el tiempo de ejecución vuelve a compilar el constructor de clase B y lo ejecuta.</span><span class="sxs-lookup"><span data-stu-id="e188b-113">Therefore, the runtime recompiles the constructor for class B and runs it.</span></span> <span data-ttu-id="e188b-114">Mientras se ejecuta el constructor, realiza una llamada al método A, lo que hace que el método a compilarse de nuevo.</span><span class="sxs-lookup"><span data-stu-id="e188b-114">While the constructor is running, it makes a call to method A, which causes method A to be recompiled again.</span></span> <span data-ttu-id="e188b-115">En este escenario, se detiene la primera recompilación de un método.</span><span class="sxs-lookup"><span data-stu-id="e188b-115">In this scenario, the first recompilation of method A is halted.</span></span> <span data-ttu-id="e188b-116">Sin embargo, ambos intenta volver a compilar una son se notifica con eventos de recompilación JIT del método.</span><span class="sxs-lookup"><span data-stu-id="e188b-116">However, both attempts to recompile method A are reported with JIT recompilation events.</span></span>  
  
 <span data-ttu-id="e188b-117">Los generadores de perfiles deben admitir la secuencia de devoluciones de llamada de recompilación JIT en casos donde dos subprocesos están realizando simultáneamente las devoluciones de llamada.</span><span class="sxs-lookup"><span data-stu-id="e188b-117">Profilers must support the sequence of JIT recompilation callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="e188b-118">Por ejemplo, un subproceso a llama a `ReJITCompilationStarted`; sin embargo, antes de un subproceso llama a [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), el subproceso B llama a [ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) con el identificador de función desde el `ReJITCompilationStarted` devolución de llamada para el subproceso A. Podría parecer que el identificador de función no debe encontrarse aún válido porque una llamada a [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) tenía no se han recibido por el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="e188b-118">For example, thread A calls `ReJITCompilationStarted`; however, before thread A calls [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from the `ReJITCompilationStarted` callback for thread A. It might appear that the function ID should not yet be valid because a call to [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) had not yet been received by the profiler.</span></span> <span data-ttu-id="e188b-119">Sin embargo, en este caso, el identificador de función es válido.</span><span class="sxs-lookup"><span data-stu-id="e188b-119">However, in this case, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e188b-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e188b-120">Requirements</span></span>  
 <span data-ttu-id="e188b-121">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e188b-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e188b-122">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e188b-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e188b-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e188b-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e188b-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e188b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e188b-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="e188b-125">See also</span></span>

- [<span data-ttu-id="e188b-126">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e188b-126">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="e188b-127">ICorProfilerCallback4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e188b-127">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [<span data-ttu-id="e188b-128">JITCompilationFinished (método)</span><span class="sxs-lookup"><span data-stu-id="e188b-128">JITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
- [<span data-ttu-id="e188b-129">ReJITCompilationFinished (método)</span><span class="sxs-lookup"><span data-stu-id="e188b-129">ReJITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)
