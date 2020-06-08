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
ms.openlocfilehash: 55955cd47bd32fb4294b0b8e852dd692702bd74f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500551"
---
# <a name="functiontailcall3-function"></a><span data-ttu-id="ebe57-102">FunctionTailcall3 (Función)</span><span class="sxs-lookup"><span data-stu-id="ebe57-102">FunctionTailcall3 Function</span></span>
<span data-ttu-id="ebe57-103">Notifica al generador de perfiles que la función que se está ejecutando actualmente está a punto de realizar una llamada de cola a otra función.</span><span class="sxs-lookup"><span data-stu-id="ebe57-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebe57-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ebe57-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionTailcall3 (FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebe57-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ebe57-105">Parameters</span></span>

- `functionOrRemappedID`

  <span data-ttu-id="ebe57-106">\[in] el identificador de la función que se ejecuta actualmente y que está a punto de realizar una llamada de cola.</span><span class="sxs-lookup"><span data-stu-id="ebe57-106">\[in] The identifier of the currently executing function that is about to make a tail call.</span></span>

## <a name="remarks"></a><span data-ttu-id="ebe57-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ebe57-107">Remarks</span></span>  
 <span data-ttu-id="ebe57-108">La `FunctionTailcall3` función de devolución de llamada notifica al generador de perfiles cuando se llama a funciones.</span><span class="sxs-lookup"><span data-stu-id="ebe57-108">The `FunctionTailcall3` callback function notifies the profiler as functions are being called.</span></span> <span data-ttu-id="ebe57-109">Use el [método ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3 (](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) para registrar su implementación de esta función.</span><span class="sxs-lookup"><span data-stu-id="ebe57-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="ebe57-110">La `FunctionTailcall3` función es una devolución de llamada; debe implementarla.</span><span class="sxs-lookup"><span data-stu-id="ebe57-110">The `FunctionTailcall3` function is a callback; you must implement it.</span></span> <span data-ttu-id="ebe57-111">La implementación debe usar el `__declspec(naked)` atributo de clase de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="ebe57-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="ebe57-112">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="ebe57-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="ebe57-113">En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="ebe57-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="ebe57-114">Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ebe57-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="ebe57-115">La implementación de `FunctionTailcall3` no debe bloquearse porque retrasará la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ebe57-115">The implementation of `FunctionTailcall3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="ebe57-116">La implementación no debe intentar una recolección de elementos no utilizados, porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ebe57-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="ebe57-117">Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que se `FunctionTailcall3` devuelva.</span><span class="sxs-lookup"><span data-stu-id="ebe57-117">If a garbage collection is attempted, the runtime will block until `FunctionTailcall3` returns.</span></span>  
  
 <span data-ttu-id="ebe57-118">La `FunctionTailcall3` función no debe llamar a código administrado ni producir una asignación de memoria administrada de ninguna manera.</span><span class="sxs-lookup"><span data-stu-id="ebe57-118">The `FunctionTailcall3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebe57-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ebe57-119">Requirements</span></span>  
 <span data-ttu-id="ebe57-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebe57-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebe57-121">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="ebe57-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="ebe57-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ebe57-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ebe57-123">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebe57-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebe57-124">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="ebe57-124">See also</span></span>

- [<span data-ttu-id="ebe57-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="ebe57-125">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="ebe57-126">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="ebe57-126">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="ebe57-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="ebe57-127">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="ebe57-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="ebe57-128">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="ebe57-129">FunctionTailcall3WithInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="ebe57-129">FunctionTailcall3WithInfo Function</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="ebe57-130">Setenterleavefunctionhooks3 (</span><span class="sxs-lookup"><span data-stu-id="ebe57-130">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="ebe57-131">Setenterleavefunctionhooks3withinfo (</span><span class="sxs-lookup"><span data-stu-id="ebe57-131">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="ebe57-132">Setfunctionidmapper (</span><span class="sxs-lookup"><span data-stu-id="ebe57-132">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="ebe57-133">Setfunctionidmapper2 (</span><span class="sxs-lookup"><span data-stu-id="ebe57-133">SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="ebe57-134">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="ebe57-134">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
