---
description: 'Más información acerca de: FunctionLeave2 (función)'
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
ms.openlocfilehash: a9a97b84c70fd50044e8340b6f59fdbefe1d1a60
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760150"
---
# <a name="functionleave2-function"></a><span data-ttu-id="538d0-103">FunctionLeave2 (Función)</span><span class="sxs-lookup"><span data-stu-id="538d0-103">FunctionLeave2 Function</span></span>

<span data-ttu-id="538d0-104">Notifica al generador de perfiles que una función está a punto de volver al autor de la llamada y proporciona información sobre el marco de pila y el valor devuelto de la función.</span><span class="sxs-lookup"><span data-stu-id="538d0-104">Notifies the profiler that a function is about to return to the caller and provides information about the stack frame and function return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="538d0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="538d0-105">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave2 (  
    [in]  FunctionID                        funcId,  
    [in]  UINT_PTR                          clientData,  
    [in]  COR_PRF_FRAME_INFO                func,  
    [in]  COR_PRF_FUNCTION_ARGUMENT_RANGE  *retvalRange  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="538d0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="538d0-106">Parameters</span></span>

<span data-ttu-id="538d0-107">`funcId` de El identificador de la función que devuelve.</span><span class="sxs-lookup"><span data-stu-id="538d0-107">`funcId` [in] The identifier of the function that is returning.</span></span>

<span data-ttu-id="538d0-108">`clientData` de Identificador de la función reasignada, que el generador de perfiles especificó previamente a través de la función [FunctionIDMapper](functionidmapper-function.md) .</span><span class="sxs-lookup"><span data-stu-id="538d0-108">`clientData` [in] The remapped function identifier, which the profiler previously specified via the [FunctionIDMapper](functionidmapper-function.md) function.</span></span>

<span data-ttu-id="538d0-109">`func` de `COR_PRF_FRAME_INFO` Valor que señala a la información sobre el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="538d0-109">`func` [in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>

<span data-ttu-id="538d0-110">El generador de perfiles debe tratarlo como un identificador opaco que se puede devolver al motor de ejecución en el método [ICorProfilerInfo2:: getfunctioninfo2 (](icorprofilerinfo2-getfunctioninfo2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="538d0-110">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
<span data-ttu-id="538d0-111">`retvalRange` de Puntero a una estructura de [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) que especifica la ubicación de memoria del valor devuelto de la función.</span><span class="sxs-lookup"><span data-stu-id="538d0-111">`retvalRange` [in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) structure that specifies the memory location of the function's return value.</span></span>

<span data-ttu-id="538d0-112">Para tener acceso a la información de los valores devueltos, `COR_PRF_ENABLE_FUNCTION_RETVAL` se debe establecer la marca.</span><span class="sxs-lookup"><span data-stu-id="538d0-112">In order to access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag must be set.</span></span> <span data-ttu-id="538d0-113">El generador de perfiles puede utilizar el método [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) para establecer las marcas de evento.</span><span class="sxs-lookup"><span data-stu-id="538d0-113">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>

## <a name="remarks"></a><span data-ttu-id="538d0-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="538d0-114">Remarks</span></span>  

 <span data-ttu-id="538d0-115">Los valores de los `func` `retvalRange` parámetros y no son válidos después de que la `FunctionLeave2` función devuelva, ya que los valores pueden cambiar o destruirse.</span><span class="sxs-lookup"><span data-stu-id="538d0-115">The values of the `func` and `retvalRange` parameters are not valid after the `FunctionLeave2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="538d0-116">La `FunctionLeave2` función es una devolución de llamada; debe implementarla.</span><span class="sxs-lookup"><span data-stu-id="538d0-116">The `FunctionLeave2` function is a callback; you must implement it.</span></span> <span data-ttu-id="538d0-117">La implementación debe usar el `__declspec` `naked` atributo de clase de almacenamiento ().</span><span class="sxs-lookup"><span data-stu-id="538d0-117">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="538d0-118">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="538d0-118">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="538d0-119">En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="538d0-119">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="538d0-120">Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="538d0-120">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="538d0-121">La implementación de `FunctionLeave2` no debe bloquearse porque retrasará la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="538d0-121">The implementation of `FunctionLeave2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="538d0-122">La implementación no debe intentar una recolección de elementos no utilizados porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="538d0-122">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="538d0-123">Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que se `FunctionLeave2` devuelva.</span><span class="sxs-lookup"><span data-stu-id="538d0-123">If a garbage collection is attempted, the runtime will block until `FunctionLeave2` returns.</span></span>  
  
 <span data-ttu-id="538d0-124">Además, la `FunctionLeave2` función no debe llamar a código administrado ni producir una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="538d0-124">Also, the `FunctionLeave2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="538d0-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="538d0-125">Requirements</span></span>  

 <span data-ttu-id="538d0-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="538d0-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="538d0-127">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="538d0-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="538d0-128">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="538d0-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="538d0-129">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="538d0-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="538d0-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="538d0-130">See also</span></span>

- [<span data-ttu-id="538d0-131">FunctionEnter2 (Función)</span><span class="sxs-lookup"><span data-stu-id="538d0-131">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="538d0-132">FunctionTailcall2 (Función)</span><span class="sxs-lookup"><span data-stu-id="538d0-132">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="538d0-133">Método SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="538d0-133">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="538d0-134">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="538d0-134">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
