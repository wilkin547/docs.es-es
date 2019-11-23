---
title: ICorProfilerCallback::ExceptionThrown (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionThrown
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionThrown
helpviewer_keywords:
- ExceptionThrown method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionThrown method [.NET Framework profiling]
ms.assetid: f1a23f3b-ac21-4905-8abf-8ea59f15af53
topic_type:
- apiref
ms.openlocfilehash: 4ecbe0ef3c3021c5633b9380da2eb31cf22aa4b1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445325"
---
# <a name="icorprofilercallbackexceptionthrown-method"></a><span data-ttu-id="e2beb-102">ICorProfilerCallback::ExceptionThrown (Método)</span><span class="sxs-lookup"><span data-stu-id="e2beb-102">ICorProfilerCallback::ExceptionThrown Method</span></span>
<span data-ttu-id="e2beb-103">Notifies the profiler that an exception has been thrown.</span><span class="sxs-lookup"><span data-stu-id="e2beb-103">Notifies the profiler that an exception has been thrown.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e2beb-104">This function is called only if the exception reaches managed code.</span><span class="sxs-lookup"><span data-stu-id="e2beb-104">This function is called only if the exception reaches managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2beb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2beb-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionThrown(  
    [in] ObjectID thrownObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2beb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e2beb-106">Parameters</span></span>  
 `thrownObjectId`  
 <span data-ttu-id="e2beb-107">[in] The ID of the object that caused the exception to be thrown.</span><span class="sxs-lookup"><span data-stu-id="e2beb-107">[in] The ID of the object that caused the exception to be thrown.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2beb-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e2beb-108">Remarks</span></span>  
 <span data-ttu-id="e2beb-109">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span><span class="sxs-lookup"><span data-stu-id="e2beb-109">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="e2beb-110">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span><span class="sxs-lookup"><span data-stu-id="e2beb-110">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="e2beb-111">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span><span class="sxs-lookup"><span data-stu-id="e2beb-111">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2beb-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e2beb-112">Requirements</span></span>  
 <span data-ttu-id="e2beb-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2beb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2beb-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e2beb-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e2beb-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2beb-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2beb-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2beb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2beb-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2beb-117">See also</span></span>

- [<span data-ttu-id="e2beb-118">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e2beb-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
