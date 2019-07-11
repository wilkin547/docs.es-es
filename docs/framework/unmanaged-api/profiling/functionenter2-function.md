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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 413cde3d0977c1fd6897fc5bd6fa7a3fef00ac02
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763340"
---
# <a name="functionenter2-function"></a><span data-ttu-id="adb27-102">FunctionEnter2 (Función)</span><span class="sxs-lookup"><span data-stu-id="adb27-102">FunctionEnter2 Function</span></span>
<span data-ttu-id="adb27-103">Notifica al generador de perfiles que el control se pasa a una función y proporciona información sobre la pila los argumentos de marco y la función.</span><span class="sxs-lookup"><span data-stu-id="adb27-103">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="adb27-104">Esta función reemplaza la [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="adb27-104">This function supersedes the [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adb27-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="adb27-105">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,   
    [in]  UINT_PTR                         clientData,   
    [in]  COR_PRF_FRAME_INFO               func,   
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="adb27-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="adb27-106">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="adb27-107">[in] El identificador de la función a la que se pasa el control.</span><span class="sxs-lookup"><span data-stu-id="adb27-107">[in] The identifier of the function to which control is passed.</span></span>  
  
 `clientData`  
 <span data-ttu-id="adb27-108">[in] El identificador de función reasignada que especificó previamente en el generador de perfiles mediante el [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="adb27-108">[in] The remapped function identifier, which the profiler previously specified by using the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function.</span></span>  
  
 `func`  
 <span data-ttu-id="adb27-109">[in] Un `COR_PRF_FRAME_INFO` valor al que apunta a la información sobre el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="adb27-109">[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>  
  
 <span data-ttu-id="adb27-110">El generador de perfiles debe tratar como un identificador opaco que puede pasarse al motor de ejecución en el [ICorProfilerInfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="adb27-110">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
 `argumentInfo`  
 <span data-ttu-id="adb27-111">[in] Un puntero a un [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) estructura que especifica las ubicaciones de memoria de los argumentos de función.</span><span class="sxs-lookup"><span data-stu-id="adb27-111">[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) structure that specifies the locations in memory of the function's arguments.</span></span>  
  
 <span data-ttu-id="adb27-112">Para tener acceso a información del argumento, el `COR_PRF_ENABLE_FUNCTION_ARGS` se debe establecer la marca.</span><span class="sxs-lookup"><span data-stu-id="adb27-112">In order to access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag must be set.</span></span> <span data-ttu-id="adb27-113">El generador de perfiles puede utilizar el [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) método para establecer las marcas de evento.</span><span class="sxs-lookup"><span data-stu-id="adb27-113">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="adb27-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="adb27-114">Remarks</span></span>  
 <span data-ttu-id="adb27-115">Los valores de la `func` y `argumentInfo` parámetros no son válidos tras el `FunctionEnter2` función devuelve porque los valores pueden cambiar o se destruye.</span><span class="sxs-lookup"><span data-stu-id="adb27-115">The values of the `func` and `argumentInfo` parameters are not valid after the `FunctionEnter2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="adb27-116">El `FunctionEnter2` función es una devolución de llamada; debe implementar.</span><span class="sxs-lookup"><span data-stu-id="adb27-116">The `FunctionEnter2` function is a callback; you must implement it.</span></span> <span data-ttu-id="adb27-117">La implementación debe usar el `__declspec`(`naked`) el atributo de clase de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="adb27-117">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="adb27-118">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="adb27-118">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="adb27-119">En la entrada, debe guardar todos los registros que utilice, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="adb27-119">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="adb27-120">En la salida, debe restaurar la pila debe extraer todos los parámetros que se insertaron su llamador.</span><span class="sxs-lookup"><span data-stu-id="adb27-120">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="adb27-121">La implementación de `FunctionEnter2` no debe bloquearse porque retrasará la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="adb27-121">The implementation of `FunctionEnter2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="adb27-122">La implementación no debe intentar una recolección porque la pila no puede estar en un estado compatible con la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="adb27-122">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="adb27-123">Si se intenta realizar una recolección, el tiempo de ejecución se bloqueará hasta que `FunctionEnter2` devuelve.</span><span class="sxs-lookup"><span data-stu-id="adb27-123">If a garbage collection is attempted, the runtime will block until `FunctionEnter2` returns.</span></span>  
  
 <span data-ttu-id="adb27-124">Además, el `FunctionEnter2` función no debe llamar a código administrado o en modo alguno provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="adb27-124">Also, the `FunctionEnter2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adb27-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="adb27-125">Requirements</span></span>  
 <span data-ttu-id="adb27-126">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="adb27-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="adb27-127">**Encabezado**: CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="adb27-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="adb27-128">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="adb27-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="adb27-129">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="adb27-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adb27-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="adb27-130">See also</span></span>

- [<span data-ttu-id="adb27-131">FunctionLeave2 (Función)</span><span class="sxs-lookup"><span data-stu-id="adb27-131">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="adb27-132">FunctionTailcall2 (Función)</span><span class="sxs-lookup"><span data-stu-id="adb27-132">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="adb27-133">SetEnterLeaveFunctionHooks2 (método)</span><span class="sxs-lookup"><span data-stu-id="adb27-133">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="adb27-134">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="adb27-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
