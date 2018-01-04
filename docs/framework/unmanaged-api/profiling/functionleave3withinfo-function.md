---
title: "FunctionLeave3WithInfo (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionLeave3WithInfo
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionLeave3WithInfo
helpviewer_keywords: FunctionLeave3WithInfo function [.NET Framework profiling]
ms.assetid: 5fa68a67-ced6-41c6-a2c0-467060fd0692
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f787b5bd78a575d862c198daeee99a0704734276
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="functionleave3withinfo-function"></a><span data-ttu-id="ee35c-102">FunctionLeave3WithInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="ee35c-102">FunctionLeave3WithInfo Function</span></span>
<span data-ttu-id="ee35c-103">Notifica al generador de perfiles que se devuelve de una función de control y proporciona un identificador que puede pasarse a la [ICorProfilerInfo3:: Getfunctionleave3info (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) para recuperar el marco de pila y el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="ee35c-103">Notifies the profiler that control is being returned from a function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionLeave3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) to retrieve the stack frame and the return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee35c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ee35c-104">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ee35c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ee35c-105">Parameters</span></span>  
 `functionIDOrClientID`  
 <span data-ttu-id="ee35c-106">[in] El identificador de la función desde la que se devuelve el control.</span><span class="sxs-lookup"><span data-stu-id="ee35c-106">[in] The identifier of the function from which control is returned.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="ee35c-107">[in] Controlador opaco que representa información sobre un marco de pila determinado.</span><span class="sxs-lookup"><span data-stu-id="ee35c-107">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="ee35c-108">Este identificador es válido solo durante la devolución de llamada a la que se pasa.</span><span class="sxs-lookup"><span data-stu-id="ee35c-108">This handle is valid only during the callback to which it is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee35c-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ee35c-109">Remarks</span></span>  
 <span data-ttu-id="ee35c-110">El `FunctionLeave3WithInfo` método de devolución de llamada notifica al generador de perfiles cuando se llaman a funciones y permite usar el generador de perfiles la [ICorProfilerInfo3:: Getfunctionleave3info (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) para inspeccionar el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="ee35c-110">The `FunctionLeave3WithInfo` callback method notifies the profiler as functions are called, and allows the profiler to use the [ICorProfilerInfo3::GetFunctionLeave3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) to inspect the return value.</span></span> <span data-ttu-id="ee35c-111">Para obtener acceso a información del valor devuelto, el `COR_PRF_ENABLE_FUNCTION_RETVAL` marca debe establecerse.</span><span class="sxs-lookup"><span data-stu-id="ee35c-111">To access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag has to be set.</span></span> <span data-ttu-id="ee35c-112">Puede usar el generador de perfiles la [ICorProfilerInfo:: SetEventMask (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) para establecer las marcas de evento y, a continuación, use la [ICorProfilerInfo3:: Setenterleavefunctionhooks3withinfo (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) para registrar su implementación de esta función.</span><span class="sxs-lookup"><span data-stu-id="ee35c-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="ee35c-113">El `FunctionLeave3WithInfo` función es una devolución de llamada; debe implementar.</span><span class="sxs-lookup"><span data-stu-id="ee35c-113">The `FunctionLeave3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="ee35c-114">La implementación debe utilizar el `__declspec(naked)` atributo de clase de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="ee35c-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="ee35c-115">El motor de ejecución no guardan los registros antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="ee35c-115">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="ee35c-116">En la entrada, debe guardar todos los registros que utilice, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="ee35c-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="ee35c-117">Al salir, debe restablecer la pila desactivando todos los parámetros que se han insertados por el llamador.</span><span class="sxs-lookup"><span data-stu-id="ee35c-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="ee35c-118">La implementación de `FunctionLeave3WithInfo` no debe bloquearse porque retrasará la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="ee35c-118">The implementation of `FunctionLeave3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="ee35c-119">La implementación no debería intentar una colección de elementos no utilizados, porque la pila no puede estar en un estado compatible con la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ee35c-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="ee35c-120">Si se intenta realizar una recolección, el tiempo de ejecución se bloqueará hasta que `FunctionLeave3WithInfo` devuelve.</span><span class="sxs-lookup"><span data-stu-id="ee35c-120">If a garbage collection is attempted, the runtime will block until `FunctionLeave3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="ee35c-121">El `FunctionLeave3WithInfo` función no debe llamar a código administrado o hacer que una asignación de memoria administrada de forma alguna.</span><span class="sxs-lookup"><span data-stu-id="ee35c-121">The `FunctionLeave3WithInfo` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee35c-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ee35c-122">Requirements</span></span>  
 <span data-ttu-id="ee35c-123">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee35c-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee35c-124">**Encabezado:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="ee35c-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="ee35c-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee35c-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee35c-126">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee35c-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee35c-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee35c-127">See Also</span></span>  
 [<span data-ttu-id="ee35c-128">GetFunctionLeave3Info</span><span class="sxs-lookup"><span data-stu-id="ee35c-128">GetFunctionLeave3Info</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md)  
 [<span data-ttu-id="ee35c-129">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="ee35c-129">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 [<span data-ttu-id="ee35c-130">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="ee35c-130">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 [<span data-ttu-id="ee35c-131">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="ee35c-131">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 [<span data-ttu-id="ee35c-132">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="ee35c-132">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [<span data-ttu-id="ee35c-133">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="ee35c-133">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [<span data-ttu-id="ee35c-134">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="ee35c-134">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)  
 [<span data-ttu-id="ee35c-135">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="ee35c-135">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)  
 [<span data-ttu-id="ee35c-136">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="ee35c-136">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
 [<span data-ttu-id="ee35c-137">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="ee35c-137">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)  
 [<span data-ttu-id="ee35c-138">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="ee35c-138">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
