---
title: "ICorProfilerCallback::JITCompilationStarted (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITCompilationStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITCompilationStarted
helpviewer_keywords:
- JITCompilationStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationStarted method [.NET Framework profiling]
ms.assetid: 31782b36-d311-4518-8f45-25f65385af5b
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a12ae3e33d5553ed99a5a26b8fc872f0d07de81e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a><span data-ttu-id="b959c-102">ICorProfilerCallback::JITCompilationStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="b959c-102">ICorProfilerCallback::JITCompilationStarted Method</span></span>
<span data-ttu-id="b959c-103">Notifica al generador de perfiles que se ha iniciado el compilador de just-in-time (JIT) compilar una función.</span><span class="sxs-lookup"><span data-stu-id="b959c-103">Notifies the profiler that the just-in-time (JIT) compiler has started to compile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b959c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b959c-104">Syntax</span></span>  
  
```  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b959c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b959c-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="b959c-106">[in] El identificador de la función para la que se está iniciando la compilación.</span><span class="sxs-lookup"><span data-stu-id="b959c-106">[in] The ID of the function for which the compilation is starting.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="b959c-107">[in] Un valor que indica al generador de perfiles si el bloqueo afectará al funcionamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b959c-107">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="b959c-108">El valor es `true` Si bloqueo puede hacer que el tiempo de ejecución esperar el subproceso de llamada devolver desde esta devolución de llamada; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="b959c-108">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="b959c-109">Aunque un valor de `true` no dañarán el tiempo de ejecución, se pueden falsear los resultados de la generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="b959c-109">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b959c-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b959c-110">Remarks</span></span>  
 <span data-ttu-id="b959c-111">Es posible recibir más de un par de `JITCompilationStarted` y [ICorProfilerCallback:: JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) llama para cada función debido al modo en el tiempo de ejecución de los constructores de clases de identificadores.</span><span class="sxs-lookup"><span data-stu-id="b959c-111">It is possible to receive more than one pair of `JITCompilationStarted` and [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="b959c-112">Por ejemplo, el tiempo de ejecución inicia la compilación JIT del método A, pero el constructor de la clase B es necesario ejecutar.</span><span class="sxs-lookup"><span data-stu-id="b959c-112">For example, the runtime starts to JIT-compile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="b959c-113">Por lo tanto, el tiempo de ejecución de la compilación JIT del constructor de clase B y lo ejecuta.</span><span class="sxs-lookup"><span data-stu-id="b959c-113">Therefore, the runtime JIT-compiles the constructor for class B and runs it.</span></span> <span data-ttu-id="b959c-114">Cuando se está ejecutando el constructor, se hace una llamada a método A, que hace que el método A para volver a estar compilado JIT.</span><span class="sxs-lookup"><span data-stu-id="b959c-114">While the constructor is running, it makes a call to method A, which causes method A to be JIT-compiled again.</span></span> <span data-ttu-id="b959c-115">En este escenario, se detiene la primera compilación JIT de un método.</span><span class="sxs-lookup"><span data-stu-id="b959c-115">In this scenario, the first JIT compilation of method A is halted.</span></span> <span data-ttu-id="b959c-116">Sin embargo, los intentos de compilación JIT del método A se notifican con los eventos de compilación JIT.</span><span class="sxs-lookup"><span data-stu-id="b959c-116">However, both attempts to JIT-compile method A are reported with JIT-compilation events.</span></span> <span data-ttu-id="b959c-117">Si el generador de perfiles se va a reemplazar el código de lenguaje intermedio (MSIL) de Microsoft para un método mediante una llamada a la [ICorProfilerInfo:: SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) método, debe hacerlo para ambos `JITCompilationStarted` eventos, pero se puede utilizar el mismo bloque MSIL para ambos.</span><span class="sxs-lookup"><span data-stu-id="b959c-117">If the profiler is going to replace Microsoft intermediate language (MSIL) code for method A by calling the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method, it must do so for both `JITCompilationStarted` events, but it may use the same MSIL block for both.</span></span>  
  
 <span data-ttu-id="b959c-118">Los generadores de perfiles deben admitir la secuencia de devoluciones de llamada JIT en casos donde dos subprocesos están realizando simultáneamente devoluciones de llamada.</span><span class="sxs-lookup"><span data-stu-id="b959c-118">Profilers must support the sequence of JIT callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="b959c-119">Por ejemplo, un subproceso llama a `JITCompilationStarted`.</span><span class="sxs-lookup"><span data-stu-id="b959c-119">For example, thread A calls `JITCompilationStarted`.</span></span> <span data-ttu-id="b959c-120">Sin embargo, antes de llamadas de subprocesos A `JITCompilationFinished`, el subproceso B llama [ICorProfilerCallback:: ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) con el identificador de función de subproceso del `JITCompilationStarted` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="b959c-120">However, before thread A calls `JITCompilationFinished`, thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from thread A's `JITCompilationStarted` callback.</span></span> <span data-ttu-id="b959c-121">Podría parecer que el identificador de función no debe encontrarse aún válido porque una llamada a `JITCompilationFinished` tenía no se han recibido por el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="b959c-121">It might appear that the function ID should not yet be valid because a call to `JITCompilationFinished` had not yet been received by the profiler.</span></span> <span data-ttu-id="b959c-122">Sin embargo, en un caso como este, el identificador de función es válido.</span><span class="sxs-lookup"><span data-stu-id="b959c-122">However, in a case like this one, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b959c-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b959c-123">Requirements</span></span>  
 <span data-ttu-id="b959c-124">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b959c-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b959c-125">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b959c-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b959c-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b959c-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b959c-127">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b959c-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b959c-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="b959c-128">See Also</span></span>  
 [<span data-ttu-id="b959c-129">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b959c-129">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="b959c-130">JITCompilationFinished (método)</span><span class="sxs-lookup"><span data-stu-id="b959c-130">JITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
