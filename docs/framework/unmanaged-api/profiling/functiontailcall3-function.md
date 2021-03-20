---
description: 'Más información acerca de: FunctionTailcall3 (función)'
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
ms.openlocfilehash: 4a67f218f0815ce6aff6ec4eda3d26ee2bf1fc3c
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759461"
---
# <a name="functiontailcall3-function"></a><span data-ttu-id="00a0b-103">FunctionTailcall3 (Función)</span><span class="sxs-lookup"><span data-stu-id="00a0b-103">FunctionTailcall3 Function</span></span>

<span data-ttu-id="00a0b-104">Notifica al generador de perfiles que la función que se está ejecutando actualmente está a punto de realizar una llamada de cola a otra función.</span><span class="sxs-lookup"><span data-stu-id="00a0b-104">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00a0b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="00a0b-105">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionTailcall3 (FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00a0b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="00a0b-106">Parameters</span></span>

<span data-ttu-id="00a0b-107">`functionOrRemappedID` de Identificador de la función que se ejecuta actualmente y que está a punto de realizar una llamada de cola.</span><span class="sxs-lookup"><span data-stu-id="00a0b-107">`functionOrRemappedID` [in] The identifier of the currently executing function that is about to make a tail call.</span></span>

## <a name="remarks"></a><span data-ttu-id="00a0b-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="00a0b-108">Remarks</span></span>  

 <span data-ttu-id="00a0b-109">La `FunctionTailcall3` función de devolución de llamada notifica al generador de perfiles cuando se llama a funciones.</span><span class="sxs-lookup"><span data-stu-id="00a0b-109">The `FunctionTailcall3` callback function notifies the profiler as functions are being called.</span></span> <span data-ttu-id="00a0b-110">Use el [método ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3 (](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) para registrar su implementación de esta función.</span><span class="sxs-lookup"><span data-stu-id="00a0b-110">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="00a0b-111">La `FunctionTailcall3` función es una devolución de llamada; debe implementarla.</span><span class="sxs-lookup"><span data-stu-id="00a0b-111">The `FunctionTailcall3` function is a callback; you must implement it.</span></span> <span data-ttu-id="00a0b-112">La implementación debe usar el `__declspec(naked)` atributo de clase de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="00a0b-112">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="00a0b-113">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="00a0b-113">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="00a0b-114">En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="00a0b-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="00a0b-115">Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="00a0b-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="00a0b-116">La implementación de `FunctionTailcall3` no debe bloquearse porque retrasará la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="00a0b-116">The implementation of `FunctionTailcall3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="00a0b-117">La implementación no debe intentar una recolección de elementos no utilizados, porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="00a0b-117">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="00a0b-118">Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que se `FunctionTailcall3` devuelva.</span><span class="sxs-lookup"><span data-stu-id="00a0b-118">If a garbage collection is attempted, the runtime will block until `FunctionTailcall3` returns.</span></span>  
  
 <span data-ttu-id="00a0b-119">La `FunctionTailcall3` función no debe llamar a código administrado ni producir una asignación de memoria administrada de ninguna manera.</span><span class="sxs-lookup"><span data-stu-id="00a0b-119">The `FunctionTailcall3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00a0b-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="00a0b-120">Requirements</span></span>  

 <span data-ttu-id="00a0b-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00a0b-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00a0b-122">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="00a0b-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="00a0b-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00a0b-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00a0b-124">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00a0b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00a0b-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="00a0b-125">See also</span></span>

- [<span data-ttu-id="00a0b-126">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="00a0b-126">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="00a0b-127">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="00a0b-127">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="00a0b-128">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="00a0b-128">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="00a0b-129">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="00a0b-129">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="00a0b-130">FunctionTailcall3WithInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="00a0b-130">FunctionTailcall3WithInfo Function</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="00a0b-131">Setenterleavefunctionhooks3 (</span><span class="sxs-lookup"><span data-stu-id="00a0b-131">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="00a0b-132">Setenterleavefunctionhooks3withinfo (</span><span class="sxs-lookup"><span data-stu-id="00a0b-132">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="00a0b-133">Setfunctionidmapper (</span><span class="sxs-lookup"><span data-stu-id="00a0b-133">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="00a0b-134">Setfunctionidmapper2 (</span><span class="sxs-lookup"><span data-stu-id="00a0b-134">SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="00a0b-135">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="00a0b-135">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
