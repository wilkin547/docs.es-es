---
description: 'Más información acerca de: FunctionLeave3 (función)'
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
ms.openlocfilehash: 9da68ffa2c54ada1437b3bef8bd6324c0791d610
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687459"
---
# <a name="functionleave3-function"></a><span data-ttu-id="f0050-103">FunctionLeave3 (Función)</span><span class="sxs-lookup"><span data-stu-id="f0050-103">FunctionLeave3 Function</span></span>

<span data-ttu-id="f0050-104">Notifica al generador de perfiles que el control se devuelve desde una función.</span><span class="sxs-lookup"><span data-stu-id="f0050-104">Notifies the profiler that control is being returned from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0050-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f0050-105">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0050-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f0050-106">Parameters</span></span>  

- `functionOrRemappedID`

  <span data-ttu-id="f0050-107">\[in] identificador de la función de la que se devuelve el control.</span><span class="sxs-lookup"><span data-stu-id="f0050-107">\[in] The identifier of the function from which control is returned.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="f0050-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f0050-108">Remarks</span></span>  

 <span data-ttu-id="f0050-109">La `FunctionLeave3` función de devolución de llamada notifica al generador de perfiles cuando se llama a las funciones, pero no admite la inspección del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="f0050-109">The `FunctionLeave3` callback function notifies the profiler as functions are being called, but does not support return value inspection.</span></span> <span data-ttu-id="f0050-110">Use el [método ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3 (](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) para registrar su implementación de esta función.</span><span class="sxs-lookup"><span data-stu-id="f0050-110">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="f0050-111">La `FunctionLeave3` función es una devolución de llamada; debe implementarla.</span><span class="sxs-lookup"><span data-stu-id="f0050-111">The `FunctionLeave3` function is a callback; you must implement it.</span></span> <span data-ttu-id="f0050-112">La implementación debe usar el `__declspec(naked)` atributo de clase de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="f0050-112">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="f0050-113">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="f0050-113">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="f0050-114">En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="f0050-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="f0050-115">Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f0050-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="f0050-116">La implementación de `FunctionLeave3` no debe bloquearse porque retrasará la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="f0050-116">The implementation of `FunctionLeave3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="f0050-117">La implementación no debe intentar una recolección de elementos no utilizados, porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="f0050-117">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="f0050-118">Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que se `FunctionLeave3` devuelva.</span><span class="sxs-lookup"><span data-stu-id="f0050-118">If a garbage collection is attempted, the runtime will block until `FunctionLeave3` returns.</span></span>  
  
 <span data-ttu-id="f0050-119">La `FunctionLeave3` función no debe llamar a código administrado ni producir una asignación de memoria administrada de ninguna manera.</span><span class="sxs-lookup"><span data-stu-id="f0050-119">The `FunctionLeave3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0050-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f0050-120">Requirements</span></span>  

 <span data-ttu-id="f0050-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0050-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0050-122">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="f0050-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="f0050-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0050-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0050-124">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0050-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0050-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0050-125">See also</span></span>

- [<span data-ttu-id="f0050-126">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="f0050-126">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="f0050-127">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="f0050-127">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="f0050-128">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="f0050-128">FunctionEnter3WithInfo</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="f0050-129">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="f0050-129">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="f0050-130">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="f0050-130">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="f0050-131">Setenterleavefunctionhooks3 (</span><span class="sxs-lookup"><span data-stu-id="f0050-131">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="f0050-132">Setenterleavefunctionhooks3withinfo (</span><span class="sxs-lookup"><span data-stu-id="f0050-132">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="f0050-133">Setfunctionidmapper (</span><span class="sxs-lookup"><span data-stu-id="f0050-133">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="f0050-134">Setfunctionidmapper2 (</span><span class="sxs-lookup"><span data-stu-id="f0050-134">SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="f0050-135">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="f0050-135">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
