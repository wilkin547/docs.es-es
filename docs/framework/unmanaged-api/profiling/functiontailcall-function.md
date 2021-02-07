---
description: 'Más información acerca de: FunctionTailcall ((función)'
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
ms.openlocfilehash: 8da3efde7d925fdb02232ca98662f8d6a6fd0adf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687316"
---
# <a name="functiontailcall-function"></a><span data-ttu-id="857ba-103">FunctionTailcall (Función)</span><span class="sxs-lookup"><span data-stu-id="857ba-103">FunctionTailcall Function</span></span>

<span data-ttu-id="857ba-104">Notifica al generador de perfiles que la función que se está ejecutando actualmente está a punto de realizar una llamada de cola a otra función.</span><span class="sxs-lookup"><span data-stu-id="857ba-104">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="857ba-105">La `FunctionTailcall` función está en desuso en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="857ba-105">The `FunctionTailcall` function is deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="857ba-106">Continuará funcionando, pero se producirá una reducción del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="857ba-106">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="857ba-107">En su lugar, use la función [FunctionTailcall2](functiontailcall2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="857ba-107">Use the [FunctionTailcall2](functiontailcall2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="857ba-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="857ba-108">Syntax</span></span>  
  
```cpp
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="857ba-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="857ba-109">Parameters</span></span>

- `funcID`

  <span data-ttu-id="857ba-110">\[in] el identificador de la función que se ejecuta actualmente y que está a punto de realizar una llamada de cola.</span><span class="sxs-lookup"><span data-stu-id="857ba-110">\[in] The identifier of the currently executing function that is about to make a tail call.</span></span>

## <a name="remarks"></a><span data-ttu-id="857ba-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="857ba-111">Remarks</span></span>  

 <span data-ttu-id="857ba-112">La función de destino de la llamada de cola usará el marco de pila actual y devolverá directamente al llamador de la función que realizó la llamada de cola.</span><span class="sxs-lookup"><span data-stu-id="857ba-112">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="857ba-113">Esto significa que no se emitirá una devolución de llamada de [FunctionLeave (](functionleave-function.md) para una función que sea el destino de una llamada de cola.</span><span class="sxs-lookup"><span data-stu-id="857ba-113">This means that a [FunctionLeave](functionleave-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="857ba-114">La `FunctionTailcall` función es una devolución de llamada; debe implementarla.</span><span class="sxs-lookup"><span data-stu-id="857ba-114">The `FunctionTailcall` function is a callback; you must implement it.</span></span> <span data-ttu-id="857ba-115">La implementación debe usar el `__declspec` `naked` atributo de clase de almacenamiento ().</span><span class="sxs-lookup"><span data-stu-id="857ba-115">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="857ba-116">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="857ba-116">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="857ba-117">En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="857ba-117">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="857ba-118">Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="857ba-118">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="857ba-119">La implementación de `FunctionTailcall` no debe bloquearse porque retrasará la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="857ba-119">The implementation of `FunctionTailcall` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="857ba-120">La implementación no debe intentar una recolección de elementos no utilizados porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="857ba-120">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="857ba-121">Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que se `FunctionTailcall` devuelva.</span><span class="sxs-lookup"><span data-stu-id="857ba-121">If a garbage collection is attempted, the runtime will block until `FunctionTailcall` returns.</span></span>  
  
 <span data-ttu-id="857ba-122">Además, la `FunctionTailcall` función no debe llamar a código administrado ni producir una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="857ba-122">Also, the `FunctionTailcall` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="857ba-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="857ba-123">Requirements</span></span>  

 <span data-ttu-id="857ba-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="857ba-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="857ba-125">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="857ba-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="857ba-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="857ba-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="857ba-127">**.NET Framework versiones:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="857ba-127">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="857ba-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="857ba-128">See also</span></span>

- [<span data-ttu-id="857ba-129">FunctionEnter2 (Función)</span><span class="sxs-lookup"><span data-stu-id="857ba-129">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="857ba-130">FunctionLeave2 (Función)</span><span class="sxs-lookup"><span data-stu-id="857ba-130">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="857ba-131">Método SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="857ba-131">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="857ba-132">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="857ba-132">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
