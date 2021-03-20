---
description: 'Más información acerca de: función FunctionEnter2'
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
ms.openlocfilehash: f68aeffdd63222cd78d7dc361f09e0b4c3e5af51
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759396"
---
# <a name="functionenter2-function"></a><span data-ttu-id="cd05a-103">FunctionEnter2 (Función)</span><span class="sxs-lookup"><span data-stu-id="cd05a-103">FunctionEnter2 Function</span></span>

<span data-ttu-id="cd05a-104">Notifica al generador de perfiles que el control se pasa a una función y proporciona información sobre el marco de pila y los argumentos de la función.</span><span class="sxs-lookup"><span data-stu-id="cd05a-104">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="cd05a-105">Esta función reemplaza la función [FunctionEnter (](functionenter-function.md) .</span><span class="sxs-lookup"><span data-stu-id="cd05a-105">This function supersedes the [FunctionEnter](functionenter-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd05a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cd05a-106">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,
    [in]  UINT_PTR                         clientData,
    [in]  COR_PRF_FRAME_INFO               func,
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd05a-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cd05a-107">Parameters</span></span>

<span data-ttu-id="cd05a-108">`funcId` de Identificador de la función a la que se pasa el control.</span><span class="sxs-lookup"><span data-stu-id="cd05a-108">`funcId` [in] The identifier of the function to which control is passed.</span></span>

<span data-ttu-id="cd05a-109">`clientData` de Identificador de la función reasignada, que el generador de perfiles especificó anteriormente mediante la función [FunctionIDMapper](functionidmapper-function.md) .</span><span class="sxs-lookup"><span data-stu-id="cd05a-109">`clientData` [in] The remapped function identifier, which the profiler previously specified by using the [FunctionIDMapper](functionidmapper-function.md) function.</span></span>
  
<span data-ttu-id="cd05a-110">`func` de `COR_PRF_FRAME_INFO` Valor que señala a la información sobre el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="cd05a-110">`func` [in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>
  
<span data-ttu-id="cd05a-111">El generador de perfiles debe tratarlo como un identificador opaco que se puede devolver al motor de ejecución en el método [ICorProfilerInfo2:: getfunctioninfo2 (](icorprofilerinfo2-getfunctioninfo2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="cd05a-111">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
<span data-ttu-id="cd05a-112">`argumentInfo` de Puntero a una estructura de [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) que especifica las ubicaciones en memoria de los argumentos de la función.</span><span class="sxs-lookup"><span data-stu-id="cd05a-112">`argumentInfo` [in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) structure that specifies the locations in memory of the function's arguments.</span></span>

<span data-ttu-id="cd05a-113">Para tener acceso a la información de los argumentos, `COR_PRF_ENABLE_FUNCTION_ARGS` se debe establecer la marca.</span><span class="sxs-lookup"><span data-stu-id="cd05a-113">In order to access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag must be set.</span></span> <span data-ttu-id="cd05a-114">El generador de perfiles puede utilizar el método [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) para establecer las marcas de evento.</span><span class="sxs-lookup"><span data-stu-id="cd05a-114">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>

## <a name="remarks"></a><span data-ttu-id="cd05a-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cd05a-115">Remarks</span></span>  

 <span data-ttu-id="cd05a-116">Los valores de los `func` `argumentInfo` parámetros y no son válidos después de que la `FunctionEnter2` función devuelva, ya que los valores pueden cambiar o destruirse.</span><span class="sxs-lookup"><span data-stu-id="cd05a-116">The values of the `func` and `argumentInfo` parameters are not valid after the `FunctionEnter2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="cd05a-117">La `FunctionEnter2` función es una devolución de llamada; debe implementarla.</span><span class="sxs-lookup"><span data-stu-id="cd05a-117">The `FunctionEnter2` function is a callback; you must implement it.</span></span> <span data-ttu-id="cd05a-118">La implementación debe usar el `__declspec` `naked` atributo de clase de almacenamiento ().</span><span class="sxs-lookup"><span data-stu-id="cd05a-118">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="cd05a-119">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="cd05a-119">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="cd05a-120">En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="cd05a-120">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="cd05a-121">Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="cd05a-121">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="cd05a-122">La implementación de `FunctionEnter2` no debe bloquearse porque retrasará la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="cd05a-122">The implementation of `FunctionEnter2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="cd05a-123">La implementación no debe intentar una recolección de elementos no utilizados porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="cd05a-123">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="cd05a-124">Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que se `FunctionEnter2` devuelva.</span><span class="sxs-lookup"><span data-stu-id="cd05a-124">If a garbage collection is attempted, the runtime will block until `FunctionEnter2` returns.</span></span>  
  
 <span data-ttu-id="cd05a-125">Además, la `FunctionEnter2` función no debe llamar a código administrado ni producir una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="cd05a-125">Also, the `FunctionEnter2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd05a-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cd05a-126">Requirements</span></span>  

 <span data-ttu-id="cd05a-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd05a-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd05a-128">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="cd05a-128">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="cd05a-129">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd05a-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd05a-130">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd05a-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd05a-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cd05a-131">See also</span></span>

- [<span data-ttu-id="cd05a-132">FunctionLeave2 (Función)</span><span class="sxs-lookup"><span data-stu-id="cd05a-132">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="cd05a-133">FunctionTailcall2 (Función)</span><span class="sxs-lookup"><span data-stu-id="cd05a-133">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="cd05a-134">Método SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="cd05a-134">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="cd05a-135">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="cd05a-135">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
