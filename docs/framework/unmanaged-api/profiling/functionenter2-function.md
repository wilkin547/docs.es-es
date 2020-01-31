---
title: FunctionEnter2 (Función)
ms.date: 03/30/2017
api_name:
- FunctionEnter2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter2
helpviewer_keywords:
- FunctionEnter2 function [.NET Framework profiling]
ms.assetid: ce7a21f9-0ca3-4b92-bc4b-bb803cae3f51
topic_type:
- apiref
ms.openlocfilehash: 6cd35c180b8a322b3402b050c6d6840073010b1f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866988"
---
# <a name="functionenter2-function"></a><span data-ttu-id="fafcf-102">FunctionEnter2 (Función)</span><span class="sxs-lookup"><span data-stu-id="fafcf-102">FunctionEnter2 Function</span></span>
<span data-ttu-id="fafcf-103">Notifica al generador de perfiles que el control se pasa a una función y proporciona información sobre el marco de pila y los argumentos de la función.</span><span class="sxs-lookup"><span data-stu-id="fafcf-103">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="fafcf-104">Esta función reemplaza la función [FunctionEnter (](functionenter-function.md) .</span><span class="sxs-lookup"><span data-stu-id="fafcf-104">This function supersedes the [FunctionEnter](functionenter-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fafcf-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fafcf-105">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,   
    [in]  UINT_PTR                         clientData,   
    [in]  COR_PRF_FRAME_INFO               func,   
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fafcf-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="fafcf-106">Parameters</span></span>

- `funcId`

  <span data-ttu-id="fafcf-107">\[en] el identificador de la función a la que se pasa el control.</span><span class="sxs-lookup"><span data-stu-id="fafcf-107">\[in] The identifier of the function to which control is passed.</span></span>

- `clientData`

  <span data-ttu-id="fafcf-108">\[in] identificador de la función reasignada, que el generador de perfiles especificó previamente mediante la función [FunctionIDMapper](functionidmapper-function.md) .</span><span class="sxs-lookup"><span data-stu-id="fafcf-108">\[in] The remapped function identifier, which the profiler previously specified by using the [FunctionIDMapper](functionidmapper-function.md) function.</span></span>
  
- `func`

  <span data-ttu-id="fafcf-109">\[en] un valor `COR_PRF_FRAME_INFO` que apunta a la información sobre el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="fafcf-109">\[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>
  
  <span data-ttu-id="fafcf-110">El generador de perfiles debe tratarlo como un identificador opaco que se puede devolver al motor de ejecución en el método [ICorProfilerInfo2:: getfunctioninfo2 (](icorprofilerinfo2-getfunctioninfo2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="fafcf-110">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
- `argumentInfo`

  <span data-ttu-id="fafcf-111">\[in] un puntero a una estructura de [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) que especifica las ubicaciones en memoria de los argumentos de la función.</span><span class="sxs-lookup"><span data-stu-id="fafcf-111">\[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) structure that specifies the locations in memory of the function's arguments.</span></span>

  <span data-ttu-id="fafcf-112">Para tener acceso a la información de los argumentos, se debe establecer la marca `COR_PRF_ENABLE_FUNCTION_ARGS`.</span><span class="sxs-lookup"><span data-stu-id="fafcf-112">In order to access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag must be set.</span></span> <span data-ttu-id="fafcf-113">El generador de perfiles puede utilizar el método [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) para establecer las marcas de evento.</span><span class="sxs-lookup"><span data-stu-id="fafcf-113">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>

## <a name="remarks"></a><span data-ttu-id="fafcf-114">Notas</span><span class="sxs-lookup"><span data-stu-id="fafcf-114">Remarks</span></span>  
 <span data-ttu-id="fafcf-115">Los valores de los parámetros `func` y `argumentInfo` no son válidos después de que se devuelva la función `FunctionEnter2` porque los valores pueden cambiar o ser destruidos.</span><span class="sxs-lookup"><span data-stu-id="fafcf-115">The values of the `func` and `argumentInfo` parameters are not valid after the `FunctionEnter2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="fafcf-116">La función `FunctionEnter2` es una devolución de llamada; debe implementarla.</span><span class="sxs-lookup"><span data-stu-id="fafcf-116">The `FunctionEnter2` function is a callback; you must implement it.</span></span> <span data-ttu-id="fafcf-117">La implementación debe usar el atributo de clase de almacenamiento `__declspec`(`naked`).</span><span class="sxs-lookup"><span data-stu-id="fafcf-117">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="fafcf-118">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="fafcf-118">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="fafcf-119">En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="fafcf-119">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="fafcf-120">Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="fafcf-120">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="fafcf-121">La implementación de `FunctionEnter2` no debe bloquearse porque retrasará la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="fafcf-121">The implementation of `FunctionEnter2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="fafcf-122">La implementación no debe intentar una recolección de elementos no utilizados porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="fafcf-122">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="fafcf-123">Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que `FunctionEnter2` devuelva.</span><span class="sxs-lookup"><span data-stu-id="fafcf-123">If a garbage collection is attempted, the runtime will block until `FunctionEnter2` returns.</span></span>  
  
 <span data-ttu-id="fafcf-124">Además, la función `FunctionEnter2` no debe llamar a código administrado ni producir una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="fafcf-124">Also, the `FunctionEnter2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fafcf-125">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="fafcf-125">Requirements</span></span>  
 <span data-ttu-id="fafcf-126">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fafcf-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fafcf-127">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="fafcf-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="fafcf-128">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fafcf-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fafcf-129">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fafcf-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fafcf-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="fafcf-130">See also</span></span>

- [<span data-ttu-id="fafcf-131">FunctionLeave2 (Función)</span><span class="sxs-lookup"><span data-stu-id="fafcf-131">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="fafcf-132">FunctionTailcall2 (Función)</span><span class="sxs-lookup"><span data-stu-id="fafcf-132">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="fafcf-133">SetEnterLeaveFunctionHooks2 (método)</span><span class="sxs-lookup"><span data-stu-id="fafcf-133">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="fafcf-134">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="fafcf-134">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
