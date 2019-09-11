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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 12ec27277fe57bd1a291c2cfe491ea2c6f40c30e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70851162"
---
# <a name="functiontailcall-function"></a><span data-ttu-id="a588e-102">FunctionTailcall (Función)</span><span class="sxs-lookup"><span data-stu-id="a588e-102">FunctionTailcall Function</span></span>
<span data-ttu-id="a588e-103">Notifica al generador de perfiles que la función que se está ejecutando actualmente está a punto de realizar una llamada de cola a otra función.</span><span class="sxs-lookup"><span data-stu-id="a588e-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a588e-104">La `FunctionTailcall` función está en desuso en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="a588e-104">The `FunctionTailcall` function is deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="a588e-105">Continuará funcionando, pero se producirá una reducción del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="a588e-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="a588e-106">En su lugar, use la función [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="a588e-106">Use the [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a588e-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a588e-107">Syntax</span></span>  
  
```cpp
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a588e-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a588e-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="a588e-109">de Identificador de la función que se ejecuta actualmente y que está a punto de realizar una llamada de cola.</span><span class="sxs-lookup"><span data-stu-id="a588e-109">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a588e-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a588e-110">Remarks</span></span>  
 <span data-ttu-id="a588e-111">La función de destino de la llamada de cola usará el marco de pila actual y devolverá directamente al llamador de la función que realizó la llamada de cola.</span><span class="sxs-lookup"><span data-stu-id="a588e-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="a588e-112">Esto significa que no se emitirá una devolución de llamada de [FunctionLeave (](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) para una función que sea el destino de una llamada de cola.</span><span class="sxs-lookup"><span data-stu-id="a588e-112">This means that a [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="a588e-113">La `FunctionTailcall` función es una devolución de llamada; debe implementarla.</span><span class="sxs-lookup"><span data-stu-id="a588e-113">The `FunctionTailcall` function is a callback; you must implement it.</span></span> <span data-ttu-id="a588e-114">La implementación debe usar el `__declspec`atributo`naked`de clase de almacenamiento ().</span><span class="sxs-lookup"><span data-stu-id="a588e-114">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="a588e-115">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="a588e-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="a588e-116">En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="a588e-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="a588e-117">Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a588e-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="a588e-118">La implementación de `FunctionTailcall` no debe bloquearse porque retrasará la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a588e-118">The implementation of `FunctionTailcall` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="a588e-119">La implementación no debe intentar una recolección de elementos no utilizados porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a588e-119">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="a588e-120">Si se intenta realizar una recolección de elementos no utilizados, el `FunctionTailcall` tiempo de ejecución se bloqueará hasta que se devuelva.</span><span class="sxs-lookup"><span data-stu-id="a588e-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall` returns.</span></span>  
  
 <span data-ttu-id="a588e-121">Además, la `FunctionTailcall` función no debe llamar a código administrado ni producir una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="a588e-121">Also, the `FunctionTailcall` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a588e-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a588e-122">Requirements</span></span>  
 <span data-ttu-id="a588e-123">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a588e-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a588e-124">**Encabezado**: CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="a588e-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="a588e-125">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a588e-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a588e-126">**.NET Framework versiones:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="a588e-126">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a588e-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="a588e-127">See also</span></span>

- [<span data-ttu-id="a588e-128">FunctionEnter2 (Función)</span><span class="sxs-lookup"><span data-stu-id="a588e-128">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="a588e-129">FunctionLeave2 (Función)</span><span class="sxs-lookup"><span data-stu-id="a588e-129">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="a588e-130">SetEnterLeaveFunctionHooks2 (método)</span><span class="sxs-lookup"><span data-stu-id="a588e-130">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="a588e-131">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a588e-131">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
