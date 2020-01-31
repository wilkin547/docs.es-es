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
ms.openlocfilehash: 0b1ecd1266528f8a08ef114de2f111dd0f71ca8b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866936"
---
# <a name="functionleave2-function"></a><span data-ttu-id="6adf2-102">FunctionLeave2 (Función)</span><span class="sxs-lookup"><span data-stu-id="6adf2-102">FunctionLeave2 Function</span></span>
<span data-ttu-id="6adf2-103">Notifica al generador de perfiles que una función está a punto de volver al autor de la llamada y proporciona información sobre el marco de pila y el valor devuelto de la función.</span><span class="sxs-lookup"><span data-stu-id="6adf2-103">Notifies the profiler that a function is about to return to the caller and provides information about the stack frame and function return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6adf2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6adf2-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave2 (  
    [in]  FunctionID                        funcId,  
    [in]  UINT_PTR                          clientData,  
    [in]  COR_PRF_FRAME_INFO                func,  
    [in]  COR_PRF_FUNCTION_ARGUMENT_RANGE  *retvalRange  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6adf2-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="6adf2-105">Parameters</span></span>

- `funcId`

  <span data-ttu-id="6adf2-106">\[en] el identificador de la función que devuelve.</span><span class="sxs-lookup"><span data-stu-id="6adf2-106">\[in] The identifier of the function that is returning.</span></span>

- `clientData`

  <span data-ttu-id="6adf2-107">\[in] identificador de la función reasignada, que el generador de perfiles especificó previamente a través de la función [FunctionIDMapper](functionidmapper-function.md) .</span><span class="sxs-lookup"><span data-stu-id="6adf2-107">\[in] The remapped function identifier, which the profiler previously specified via the [FunctionIDMapper](functionidmapper-function.md) function.</span></span>

- `func`

  <span data-ttu-id="6adf2-108">\[en] un valor `COR_PRF_FRAME_INFO` que apunta a la información sobre el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="6adf2-108">\[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>

  <span data-ttu-id="6adf2-109">El generador de perfiles debe tratarlo como un identificador opaco que se puede devolver al motor de ejecución en el método [ICorProfilerInfo2:: getfunctioninfo2 (](icorprofilerinfo2-getfunctioninfo2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="6adf2-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
- `retvalRange`

  <span data-ttu-id="6adf2-110">\[in] un puntero a una estructura de [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) que especifica la ubicación de memoria del valor devuelto de la función.</span><span class="sxs-lookup"><span data-stu-id="6adf2-110">\[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) structure that specifies the memory location of the function's return value.</span></span>

  <span data-ttu-id="6adf2-111">Para tener acceso a la información de los valores devueltos, se debe establecer la marca `COR_PRF_ENABLE_FUNCTION_RETVAL`.</span><span class="sxs-lookup"><span data-stu-id="6adf2-111">In order to access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag must be set.</span></span> <span data-ttu-id="6adf2-112">El generador de perfiles puede utilizar el método [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) para establecer las marcas de evento.</span><span class="sxs-lookup"><span data-stu-id="6adf2-112">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>

## <a name="remarks"></a><span data-ttu-id="6adf2-113">Notas</span><span class="sxs-lookup"><span data-stu-id="6adf2-113">Remarks</span></span>  
 <span data-ttu-id="6adf2-114">Los valores de los parámetros `func` y `retvalRange` no son válidos después de que se devuelva la función `FunctionLeave2` porque los valores pueden cambiar o ser destruidos.</span><span class="sxs-lookup"><span data-stu-id="6adf2-114">The values of the `func` and `retvalRange` parameters are not valid after the `FunctionLeave2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="6adf2-115">La función `FunctionLeave2` es una devolución de llamada; debe implementarla.</span><span class="sxs-lookup"><span data-stu-id="6adf2-115">The `FunctionLeave2` function is a callback; you must implement it.</span></span> <span data-ttu-id="6adf2-116">La implementación debe usar el atributo de clase de almacenamiento `__declspec`(`naked`).</span><span class="sxs-lookup"><span data-stu-id="6adf2-116">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="6adf2-117">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="6adf2-117">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="6adf2-118">En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="6adf2-118">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="6adf2-119">Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="6adf2-119">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="6adf2-120">La implementación de `FunctionLeave2` no debe bloquearse porque retrasará la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="6adf2-120">The implementation of `FunctionLeave2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="6adf2-121">La implementación no debe intentar una recolección de elementos no utilizados porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="6adf2-121">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="6adf2-122">Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que `FunctionLeave2` devuelva.</span><span class="sxs-lookup"><span data-stu-id="6adf2-122">If a garbage collection is attempted, the runtime will block until `FunctionLeave2` returns.</span></span>  
  
 <span data-ttu-id="6adf2-123">Además, la función `FunctionLeave2` no debe llamar a código administrado ni producir una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="6adf2-123">Also, the `FunctionLeave2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6adf2-124">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="6adf2-124">Requirements</span></span>  
 <span data-ttu-id="6adf2-125">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6adf2-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6adf2-126">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="6adf2-126">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="6adf2-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6adf2-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6adf2-128">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6adf2-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6adf2-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="6adf2-129">See also</span></span>

- [<span data-ttu-id="6adf2-130">FunctionEnter2 (Función)</span><span class="sxs-lookup"><span data-stu-id="6adf2-130">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="6adf2-131">FunctionTailcall2 (Función)</span><span class="sxs-lookup"><span data-stu-id="6adf2-131">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="6adf2-132">SetEnterLeaveFunctionHooks2 (método)</span><span class="sxs-lookup"><span data-stu-id="6adf2-132">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="6adf2-133">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="6adf2-133">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
