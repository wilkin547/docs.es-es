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
ms.openlocfilehash: e05cb944ea4f3a9ca718dc22c6cd726b6a516ea9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866239"
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a><span data-ttu-id="ac752-102">ICorProfilerCallback::JITCompilationStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="ac752-102">ICorProfilerCallback::JITCompilationStarted Method</span></span>
<span data-ttu-id="ac752-103">Notifica al generador de perfiles que el compilador Just-in-Time (JIT) ha empezado a compilar una función.</span><span class="sxs-lookup"><span data-stu-id="ac752-103">Notifies the profiler that the just-in-time (JIT) compiler has started to compile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac752-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac752-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac752-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="ac752-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="ac752-106">de IDENTIFICADOR de la función para la que se está iniciando la compilación.</span><span class="sxs-lookup"><span data-stu-id="ac752-106">[in] The ID of the function for which the compilation is starting.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="ac752-107">de Un valor que indica al generador de perfiles si el bloqueo afectará al funcionamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ac752-107">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="ac752-108">El valor es `true` si el bloqueo puede hacer que el tiempo de ejecución espere a que el subproceso que realiza la llamada devuelva de esta devolución de llamada; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="ac752-108">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="ac752-109">Aunque el valor `true` no perjudicará el tiempo de ejecución, puede sesgar los resultados de la generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="ac752-109">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac752-110">Notas</span><span class="sxs-lookup"><span data-stu-id="ac752-110">Remarks</span></span>  
 <span data-ttu-id="ac752-111">Es posible recibir más de un par de `JITCompilationStarted` y las llamadas a [ICorProfilerCallback:: JITCompilationFinished (](icorprofilercallback-jitcompilationfinished-method.md) para cada función debido al modo en que el Runtime controla los constructores de clase.</span><span class="sxs-lookup"><span data-stu-id="ac752-111">It is possible to receive more than one pair of `JITCompilationStarted` and [ICorProfilerCallback::JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md) calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="ac752-112">Por ejemplo, el tiempo de ejecución comienza a compilar de forma JIT el método A, pero es necesario ejecutar el constructor de clase de la clase B.</span><span class="sxs-lookup"><span data-stu-id="ac752-112">For example, the runtime starts to JIT-compile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="ac752-113">Por lo tanto, el Runtime compila el constructor para la clase B y lo ejecuta.</span><span class="sxs-lookup"><span data-stu-id="ac752-113">Therefore, the runtime JIT-compiles the constructor for class B and runs it.</span></span> <span data-ttu-id="ac752-114">Mientras se ejecuta el constructor, realiza una llamada al método a, lo que hace que el método a se vuelva a compilar JIT.</span><span class="sxs-lookup"><span data-stu-id="ac752-114">While the constructor is running, it makes a call to method A, which causes method A to be JIT-compiled again.</span></span> <span data-ttu-id="ac752-115">En este escenario, se detiene la primera compilación JIT del método A.</span><span class="sxs-lookup"><span data-stu-id="ac752-115">In this scenario, the first JIT compilation of method A is halted.</span></span> <span data-ttu-id="ac752-116">Sin embargo, ambos intentos de compilar de forma JIT a se registran con eventos de compilación JIT.</span><span class="sxs-lookup"><span data-stu-id="ac752-116">However, both attempts to JIT-compile method A are reported with JIT-compilation events.</span></span> <span data-ttu-id="ac752-117">Si el generador de perfiles va a reemplazar el código del lenguaje intermedio de Microsoft (MSIL) para el método A llamando al método [ICorProfilerInfo:: SetILFunctionBody (](icorprofilerinfo-setilfunctionbody-method.md) , debe hacerlo en ambos eventos `JITCompilationStarted`, pero puede usar el mismo bloque MSIL para ambos.</span><span class="sxs-lookup"><span data-stu-id="ac752-117">If the profiler is going to replace Microsoft intermediate language (MSIL) code for method A by calling the [ICorProfilerInfo::SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) method, it must do so for both `JITCompilationStarted` events, but it may use the same MSIL block for both.</span></span>  
  
 <span data-ttu-id="ac752-118">Los perfiles de servicio deben admitir la secuencia de devoluciones de llamada JIT en los casos en que dos subprocesos realizan simultáneamente devoluciones de llamada.</span><span class="sxs-lookup"><span data-stu-id="ac752-118">Profilers must support the sequence of JIT callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="ac752-119">Por ejemplo, el subproceso A llama a `JITCompilationStarted`.</span><span class="sxs-lookup"><span data-stu-id="ac752-119">For example, thread A calls `JITCompilationStarted`.</span></span> <span data-ttu-id="ac752-120">Sin embargo, antes de que el subproceso A llame a `JITCompilationFinished`, el subproceso B llama a [ICorProfilerCallback:: exceptionsearchfunctionenter (](icorprofilercallback-exceptionsearchfunctionenter-method.md) con el identificador de función de la devolución de llamada de `JITCompilationStarted` del subproceso a.</span><span class="sxs-lookup"><span data-stu-id="ac752-120">However, before thread A calls `JITCompilationFinished`, thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from thread A's `JITCompilationStarted` callback.</span></span> <span data-ttu-id="ac752-121">Podría parecer que el ID. de función no debería ser válido todavía porque el generador de perfiles no ha recibido todavía una llamada a `JITCompilationFinished`.</span><span class="sxs-lookup"><span data-stu-id="ac752-121">It might appear that the function ID should not yet be valid because a call to `JITCompilationFinished` had not yet been received by the profiler.</span></span> <span data-ttu-id="ac752-122">Sin embargo, en un caso como este, el identificador de función es válido.</span><span class="sxs-lookup"><span data-stu-id="ac752-122">However, in a case like this one, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac752-123">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="ac752-123">Requirements</span></span>  
 <span data-ttu-id="ac752-124">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac752-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac752-125">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ac752-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ac752-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac752-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac752-127">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac752-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac752-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac752-128">See also</span></span>

- [<span data-ttu-id="ac752-129">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ac752-129">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="ac752-130">JITCompilationFinished (método)</span><span class="sxs-lookup"><span data-stu-id="ac752-130">JITCompilationFinished Method</span></span>](icorprofilercallback-jitcompilationfinished-method.md)
