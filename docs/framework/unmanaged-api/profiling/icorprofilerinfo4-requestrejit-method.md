---
title: ICorProfilerInfo4::RequestReJIT (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.RequestReJIT
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::RequestReJIT
helpviewer_keywords:
- RequestReJIT method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::RequestReJIT method [.NET Framework profiling]
ms.assetid: 781ed736-f30c-4816-920e-3552e36542c6
topic_type:
- apiref
ms.openlocfilehash: d2f8d538adb965864915fb1195bf9f2b8488aac8
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868413"
---
# <a name="icorprofilerinfo4requestrejit-method"></a><span data-ttu-id="6163e-102">ICorProfilerInfo4::RequestReJIT (Método)</span><span class="sxs-lookup"><span data-stu-id="6163e-102">ICorProfilerInfo4::RequestReJIT Method</span></span>
<span data-ttu-id="6163e-103">Solicita una recompilación con JIT de todas las instancias de las funciones especificadas.</span><span class="sxs-lookup"><span data-stu-id="6163e-103">Requests a JIT recompilation of all instances of the specified functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6163e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6163e-104">Syntax</span></span>  
  
```cpp  
HRESULT RequestReJIT (  
   [in] ULONG    cFunctions,  
   [in, size_is(cFunctions)]  ModuleID    moduleIds[],  
   [in, size_is(cFunctions)]  mdMethodDef methodIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6163e-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="6163e-105">Parameters</span></span>  
 `cFunctions`  
 <span data-ttu-id="6163e-106">[in] Número de funciones que se va a recompilar.</span><span class="sxs-lookup"><span data-stu-id="6163e-106">[in] The number of functions to recompile.</span></span>  
  
 `moduleIds`  
 <span data-ttu-id="6163e-107">[in] Especifica la parte `moduleId` de los pares (`module`, `methodDef`) que identifican las funciones que se van a recompilar.</span><span class="sxs-lookup"><span data-stu-id="6163e-107">[in] Specifies the `moduleId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>  
  
 `methodIds`  
 <span data-ttu-id="6163e-108">[in] Especifica la parte `methodId` de los pares (`module`, `methodDef`) que identifican las funciones que se van a recompilar.</span><span class="sxs-lookup"><span data-stu-id="6163e-108">[in] Specifies the `methodId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6163e-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6163e-109">Return Value</span></span>  
 <span data-ttu-id="6163e-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="6163e-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="6163e-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6163e-111">HRESULT</span></span>|<span data-ttu-id="6163e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6163e-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6163e-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="6163e-113">S_OK</span></span>|<span data-ttu-id="6163e-114">Se intentó marcar todos los métodos para la recompilación con JIT.</span><span class="sxs-lookup"><span data-stu-id="6163e-114">An attempt was made to mark all the methods for JIT recompilation.</span></span> <span data-ttu-id="6163e-115">El generador de perfiles debe implementar el método [ICorProfilerCallback4:: rejiterror (](icorprofilercallback4-rejiterror-method.md) para determinar qué métodos se marcaron correctamente para la recompilación JIT.</span><span class="sxs-lookup"><span data-stu-id="6163e-115">The profiler must implement the [ICorProfilerCallback4::ReJITError](icorprofilercallback4-rejiterror-method.md) method to determine which methods were successfully marked for JIT recompilation.</span></span>|  
|<span data-ttu-id="6163e-116">CORPROF_E_CALLBACK4_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="6163e-116">CORPROF_E_CALLBACK4_REQUIRED</span></span>|<span data-ttu-id="6163e-117">El generador de perfiles debe implementar la interfaz [ICorProfilerCallback4](icorprofilercallback4-interface.md) para que se admita esta llamada.</span><span class="sxs-lookup"><span data-stu-id="6163e-117">The profiler must implement the [ICorProfilerCallback4](icorprofilercallback4-interface.md) interface for this call to be supported.</span></span>|  
|<span data-ttu-id="6163e-118">CORPROF_E_REJIT_NOT_ENABLED</span><span class="sxs-lookup"><span data-stu-id="6163e-118">CORPROF_E_REJIT_NOT_ENABLED</span></span>|<span data-ttu-id="6163e-119">No se habilitó la recompilación con JIT.</span><span class="sxs-lookup"><span data-stu-id="6163e-119">JIT recompilation has not been enabled.</span></span> <span data-ttu-id="6163e-120">Debe habilitar la recompilación JIT durante la inicialización mediante el método [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) para establecer la marca de `COR_PRF_ENABLE_REJIT`.</span><span class="sxs-lookup"><span data-stu-id="6163e-120">You must enable JIT recompilation during initialization by using the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the `COR_PRF_ENABLE_REJIT` flag.</span></span>|  
|<span data-ttu-id="6163e-121">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="6163e-121">E_INVALIDARG</span></span>|<span data-ttu-id="6163e-122">`cFunctions` es 0, o `moduleIds` o `methodIds` es `NULL`.</span><span class="sxs-lookup"><span data-stu-id="6163e-122">`cFunctions` is 0, or `moduleIds` or `methodIds` is `NULL`.</span></span>|  
|||  
|<span data-ttu-id="6163e-123">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="6163e-123">E_OUTOFMEMORY</span></span>|<span data-ttu-id="6163e-124">El CLR no pudo completar la solicitud porque se quedó sin memoria.</span><span class="sxs-lookup"><span data-stu-id="6163e-124">The CLR was unable to complete the request because it ran out of memory.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6163e-125">Notas</span><span class="sxs-lookup"><span data-stu-id="6163e-125">Remarks</span></span>  
 <span data-ttu-id="6163e-126">Llame a `RequestReJIT` para que el tiempo de ejecución recompile un conjunto especificado de funciones.</span><span class="sxs-lookup"><span data-stu-id="6163e-126">Call `RequestReJIT` to have the runtime recompile a specified set of functions.</span></span> <span data-ttu-id="6163e-127">Un generador de perfiles de código puede utilizar la interfaz [ICorProfilerFunctionControl](icorprofilerfunctioncontrol-interface.md) para ajustar el código que se genera cuando se vuelven a compilar las funciones.</span><span class="sxs-lookup"><span data-stu-id="6163e-127">A code profiler can then use the [ICorProfilerFunctionControl](icorprofilerfunctioncontrol-interface.md) interface to adjust the code that is generated when the functions are recompiled.</span></span> <span data-ttu-id="6163e-128">Esto no afecta a las funciones actualmente en ejecución, solo a futuras llamadas a funciones.</span><span class="sxs-lookup"><span data-stu-id="6163e-128">This does not affect currently executing functions, only future function invocations.</span></span> <span data-ttu-id="6163e-129">Si alguna de las funciones especificadas ya se había recompilado con JIT, la solicitud de recompilación equivale a revertir y recompilar la función.</span><span class="sxs-lookup"><span data-stu-id="6163e-129">If any of the specified functions has previously been JIT-recompiled, requesting a recompilation is equivalent to reverting and recompiling the function.</span></span> <span data-ttu-id="6163e-130">Para conservar la reversibilidad, cuando el compilador JIT compila la versión original de una función, solo tiene en cuenta las versiones originales de los destinatarios para las decisiones de inserción.</span><span class="sxs-lookup"><span data-stu-id="6163e-130">To preserve reversibility, when the JIT compiler compiles the original version of a function, it considers only the original versions of its callees for inlining decisions.</span></span> <span data-ttu-id="6163e-131">Cuando el compilador JIT recompila una función, tiene en cuenta las versiones actuales (recompiladas u originales) de los destinatarios para la inserción.</span><span class="sxs-lookup"><span data-stu-id="6163e-131">When the JIT compiler recompiles a function, it considers the current versions (recompiled or original) of its callees for inlining.</span></span>  
  
 <span data-ttu-id="6163e-132">Normalmente, un generador de perfiles llama a `RequestReJIT` en respuesta a una entrada del usuario que solicita que el generador de perfiles instrumente uno o más métodos.</span><span class="sxs-lookup"><span data-stu-id="6163e-132">A profiler typically calls `RequestReJIT` in response to user input requesting that the profiler instrument one or more methods.</span></span> <span data-ttu-id="6163e-133">Normalmente, `RequestReJIT` suspende el tiempo de ejecución para realizar algunas de sus tareas y puede desencadenar una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="6163e-133">`RequestReJIT` typically suspends the runtime in order to do some of its work, and can potentially trigger a garbage collection.</span></span> <span data-ttu-id="6163e-134">Por lo tanto, el generador de perfiles debe llamar a `RequestReJIT` desde un subproceso creado anteriormente y no desde un subproceso creado por el CLR que está ejecutando actualmente una devolución de llamada del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="6163e-134">As such, the profiler should call `RequestReJIT` from a thread it previously created, and not from a CLR-created thread that is currently executing a profiler callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6163e-135">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="6163e-135">Requirements</span></span>  
 <span data-ttu-id="6163e-136">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6163e-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6163e-137">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6163e-137">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6163e-138">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6163e-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6163e-139">**.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6163e-139">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6163e-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="6163e-140">See also</span></span>

- [<span data-ttu-id="6163e-141">ICorProfilerInfo4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6163e-141">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="6163e-142">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="6163e-142">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="6163e-143">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="6163e-143">Profiling</span></span>](index.md)
