---
title: "FunctionTailcall (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 223f112ba405e29b800456adca2f83e0cef6e7b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="functiontailcall-function"></a><span data-ttu-id="8981a-102">FunctionTailcall (Función)</span><span class="sxs-lookup"><span data-stu-id="8981a-102">FunctionTailcall Function</span></span>
<span data-ttu-id="8981a-103">Notifica al generador de perfiles que la función en ejecución está a punto de realizar una llamada de cola a otra función.</span><span class="sxs-lookup"><span data-stu-id="8981a-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8981a-104">El `FunctionTailcall` función está desusada en la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8981a-104">The `FunctionTailcall` function is deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="8981a-105">Seguirán funcionando, pero se le cobrará una reducción del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="8981a-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="8981a-106">Use la [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) funcione en su lugar.</span><span class="sxs-lookup"><span data-stu-id="8981a-106">Use the [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8981a-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8981a-107">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8981a-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8981a-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="8981a-109">[in] El identificador de la función en ejecución que se va a realizar una cola llamada.</span><span class="sxs-lookup"><span data-stu-id="8981a-109">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8981a-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8981a-110">Remarks</span></span>  
 <span data-ttu-id="8981a-111">La función de destino de la llamada de cola usará el marco de pila actual y devolverá directamente al autor de llamada de la función que realizó el final de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8981a-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="8981a-112">Esto significa que un [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) devolución de llamada no se emitirá para una función que es el destino de una llamada de cola.</span><span class="sxs-lookup"><span data-stu-id="8981a-112">This means that a [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="8981a-113">El `FunctionTailcall` función es una devolución de llamada; debe implementar.</span><span class="sxs-lookup"><span data-stu-id="8981a-113">The `FunctionTailcall` function is a callback; you must implement it.</span></span> <span data-ttu-id="8981a-114">La implementación debe utilizar el `__declspec`(`naked`) el atributo de clase de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="8981a-114">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="8981a-115">El motor de ejecución no guardan los registros antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="8981a-115">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="8981a-116">En la entrada, debe guardar todos los registros que utilice, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="8981a-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="8981a-117">Al salir, debe restablecer la pila desactivando todos los parámetros que se han insertados por el llamador.</span><span class="sxs-lookup"><span data-stu-id="8981a-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="8981a-118">La implementación de `FunctionTailcall` no debe bloquearse porque retrasará la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="8981a-118">The implementation of `FunctionTailcall` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="8981a-119">La implementación no debería intentar una recolección porque la pila no puede estar en un estado compatible con la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="8981a-119">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="8981a-120">Si se intenta realizar una recolección, el tiempo de ejecución se bloqueará hasta que `FunctionTailcall` devuelve.</span><span class="sxs-lookup"><span data-stu-id="8981a-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall` returns.</span></span>  
  
 <span data-ttu-id="8981a-121">Además, la `FunctionTailcall` función no debe llamar a código administrado o en modo alguno provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="8981a-121">Also, the `FunctionTailcall` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8981a-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8981a-122">Requirements</span></span>  
 <span data-ttu-id="8981a-123">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8981a-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8981a-124">**Encabezado:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="8981a-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="8981a-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8981a-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8981a-126">**Versiones de .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="8981a-126">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8981a-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="8981a-127">See Also</span></span>  
 [<span data-ttu-id="8981a-128">FunctionEnter2 (Función)</span><span class="sxs-lookup"><span data-stu-id="8981a-128">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [<span data-ttu-id="8981a-129">FunctionLeave2 (Función)</span><span class="sxs-lookup"><span data-stu-id="8981a-129">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [<span data-ttu-id="8981a-130">SetEnterLeaveFunctionHooks2 (método)</span><span class="sxs-lookup"><span data-stu-id="8981a-130">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [<span data-ttu-id="8981a-131">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="8981a-131">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
