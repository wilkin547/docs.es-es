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
ms.openlocfilehash: f4deec3e2b49b5cd6a924af8024e775c5c549f97
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440851"
---
# <a name="functionenter2-function"></a><span data-ttu-id="1e8df-102">FunctionEnter2 (Función)</span><span class="sxs-lookup"><span data-stu-id="1e8df-102">FunctionEnter2 Function</span></span>
<span data-ttu-id="1e8df-103">Notifica al generador de perfiles que el control se pasa a una función y proporciona información sobre el marco de pila y los argumentos de la función.</span><span class="sxs-lookup"><span data-stu-id="1e8df-103">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="1e8df-104">Esta función reemplaza la función [FunctionEnter (](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) .</span><span class="sxs-lookup"><span data-stu-id="1e8df-104">This function supersedes the [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e8df-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1e8df-105">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,   
    [in]  UINT_PTR                         clientData,   
    [in]  COR_PRF_FRAME_INFO               func,   
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e8df-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1e8df-106">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="1e8df-107">de Identificador de la función a la que se pasa el control.</span><span class="sxs-lookup"><span data-stu-id="1e8df-107">[in] The identifier of the function to which control is passed.</span></span>  
  
 `clientData`  
 <span data-ttu-id="1e8df-108">de Identificador de la función reasignada, que el generador de perfiles especificó anteriormente mediante la función [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) .</span><span class="sxs-lookup"><span data-stu-id="1e8df-108">[in] The remapped function identifier, which the profiler previously specified by using the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function.</span></span>  
  
 `func`  
 <span data-ttu-id="1e8df-109">de `COR_PRF_FRAME_INFO` valor que apunta a la información sobre el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="1e8df-109">[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>  
  
 <span data-ttu-id="1e8df-110">El generador de perfiles debe tratarlo como un identificador opaco que se puede devolver al motor de ejecución en el método [ICorProfilerInfo2:: getfunctioninfo2 (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1e8df-110">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
 `argumentInfo`  
 <span data-ttu-id="1e8df-111">de Puntero a una estructura de [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) que especifica las ubicaciones en memoria de los argumentos de la función.</span><span class="sxs-lookup"><span data-stu-id="1e8df-111">[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) structure that specifies the locations in memory of the function's arguments.</span></span>  
  
 <span data-ttu-id="1e8df-112">Para tener acceso a la información de los argumentos, se debe establecer la marca `COR_PRF_ENABLE_FUNCTION_ARGS`.</span><span class="sxs-lookup"><span data-stu-id="1e8df-112">In order to access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag must be set.</span></span> <span data-ttu-id="1e8df-113">El generador de perfiles puede utilizar el método [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) para establecer las marcas de evento.</span><span class="sxs-lookup"><span data-stu-id="1e8df-113">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1e8df-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1e8df-114">Remarks</span></span>  
 <span data-ttu-id="1e8df-115">Los valores de los parámetros `func` y `argumentInfo` no son válidos después de que se devuelva la función `FunctionEnter2` porque los valores pueden cambiar o ser destruidos.</span><span class="sxs-lookup"><span data-stu-id="1e8df-115">The values of the `func` and `argumentInfo` parameters are not valid after the `FunctionEnter2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="1e8df-116">La función `FunctionEnter2` es una devolución de llamada; debe implementarla.</span><span class="sxs-lookup"><span data-stu-id="1e8df-116">The `FunctionEnter2` function is a callback; you must implement it.</span></span> <span data-ttu-id="1e8df-117">La implementación debe usar el atributo de clase de almacenamiento `__declspec`(`naked`).</span><span class="sxs-lookup"><span data-stu-id="1e8df-117">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="1e8df-118">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="1e8df-118">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="1e8df-119">En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="1e8df-119">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="1e8df-120">Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="1e8df-120">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="1e8df-121">La implementación de `FunctionEnter2` no debe bloquearse porque retrasará la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="1e8df-121">The implementation of `FunctionEnter2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="1e8df-122">La implementación no debe intentar una recolección de elementos no utilizados porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="1e8df-122">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="1e8df-123">Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que `FunctionEnter2` devuelva.</span><span class="sxs-lookup"><span data-stu-id="1e8df-123">If a garbage collection is attempted, the runtime will block until `FunctionEnter2` returns.</span></span>  
  
 <span data-ttu-id="1e8df-124">Además, la función `FunctionEnter2` no debe llamar a código administrado ni producir una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="1e8df-124">Also, the `FunctionEnter2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e8df-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1e8df-125">Requirements</span></span>  
 <span data-ttu-id="1e8df-126">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e8df-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e8df-127">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="1e8df-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="1e8df-128">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e8df-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e8df-129">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e8df-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e8df-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e8df-130">See also</span></span>

- [<span data-ttu-id="1e8df-131">FunctionLeave2 (Función)</span><span class="sxs-lookup"><span data-stu-id="1e8df-131">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="1e8df-132">FunctionTailcall2 (Función)</span><span class="sxs-lookup"><span data-stu-id="1e8df-132">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="1e8df-133">SetEnterLeaveFunctionHooks2 (método)</span><span class="sxs-lookup"><span data-stu-id="1e8df-133">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="1e8df-134">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="1e8df-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
