---
description: 'Más información sobre: ICorProfilerInfo4:: Requestrejit ((método)'
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
ms.openlocfilehash: 2da65c2db5722f689f1a8588169ea099aff71be6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799023"
---
# <a name="icorprofilerinfo4requestrejit-method"></a><span data-ttu-id="d82c2-103">ICorProfilerInfo4::RequestReJIT (Método)</span><span class="sxs-lookup"><span data-stu-id="d82c2-103">ICorProfilerInfo4::RequestReJIT Method</span></span>

<span data-ttu-id="d82c2-104">Solicita una recompilación con JIT de todas las instancias de las funciones especificadas.</span><span class="sxs-lookup"><span data-stu-id="d82c2-104">Requests a JIT recompilation of all instances of the specified functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d82c2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d82c2-105">Syntax</span></span>  
  
```cpp  
HRESULT RequestReJIT (  
   [in] ULONG    cFunctions,  
   [in, size_is(cFunctions)]  ModuleID    moduleIds[],  
   [in, size_is(cFunctions)]  mdMethodDef methodIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d82c2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d82c2-106">Parameters</span></span>  

 `cFunctions`  
 <span data-ttu-id="d82c2-107">[in] Número de funciones que se va a recompilar.</span><span class="sxs-lookup"><span data-stu-id="d82c2-107">[in] The number of functions to recompile.</span></span>  
  
 `moduleIds`  
 <span data-ttu-id="d82c2-108">[in] Especifica la parte `moduleId` de los pares (`module`, `methodDef`) que identifican las funciones que se van a recompilar.</span><span class="sxs-lookup"><span data-stu-id="d82c2-108">[in] Specifies the `moduleId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>  
  
 `methodIds`  
 <span data-ttu-id="d82c2-109">[in] Especifica la parte `methodId` de los pares (`module`, `methodDef`) que identifican las funciones que se van a recompilar.</span><span class="sxs-lookup"><span data-stu-id="d82c2-109">[in] Specifies the `methodId` portion of the (`module`, `methodDef`) pairs that identify the functions to be recompiled.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d82c2-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d82c2-110">Return Value</span></span>  

 <span data-ttu-id="d82c2-111">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="d82c2-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d82c2-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d82c2-112">HRESULT</span></span>|<span data-ttu-id="d82c2-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="d82c2-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d82c2-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="d82c2-114">S_OK</span></span>|<span data-ttu-id="d82c2-115">Se intentó marcar todos los métodos para la recompilación con JIT.</span><span class="sxs-lookup"><span data-stu-id="d82c2-115">An attempt was made to mark all the methods for JIT recompilation.</span></span> <span data-ttu-id="d82c2-116">El generador de perfiles debe implementar el método [ICorProfilerCallback4:: rejiterror (](icorprofilercallback4-rejiterror-method.md) para determinar qué métodos se marcaron correctamente para la recompilación JIT.</span><span class="sxs-lookup"><span data-stu-id="d82c2-116">The profiler must implement the [ICorProfilerCallback4::ReJITError](icorprofilercallback4-rejiterror-method.md) method to determine which methods were successfully marked for JIT recompilation.</span></span>|  
|<span data-ttu-id="d82c2-117">CORPROF_E_CALLBACK4_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="d82c2-117">CORPROF_E_CALLBACK4_REQUIRED</span></span>|<span data-ttu-id="d82c2-118">El generador de perfiles debe implementar la interfaz [ICorProfilerCallback4](icorprofilercallback4-interface.md) para que se admita esta llamada.</span><span class="sxs-lookup"><span data-stu-id="d82c2-118">The profiler must implement the [ICorProfilerCallback4](icorprofilercallback4-interface.md) interface for this call to be supported.</span></span>|  
|<span data-ttu-id="d82c2-119">CORPROF_E_REJIT_NOT_ENABLED</span><span class="sxs-lookup"><span data-stu-id="d82c2-119">CORPROF_E_REJIT_NOT_ENABLED</span></span>|<span data-ttu-id="d82c2-120">No se habilitó la recompilación con JIT.</span><span class="sxs-lookup"><span data-stu-id="d82c2-120">JIT recompilation has not been enabled.</span></span> <span data-ttu-id="d82c2-121">Debe habilitar la recompilación JIT durante la inicialización mediante el método [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) para establecer la `COR_PRF_ENABLE_REJIT` marca.</span><span class="sxs-lookup"><span data-stu-id="d82c2-121">You must enable JIT recompilation during initialization by using the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the `COR_PRF_ENABLE_REJIT` flag.</span></span>|  
|<span data-ttu-id="d82c2-122">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d82c2-122">E_INVALIDARG</span></span>|<span data-ttu-id="d82c2-123">`cFunctions` es 0, o `moduleIds` o `methodIds` es `NULL`.</span><span class="sxs-lookup"><span data-stu-id="d82c2-123">`cFunctions` is 0, or `moduleIds` or `methodIds` is `NULL`.</span></span>|  
|||  
|<span data-ttu-id="d82c2-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d82c2-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="d82c2-125">El CLR no pudo completar la solicitud porque se quedó sin memoria.</span><span class="sxs-lookup"><span data-stu-id="d82c2-125">The CLR was unable to complete the request because it ran out of memory.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d82c2-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d82c2-126">Remarks</span></span>  

 <span data-ttu-id="d82c2-127">Llame a `RequestReJIT` para que el tiempo de ejecución recompile un conjunto especificado de funciones.</span><span class="sxs-lookup"><span data-stu-id="d82c2-127">Call `RequestReJIT` to have the runtime recompile a specified set of functions.</span></span> <span data-ttu-id="d82c2-128">Un generador de perfiles de código puede utilizar la interfaz [ICorProfilerFunctionControl](icorprofilerfunctioncontrol-interface.md) para ajustar el código que se genera cuando se vuelven a compilar las funciones.</span><span class="sxs-lookup"><span data-stu-id="d82c2-128">A code profiler can then use the [ICorProfilerFunctionControl](icorprofilerfunctioncontrol-interface.md) interface to adjust the code that is generated when the functions are recompiled.</span></span> <span data-ttu-id="d82c2-129">Esto no afecta a las funciones actualmente en ejecución, solo a futuras llamadas a funciones.</span><span class="sxs-lookup"><span data-stu-id="d82c2-129">This does not affect currently executing functions, only future function invocations.</span></span> <span data-ttu-id="d82c2-130">Si alguna de las funciones especificadas ya se había recompilado con JIT, la solicitud de recompilación equivale a revertir y recompilar la función.</span><span class="sxs-lookup"><span data-stu-id="d82c2-130">If any of the specified functions has previously been JIT-recompiled, requesting a recompilation is equivalent to reverting and recompiling the function.</span></span> <span data-ttu-id="d82c2-131">Para conservar la reversibilidad, cuando el compilador JIT compila la versión original de una función, solo tiene en cuenta las versiones originales de los destinatarios para las decisiones de inserción.</span><span class="sxs-lookup"><span data-stu-id="d82c2-131">To preserve reversibility, when the JIT compiler compiles the original version of a function, it considers only the original versions of its callees for inlining decisions.</span></span> <span data-ttu-id="d82c2-132">Cuando el compilador JIT recompila una función, tiene en cuenta las versiones actuales (recompiladas u originales) de los destinatarios para la inserción.</span><span class="sxs-lookup"><span data-stu-id="d82c2-132">When the JIT compiler recompiles a function, it considers the current versions (recompiled or original) of its callees for inlining.</span></span>  
  
 <span data-ttu-id="d82c2-133">Normalmente, un generador de perfiles llama a `RequestReJIT` en respuesta a una entrada del usuario que solicita que el generador de perfiles instrumente uno o más métodos.</span><span class="sxs-lookup"><span data-stu-id="d82c2-133">A profiler typically calls `RequestReJIT` in response to user input requesting that the profiler instrument one or more methods.</span></span> <span data-ttu-id="d82c2-134">Normalmente, `RequestReJIT` suspende el tiempo de ejecución para realizar algunas de sus tareas y puede desencadenar una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="d82c2-134">`RequestReJIT` typically suspends the runtime in order to do some of its work, and can potentially trigger a garbage collection.</span></span> <span data-ttu-id="d82c2-135">Por lo tanto, el generador de perfiles debe llamar a `RequestReJIT` desde un subproceso creado anteriormente y no desde un subproceso creado por el CLR que está ejecutando actualmente una devolución de llamada del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="d82c2-135">As such, the profiler should call `RequestReJIT` from a thread it previously created, and not from a CLR-created thread that is currently executing a profiler callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d82c2-136">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d82c2-136">Requirements</span></span>  

 <span data-ttu-id="d82c2-137">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d82c2-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d82c2-138">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d82c2-138">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d82c2-139">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d82c2-139">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d82c2-140">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d82c2-140">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d82c2-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="d82c2-141">See also</span></span>

- [<span data-ttu-id="d82c2-142">ICorProfilerInfo4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d82c2-142">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="d82c2-143">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="d82c2-143">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="d82c2-144">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="d82c2-144">Profiling</span></span>](index.md)
