---
title: FunctionEnter (Función)
ms.date: 03/30/2017
api_name:
- FunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter
helpviewer_keywords:
- FunctionEnter function [.NET Framework profiling]
ms.assetid: bf4ffa50-4506-4dd4-aa13-a0457b47ca74
topic_type:
- apiref
ms.openlocfilehash: 9bc88d7dd5b00213da634dc9f511cfe0d39b42f1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729842"
---
# <a name="functionenter-function"></a><span data-ttu-id="89496-102">FunctionEnter (Función)</span><span class="sxs-lookup"><span data-stu-id="89496-102">FunctionEnter Function</span></span>

<span data-ttu-id="89496-103">Notifica al generador de perfiles que el control se pasa a una función.</span><span class="sxs-lookup"><span data-stu-id="89496-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="89496-104">La `FunctionEnter` función está en desuso en la .NET Framework versión 2,0, y su uso implicará una penalización del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="89496-104">The `FunctionEnter` function is deprecated in the .NET Framework version 2.0, and its use will incur a performance penalty.</span></span> <span data-ttu-id="89496-105">En su lugar, use la función [FunctionEnter2](functionenter2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="89496-105">Use the [FunctionEnter2](functionenter2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89496-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89496-106">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89496-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="89496-107">Parameters</span></span>

- `funcID`

  <span data-ttu-id="89496-108">\[in] el identificador de la función a la que se pasa el control.</span><span class="sxs-lookup"><span data-stu-id="89496-108">\[in] The identifier of the function to which control is passed.</span></span>

## <a name="remarks"></a><span data-ttu-id="89496-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="89496-109">Remarks</span></span>  

 <span data-ttu-id="89496-110">La `FunctionEnter` función es una devolución de llamada; debe implementarla.</span><span class="sxs-lookup"><span data-stu-id="89496-110">The `FunctionEnter` function is a callback; you must implement it.</span></span> <span data-ttu-id="89496-111">La implementación debe usar el `__declspec` `naked` atributo de clase de almacenamiento ().</span><span class="sxs-lookup"><span data-stu-id="89496-111">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="89496-112">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="89496-112">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="89496-113">En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="89496-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="89496-114">Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="89496-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="89496-115">La implementación de `FunctionEnter` no debe bloquearse porque retrasará la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="89496-115">The implementation of `FunctionEnter` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="89496-116">La implementación no debe intentar una recolección de elementos no utilizados porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="89496-116">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="89496-117">Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que se `FunctionEnter` devuelva.</span><span class="sxs-lookup"><span data-stu-id="89496-117">If a garbage collection is attempted, the runtime will block until `FunctionEnter` returns.</span></span>  
  
 <span data-ttu-id="89496-118">Además, la `FunctionEnter` función no debe llamar a código administrado ni producir una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="89496-118">Also, the `FunctionEnter` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89496-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="89496-119">Requirements</span></span>  

 <span data-ttu-id="89496-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89496-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89496-121">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="89496-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="89496-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89496-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89496-123">**.NET Framework versiones:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="89496-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89496-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="89496-124">See also</span></span>

- [<span data-ttu-id="89496-125">FunctionEnter2 (Función)</span><span class="sxs-lookup"><span data-stu-id="89496-125">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="89496-126">FunctionLeave2 (Función)</span><span class="sxs-lookup"><span data-stu-id="89496-126">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="89496-127">FunctionTailcall2 (Función)</span><span class="sxs-lookup"><span data-stu-id="89496-127">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="89496-128">Método SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="89496-128">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="89496-129">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="89496-129">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
