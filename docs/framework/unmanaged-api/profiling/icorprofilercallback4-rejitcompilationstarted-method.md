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
ms.openlocfilehash: 81d11c87c9bc970dd5b5c9010023610cea7c0e72
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865199"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a><span data-ttu-id="85e81-102">ICorProfilerCallback4::ReJITCompilationStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="85e81-102">ICorProfilerCallback4::ReJITCompilationStarted Method</span></span>
<span data-ttu-id="85e81-103">Notifica al generador de perfiles que el compilador Just-in-Time (JIT) ha empezado a volver a compilar una función.</span><span class="sxs-lookup"><span data-stu-id="85e81-103">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85e81-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85e81-104">Syntax</span></span>  
  
```cpp  
HRESULT ReJITCompilationStarted(   
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85e81-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="85e81-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="85e81-106">de IDENTIFICADOR de la función que el compilador JIT ha empezado a volver a compilar.</span><span class="sxs-lookup"><span data-stu-id="85e81-106">[in] The ID of the function that the JIT compiler has started to recompile.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="85e81-107">de IDENTIFICADOR de recompilación de la nueva versión de la función.</span><span class="sxs-lookup"><span data-stu-id="85e81-107">[in] The recompilation ID of the new version of the function.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="85e81-108">[in] `true` para indicar que el bloqueo puede hacer que el tiempo de ejecución espere a que el subproceso que realiza la llamada devuelva de esta devolución de llamada; `false` para indicar que el bloqueo no afectará al funcionamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="85e81-108">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span> <span data-ttu-id="85e81-109">Un valor de `true` no perjudica al tiempo de ejecución, pero puede afectar a los resultados de la generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="85e81-109">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85e81-110">Notas</span><span class="sxs-lookup"><span data-stu-id="85e81-110">Remarks</span></span>  
 <span data-ttu-id="85e81-111">Es posible recibir más de un par de llamadas a métodos `ReJITCompilationStarted` y [rejitcompilationfinished (](icorprofilercallback4-rejitcompilationfinished-method.md) para cada función debido a la manera en que el tiempo de ejecución controla los constructores de clase.</span><span class="sxs-lookup"><span data-stu-id="85e81-111">It is possible to receive more than one pair of `ReJITCompilationStarted` and [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) method calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="85e81-112">Por ejemplo, el tiempo de ejecución comienza a volver a compilar el método A, pero es necesario ejecutar el constructor de clase de la clase B.</span><span class="sxs-lookup"><span data-stu-id="85e81-112">For example, the runtime starts to recompile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="85e81-113">Por consiguiente, el tiempo de ejecución vuelve a compilar el constructor de la clase B y lo ejecuta.</span><span class="sxs-lookup"><span data-stu-id="85e81-113">Therefore, the runtime recompiles the constructor for class B and runs it.</span></span> <span data-ttu-id="85e81-114">Mientras se ejecuta el constructor, realiza una llamada al método a, que hace que se vuelva a compilar el método a.</span><span class="sxs-lookup"><span data-stu-id="85e81-114">While the constructor is running, it makes a call to method A, which causes method A to be recompiled again.</span></span> <span data-ttu-id="85e81-115">En este escenario, se detiene la primera recompilación del método A.</span><span class="sxs-lookup"><span data-stu-id="85e81-115">In this scenario, the first recompilation of method A is halted.</span></span> <span data-ttu-id="85e81-116">Sin embargo, ambos intentos de volver a compilar el método A se registran con eventos de recompilación JIT.</span><span class="sxs-lookup"><span data-stu-id="85e81-116">However, both attempts to recompile method A are reported with JIT recompilation events.</span></span>  
  
 <span data-ttu-id="85e81-117">Los profileres deben admitir la secuencia de devoluciones de llamada de recompilación JIT en los casos en que dos subprocesos realizan simultáneamente devoluciones de llamada.</span><span class="sxs-lookup"><span data-stu-id="85e81-117">Profilers must support the sequence of JIT recompilation callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="85e81-118">Por ejemplo, el subproceso A llama a `ReJITCompilationStarted`; sin embargo, antes de que el subproceso A llame a [rejitcompilationfinished (](icorprofilercallback4-rejitcompilationfinished-method.md), el subproceso B llama a [ICorProfilerCallback:: EXCEPTIONSEARCHFUNCTIONENTER (](icorprofilercallback-exceptionsearchfunctionenter-method.md) con el identificador de función de la devolución de llamada `ReJITCompilationStarted` para el subproceso A. Podría parecer que el identificador de función no debería ser válido todavía porque el generador de perfiles no ha recibido todavía una llamada a [rejitcompilationfinished (](icorprofilercallback4-rejitcompilationfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="85e81-118">For example, thread A calls `ReJITCompilationStarted`; however, before thread A calls [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md), thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from the `ReJITCompilationStarted` callback for thread A. It might appear that the function ID should not yet be valid because a call to [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) had not yet been received by the profiler.</span></span> <span data-ttu-id="85e81-119">Sin embargo, en este caso, el identificador de función es válido.</span><span class="sxs-lookup"><span data-stu-id="85e81-119">However, in this case, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85e81-120">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="85e81-120">Requirements</span></span>  
 <span data-ttu-id="85e81-121">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85e81-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85e81-122">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="85e81-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="85e81-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85e81-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85e81-124">**.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85e81-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85e81-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="85e81-125">See also</span></span>

- [<span data-ttu-id="85e81-126">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="85e81-126">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="85e81-127">ICorProfilerCallback4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="85e81-127">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
- [<span data-ttu-id="85e81-128">JITCompilationFinished (método)</span><span class="sxs-lookup"><span data-stu-id="85e81-128">JITCompilationFinished Method</span></span>](icorprofilercallback-jitcompilationfinished-method.md)
- [<span data-ttu-id="85e81-129">ReJITCompilationFinished (método)</span><span class="sxs-lookup"><span data-stu-id="85e81-129">ReJITCompilationFinished Method</span></span>](icorprofilercallback4-rejitcompilationfinished-method.md)
