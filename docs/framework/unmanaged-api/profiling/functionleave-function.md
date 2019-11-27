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
ms.openlocfilehash: 774a5d4e48f00ea8c28977f3f685dcd5a8da3199
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440590"
---
# <a name="functionleave-function"></a><span data-ttu-id="22e1d-102">FunctionLeave (Función)</span><span class="sxs-lookup"><span data-stu-id="22e1d-102">FunctionLeave Function</span></span>
<span data-ttu-id="22e1d-103">Notifica al generador de perfiles que una función está a punto de volver al llamador.</span><span class="sxs-lookup"><span data-stu-id="22e1d-103">Notifies the profiler that a function is about to return to the caller.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="22e1d-104">La función `FunctionLeave` está en desuso en el .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="22e1d-104">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span></span> <span data-ttu-id="22e1d-105">Continuará funcionando, pero se producirá una reducción del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="22e1d-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="22e1d-106">En su lugar, use la función [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="22e1d-106">Use the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22e1d-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="22e1d-107">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22e1d-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="22e1d-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="22e1d-109">de El identificador de la función que devuelve.</span><span class="sxs-lookup"><span data-stu-id="22e1d-109">[in] The identifier of the function that is returning.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22e1d-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="22e1d-110">Remarks</span></span>  
 <span data-ttu-id="22e1d-111">La función `FunctionLeave` es una devolución de llamada; debe implementarla.</span><span class="sxs-lookup"><span data-stu-id="22e1d-111">The `FunctionLeave` function is a callback; you must implement it.</span></span> <span data-ttu-id="22e1d-112">La implementación debe usar el atributo de clase de almacenamiento `__declspec`(`naked`).</span><span class="sxs-lookup"><span data-stu-id="22e1d-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="22e1d-113">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="22e1d-113">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="22e1d-114">En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="22e1d-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="22e1d-115">Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="22e1d-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="22e1d-116">La implementación de `FunctionLeave` no debe bloquearse porque retrasará la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="22e1d-116">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="22e1d-117">La implementación no debe intentar una recolección de elementos no utilizados porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="22e1d-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="22e1d-118">Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que `FunctionLeave` devuelva.</span><span class="sxs-lookup"><span data-stu-id="22e1d-118">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span></span>  
  
 <span data-ttu-id="22e1d-119">Además, la función `FunctionLeave` no debe llamar a código administrado ni producir una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="22e1d-119">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22e1d-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="22e1d-120">Requirements</span></span>  
 <span data-ttu-id="22e1d-121">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22e1d-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22e1d-122">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="22e1d-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="22e1d-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22e1d-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22e1d-124">**.NET Framework versiones:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="22e1d-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22e1d-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="22e1d-125">See also</span></span>

- [<span data-ttu-id="22e1d-126">FunctionEnter2 (Función)</span><span class="sxs-lookup"><span data-stu-id="22e1d-126">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="22e1d-127">FunctionLeave2 (Función)</span><span class="sxs-lookup"><span data-stu-id="22e1d-127">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="22e1d-128">FunctionTailcall2 (Función)</span><span class="sxs-lookup"><span data-stu-id="22e1d-128">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="22e1d-129">SetEnterLeaveFunctionHooks2 (método)</span><span class="sxs-lookup"><span data-stu-id="22e1d-129">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="22e1d-130">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="22e1d-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
