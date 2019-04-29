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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3efee2e2b595f1e0d9116dcac3fdaa99aa4659d4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598901"
---
# <a name="functionleave2-function"></a><span data-ttu-id="0b331-102">FunctionLeave2 (Función)</span><span class="sxs-lookup"><span data-stu-id="0b331-102">FunctionLeave2 Function</span></span>
<span data-ttu-id="0b331-103">Notifica al generador de perfiles que una función está a punto de devolver al autor de llamada y proporciona información sobre la pila marco y la función de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="0b331-103">Notifies the profiler that a function is about to return to the caller and provides information about the stack frame and function return value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b331-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0b331-104">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave2 (  
    [in]  FunctionID                        funcId,  
    [in]  UINT_PTR                          clientData,  
    [in]  COR_PRF_FRAME_INFO                func,  
    [in]  COR_PRF_FUNCTION_ARGUMENT_RANGE  *retvalRange  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b331-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0b331-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="0b331-106">[in] El identificador de la función que devuelve.</span><span class="sxs-lookup"><span data-stu-id="0b331-106">[in] The identifier of the function that is returning.</span></span>  
  
 `clientData`  
 <span data-ttu-id="0b331-107">[in] El identificador de la función reasignada, que el generador de perfiles especificado anteriormente a través de la [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="0b331-107">[in] The remapped function identifier, which the profiler previously specified via the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function.</span></span>  
  
 `func`  
 <span data-ttu-id="0b331-108">[in] Un `COR_PRF_FRAME_INFO` valor al que apunta a la información sobre el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="0b331-108">[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>  
  
 <span data-ttu-id="0b331-109">El generador de perfiles debe tratar como un identificador opaco que puede pasarse al motor de ejecución en el [ICorProfilerInfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="0b331-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
 `retvalRange`  
 <span data-ttu-id="0b331-110">[in] Un puntero a un [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) estructura que especifica la ubicación de memoria del valor devuelto de la función.</span><span class="sxs-lookup"><span data-stu-id="0b331-110">[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structure that specifies the memory location of the function's return value.</span></span>  
  
 <span data-ttu-id="0b331-111">Para tener acceso a información del valor devuelto, el `COR_PRF_ENABLE_FUNCTION_RETVAL` se debe establecer la marca.</span><span class="sxs-lookup"><span data-stu-id="0b331-111">In order to access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag must be set.</span></span> <span data-ttu-id="0b331-112">El generador de perfiles puede utilizar el [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) método para establecer las marcas de evento.</span><span class="sxs-lookup"><span data-stu-id="0b331-112">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b331-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0b331-113">Remarks</span></span>  
 <span data-ttu-id="0b331-114">Los valores de la `func` y `retvalRange` parámetros no son válidos tras el `FunctionLeave2` función devuelve porque los valores pueden cambiar o se destruye.</span><span class="sxs-lookup"><span data-stu-id="0b331-114">The values of the `func` and `retvalRange` parameters are not valid after the `FunctionLeave2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="0b331-115">El `FunctionLeave2` función es una devolución de llamada; debe implementar.</span><span class="sxs-lookup"><span data-stu-id="0b331-115">The `FunctionLeave2` function is a callback; you must implement it.</span></span> <span data-ttu-id="0b331-116">La implementación debe usar el `__declspec`(`naked`) el atributo de clase de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="0b331-116">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="0b331-117">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="0b331-117">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="0b331-118">En la entrada, debe guardar todos los registros que utilice, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="0b331-118">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="0b331-119">En la salida, debe restaurar la pila debe extraer todos los parámetros que se insertaron su llamador.</span><span class="sxs-lookup"><span data-stu-id="0b331-119">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="0b331-120">La implementación de `FunctionLeave2` no debe bloquearse porque retrasará la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="0b331-120">The implementation of `FunctionLeave2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="0b331-121">La implementación no debe intentar una recolección porque la pila no puede estar en un estado compatible con la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="0b331-121">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="0b331-122">Si se intenta realizar una recolección, el tiempo de ejecución se bloqueará hasta que `FunctionLeave2` devuelve.</span><span class="sxs-lookup"><span data-stu-id="0b331-122">If a garbage collection is attempted, the runtime will block until `FunctionLeave2` returns.</span></span>  
  
 <span data-ttu-id="0b331-123">Además, el `FunctionLeave2` función no debe llamar a código administrado o en modo alguno provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="0b331-123">Also, the `FunctionLeave2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b331-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0b331-124">Requirements</span></span>  
 <span data-ttu-id="0b331-125">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b331-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b331-126">**Encabezado**: CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="0b331-126">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="0b331-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b331-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b331-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b331-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b331-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b331-129">See also</span></span>

- [<span data-ttu-id="0b331-130">FunctionEnter2 (Función)</span><span class="sxs-lookup"><span data-stu-id="0b331-130">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="0b331-131">FunctionTailcall2 (Función)</span><span class="sxs-lookup"><span data-stu-id="0b331-131">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="0b331-132">SetEnterLeaveFunctionHooks2 (método)</span><span class="sxs-lookup"><span data-stu-id="0b331-132">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="0b331-133">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="0b331-133">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
