---
title: ICorProfilerCallback::JITCompilationStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationStarted
helpviewer_keywords:
- JITCompilationStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationStarted method [.NET Framework profiling]
ms.assetid: 31782b36-d311-4518-8f45-25f65385af5b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4b75eebd8d9bf439a0317521a61c06ece3745be0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075326"
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a><span data-ttu-id="4fc6c-102">ICorProfilerCallback::JITCompilationStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="4fc6c-102">ICorProfilerCallback::JITCompilationStarted Method</span></span>
<span data-ttu-id="4fc6c-103">Notifica al generador de perfiles que se ha iniciado el compilador de just-in-time (JIT) compilar una función.</span><span class="sxs-lookup"><span data-stu-id="4fc6c-103">Notifies the profiler that the just-in-time (JIT) compiler has started to compile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fc6c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4fc6c-104">Syntax</span></span>  
  
```  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4fc6c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4fc6c-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="4fc6c-106">[in] El identificador de la función para el que se está iniciando la compilación.</span><span class="sxs-lookup"><span data-stu-id="4fc6c-106">[in] The ID of the function for which the compilation is starting.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="4fc6c-107">[in] Un valor que indica al generador de perfiles si el bloqueo afectará al funcionamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4fc6c-107">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="4fc6c-108">El valor es `true` Si bloqueo puede provocar el tiempo de ejecución esperar el subproceso de llamada devolver desde esta devolución de llamada; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="4fc6c-108">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="4fc6c-109">Aunque un valor de `true` no dañarán el tiempo de ejecución, pueden sesgar los resultados de la generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="4fc6c-109">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4fc6c-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4fc6c-110">Remarks</span></span>  
 <span data-ttu-id="4fc6c-111">Es posible recibir más de un par de `JITCompilationStarted` y [ICorProfilerCallback:: JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) llama para cada función debido al modo en el tiempo de ejecución controla los constructores de clase.</span><span class="sxs-lookup"><span data-stu-id="4fc6c-111">It is possible to receive more than one pair of `JITCompilationStarted` and [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="4fc6c-112">Por ejemplo, el tiempo de ejecución se inicia la compilación JIT del método A, pero el constructor de la clase B debe ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="4fc6c-112">For example, the runtime starts to JIT-compile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="4fc6c-113">Por lo tanto, el tiempo de ejecución JIT compila el constructor de clase B y lo ejecuta.</span><span class="sxs-lookup"><span data-stu-id="4fc6c-113">Therefore, the runtime JIT-compiles the constructor for class B and runs it.</span></span> <span data-ttu-id="4fc6c-114">Mientras se ejecuta el constructor, realiza una llamada al método A, que hace que el método A volver a estar compilado JIT.</span><span class="sxs-lookup"><span data-stu-id="4fc6c-114">While the constructor is running, it makes a call to method A, which causes method A to be JIT-compiled again.</span></span> <span data-ttu-id="4fc6c-115">En este escenario, se detiene la primera compilación JIT del método.</span><span class="sxs-lookup"><span data-stu-id="4fc6c-115">In this scenario, the first JIT compilation of method A is halted.</span></span> <span data-ttu-id="4fc6c-116">Sin embargo, se notifica tanto a la compilación JIT del método A los intentos con eventos de compilación JIT.</span><span class="sxs-lookup"><span data-stu-id="4fc6c-116">However, both attempts to JIT-compile method A are reported with JIT-compilation events.</span></span> <span data-ttu-id="4fc6c-117">Si el generador de perfiles se va a reemplazar el código de lenguaje intermedio (MSIL) de Microsoft para un método mediante una llamada a la [SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) método, debe hacerlo para ambos `JITCompilationStarted` eventos, pero se puede usar el mismo bloque MSIL para ambos.</span><span class="sxs-lookup"><span data-stu-id="4fc6c-117">If the profiler is going to replace Microsoft intermediate language (MSIL) code for method A by calling the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method, it must do so for both `JITCompilationStarted` events, but it may use the same MSIL block for both.</span></span>  
  
 <span data-ttu-id="4fc6c-118">Los generadores de perfiles deben admitir la secuencia de devoluciones de llamada JIT en casos donde dos subprocesos están realizando simultáneamente las devoluciones de llamada.</span><span class="sxs-lookup"><span data-stu-id="4fc6c-118">Profilers must support the sequence of JIT callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="4fc6c-119">Por ejemplo, un subproceso a llama a `JITCompilationStarted`.</span><span class="sxs-lookup"><span data-stu-id="4fc6c-119">For example, thread A calls `JITCompilationStarted`.</span></span> <span data-ttu-id="4fc6c-120">Sin embargo, antes de un subproceso llama a `JITCompilationFinished`, el subproceso B llama a [ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) con el identificador de función desde el subproceso del `JITCompilationStarted` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="4fc6c-120">However, before thread A calls `JITCompilationFinished`, thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from thread A's `JITCompilationStarted` callback.</span></span> <span data-ttu-id="4fc6c-121">Podría parecer que el identificador de función no debe encontrarse aún válido porque una llamada a `JITCompilationFinished` tenía no se han recibido por el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="4fc6c-121">It might appear that the function ID should not yet be valid because a call to `JITCompilationFinished` had not yet been received by the profiler.</span></span> <span data-ttu-id="4fc6c-122">Sin embargo, en un caso como éste, el identificador de función es válido.</span><span class="sxs-lookup"><span data-stu-id="4fc6c-122">However, in a case like this one, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fc6c-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4fc6c-123">Requirements</span></span>  
 <span data-ttu-id="4fc6c-124">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fc6c-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fc6c-125">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4fc6c-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4fc6c-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4fc6c-126">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="4fc6c-127">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="4fc6c-127">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4fc6c-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="4fc6c-128">See also</span></span>

- [<span data-ttu-id="4fc6c-129">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4fc6c-129">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="4fc6c-130">Método JITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="4fc6c-130">JITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
