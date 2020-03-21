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
ms.openlocfilehash: 9aeb7a294beb10f9c2968e6161c72fdc362c4991
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177064"
---
# <a name="functionenter2-function"></a><span data-ttu-id="35528-102">FunctionEnter2 (Función)</span><span class="sxs-lookup"><span data-stu-id="35528-102">FunctionEnter2 Function</span></span>
<span data-ttu-id="35528-103">Notifica al generador de perfiles que el control se pasa a una función y proporciona información sobre el marco de pila y los argumentos de función.</span><span class="sxs-lookup"><span data-stu-id="35528-103">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="35528-104">Esta función sustituye a la función [FunctionEnter.](functionenter-function.md)</span><span class="sxs-lookup"><span data-stu-id="35528-104">This function supersedes the [FunctionEnter](functionenter-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35528-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35528-105">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,
    [in]  UINT_PTR                         clientData,
    [in]  COR_PRF_FRAME_INFO               func,
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35528-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="35528-106">Parameters</span></span>

- `funcId`

  <span data-ttu-id="35528-107">\[en] El identificador de la función a la que se pasa el control.</span><span class="sxs-lookup"><span data-stu-id="35528-107">\[in] The identifier of the function to which control is passed.</span></span>

- `clientData`

  <span data-ttu-id="35528-108">\[en] El identificador de función reasignado, que el generador de perfiles especificó previamente mediante la función [FunctionIDMapper.](functionidmapper-function.md)</span><span class="sxs-lookup"><span data-stu-id="35528-108">\[in] The remapped function identifier, which the profiler previously specified by using the [FunctionIDMapper](functionidmapper-function.md) function.</span></span>
  
- `func`

  <span data-ttu-id="35528-109">\[en] `COR_PRF_FRAME_INFO` Un valor que apunta a información sobre el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="35528-109">\[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>
  
  <span data-ttu-id="35528-110">El generador de perfiles debe tratar esto como un identificador opaco que se puede volver al motor de ejecución en el [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="35528-110">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
- `argumentInfo`

  <span data-ttu-id="35528-111">\[en] Un puntero a una estructura [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) que especifica las ubicaciones en memoria de los argumentos de la función.</span><span class="sxs-lookup"><span data-stu-id="35528-111">\[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) structure that specifies the locations in memory of the function's arguments.</span></span>

  <span data-ttu-id="35528-112">Para acceder a la `COR_PRF_ENABLE_FUNCTION_ARGS` información del argumento, se debe establecer el indicador.</span><span class="sxs-lookup"><span data-stu-id="35528-112">In order to access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag must be set.</span></span> <span data-ttu-id="35528-113">El generador de perfiles puede utilizar el método [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) para establecer los indicadores de evento.</span><span class="sxs-lookup"><span data-stu-id="35528-113">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>

## <a name="remarks"></a><span data-ttu-id="35528-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="35528-114">Remarks</span></span>  
 <span data-ttu-id="35528-115">Los valores `func` de `argumentInfo` los parámetros `FunctionEnter2` y no son válidos después de que la función devuelve porque los valores pueden cambiar o destruirse.</span><span class="sxs-lookup"><span data-stu-id="35528-115">The values of the `func` and `argumentInfo` parameters are not valid after the `FunctionEnter2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="35528-116">La `FunctionEnter2` función es una devolución de llamada; debe implementarlo.</span><span class="sxs-lookup"><span data-stu-id="35528-116">The `FunctionEnter2` function is a callback; you must implement it.</span></span> <span data-ttu-id="35528-117">La implementación `__declspec`debe`naked`usar el atributo de clase de almacenamiento ( ).</span><span class="sxs-lookup"><span data-stu-id="35528-117">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="35528-118">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="35528-118">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="35528-119">En la entrada, debe guardar todos los registros que utilice, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="35528-119">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="35528-120">Al salir, debe restaurar la pila desprendendo todos los parámetros que fueron empujados por su llamador.</span><span class="sxs-lookup"><span data-stu-id="35528-120">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="35528-121">La implementación de no debe bloquearse porque retrasará la recolección de `FunctionEnter2` elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="35528-121">The implementation of `FunctionEnter2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="35528-122">La implementación no debe intentar una recolección de elementos no utilizados porque la pila puede no estar en un estado compatible con la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="35528-122">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="35528-123">Si se intenta una recolección de `FunctionEnter2` elementos no utilizados, el tiempo de ejecución se bloqueará hasta que se devuelva.</span><span class="sxs-lookup"><span data-stu-id="35528-123">If a garbage collection is attempted, the runtime will block until `FunctionEnter2` returns.</span></span>  
  
 <span data-ttu-id="35528-124">Además, la `FunctionEnter2` función no debe llamar al código administrado ni de ninguna manera provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="35528-124">Also, the `FunctionEnter2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35528-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="35528-125">Requirements</span></span>  
 <span data-ttu-id="35528-126">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35528-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35528-127">**Encabezado:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="35528-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="35528-128">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35528-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35528-129">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35528-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35528-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="35528-130">See also</span></span>

- [<span data-ttu-id="35528-131">FunctionLeave2 (Función)</span><span class="sxs-lookup"><span data-stu-id="35528-131">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="35528-132">FunctionTailcall2 (Función)</span><span class="sxs-lookup"><span data-stu-id="35528-132">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="35528-133">Método SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="35528-133">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="35528-134">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="35528-134">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
