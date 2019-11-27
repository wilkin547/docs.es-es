---
title: FunctionTailcall (Función)
ms.date: 03/30/2017
api_name:
- FunctionTailcall
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall
helpviewer_keywords:
- FunctionTailcall function [.NET Framework profiling]
ms.assetid: 66347e03-9a97-41e8-8f9d-89b80803f7b5
topic_type:
- apiref
ms.openlocfilehash: c83a55a74542d94559b50b89ef784de0bd55d0db
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427350"
---
# <a name="functiontailcall-function"></a><span data-ttu-id="54dbc-102">FunctionTailcall (Función)</span><span class="sxs-lookup"><span data-stu-id="54dbc-102">FunctionTailcall Function</span></span>
<span data-ttu-id="54dbc-103">Notifica al generador de perfiles que la función que se está ejecutando actualmente está a punto de realizar una llamada de cola a otra función.</span><span class="sxs-lookup"><span data-stu-id="54dbc-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="54dbc-104">La función `FunctionTailcall` está en desuso en la versión 2,0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="54dbc-104">The `FunctionTailcall` function is deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="54dbc-105">Continuará funcionando, pero se producirá una reducción del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="54dbc-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="54dbc-106">En su lugar, use la función [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="54dbc-106">Use the [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54dbc-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54dbc-107">Syntax</span></span>  
  
```cpp
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54dbc-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="54dbc-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="54dbc-109">de Identificador de la función que se ejecuta actualmente y que está a punto de realizar una llamada de cola.</span><span class="sxs-lookup"><span data-stu-id="54dbc-109">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54dbc-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="54dbc-110">Remarks</span></span>  
 <span data-ttu-id="54dbc-111">La función de destino de la llamada de cola usará el marco de pila actual y devolverá directamente al llamador de la función que realizó la llamada de cola.</span><span class="sxs-lookup"><span data-stu-id="54dbc-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="54dbc-112">Esto significa que no se emitirá una devolución de llamada de [FunctionLeave (](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) para una función que sea el destino de una llamada de cola.</span><span class="sxs-lookup"><span data-stu-id="54dbc-112">This means that a [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="54dbc-113">La función `FunctionTailcall` es una devolución de llamada; debe implementarla.</span><span class="sxs-lookup"><span data-stu-id="54dbc-113">The `FunctionTailcall` function is a callback; you must implement it.</span></span> <span data-ttu-id="54dbc-114">La implementación debe usar el atributo de clase de almacenamiento `__declspec`(`naked`).</span><span class="sxs-lookup"><span data-stu-id="54dbc-114">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="54dbc-115">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="54dbc-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="54dbc-116">En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="54dbc-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="54dbc-117">Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="54dbc-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="54dbc-118">La implementación de `FunctionTailcall` no debe bloquearse porque retrasará la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="54dbc-118">The implementation of `FunctionTailcall` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="54dbc-119">La implementación no debe intentar una recolección de elementos no utilizados porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="54dbc-119">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="54dbc-120">Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que `FunctionTailcall` devuelva.</span><span class="sxs-lookup"><span data-stu-id="54dbc-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall` returns.</span></span>  
  
 <span data-ttu-id="54dbc-121">Además, la función `FunctionTailcall` no debe llamar a código administrado ni producir una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="54dbc-121">Also, the `FunctionTailcall` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54dbc-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="54dbc-122">Requirements</span></span>  
 <span data-ttu-id="54dbc-123">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54dbc-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54dbc-124">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="54dbc-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="54dbc-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54dbc-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54dbc-126">**.NET Framework versiones:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="54dbc-126">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54dbc-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="54dbc-127">See also</span></span>

- [<span data-ttu-id="54dbc-128">FunctionEnter2 (Función)</span><span class="sxs-lookup"><span data-stu-id="54dbc-128">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="54dbc-129">FunctionLeave2 (Función)</span><span class="sxs-lookup"><span data-stu-id="54dbc-129">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="54dbc-130">SetEnterLeaveFunctionHooks2 (método)</span><span class="sxs-lookup"><span data-stu-id="54dbc-130">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="54dbc-131">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="54dbc-131">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
