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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b31c3045b021bd3b00d2b2e42bf7a118110305b1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59099894"
---
# <a name="functionleave3-function"></a><span data-ttu-id="aef00-102">FunctionLeave3 (Función)</span><span class="sxs-lookup"><span data-stu-id="aef00-102">FunctionLeave3 Function</span></span>
<span data-ttu-id="aef00-103">Notifica al generador de perfiles que se devuelve desde una función de control.</span><span class="sxs-lookup"><span data-stu-id="aef00-103">Notifies the profiler that control is being returned from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aef00-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aef00-104">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aef00-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aef00-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="aef00-106">[in] El identificador de la función desde el que se devuelve el control.</span><span class="sxs-lookup"><span data-stu-id="aef00-106">[in] The identifier of the function from which control is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aef00-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aef00-107">Remarks</span></span>  
 <span data-ttu-id="aef00-108">El `FunctionLeave3` función de devolución de llamada notifica el generador de perfiles cuando se llama a funciones, pero no es compatible con la inspección del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="aef00-108">The `FunctionLeave3` callback function notifies the profiler as functions are being called, but does not support return value inspection.</span></span> <span data-ttu-id="aef00-109">Use la [ICorProfilerInfo3:: Setenterleavefunctionhooks3 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) para registrar su implementación de esta función.</span><span class="sxs-lookup"><span data-stu-id="aef00-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="aef00-110">El `FunctionLeave3` función es una devolución de llamada; debe implementar.</span><span class="sxs-lookup"><span data-stu-id="aef00-110">The `FunctionLeave3` function is a callback; you must implement it.</span></span> <span data-ttu-id="aef00-111">La implementación debe usar el `__declspec(naked)` atributo de clase de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="aef00-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="aef00-112">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="aef00-112">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="aef00-113">En la entrada, debe guardar todos los registros que utilice, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="aef00-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="aef00-114">En la salida, debe restaurar la pila debe extraer todos los parámetros que se insertaron su llamador.</span><span class="sxs-lookup"><span data-stu-id="aef00-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="aef00-115">La implementación de `FunctionLeave3` no debe bloquearse, porque ello retrasará la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="aef00-115">The implementation of `FunctionLeave3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="aef00-116">La implementación no debe intentar una recolección de elementos, ya que la pila no puede estar en un estado compatible con la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="aef00-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="aef00-117">Si se intenta realizar una recolección, el tiempo de ejecución se bloqueará hasta que `FunctionLeave3` devuelve.</span><span class="sxs-lookup"><span data-stu-id="aef00-117">If a garbage collection is attempted, the runtime will block until `FunctionLeave3` returns.</span></span>  
  
 <span data-ttu-id="aef00-118">El `FunctionLeave3` función no debe llamar al código administrado o provocar una asignación de memoria administrada de ninguna manera.</span><span class="sxs-lookup"><span data-stu-id="aef00-118">The `FunctionLeave3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aef00-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aef00-119">Requirements</span></span>  
 <span data-ttu-id="aef00-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aef00-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aef00-121">**Encabezado**: CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="aef00-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="aef00-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aef00-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aef00-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aef00-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aef00-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="aef00-124">See also</span></span>

- [<span data-ttu-id="aef00-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="aef00-125">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="aef00-126">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="aef00-126">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="aef00-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="aef00-127">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="aef00-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="aef00-128">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="aef00-129">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="aef00-129">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="aef00-130">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="aef00-130">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="aef00-131">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="aef00-131">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="aef00-132">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="aef00-132">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="aef00-133">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="aef00-133">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="aef00-134">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="aef00-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
