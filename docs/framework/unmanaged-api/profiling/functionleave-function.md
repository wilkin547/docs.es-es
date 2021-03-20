---
description: 'Más información acerca de: FunctionLeave ((función)'
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
ms.openlocfilehash: 619c1ecd92d2cc53512687d542becb3a2636b8af
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759500"
---
# <a name="functionleave-function"></a><span data-ttu-id="006ca-103">FunctionLeave (Función)</span><span class="sxs-lookup"><span data-stu-id="006ca-103">FunctionLeave Function</span></span>

<span data-ttu-id="006ca-104">Notifica al generador de perfiles que una función está a punto de volver al llamador.</span><span class="sxs-lookup"><span data-stu-id="006ca-104">Notifies the profiler that a function is about to return to the caller.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="006ca-105">La `FunctionLeave` función está en desuso en el .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="006ca-105">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span></span> <span data-ttu-id="006ca-106">Continuará funcionando, pero se producirá una reducción del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="006ca-106">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="006ca-107">En su lugar, use la función [FunctionLeave2](functionleave2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="006ca-107">Use the [FunctionLeave2](functionleave2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="006ca-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="006ca-108">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="006ca-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="006ca-109">Parameters</span></span>

<span data-ttu-id="006ca-110">`funcID` de El identificador de la función que devuelve.</span><span class="sxs-lookup"><span data-stu-id="006ca-110">`funcID` [in] The identifier of the function that is returning.</span></span>

## <a name="remarks"></a><span data-ttu-id="006ca-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="006ca-111">Remarks</span></span>  

 <span data-ttu-id="006ca-112">La `FunctionLeave` función es una devolución de llamada; debe implementarla.</span><span class="sxs-lookup"><span data-stu-id="006ca-112">The `FunctionLeave` function is a callback; you must implement it.</span></span> <span data-ttu-id="006ca-113">La implementación debe usar el `__declspec` `naked` atributo de clase de almacenamiento ().</span><span class="sxs-lookup"><span data-stu-id="006ca-113">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="006ca-114">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="006ca-114">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="006ca-115">En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="006ca-115">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="006ca-116">Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="006ca-116">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="006ca-117">La implementación de `FunctionLeave` no debe bloquearse porque retrasará la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="006ca-117">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="006ca-118">La implementación no debe intentar una recolección de elementos no utilizados porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="006ca-118">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="006ca-119">Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que se `FunctionLeave` devuelva.</span><span class="sxs-lookup"><span data-stu-id="006ca-119">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span></span>  
  
 <span data-ttu-id="006ca-120">Además, la `FunctionLeave` función no debe llamar a código administrado ni producir una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="006ca-120">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="006ca-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="006ca-121">Requirements</span></span>  

 <span data-ttu-id="006ca-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="006ca-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="006ca-123">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="006ca-123">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="006ca-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="006ca-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="006ca-125">**.NET Framework versiones:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="006ca-125">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="006ca-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="006ca-126">See also</span></span>

- [<span data-ttu-id="006ca-127">FunctionEnter2 (Función)</span><span class="sxs-lookup"><span data-stu-id="006ca-127">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="006ca-128">FunctionLeave2 (Función)</span><span class="sxs-lookup"><span data-stu-id="006ca-128">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="006ca-129">FunctionTailcall2 (Función)</span><span class="sxs-lookup"><span data-stu-id="006ca-129">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="006ca-130">Método SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="006ca-130">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="006ca-131">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="006ca-131">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
