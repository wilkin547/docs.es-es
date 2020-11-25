---
title: FunctionLeave (Función)
ms.date: 03/30/2017
api_name:
- FunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave
helpviewer_keywords:
- FunctionLeave function [.NET Framework profiling]
ms.assetid: 18e89f45-e068-426a-be16-9f53a4346860
topic_type:
- apiref
ms.openlocfilehash: 13636da9c3e8ac4aa9e8dc1fa02b2e33afef4717
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722263"
---
# <a name="functionleave-function"></a><span data-ttu-id="74477-102">FunctionLeave (Función)</span><span class="sxs-lookup"><span data-stu-id="74477-102">FunctionLeave Function</span></span>

<span data-ttu-id="74477-103">Notifica al generador de perfiles que una función está a punto de volver al llamador.</span><span class="sxs-lookup"><span data-stu-id="74477-103">Notifies the profiler that a function is about to return to the caller.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="74477-104">La `FunctionLeave` función está en desuso en el .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="74477-104">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span></span> <span data-ttu-id="74477-105">Continuará funcionando, pero se producirá una reducción del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="74477-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="74477-106">En su lugar, use la función [FunctionLeave2](functionleave2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="74477-106">Use the [FunctionLeave2](functionleave2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74477-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74477-107">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74477-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="74477-108">Parameters</span></span>

- `funcID`

  <span data-ttu-id="74477-109">\[in] el identificador de la función que devuelve.</span><span class="sxs-lookup"><span data-stu-id="74477-109">\[in] The identifier of the function that is returning.</span></span>

## <a name="remarks"></a><span data-ttu-id="74477-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="74477-110">Remarks</span></span>  

 <span data-ttu-id="74477-111">La `FunctionLeave` función es una devolución de llamada; debe implementarla.</span><span class="sxs-lookup"><span data-stu-id="74477-111">The `FunctionLeave` function is a callback; you must implement it.</span></span> <span data-ttu-id="74477-112">La implementación debe usar el `__declspec` `naked` atributo de clase de almacenamiento ().</span><span class="sxs-lookup"><span data-stu-id="74477-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="74477-113">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="74477-113">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="74477-114">En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="74477-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="74477-115">Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="74477-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="74477-116">La implementación de `FunctionLeave` no debe bloquearse porque retrasará la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="74477-116">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="74477-117">La implementación no debe intentar una recolección de elementos no utilizados porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="74477-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="74477-118">Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que se `FunctionLeave` devuelva.</span><span class="sxs-lookup"><span data-stu-id="74477-118">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span></span>  
  
 <span data-ttu-id="74477-119">Además, la `FunctionLeave` función no debe llamar a código administrado ni producir una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="74477-119">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74477-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74477-120">Requirements</span></span>  

 <span data-ttu-id="74477-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74477-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74477-122">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="74477-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="74477-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74477-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74477-124">**.NET Framework versiones:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="74477-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74477-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="74477-125">See also</span></span>

- [<span data-ttu-id="74477-126">FunctionEnter2 (Función)</span><span class="sxs-lookup"><span data-stu-id="74477-126">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="74477-127">FunctionLeave2 (Función)</span><span class="sxs-lookup"><span data-stu-id="74477-127">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="74477-128">FunctionTailcall2 (Función)</span><span class="sxs-lookup"><span data-stu-id="74477-128">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="74477-129">Método SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="74477-129">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="74477-130">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="74477-130">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
