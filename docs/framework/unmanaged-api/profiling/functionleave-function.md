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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 238a5f19bd8cbd89a5537b2b9297bfa9e1f54613
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952884"
---
# <a name="functionleave-function"></a><span data-ttu-id="d9114-102">FunctionLeave (Función)</span><span class="sxs-lookup"><span data-stu-id="d9114-102">FunctionLeave Function</span></span>
<span data-ttu-id="d9114-103">Notifica al generador de perfiles que una función está a punto de volver al llamador.</span><span class="sxs-lookup"><span data-stu-id="d9114-103">Notifies the profiler that a function is about to return to the caller.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d9114-104">La `FunctionLeave` función está en desuso en el .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="d9114-104">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span></span> <span data-ttu-id="d9114-105">Continuará funcionando, pero se producirá una reducción del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="d9114-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="d9114-106">En su lugar, use la función [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="d9114-106">Use the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9114-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9114-107">Syntax</span></span>  
  
```cpp  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9114-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d9114-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="d9114-109">de El identificador de la función que devuelve.</span><span class="sxs-lookup"><span data-stu-id="d9114-109">[in] The identifier of the function that is returning.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9114-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d9114-110">Remarks</span></span>  
 <span data-ttu-id="d9114-111">La `FunctionLeave` función es una devolución de llamada; debe implementarla.</span><span class="sxs-lookup"><span data-stu-id="d9114-111">The `FunctionLeave` function is a callback; you must implement it.</span></span> <span data-ttu-id="d9114-112">La implementación debe usar el `__declspec`atributo`naked`de clase de almacenamiento ().</span><span class="sxs-lookup"><span data-stu-id="d9114-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="d9114-113">El motor de ejecución no guarda ningún registro antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="d9114-113">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="d9114-114">En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="d9114-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="d9114-115">Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d9114-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="d9114-116">La implementación de `FunctionLeave` no debe bloquearse porque retrasará la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="d9114-116">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="d9114-117">La implementación no debe intentar una recolección de elementos no utilizados porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="d9114-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="d9114-118">Si se intenta realizar una recolección de elementos no utilizados, el `FunctionLeave` tiempo de ejecución se bloqueará hasta que se devuelva.</span><span class="sxs-lookup"><span data-stu-id="d9114-118">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span></span>  
  
 <span data-ttu-id="d9114-119">Además, la `FunctionLeave` función no debe llamar a código administrado ni producir una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="d9114-119">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9114-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d9114-120">Requirements</span></span>  
 <span data-ttu-id="d9114-121">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9114-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9114-122">**Encabezado**: CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="d9114-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="d9114-123">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9114-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9114-124">**.NET Framework versiones:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="d9114-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9114-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9114-125">See also</span></span>

- [<span data-ttu-id="d9114-126">FunctionEnter2 (Función)</span><span class="sxs-lookup"><span data-stu-id="d9114-126">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="d9114-127">FunctionLeave2 (Función)</span><span class="sxs-lookup"><span data-stu-id="d9114-127">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="d9114-128">FunctionTailcall2 (Función)</span><span class="sxs-lookup"><span data-stu-id="d9114-128">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [<span data-ttu-id="d9114-129">SetEnterLeaveFunctionHooks2 (método)</span><span class="sxs-lookup"><span data-stu-id="d9114-129">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="d9114-130">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="d9114-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
