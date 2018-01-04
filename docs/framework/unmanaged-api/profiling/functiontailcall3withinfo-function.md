---
title: "FunctionTailcall3WithInfo (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionTailcall3WithInfo
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionTailcall3WithInfo
helpviewer_keywords: FunctionTailcall3WithInfo function [.NET Framework profiling]
ms.assetid: 46380fcc-0198-43ae-a1f5-2d4939425886
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4bd2bb56724f977d93e6ebff7d2c4c855a5a222b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="functiontailcall3withinfo-function"></a><span data-ttu-id="0be98-102">FunctionTailcall3WithInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="0be98-102">FunctionTailcall3WithInfo Function</span></span>
<span data-ttu-id="0be98-103">Notifica al generador de perfiles que la función en ejecución está a punto de realizar una llamada de cola a otra función y proporciona un identificador que puede pasarse a la [ICorProfilerInfo3:: Getfunctiontailcall3info (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) para recuperar el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="0be98-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionTailcall3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) to retrieve the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0be98-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0be98-104">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0be98-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0be98-105">Parameters</span></span>  
 `functionIDOrClientID`  
 <span data-ttu-id="0be98-106">[in] El identificador de la función en ejecución que se va a realizar una cola llamada.</span><span class="sxs-lookup"><span data-stu-id="0be98-106">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="0be98-107">[in] Controlador opaco que representa información sobre un marco de pila determinado.</span><span class="sxs-lookup"><span data-stu-id="0be98-107">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="0be98-108">Este identificador es válido solo durante la devolución de llamada a la que se pasa.</span><span class="sxs-lookup"><span data-stu-id="0be98-108">This handle is valid only during the callback to which it is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0be98-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0be98-109">Remarks</span></span>  
 <span data-ttu-id="0be98-110">El `FunctionTailcall3WithInfo` método de devolución de llamada notifica al generador de perfiles cuando se llaman a funciones y permite usar el generador de perfiles la [ICorProfilerInfo3:: Getfunctiontailcall3info (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) para inspeccionar el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="0be98-110">The `FunctionTailcall3WithInfo` callback method notifies the profiler as functions are called, and allows the profiler to use the [ICorProfilerInfo3::GetFunctionTailcall3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) to inspect the stack frame.</span></span> <span data-ttu-id="0be98-111">Para obtener acceso a información del marco de pila, el `COR_PRF_ENABLE_FRAME_INFO` marca debe establecerse.</span><span class="sxs-lookup"><span data-stu-id="0be98-111">To access stack frame information, the `COR_PRF_ENABLE_FRAME_INFO` flag has to be set.</span></span> <span data-ttu-id="0be98-112">Puede usar el generador de perfiles la [ICorProfilerInfo:: SetEventMask (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) para establecer las marcas de evento y, a continuación, use la [ICorProfilerInfo3:: Setenterleavefunctionhooks3withinfo (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) para registrar su implementación de esta función.</span><span class="sxs-lookup"><span data-stu-id="0be98-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="0be98-113">El `FunctionTailcall3WithInfo` función es una devolución de llamada; debe implementar.</span><span class="sxs-lookup"><span data-stu-id="0be98-113">The `FunctionTailcall3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="0be98-114">La implementación debe utilizar el `__declspec(naked)` atributo de clase de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="0be98-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="0be98-115">El motor de ejecución no guardan los registros antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="0be98-115">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="0be98-116">En la entrada, debe guardar todos los registros que utilice, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="0be98-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="0be98-117">Al salir, debe restablecer la pila desactivando todos los parámetros que se han insertados por el llamador.</span><span class="sxs-lookup"><span data-stu-id="0be98-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="0be98-118">La implementación de `FunctionTailcall3WithInfo` no debe bloquearse porque retrasará la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="0be98-118">The implementation of `FunctionTailcall3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="0be98-119">La implementación no debería intentar una colección de elementos no utilizados, porque la pila no puede estar en un estado compatible con la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="0be98-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="0be98-120">Si se intenta realizar una recolección, el tiempo de ejecución se bloqueará hasta que `FunctionTailcall3WithInfo` devuelve.</span><span class="sxs-lookup"><span data-stu-id="0be98-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="0be98-121">Además, la función FunctionTailcall3WithInfo no debe llamar al código administrado o hacer que una asignación de memoria administrada de ninguna manera.</span><span class="sxs-lookup"><span data-stu-id="0be98-121">Also, the FunctionTailcall3WithInfo function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0be98-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0be98-122">Requirements</span></span>  
 <span data-ttu-id="0be98-123">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0be98-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0be98-124">**Encabezado:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="0be98-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="0be98-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0be98-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0be98-126">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0be98-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0be98-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="0be98-127">See Also</span></span>  
 [<span data-ttu-id="0be98-128">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="0be98-128">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 [<span data-ttu-id="0be98-129">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="0be98-129">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 [<span data-ttu-id="0be98-130">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="0be98-130">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 [<span data-ttu-id="0be98-131">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="0be98-131">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 [<span data-ttu-id="0be98-132">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="0be98-132">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [<span data-ttu-id="0be98-133">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="0be98-133">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)  
 [<span data-ttu-id="0be98-134">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="0be98-134">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)  
 [<span data-ttu-id="0be98-135">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="0be98-135">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
 [<span data-ttu-id="0be98-136">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="0be98-136">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)  
 [<span data-ttu-id="0be98-137">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="0be98-137">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
