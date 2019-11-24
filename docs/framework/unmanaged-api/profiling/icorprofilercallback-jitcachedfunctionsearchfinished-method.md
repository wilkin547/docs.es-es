---
title: ICorProfilerCallback::JITCachedFunctionSearchFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCachedFunctionSearchFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCachedFunctionSearchFinished
helpviewer_keywords:
- JITCachedFunctionSearchFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchFinished method [.NET Framework profiling]
ms.assetid: 3c325c82-cddd-4b00-b3da-e450c36abf62
topic_type:
- apiref
ms.openlocfilehash: bea857f65081432eb3f5501c75af6d13805c76d7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426236"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchfinished-method"></a><span data-ttu-id="c308a-102">ICorProfilerCallback::JITCachedFunctionSearchFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="c308a-102">ICorProfilerCallback::JITCachedFunctionSearchFinished Method</span></span>
<span data-ttu-id="c308a-103">Notifies the profiler that a search has finished for a function that was compiled previously using the Native Image Generator (NGen.exe).</span><span class="sxs-lookup"><span data-stu-id="c308a-103">Notifies the profiler that a search has finished for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c308a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c308a-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCachedFunctionSearchFinished(  
    [in] FunctionID        functionId,  
    [in] COR_PRF_JIT_CACHE result);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c308a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c308a-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="c308a-106">[in] The ID of the function for which the search was performed.</span><span class="sxs-lookup"><span data-stu-id="c308a-106">[in] The ID of the function for which the search was performed.</span></span>  
  
 `result`  
 <span data-ttu-id="c308a-107">[in] A value of the [COR_PRF_JIT_CACHE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md) enumeration that indicates the result of the search.</span><span class="sxs-lookup"><span data-stu-id="c308a-107">[in] A value of the [COR_PRF_JIT_CACHE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md) enumeration that indicates the result of the search.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c308a-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c308a-108">Remarks</span></span>  
 <span data-ttu-id="c308a-109">In the .NET Framework version 2.0, the [ICorProfilerCallback::JITCachedFunctionSearchStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md) and `JITCachedFunctionSearchFinished` callbacks will not be made for all functions in regular NGen images.</span><span class="sxs-lookup"><span data-stu-id="c308a-109">In the .NET Framework version 2.0, the [ICorProfilerCallback::JITCachedFunctionSearchStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md) and `JITCachedFunctionSearchFinished` callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="c308a-110">Only NGen images optimized for a profiler will generate callbacks for all functions in the image.</span><span class="sxs-lookup"><span data-stu-id="c308a-110">Only NGen images optimized for a profiler will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="c308a-111">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="c308a-111">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="c308a-112">Otherwise, the profiler should use a lazy strategy for gathering function information.</span><span class="sxs-lookup"><span data-stu-id="c308a-112">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c308a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c308a-113">Requirements</span></span>  
 <span data-ttu-id="c308a-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c308a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c308a-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c308a-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c308a-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c308a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c308a-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c308a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c308a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c308a-118">See also</span></span>

- [<span data-ttu-id="c308a-119">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c308a-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
