---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ce1f5a707cd739ec3b3e8384be2c70843748c8a4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586713"
---
# <a name="functionleave3withinfo-function"></a><span data-ttu-id="e967b-102">FunctionLeave3WithInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="e967b-102">FunctionLeave3WithInfo Function</span></span>
<span data-ttu-id="e967b-103">Notifica al generador de perfiles que se devuelve desde una función de control y proporciona un identificador que puede pasarse a la [método ICorProfilerInfo3:: Getfunctionleave3info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) para recuperar el marco de pila y el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="e967b-103">Notifies the profiler that control is being returned from a function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionLeave3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) to retrieve the stack frame and the return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e967b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e967b-104">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e967b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e967b-105">Parameters</span></span>  
 `functionIDOrClientID`  
 <span data-ttu-id="e967b-106">[in] El identificador de la función desde el que se devuelve el control.</span><span class="sxs-lookup"><span data-stu-id="e967b-106">[in] The identifier of the function from which control is returned.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="e967b-107">[in] Controlador opaco que representa información sobre un marco de pila determinado.</span><span class="sxs-lookup"><span data-stu-id="e967b-107">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="e967b-108">Este identificador es válido solo durante la devolución de llamada a la que se pasa.</span><span class="sxs-lookup"><span data-stu-id="e967b-108">This handle is valid only during the callback to which it is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e967b-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e967b-109">Remarks</span></span>  
 <span data-ttu-id="e967b-110">El `FunctionLeave3WithInfo` método de devolución de llamada notifica el generador de perfiles cuando se llama a las funciones y permite usar el generador de perfiles la [método ICorProfilerInfo3:: Getfunctionleave3info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) para inspeccionar el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="e967b-110">The `FunctionLeave3WithInfo` callback method notifies the profiler as functions are called, and allows the profiler to use the [ICorProfilerInfo3::GetFunctionLeave3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) to inspect the return value.</span></span> <span data-ttu-id="e967b-111">Para obtener acceso a información del valor devuelto, el `COR_PRF_ENABLE_FUNCTION_RETVAL` marca se ha establecido.</span><span class="sxs-lookup"><span data-stu-id="e967b-111">To access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag has to be set.</span></span> <span data-ttu-id="e967b-112">El generador de perfiles puede utilizar el [SetEventMask (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) para establecer las marcas de evento y, a continuación, utilice el [ICorProfilerInfo3:: Setenterleavefunctionhooks3withinfo (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) para registrar su implementación de esta función.</span><span class="sxs-lookup"><span data-stu-id="e967b-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="e967b-113">El `FunctionLeave3WithInfo` función es una devolución de llamada; debe implementar.</span><span class="sxs-lookup"><span data-stu-id="e967b-113">The `FunctionLeave3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="e967b-114">La implementación debe usar el `__declspec(naked)` atributo de clase de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="e967b-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="e967b-115">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="e967b-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="e967b-116">En la entrada, debe guardar todos los registros que utilice, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="e967b-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="e967b-117">En la salida, debe restaurar la pila debe extraer todos los parámetros que se insertaron su llamador.</span><span class="sxs-lookup"><span data-stu-id="e967b-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="e967b-118">La implementación de `FunctionLeave3WithInfo` no debe bloquearse, porque ello retrasará la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="e967b-118">The implementation of `FunctionLeave3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="e967b-119">La implementación no debe intentar una recolección de elementos, ya que la pila no puede estar en un estado compatible con la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="e967b-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="e967b-120">Si se intenta realizar una recolección, el tiempo de ejecución se bloqueará hasta que `FunctionLeave3WithInfo` devuelve.</span><span class="sxs-lookup"><span data-stu-id="e967b-120">If a garbage collection is attempted, the runtime will block until `FunctionLeave3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="e967b-121">El `FunctionLeave3WithInfo` función no debe llamar al código administrado o provocar una asignación de memoria administrada de ninguna manera.</span><span class="sxs-lookup"><span data-stu-id="e967b-121">The `FunctionLeave3WithInfo` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e967b-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e967b-122">Requirements</span></span>  
 <span data-ttu-id="e967b-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e967b-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e967b-124">**Encabezado**: CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="e967b-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="e967b-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e967b-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e967b-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e967b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e967b-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="e967b-127">See also</span></span>

- [<span data-ttu-id="e967b-128">GetFunctionLeave3Info</span><span class="sxs-lookup"><span data-stu-id="e967b-128">GetFunctionLeave3Info</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md)
- [<span data-ttu-id="e967b-129">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="e967b-129">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="e967b-130">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="e967b-130">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="e967b-131">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="e967b-131">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="e967b-132">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e967b-132">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="e967b-133">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e967b-133">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="e967b-134">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="e967b-134">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="e967b-135">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e967b-135">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="e967b-136">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="e967b-136">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="e967b-137">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="e967b-137">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="e967b-138">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e967b-138">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
