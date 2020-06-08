---
title: FunctionEnter3WithInfo (Función)
ms.date: 03/30/2017
api_name:
- FunctionEnter3WithInfo
api_location:
- mscorwks.cll
api_type:
- COM
f1_keywords:
- FunctionEnter3WithInfo
helpviewer_keywords:
- FunctionEnter3WithInfo function [.NET Framework profiling]
ms.assetid: 277c3344-d0cb-431e-beae-eb1eeeba8eea
topic_type:
- apiref
ms.openlocfilehash: ff4b32185e604611eaaead2847c11bc139d405a6
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500694"
---
# <a name="functionenter3withinfo-function"></a><span data-ttu-id="cb34a-102">FunctionEnter3WithInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="cb34a-102">FunctionEnter3WithInfo Function</span></span>
<span data-ttu-id="cb34a-103">Notifica al generador de perfiles que el control se pasa a una función y proporciona un identificador que se puede pasar al [método ICorProfilerInfo3:: GetFunctionEnter3Info (](icorprofilerinfo3-getfunctionenter3info-method.md) para recuperar el marco de pila y los argumentos de la función.</span><span class="sxs-lookup"><span data-stu-id="cb34a-103">Notifies the profiler that control is being passed to a function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionEnter3Info method](icorprofilerinfo3-getfunctionenter3info-method.md) to retrieve the stack frame and function arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb34a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cb34a-104">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb34a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cb34a-105">Parameters</span></span>

- `functionIDOrClientID`

  <span data-ttu-id="cb34a-106">\[in] el identificador de la función a la que se pasa el control.</span><span class="sxs-lookup"><span data-stu-id="cb34a-106">\[in] The identifier of the function to which control is passed.</span></span>

- `eltInfo`

  <span data-ttu-id="cb34a-107">\[in] un identificador opaco que representa información sobre un marco de pila determinado.</span><span class="sxs-lookup"><span data-stu-id="cb34a-107">\[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="cb34a-108">Este identificador es válido solo durante la devolución de llamada a la que se pasa.</span><span class="sxs-lookup"><span data-stu-id="cb34a-108">This handle is valid only during the callback to which it is passed.</span></span>

## <a name="remarks"></a><span data-ttu-id="cb34a-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cb34a-109">Remarks</span></span>  
 <span data-ttu-id="cb34a-110">El `FunctionEnter3WithInfo` método de devolución de llamada notifica al generador de perfiles cuando se llama a las funciones y permite al generador de perfiles usar el [método ICorProfilerInfo3:: GetFunctionEnter3Info (](icorprofilerinfo3-getfunctionenter3info-method.md) para inspeccionar los valores de argumento.</span><span class="sxs-lookup"><span data-stu-id="cb34a-110">The `FunctionEnter3WithInfo` callback method notifies the profiler as functions are called, and enables the profiler to use the [ICorProfilerInfo3::GetFunctionEnter3Info method](icorprofilerinfo3-getfunctionenter3info-method.md) to inspect argument values.</span></span> <span data-ttu-id="cb34a-111">Para tener acceso a la información de los argumentos, se debe `COR_PRF_ENABLE_FUNCTION_ARGS` establecer la marca.</span><span class="sxs-lookup"><span data-stu-id="cb34a-111">To access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag has to be set.</span></span> <span data-ttu-id="cb34a-112">El generador de perfiles puede utilizar el [método ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) para establecer las marcas de evento y, a continuación, usar el [método ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo (](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) para registrar la implementación de esta función.</span><span class="sxs-lookup"><span data-stu-id="cb34a-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="cb34a-113">La `FunctionEnter3WithInfo` función es una devolución de llamada; debe implementarla.</span><span class="sxs-lookup"><span data-stu-id="cb34a-113">The `FunctionEnter3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="cb34a-114">La implementación debe usar el `__declspec(naked)` atributo de clase de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="cb34a-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="cb34a-115">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="cb34a-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="cb34a-116">En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="cb34a-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="cb34a-117">Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="cb34a-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="cb34a-118">La implementación de `FunctionEnter3WithInfo` no debe bloquearse porque retrasará la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="cb34a-118">The implementation of `FunctionEnter3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="cb34a-119">La implementación no debe intentar una recolección de elementos no utilizados, porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="cb34a-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="cb34a-120">Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que se `FunctionEnter3WithInfo` devuelva.</span><span class="sxs-lookup"><span data-stu-id="cb34a-120">If a garbage collection is attempted, the runtime will block until `FunctionEnter3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="cb34a-121">La `FunctionEnter3WithInfo` función no debe llamar a código administrado ni producir una asignación de memoria administrada de ninguna manera.</span><span class="sxs-lookup"><span data-stu-id="cb34a-121">The `FunctionEnter3WithInfo` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb34a-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cb34a-122">Requirements</span></span>  
 <span data-ttu-id="cb34a-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb34a-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb34a-124">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="cb34a-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="cb34a-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb34a-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb34a-126">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb34a-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb34a-127">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="cb34a-127">See also</span></span>

- [<span data-ttu-id="cb34a-128">Getfunctionenter3info (</span><span class="sxs-lookup"><span data-stu-id="cb34a-128">GetFunctionEnter3Info</span></span>](icorprofilerinfo3-getfunctionenter3info-method.md)
- [<span data-ttu-id="cb34a-129">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="cb34a-129">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="cb34a-130">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="cb34a-130">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="cb34a-131">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="cb34a-131">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
