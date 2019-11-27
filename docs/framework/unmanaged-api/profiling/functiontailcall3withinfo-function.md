---
title: FunctionTailcall3WithInfo (Función)
ms.date: 03/30/2017
api_name:
- FunctionTailcall3WithInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall3WithInfo
helpviewer_keywords:
- FunctionTailcall3WithInfo function [.NET Framework profiling]
ms.assetid: 46380fcc-0198-43ae-a1f5-2d4939425886
topic_type:
- apiref
ms.openlocfilehash: 202aed64de78675c79f998afb4483e0d19b811de
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445960"
---
# <a name="functiontailcall3withinfo-function"></a><span data-ttu-id="138ba-102">FunctionTailcall3WithInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="138ba-102">FunctionTailcall3WithInfo Function</span></span>
<span data-ttu-id="138ba-103">Notifica al generador de perfiles que la función que se está ejecutando actualmente está a punto de realizar una llamada de cola a otra función y proporciona un identificador que se puede pasar al [método ICorProfilerInfo3:: GetFunctionTailcall3Info (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) para recuperar el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="138ba-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionTailcall3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) to retrieve the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="138ba-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="138ba-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionTailcall3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="138ba-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="138ba-105">Parameters</span></span>  
 `functionIDOrClientID`  
 <span data-ttu-id="138ba-106">de Identificador de la función que se ejecuta actualmente y que está a punto de realizar una llamada de cola.</span><span class="sxs-lookup"><span data-stu-id="138ba-106">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="138ba-107">[in] Controlador opaco que representa información sobre un marco de pila determinado.</span><span class="sxs-lookup"><span data-stu-id="138ba-107">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="138ba-108">Este identificador es válido solo durante la devolución de llamada a la que se pasa.</span><span class="sxs-lookup"><span data-stu-id="138ba-108">This handle is valid only during the callback to which it is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="138ba-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="138ba-109">Remarks</span></span>  
 <span data-ttu-id="138ba-110">El método de devolución de llamada `FunctionTailcall3WithInfo` notifica al generador de perfiles cuando se llama a las funciones y permite al generador de perfiles usar el [método ICorProfilerInfo3:: GetFunctionTailcall3Info (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) para inspeccionar el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="138ba-110">The `FunctionTailcall3WithInfo` callback method notifies the profiler as functions are called, and allows the profiler to use the [ICorProfilerInfo3::GetFunctionTailcall3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) to inspect the stack frame.</span></span> <span data-ttu-id="138ba-111">Para obtener acceso a la información del marco de pila, se debe establecer la marca `COR_PRF_ENABLE_FRAME_INFO`.</span><span class="sxs-lookup"><span data-stu-id="138ba-111">To access stack frame information, the `COR_PRF_ENABLE_FRAME_INFO` flag has to be set.</span></span> <span data-ttu-id="138ba-112">El generador de perfiles puede utilizar el [método ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) para establecer las marcas de evento y, a continuación, usar el [método ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) para registrar la implementación de esta función.</span><span class="sxs-lookup"><span data-stu-id="138ba-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="138ba-113">La función `FunctionTailcall3WithInfo` es una devolución de llamada; debe implementarla.</span><span class="sxs-lookup"><span data-stu-id="138ba-113">The `FunctionTailcall3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="138ba-114">La implementación de debe utilizar el atributo de clase de almacenamiento `__declspec(naked)`.</span><span class="sxs-lookup"><span data-stu-id="138ba-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="138ba-115">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="138ba-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="138ba-116">En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="138ba-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="138ba-117">Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="138ba-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="138ba-118">La implementación de `FunctionTailcall3WithInfo` no debe bloquearse porque retrasará la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="138ba-118">The implementation of `FunctionTailcall3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="138ba-119">La implementación no debe intentar una recolección de elementos no utilizados, porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="138ba-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="138ba-120">Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que `FunctionTailcall3WithInfo` devuelva.</span><span class="sxs-lookup"><span data-stu-id="138ba-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="138ba-121">Además, la función FunctionTailcall3WithInfo no debe llamar a código administrado ni producir una asignación de memoria administrada de ninguna manera.</span><span class="sxs-lookup"><span data-stu-id="138ba-121">Also, the FunctionTailcall3WithInfo function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="138ba-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="138ba-122">Requirements</span></span>  
 <span data-ttu-id="138ba-123">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="138ba-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="138ba-124">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="138ba-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="138ba-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="138ba-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="138ba-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="138ba-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="138ba-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="138ba-127">See also</span></span>

- [<span data-ttu-id="138ba-128">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="138ba-128">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="138ba-129">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="138ba-129">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="138ba-130">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="138ba-130">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="138ba-131">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="138ba-131">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="138ba-132">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="138ba-132">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="138ba-133">Setenterleavefunctionhooks3 (</span><span class="sxs-lookup"><span data-stu-id="138ba-133">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="138ba-134">Setenterleavefunctionhooks3withinfo (</span><span class="sxs-lookup"><span data-stu-id="138ba-134">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="138ba-135">Setfunctionidmapper (</span><span class="sxs-lookup"><span data-stu-id="138ba-135">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="138ba-136">Setfunctionidmapper2 (</span><span class="sxs-lookup"><span data-stu-id="138ba-136">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="138ba-137">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="138ba-137">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
