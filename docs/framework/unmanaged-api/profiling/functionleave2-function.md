---
title: FunctionLeave2 (Función)
ms.date: 03/30/2017
api_name:
- FunctionLeave2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave2
helpviewer_keywords:
- FunctionLeave2 function [.NET Framework profiling]
ms.assetid: 8cdac941-8b94-4497-b874-4e571785f3fe
topic_type:
- apiref
ms.openlocfilehash: a2a3d58e0631fceab96c32f9d86fef25973fed84
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500668"
---
# <a name="functionleave2-function"></a><span data-ttu-id="e9130-102">FunctionLeave2 (Función)</span><span class="sxs-lookup"><span data-stu-id="e9130-102">FunctionLeave2 Function</span></span>
<span data-ttu-id="e9130-103">Notifica al generador de perfiles que una función está a punto de volver al autor de la llamada y proporciona información sobre el marco de pila y el valor devuelto de la función.</span><span class="sxs-lookup"><span data-stu-id="e9130-103">Notifies the profiler that a function is about to return to the caller and provides information about the stack frame and function return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9130-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9130-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave2 (  
    [in]  FunctionID                        funcId,  
    [in]  UINT_PTR                          clientData,  
    [in]  COR_PRF_FRAME_INFO                func,  
    [in]  COR_PRF_FUNCTION_ARGUMENT_RANGE  *retvalRange  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9130-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e9130-105">Parameters</span></span>

- `funcId`

  <span data-ttu-id="e9130-106">\[in] el identificador de la función que devuelve.</span><span class="sxs-lookup"><span data-stu-id="e9130-106">\[in] The identifier of the function that is returning.</span></span>

- `clientData`

  <span data-ttu-id="e9130-107">\[in] el identificador de la función reasignada, que el generador de perfiles especificó previamente a través de la función [FunctionIDMapper](functionidmapper-function.md) .</span><span class="sxs-lookup"><span data-stu-id="e9130-107">\[in] The remapped function identifier, which the profiler previously specified via the [FunctionIDMapper](functionidmapper-function.md) function.</span></span>

- `func`

  <span data-ttu-id="e9130-108">\[en] un `COR_PRF_FRAME_INFO` valor que señala a la información sobre el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="e9130-108">\[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>

  <span data-ttu-id="e9130-109">El generador de perfiles debe tratarlo como un identificador opaco que se puede devolver al motor de ejecución en el método [ICorProfilerInfo2:: getfunctioninfo2 (](icorprofilerinfo2-getfunctioninfo2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e9130-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
- `retvalRange`

  <span data-ttu-id="e9130-110">\[in] un puntero a una estructura de [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) que especifica la ubicación de memoria del valor devuelto de la función.</span><span class="sxs-lookup"><span data-stu-id="e9130-110">\[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) structure that specifies the memory location of the function's return value.</span></span>

  <span data-ttu-id="e9130-111">Para tener acceso a la información de los valores devueltos, `COR_PRF_ENABLE_FUNCTION_RETVAL` se debe establecer la marca.</span><span class="sxs-lookup"><span data-stu-id="e9130-111">In order to access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag must be set.</span></span> <span data-ttu-id="e9130-112">El generador de perfiles puede utilizar el método [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) para establecer las marcas de evento.</span><span class="sxs-lookup"><span data-stu-id="e9130-112">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>

## <a name="remarks"></a><span data-ttu-id="e9130-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e9130-113">Remarks</span></span>  
 <span data-ttu-id="e9130-114">Los valores de los `func` `retvalRange` parámetros y no son válidos después de que la `FunctionLeave2` función devuelva, ya que los valores pueden cambiar o destruirse.</span><span class="sxs-lookup"><span data-stu-id="e9130-114">The values of the `func` and `retvalRange` parameters are not valid after the `FunctionLeave2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="e9130-115">La `FunctionLeave2` función es una devolución de llamada; debe implementarla.</span><span class="sxs-lookup"><span data-stu-id="e9130-115">The `FunctionLeave2` function is a callback; you must implement it.</span></span> <span data-ttu-id="e9130-116">La implementación debe usar el `__declspec` `naked` atributo de clase de almacenamiento ().</span><span class="sxs-lookup"><span data-stu-id="e9130-116">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="e9130-117">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="e9130-117">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="e9130-118">En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="e9130-118">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="e9130-119">Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="e9130-119">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="e9130-120">La implementación de `FunctionLeave2` no debe bloquearse porque retrasará la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="e9130-120">The implementation of `FunctionLeave2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="e9130-121">La implementación no debe intentar una recolección de elementos no utilizados porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="e9130-121">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="e9130-122">Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que se `FunctionLeave2` devuelva.</span><span class="sxs-lookup"><span data-stu-id="e9130-122">If a garbage collection is attempted, the runtime will block until `FunctionLeave2` returns.</span></span>  
  
 <span data-ttu-id="e9130-123">Además, la `FunctionLeave2` función no debe llamar a código administrado ni producir una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="e9130-123">Also, the `FunctionLeave2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9130-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e9130-124">Requirements</span></span>  
 <span data-ttu-id="e9130-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9130-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9130-126">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="e9130-126">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="e9130-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9130-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9130-128">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9130-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9130-129">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="e9130-129">See also</span></span>

- [<span data-ttu-id="e9130-130">FunctionEnter2 (Función)</span><span class="sxs-lookup"><span data-stu-id="e9130-130">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="e9130-131">FunctionTailcall2 (Función)</span><span class="sxs-lookup"><span data-stu-id="e9130-131">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="e9130-132">Método SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="e9130-132">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="e9130-133">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e9130-133">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
