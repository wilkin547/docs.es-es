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
ms.openlocfilehash: 6e340fa08800f31d36e6cfb280cac847a4fca548
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499355"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a><span data-ttu-id="c18c7-102">ICorProfilerCallback4::ReJITCompilationStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="c18c7-102">ICorProfilerCallback4::ReJITCompilationStarted Method</span></span>
<span data-ttu-id="c18c7-103">Notifica al generador de perfiles que el compilador Just-in-Time (JIT) ha empezado a volver a compilar una función.</span><span class="sxs-lookup"><span data-stu-id="c18c7-103">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c18c7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c18c7-104">Syntax</span></span>  
  
```cpp  
HRESULT ReJITCompilationStarted(
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c18c7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c18c7-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="c18c7-106">de IDENTIFICADOR de la función que el compilador JIT ha empezado a volver a compilar.</span><span class="sxs-lookup"><span data-stu-id="c18c7-106">[in] The ID of the function that the JIT compiler has started to recompile.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="c18c7-107">de IDENTIFICADOR de recompilación de la nueva versión de la función.</span><span class="sxs-lookup"><span data-stu-id="c18c7-107">[in] The recompilation ID of the new version of the function.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="c18c7-108">[in] `true` para indicar que el bloqueo puede hacer que el tiempo de ejecución espere a que el subproceso que realiza la llamada devuelva de esta devolución de llamada; `false`para indicar que el bloqueo no afectará al funcionamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c18c7-108">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span> <span data-ttu-id="c18c7-109">Un valor de no `true` perjudica al tiempo de ejecución, pero puede afectar a los resultados de la generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="c18c7-109">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c18c7-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c18c7-110">Remarks</span></span>  
 <span data-ttu-id="c18c7-111">Es posible recibir más de un par de `ReJITCompilationStarted` llamadas al método [rejitcompilationfinished (](icorprofilercallback4-rejitcompilationfinished-method.md) y para cada función debido al modo en que el Runtime controla los constructores de clase.</span><span class="sxs-lookup"><span data-stu-id="c18c7-111">It is possible to receive more than one pair of `ReJITCompilationStarted` and [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) method calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="c18c7-112">Por ejemplo, el tiempo de ejecución comienza a volver a compilar el método A, pero es necesario ejecutar el constructor de clase de la clase B.</span><span class="sxs-lookup"><span data-stu-id="c18c7-112">For example, the runtime starts to recompile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="c18c7-113">Por consiguiente, el tiempo de ejecución vuelve a compilar el constructor de la clase B y lo ejecuta.</span><span class="sxs-lookup"><span data-stu-id="c18c7-113">Therefore, the runtime recompiles the constructor for class B and runs it.</span></span> <span data-ttu-id="c18c7-114">Mientras se ejecuta el constructor, realiza una llamada al método a, que hace que se vuelva a compilar el método a.</span><span class="sxs-lookup"><span data-stu-id="c18c7-114">While the constructor is running, it makes a call to method A, which causes method A to be recompiled again.</span></span> <span data-ttu-id="c18c7-115">En este escenario, se detiene la primera recompilación del método A.</span><span class="sxs-lookup"><span data-stu-id="c18c7-115">In this scenario, the first recompilation of method A is halted.</span></span> <span data-ttu-id="c18c7-116">Sin embargo, ambos intentos de volver a compilar el método A se registran con eventos de recompilación JIT.</span><span class="sxs-lookup"><span data-stu-id="c18c7-116">However, both attempts to recompile method A are reported with JIT recompilation events.</span></span>  
  
 <span data-ttu-id="c18c7-117">Los profileres deben admitir la secuencia de devoluciones de llamada de recompilación JIT en los casos en que dos subprocesos realizan simultáneamente devoluciones de llamada.</span><span class="sxs-lookup"><span data-stu-id="c18c7-117">Profilers must support the sequence of JIT recompilation callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="c18c7-118">Por ejemplo, el subproceso A llama a `ReJITCompilationStarted` ; sin embargo, antes de que el subproceso a llame a [rejitcompilationfinished (](icorprofilercallback4-rejitcompilationfinished-method.md), el subproceso B llama a [ICorProfilerCallback:: exceptionsearchfunctionenter (](icorprofilercallback-exceptionsearchfunctionenter-method.md) con el identificador de función de la `ReJITCompilationStarted` devolución de llamada para el subproceso A. Podría parecer que el identificador de función no debería ser válido todavía porque el generador de perfiles no ha recibido todavía una llamada a [rejitcompilationfinished (](icorprofilercallback4-rejitcompilationfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c18c7-118">For example, thread A calls `ReJITCompilationStarted`; however, before thread A calls [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md), thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from the `ReJITCompilationStarted` callback for thread A. It might appear that the function ID should not yet be valid because a call to [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) had not yet been received by the profiler.</span></span> <span data-ttu-id="c18c7-119">Sin embargo, en este caso, el identificador de función es válido.</span><span class="sxs-lookup"><span data-stu-id="c18c7-119">However, in this case, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c18c7-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c18c7-120">Requirements</span></span>  
 <span data-ttu-id="c18c7-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c18c7-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c18c7-122">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c18c7-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c18c7-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c18c7-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c18c7-124">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c18c7-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c18c7-125">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="c18c7-125">See also</span></span>

- [<span data-ttu-id="c18c7-126">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c18c7-126">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="c18c7-127">ICorProfilerCallback4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c18c7-127">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
- [<span data-ttu-id="c18c7-128">Método JITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="c18c7-128">JITCompilationFinished Method</span></span>](icorprofilercallback-jitcompilationfinished-method.md)
- [<span data-ttu-id="c18c7-129">Método ReJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="c18c7-129">ReJITCompilationFinished Method</span></span>](icorprofilercallback4-rejitcompilationfinished-method.md)
