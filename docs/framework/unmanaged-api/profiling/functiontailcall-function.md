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
# <a name="functiontailcall-function"></a><span data-ttu-id="ec8f4-102">FunctionTailcall (Función)</span><span class="sxs-lookup"><span data-stu-id="ec8f4-102">FunctionTailcall Function</span></span>
<span data-ttu-id="ec8f4-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span><span class="sxs-lookup"><span data-stu-id="ec8f4-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ec8f4-104">The `FunctionTailcall` function is deprecated in the .NET Framework version 2.0.</span><span class="sxs-lookup"><span data-stu-id="ec8f4-104">The `FunctionTailcall` function is deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="ec8f4-105">It will continue to work, but will incur a performance penalty.</span><span class="sxs-lookup"><span data-stu-id="ec8f4-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="ec8f4-106">Use the [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) function instead.</span><span class="sxs-lookup"><span data-stu-id="ec8f4-106">Use the [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec8f4-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec8f4-107">Syntax</span></span>  
  
```cpp
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec8f4-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ec8f4-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="ec8f4-109">[in] The identifier of the currently executing function that is about to make a tail call.</span><span class="sxs-lookup"><span data-stu-id="ec8f4-109">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec8f4-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ec8f4-110">Remarks</span></span>  
 <span data-ttu-id="ec8f4-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span><span class="sxs-lookup"><span data-stu-id="ec8f4-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="ec8f4-112">This means that a [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) callback will not be issued for a function that is the target of a tail call.</span><span class="sxs-lookup"><span data-stu-id="ec8f4-112">This means that a [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="ec8f4-113">The `FunctionTailcall` function is a callback; you must implement it.</span><span class="sxs-lookup"><span data-stu-id="ec8f4-113">The `FunctionTailcall` function is a callback; you must implement it.</span></span> <span data-ttu-id="ec8f4-114">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span><span class="sxs-lookup"><span data-stu-id="ec8f4-114">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="ec8f4-115">The execution engine does not save any registers before calling this function.</span><span class="sxs-lookup"><span data-stu-id="ec8f4-115">The execution engine does not save any registers before calling this function.</span></span>  
  
- <span data-ttu-id="ec8f4-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span><span class="sxs-lookup"><span data-stu-id="ec8f4-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
- <span data-ttu-id="ec8f4-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span><span class="sxs-lookup"><span data-stu-id="ec8f4-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="ec8f4-118">The implementation of `FunctionTailcall` should not block because it will delay garbage collection.</span><span class="sxs-lookup"><span data-stu-id="ec8f4-118">The implementation of `FunctionTailcall` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="ec8f4-119">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span><span class="sxs-lookup"><span data-stu-id="ec8f4-119">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="ec8f4-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall` returns.</span><span class="sxs-lookup"><span data-stu-id="ec8f4-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall` returns.</span></span>  
  
 <span data-ttu-id="ec8f4-121">Also, the `FunctionTailcall` function must not call into managed code or in any way cause a managed memory allocation.</span><span class="sxs-lookup"><span data-stu-id="ec8f4-121">Also, the `FunctionTailcall` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec8f4-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ec8f4-122">Requirements</span></span>  
 <span data-ttu-id="ec8f4-123">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec8f4-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec8f4-124">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="ec8f4-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="ec8f4-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec8f4-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec8f4-126">**.NET Framework Versions:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="ec8f4-126">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec8f4-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec8f4-127">See also</span></span>

- [<span data-ttu-id="ec8f4-128">FunctionEnter2 (Función)</span><span class="sxs-lookup"><span data-stu-id="ec8f4-128">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)
- [<span data-ttu-id="ec8f4-129">FunctionLeave2 (Función)</span><span class="sxs-lookup"><span data-stu-id="ec8f4-129">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [<span data-ttu-id="ec8f4-130">SetEnterLeaveFunctionHooks2 (método)</span><span class="sxs-lookup"><span data-stu-id="ec8f4-130">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [<span data-ttu-id="ec8f4-131">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="ec8f4-131">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
