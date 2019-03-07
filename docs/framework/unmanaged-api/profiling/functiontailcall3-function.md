---
title: FunctionTailcall3 (Función)
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2204ee8adaf433152b203cbe93f8db9bb45de53c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498034"
---
# <a name="functiontailcall3-function"></a><span data-ttu-id="068d6-102">FunctionTailcall3 (Función)</span><span class="sxs-lookup"><span data-stu-id="068d6-102">FunctionTailcall3 Function</span></span>
<span data-ttu-id="068d6-103">Notifica al generador de perfiles que la función que se ejecuta actualmente está a punto de realizar una llamada de cola a otra función.</span><span class="sxs-lookup"><span data-stu-id="068d6-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="068d6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="068d6-104">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall3 (FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="068d6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="068d6-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="068d6-106">[in] El identificador de la función que se ejecuta actualmente que se va a llamar a una cola.</span><span class="sxs-lookup"><span data-stu-id="068d6-106">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="068d6-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="068d6-107">Remarks</span></span>  
 <span data-ttu-id="068d6-108">El `FunctionTailcall3` función de devolución de llamada notifica el generador de perfiles cuando se llama a funciones.</span><span class="sxs-lookup"><span data-stu-id="068d6-108">The `FunctionTailcall3` callback function notifies the profiler as functions are being called.</span></span> <span data-ttu-id="068d6-109">Use la [ICorProfilerInfo3:: Setenterleavefunctionhooks3 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) para registrar su implementación de esta función.</span><span class="sxs-lookup"><span data-stu-id="068d6-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="068d6-110">El `FunctionTailcall3` función es una devolución de llamada; debe implementar.</span><span class="sxs-lookup"><span data-stu-id="068d6-110">The `FunctionTailcall3` function is a callback; you must implement it.</span></span> <span data-ttu-id="068d6-111">La implementación debe usar el `__declspec(naked)` atributo de clase de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="068d6-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="068d6-112">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="068d6-112">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="068d6-113">En la entrada, debe guardar todos los registros que utilice, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="068d6-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="068d6-114">En la salida, debe restaurar la pila debe extraer todos los parámetros que se insertaron su llamador.</span><span class="sxs-lookup"><span data-stu-id="068d6-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="068d6-115">La implementación de `FunctionTailcall3` no debe bloquearse, porque ello retrasará la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="068d6-115">The implementation of `FunctionTailcall3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="068d6-116">La implementación no debe intentar una recolección de elementos, ya que la pila no puede estar en un estado compatible con la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="068d6-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="068d6-117">Si se intenta realizar una recolección, el tiempo de ejecución se bloqueará hasta que `FunctionTailcall3` devuelve.</span><span class="sxs-lookup"><span data-stu-id="068d6-117">If a garbage collection is attempted, the runtime will block until `FunctionTailcall3` returns.</span></span>  
  
 <span data-ttu-id="068d6-118">El `FunctionTailcall3` función no debe llamar al código administrado o provocar una asignación de memoria administrada de ninguna manera.</span><span class="sxs-lookup"><span data-stu-id="068d6-118">The `FunctionTailcall3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="068d6-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="068d6-119">Requirements</span></span>  
 <span data-ttu-id="068d6-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="068d6-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="068d6-121">**Encabezado**: CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="068d6-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="068d6-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="068d6-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="068d6-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="068d6-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="068d6-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="068d6-124">See also</span></span>
- [<span data-ttu-id="068d6-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="068d6-125">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="068d6-126">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="068d6-126">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="068d6-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="068d6-127">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="068d6-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="068d6-128">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="068d6-129">FunctionTailcall3WithInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="068d6-129">FunctionTailcall3WithInfo Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="068d6-130">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="068d6-130">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="068d6-131">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="068d6-131">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="068d6-132">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="068d6-132">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="068d6-133">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="068d6-133">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="068d6-134">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="068d6-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
