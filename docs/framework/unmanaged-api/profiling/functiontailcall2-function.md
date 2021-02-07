---
description: 'Más información acerca de: FunctionTailcall2 (función)'
title: FunctionTailcall2 (Función)
ms.date: 03/30/2017
api_name:
- FunctionTailcall2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall2
helpviewer_keywords:
- FunctionTailcall2 function [.NET Framework profiling]
ms.assetid: 249f9892-b5a9-41e1-b329-28a925904df6
topic_type:
- apiref
ms.openlocfilehash: 03547537d43a76f26d6946666589f38ca4e02ec4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687433"
---
# <a name="functiontailcall2-function"></a><span data-ttu-id="d47c7-103">FunctionTailcall2 (Función)</span><span class="sxs-lookup"><span data-stu-id="d47c7-103">FunctionTailcall2 Function</span></span>

<span data-ttu-id="d47c7-104">Notifica al generador de perfiles que la función que se está ejecutando actualmente está a punto de realizar una llamada de cola a otra función y proporciona información sobre el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="d47c7-104">Notifies the profiler that the currently executing function is about to perform a tail call to another function and provides information about the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d47c7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d47c7-105">Syntax</span></span>  
  
```cpp
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,
    [in] UINT_PTR           clientData,
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d47c7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d47c7-106">Parameters</span></span>

- `funcId`

  <span data-ttu-id="d47c7-107">\[in] el identificador de la función que se ejecuta actualmente y que está a punto de realizar una llamada de cola.</span><span class="sxs-lookup"><span data-stu-id="d47c7-107">\[in] The identifier of the currently executing function that is about to make a tail call.</span></span>

- `clientData`

  <span data-ttu-id="d47c7-108">\[in] el identificador de la función reasignada, que el generador de perfiles especificó previamente a través de [FunctionIDMapper](functionidmapper-function.md), de la función que se ejecuta actualmente y que está a punto de realizar una llamada de cola.</span><span class="sxs-lookup"><span data-stu-id="d47c7-108">\[in] The remapped function identifier, which the profiler previously specified via [FunctionIDMapper](functionidmapper-function.md), of the currently executing function that is about to make a tail call.</span></span>
  
- `func`

  <span data-ttu-id="d47c7-109">\[en] un `COR_PRF_FRAME_INFO` valor que señala a la información sobre el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="d47c7-109">\[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>

  <span data-ttu-id="d47c7-110">El generador de perfiles debe tratarlo como un identificador opaco que se puede devolver al motor de ejecución en el método [ICorProfilerInfo2:: getfunctioninfo2 (](icorprofilerinfo2-getfunctioninfo2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d47c7-110">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>

## <a name="remarks"></a><span data-ttu-id="d47c7-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d47c7-111">Remarks</span></span>  

 <span data-ttu-id="d47c7-112">La función de destino de la llamada de cola usará el marco de pila actual y devolverá directamente al llamador de la función que realizó la llamada de cola.</span><span class="sxs-lookup"><span data-stu-id="d47c7-112">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="d47c7-113">Esto significa que no se emitirá una devolución de llamada de [FunctionLeave2](functionleave2-function.md) para una función que sea el destino de una llamada de cola.</span><span class="sxs-lookup"><span data-stu-id="d47c7-113">This means that a [FunctionLeave2](functionleave2-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="d47c7-114">El valor del `func` parámetro no es válido después de que la `FunctionTailcall2` función devuelva porque el valor puede cambiar o ser destruido.</span><span class="sxs-lookup"><span data-stu-id="d47c7-114">The value of the `func` parameter is not valid after the `FunctionTailcall2` function returns because the value may change or be destroyed.</span></span>  
  
 <span data-ttu-id="d47c7-115">La `FunctionTailcall2` función es una devolución de llamada; debe implementarla.</span><span class="sxs-lookup"><span data-stu-id="d47c7-115">The `FunctionTailcall2` function is a callback; you must implement it.</span></span> <span data-ttu-id="d47c7-116">La implementación debe usar el `__declspec` `naked` atributo de clase de almacenamiento ().</span><span class="sxs-lookup"><span data-stu-id="d47c7-116">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="d47c7-117">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="d47c7-117">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="d47c7-118">En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="d47c7-118">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="d47c7-119">Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d47c7-119">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="d47c7-120">La implementación de `FunctionTailcall2` no debe bloquearse porque retrasará la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="d47c7-120">The implementation of `FunctionTailcall2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="d47c7-121">La implementación no debe intentar una recolección de elementos no utilizados porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="d47c7-121">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="d47c7-122">Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que se `FunctionTailcall2` devuelva.</span><span class="sxs-lookup"><span data-stu-id="d47c7-122">If a garbage collection is attempted, the runtime will block until `FunctionTailcall2` returns.</span></span>  
  
 <span data-ttu-id="d47c7-123">Además, la `FunctionTailcall2` función no debe llamar a código administrado ni producir una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="d47c7-123">Also, the `FunctionTailcall2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d47c7-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d47c7-124">Requirements</span></span>  

 <span data-ttu-id="d47c7-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d47c7-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d47c7-126">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="d47c7-126">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="d47c7-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d47c7-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d47c7-128">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d47c7-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d47c7-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="d47c7-129">See also</span></span>

- [<span data-ttu-id="d47c7-130">FunctionEnter2 (Función)</span><span class="sxs-lookup"><span data-stu-id="d47c7-130">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="d47c7-131">FunctionLeave2 (Función)</span><span class="sxs-lookup"><span data-stu-id="d47c7-131">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="d47c7-132">Método SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="d47c7-132">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="d47c7-133">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="d47c7-133">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
