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
ms.openlocfilehash: 104a6c3c42c310513040cb45db7f51ffe729c19d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427439"
---
# <a name="functionleave3-function"></a><span data-ttu-id="d4702-102">FunctionLeave3 (Función)</span><span class="sxs-lookup"><span data-stu-id="d4702-102">FunctionLeave3 Function</span></span>
<span data-ttu-id="d4702-103">Notifica al generador de perfiles que el control se devuelve desde una función.</span><span class="sxs-lookup"><span data-stu-id="d4702-103">Notifies the profiler that control is being returned from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4702-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d4702-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4702-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d4702-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="d4702-106">de Identificador de la función de la que se devuelve el control.</span><span class="sxs-lookup"><span data-stu-id="d4702-106">[in] The identifier of the function from which control is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4702-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d4702-107">Remarks</span></span>  
 <span data-ttu-id="d4702-108">La función de devolución de llamada `FunctionLeave3` notifica al generador de perfiles cuando se llama a las funciones, pero no admite la inspección del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="d4702-108">The `FunctionLeave3` callback function notifies the profiler as functions are being called, but does not support return value inspection.</span></span> <span data-ttu-id="d4702-109">Use el [método ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3 (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) para registrar su implementación de esta función.</span><span class="sxs-lookup"><span data-stu-id="d4702-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="d4702-110">La función `FunctionLeave3` es una devolución de llamada; debe implementarla.</span><span class="sxs-lookup"><span data-stu-id="d4702-110">The `FunctionLeave3` function is a callback; you must implement it.</span></span> <span data-ttu-id="d4702-111">La implementación de debe utilizar el atributo de clase de almacenamiento `__declspec(naked)`.</span><span class="sxs-lookup"><span data-stu-id="d4702-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="d4702-112">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="d4702-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="d4702-113">En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="d4702-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="d4702-114">Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d4702-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="d4702-115">La implementación de `FunctionLeave3` no debe bloquearse porque retrasará la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="d4702-115">The implementation of `FunctionLeave3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="d4702-116">La implementación no debe intentar una recolección de elementos no utilizados, porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="d4702-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="d4702-117">Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que `FunctionLeave3` devuelva.</span><span class="sxs-lookup"><span data-stu-id="d4702-117">If a garbage collection is attempted, the runtime will block until `FunctionLeave3` returns.</span></span>  
  
 <span data-ttu-id="d4702-118">La función `FunctionLeave3` no debe llamar a código administrado ni producir una asignación de memoria administrada de ninguna manera.</span><span class="sxs-lookup"><span data-stu-id="d4702-118">The `FunctionLeave3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4702-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d4702-119">Requirements</span></span>  
 <span data-ttu-id="d4702-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4702-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4702-121">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="d4702-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="d4702-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4702-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4702-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4702-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4702-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4702-124">See also</span></span>

- [<span data-ttu-id="d4702-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="d4702-125">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="d4702-126">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="d4702-126">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="d4702-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="d4702-127">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="d4702-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="d4702-128">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="d4702-129">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="d4702-129">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="d4702-130">Setenterleavefunctionhooks3 (</span><span class="sxs-lookup"><span data-stu-id="d4702-130">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="d4702-131">Setenterleavefunctionhooks3withinfo (</span><span class="sxs-lookup"><span data-stu-id="d4702-131">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="d4702-132">Setfunctionidmapper (</span><span class="sxs-lookup"><span data-stu-id="d4702-132">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="d4702-133">Setfunctionidmapper2 (</span><span class="sxs-lookup"><span data-stu-id="d4702-133">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="d4702-134">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="d4702-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
