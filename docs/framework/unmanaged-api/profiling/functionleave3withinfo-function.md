---
description: 'Más información acerca de: FunctionLeave3WithInfo (función)'
title: FunctionLeave3WithInfo (Función)
ms.date: 03/30/2017
api_name:
- FunctionLeave3WithInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave3WithInfo
helpviewer_keywords:
- FunctionLeave3WithInfo function [.NET Framework profiling]
ms.assetid: 5fa68a67-ced6-41c6-a2c0-467060fd0692
topic_type:
- apiref
ms.openlocfilehash: 6a861f455e827258368764b80547c3b3e9c986cd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687420"
---
# <a name="functionleave3withinfo-function"></a><span data-ttu-id="c46de-103">FunctionLeave3WithInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="c46de-103">FunctionLeave3WithInfo Function</span></span>

<span data-ttu-id="c46de-104">Notifica al generador de perfiles que el control se devuelve desde una función y proporciona un identificador que se puede pasar al [método ICorProfilerInfo3:: GetFunctionLeave3Info (](icorprofilerinfo3-getfunctionleave3info-method.md) para recuperar el marco de pila y el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="c46de-104">Notifies the profiler that control is being returned from a function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionLeave3Info method](icorprofilerinfo3-getfunctionleave3info-method.md) to retrieve the stack frame and the return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c46de-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c46de-105">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c46de-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c46de-106">Parameters</span></span>

- `functionIDOrClientID`

  <span data-ttu-id="c46de-107">\[in] identificador de la función de la que se devuelve el control.</span><span class="sxs-lookup"><span data-stu-id="c46de-107">\[in] The identifier of the function from which control is returned.</span></span>

- `eltInfo`

  <span data-ttu-id="c46de-108">\[in] un identificador opaco que representa información sobre un marco de pila determinado.</span><span class="sxs-lookup"><span data-stu-id="c46de-108">\[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="c46de-109">Este identificador es válido solo durante la devolución de llamada a la que se pasa.</span><span class="sxs-lookup"><span data-stu-id="c46de-109">This handle is valid only during the callback to which it is passed.</span></span>

## <a name="remarks"></a><span data-ttu-id="c46de-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c46de-110">Remarks</span></span>  

 <span data-ttu-id="c46de-111">El `FunctionLeave3WithInfo` método de devolución de llamada notifica al generador de perfiles cuando se llama a las funciones y permite que el generador de perfiles use el [método ICorProfilerInfo3:: GetFunctionLeave3Info (](icorprofilerinfo3-getfunctionleave3info-method.md) para inspeccionar el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="c46de-111">The `FunctionLeave3WithInfo` callback method notifies the profiler as functions are called, and allows the profiler to use the [ICorProfilerInfo3::GetFunctionLeave3Info method](icorprofilerinfo3-getfunctionleave3info-method.md) to inspect the return value.</span></span> <span data-ttu-id="c46de-112">Para tener acceso a la información del valor devuelto, se debe `COR_PRF_ENABLE_FUNCTION_RETVAL` establecer la marca.</span><span class="sxs-lookup"><span data-stu-id="c46de-112">To access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag has to be set.</span></span> <span data-ttu-id="c46de-113">El generador de perfiles puede utilizar el [método ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) para establecer las marcas de evento y, a continuación, usar el [método ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo (](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) para registrar la implementación de esta función.</span><span class="sxs-lookup"><span data-stu-id="c46de-113">The profiler can use the [ICorProfilerInfo::SetEventMask method](icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="c46de-114">La `FunctionLeave3WithInfo` función es una devolución de llamada; debe implementarla.</span><span class="sxs-lookup"><span data-stu-id="c46de-114">The `FunctionLeave3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="c46de-115">La implementación debe usar el `__declspec(naked)` atributo de clase de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="c46de-115">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="c46de-116">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="c46de-116">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="c46de-117">En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="c46de-117">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="c46de-118">Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="c46de-118">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="c46de-119">La implementación de `FunctionLeave3WithInfo` no debe bloquearse porque retrasará la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="c46de-119">The implementation of `FunctionLeave3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="c46de-120">La implementación no debe intentar una recolección de elementos no utilizados, porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="c46de-120">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="c46de-121">Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que se `FunctionLeave3WithInfo` devuelva.</span><span class="sxs-lookup"><span data-stu-id="c46de-121">If a garbage collection is attempted, the runtime will block until `FunctionLeave3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="c46de-122">La `FunctionLeave3WithInfo` función no debe llamar a código administrado ni producir una asignación de memoria administrada de ninguna manera.</span><span class="sxs-lookup"><span data-stu-id="c46de-122">The `FunctionLeave3WithInfo` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c46de-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c46de-123">Requirements</span></span>  

 <span data-ttu-id="c46de-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c46de-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c46de-125">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="c46de-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="c46de-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c46de-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c46de-127">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c46de-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c46de-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="c46de-128">See also</span></span>

- [<span data-ttu-id="c46de-129">Getfunctionleave3info (</span><span class="sxs-lookup"><span data-stu-id="c46de-129">GetFunctionLeave3Info</span></span>](icorprofilerinfo3-getfunctionleave3info-method.md)
- [<span data-ttu-id="c46de-130">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="c46de-130">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="c46de-131">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="c46de-131">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="c46de-132">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="c46de-132">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="c46de-133">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="c46de-133">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="c46de-134">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="c46de-134">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="c46de-135">Setenterleavefunctionhooks3 (</span><span class="sxs-lookup"><span data-stu-id="c46de-135">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="c46de-136">Setenterleavefunctionhooks3withinfo (</span><span class="sxs-lookup"><span data-stu-id="c46de-136">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="c46de-137">Setfunctionidmapper (</span><span class="sxs-lookup"><span data-stu-id="c46de-137">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="c46de-138">Setfunctionidmapper2 (</span><span class="sxs-lookup"><span data-stu-id="c46de-138">SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="c46de-139">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="c46de-139">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
