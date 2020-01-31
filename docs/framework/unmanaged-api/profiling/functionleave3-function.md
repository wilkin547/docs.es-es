---
title: FunctionLeave3 (Función)
ms.date: 03/30/2017
api_name:
- FunctionLeave3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave3
helpviewer_keywords:
- FunctionLeave3 function [.NET Framework profiling]
ms.assetid: 5d798088-7992-48a0-ae55-d2a7ee31913f
topic_type:
- apiref
ms.openlocfilehash: 32d86f19e9c50694c7d113195e6967645b710666
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866874"
---
# <a name="functionleave3-function"></a><span data-ttu-id="59823-102">FunctionLeave3 (Función)</span><span class="sxs-lookup"><span data-stu-id="59823-102">FunctionLeave3 Function</span></span>
<span data-ttu-id="59823-103">Notifica al generador de perfiles que el control se devuelve desde una función.</span><span class="sxs-lookup"><span data-stu-id="59823-103">Notifies the profiler that control is being returned from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59823-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59823-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59823-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="59823-105">Parameters</span></span>  

- `functionOrRemappedID`

  <span data-ttu-id="59823-106">\[en] el identificador de la función de la que se devuelve el control.</span><span class="sxs-lookup"><span data-stu-id="59823-106">\[in] The identifier of the function from which control is returned.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="59823-107">Notas</span><span class="sxs-lookup"><span data-stu-id="59823-107">Remarks</span></span>  
 <span data-ttu-id="59823-108">La función de devolución de llamada `FunctionLeave3` notifica al generador de perfiles cuando se llama a las funciones, pero no admite la inspección del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="59823-108">The `FunctionLeave3` callback function notifies the profiler as functions are being called, but does not support return value inspection.</span></span> <span data-ttu-id="59823-109">Use el [método ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3 (](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) para registrar su implementación de esta función.</span><span class="sxs-lookup"><span data-stu-id="59823-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="59823-110">La función `FunctionLeave3` es una devolución de llamada; debe implementarla.</span><span class="sxs-lookup"><span data-stu-id="59823-110">The `FunctionLeave3` function is a callback; you must implement it.</span></span> <span data-ttu-id="59823-111">La implementación de debe utilizar el atributo de clase de almacenamiento `__declspec(naked)`.</span><span class="sxs-lookup"><span data-stu-id="59823-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="59823-112">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="59823-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="59823-113">En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="59823-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="59823-114">Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="59823-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="59823-115">La implementación de `FunctionLeave3` no debe bloquearse porque retrasará la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="59823-115">The implementation of `FunctionLeave3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="59823-116">La implementación no debe intentar una recolección de elementos no utilizados, porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="59823-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="59823-117">Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que `FunctionLeave3` devuelva.</span><span class="sxs-lookup"><span data-stu-id="59823-117">If a garbage collection is attempted, the runtime will block until `FunctionLeave3` returns.</span></span>  
  
 <span data-ttu-id="59823-118">La función `FunctionLeave3` no debe llamar a código administrado ni producir una asignación de memoria administrada de ninguna manera.</span><span class="sxs-lookup"><span data-stu-id="59823-118">The `FunctionLeave3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59823-119">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="59823-119">Requirements</span></span>  
 <span data-ttu-id="59823-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59823-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59823-121">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="59823-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="59823-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59823-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59823-123">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59823-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59823-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="59823-124">See also</span></span>

- [<span data-ttu-id="59823-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="59823-125">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="59823-126">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="59823-126">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="59823-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="59823-127">FunctionEnter3WithInfo</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="59823-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="59823-128">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="59823-129">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="59823-129">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="59823-130">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="59823-130">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="59823-131">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="59823-131">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="59823-132">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="59823-132">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="59823-133">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="59823-133">SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="59823-134">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="59823-134">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
