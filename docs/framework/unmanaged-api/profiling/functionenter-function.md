---
description: 'Más información acerca de: FunctionEnter ((función)'
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
ms.openlocfilehash: 07b91a81480e453be16e840b89fa822cb91002ba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788961"
---
# <a name="functionenter-function"></a><span data-ttu-id="5a3e1-103">FunctionEnter (Función)</span><span class="sxs-lookup"><span data-stu-id="5a3e1-103">FunctionEnter Function</span></span>

<span data-ttu-id="5a3e1-104">Notifica al generador de perfiles que el control se pasa a una función.</span><span class="sxs-lookup"><span data-stu-id="5a3e1-104">Notifies the profiler that control is being passed to a function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5a3e1-105">La `FunctionEnter` función está en desuso en la .NET Framework versión 2,0, y su uso implicará una penalización del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="5a3e1-105">The `FunctionEnter` function is deprecated in the .NET Framework version 2.0, and its use will incur a performance penalty.</span></span> <span data-ttu-id="5a3e1-106">En su lugar, use la función [FunctionEnter2](functionenter2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="5a3e1-106">Use the [FunctionEnter2](functionenter2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a3e1-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a3e1-107">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a3e1-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5a3e1-108">Parameters</span></span>

- `funcID`

  <span data-ttu-id="5a3e1-109">\[in] el identificador de la función a la que se pasa el control.</span><span class="sxs-lookup"><span data-stu-id="5a3e1-109">\[in] The identifier of the function to which control is passed.</span></span>

## <a name="remarks"></a><span data-ttu-id="5a3e1-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5a3e1-110">Remarks</span></span>  

 <span data-ttu-id="5a3e1-111">La `FunctionEnter` función es una devolución de llamada; debe implementarla.</span><span class="sxs-lookup"><span data-stu-id="5a3e1-111">The `FunctionEnter` function is a callback; you must implement it.</span></span> <span data-ttu-id="5a3e1-112">La implementación debe usar el `__declspec` `naked` atributo de clase de almacenamiento ().</span><span class="sxs-lookup"><span data-stu-id="5a3e1-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="5a3e1-113">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="5a3e1-113">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="5a3e1-114">En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="5a3e1-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="5a3e1-115">Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5a3e1-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="5a3e1-116">La implementación de `FunctionEnter` no debe bloquearse porque retrasará la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="5a3e1-116">The implementation of `FunctionEnter` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="5a3e1-117">La implementación no debe intentar una recolección de elementos no utilizados porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="5a3e1-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="5a3e1-118">Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que se `FunctionEnter` devuelva.</span><span class="sxs-lookup"><span data-stu-id="5a3e1-118">If a garbage collection is attempted, the runtime will block until `FunctionEnter` returns.</span></span>  
  
 <span data-ttu-id="5a3e1-119">Además, la `FunctionEnter` función no debe llamar a código administrado ni producir una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="5a3e1-119">Also, the `FunctionEnter` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a3e1-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a3e1-120">Requirements</span></span>  

 <span data-ttu-id="5a3e1-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a3e1-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a3e1-122">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="5a3e1-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="5a3e1-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a3e1-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a3e1-124">**.NET Framework versiones:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="5a3e1-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a3e1-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a3e1-125">See also</span></span>

- [<span data-ttu-id="5a3e1-126">FunctionEnter2 (Función)</span><span class="sxs-lookup"><span data-stu-id="5a3e1-126">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="5a3e1-127">FunctionLeave2 (Función)</span><span class="sxs-lookup"><span data-stu-id="5a3e1-127">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="5a3e1-128">FunctionTailcall2 (Función)</span><span class="sxs-lookup"><span data-stu-id="5a3e1-128">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="5a3e1-129">Método SetEnterLeaveFunctionHooks2</span><span class="sxs-lookup"><span data-stu-id="5a3e1-129">SetEnterLeaveFunctionHooks2 Method</span></span>](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="5a3e1-130">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="5a3e1-130">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
