---
title: "FunctionTailcall3 (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- FunctionTailcall3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall3
helpviewer_keywords:
- FunctionTailcall3 function [.NET Framework profiling]
ms.assetid: 1e48243f-5de6-4bd6-a1d0-e1d248bca4b8
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f2ae13f25a1f99de4cf7dcb46dd33ed86682bf64
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="functiontailcall3-function"></a><span data-ttu-id="5244d-102">FunctionTailcall3 (Función)</span><span class="sxs-lookup"><span data-stu-id="5244d-102">FunctionTailcall3 Function</span></span>
<span data-ttu-id="5244d-103">Notifica al generador de perfiles que la función en ejecución está a punto de realizar una llamada de cola a otra función.</span><span class="sxs-lookup"><span data-stu-id="5244d-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5244d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5244d-104">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall3 (FunctionOrRemappedID functionOrRemappedID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5244d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5244d-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="5244d-106">[in] El identificador de la función en ejecución que se va a realizar una cola llamada.</span><span class="sxs-lookup"><span data-stu-id="5244d-106">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5244d-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5244d-107">Remarks</span></span>  
 <span data-ttu-id="5244d-108">El `FunctionTailcall3` función de devolución de llamada notifica al generador de perfiles cuando se llama a funciones.</span><span class="sxs-lookup"><span data-stu-id="5244d-108">The `FunctionTailcall3` callback function notifies the profiler as functions are being called.</span></span> <span data-ttu-id="5244d-109">Use la [ICorProfilerInfo3:: Setenterleavefunctionhooks3 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) para registrar su implementación de esta función.</span><span class="sxs-lookup"><span data-stu-id="5244d-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="5244d-110">El `FunctionTailcall3` función es una devolución de llamada; debe implementar.</span><span class="sxs-lookup"><span data-stu-id="5244d-110">The `FunctionTailcall3` function is a callback; you must implement it.</span></span> <span data-ttu-id="5244d-111">La implementación debe utilizar el `__declspec(naked)` atributo de clase de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="5244d-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="5244d-112">El motor de ejecución no guardan los registros antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="5244d-112">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="5244d-113">En la entrada, debe guardar todos los registros que utilice, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="5244d-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="5244d-114">Al salir, debe restablecer la pila desactivando todos los parámetros que se han insertados por el llamador.</span><span class="sxs-lookup"><span data-stu-id="5244d-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="5244d-115">La implementación de `FunctionTailcall3` no debe bloquearse porque retrasará la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="5244d-115">The implementation of `FunctionTailcall3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="5244d-116">La implementación no debería intentar una colección de elementos no utilizados, porque la pila no puede estar en un estado compatible con la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="5244d-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="5244d-117">Si se intenta realizar una recolección, el tiempo de ejecución se bloqueará hasta que `FunctionTailcall3` devuelve.</span><span class="sxs-lookup"><span data-stu-id="5244d-117">If a garbage collection is attempted, the runtime will block until `FunctionTailcall3` returns.</span></span>  
  
 <span data-ttu-id="5244d-118">El `FunctionTailcall3` función no debe llamar a código administrado o hacer que una asignación de memoria administrada de forma alguna.</span><span class="sxs-lookup"><span data-stu-id="5244d-118">The `FunctionTailcall3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5244d-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5244d-119">Requirements</span></span>  
 <span data-ttu-id="5244d-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5244d-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5244d-121">**Encabezado:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="5244d-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="5244d-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5244d-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5244d-123">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5244d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5244d-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="5244d-124">See Also</span></span>  
 [<span data-ttu-id="5244d-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="5244d-125">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 [<span data-ttu-id="5244d-126">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="5244d-126">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 [<span data-ttu-id="5244d-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="5244d-127">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [<span data-ttu-id="5244d-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="5244d-128">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [<span data-ttu-id="5244d-129">FunctionTailcall3WithInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="5244d-129">FunctionTailcall3WithInfo Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [<span data-ttu-id="5244d-130">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="5244d-130">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)  
 [<span data-ttu-id="5244d-131">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="5244d-131">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)  
 [<span data-ttu-id="5244d-132">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="5244d-132">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
 [<span data-ttu-id="5244d-133">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="5244d-133">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)  
 [<span data-ttu-id="5244d-134">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="5244d-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
