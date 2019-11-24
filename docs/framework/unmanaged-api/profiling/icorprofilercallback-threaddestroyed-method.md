---
title: ICorProfilerCallback::ThreadDestroyed (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadDestroyed
helpviewer_keywords:
- ThreadDestroyed method [.NET Framework profiling]
- ICorProfilerCallback::ThreadDestroyed method [.NET Framework profiling]
ms.assetid: 4c2b66fd-0595-40a3-8931-f9c4fff97ac8
topic_type:
- apiref
ms.openlocfilehash: 35b87b3a2c0230b26fb68af44dc1aa864a6449e0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439930"
---
# <a name="icorprofilercallbackthreaddestroyed-method"></a><span data-ttu-id="087a8-102">ICorProfilerCallback::ThreadDestroyed (Método)</span><span class="sxs-lookup"><span data-stu-id="087a8-102">ICorProfilerCallback::ThreadDestroyed Method</span></span>
<span data-ttu-id="087a8-103">Notifies the profiler that a thread has been destroyed.</span><span class="sxs-lookup"><span data-stu-id="087a8-103">Notifies the profiler that a thread has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="087a8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="087a8-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadDestroyed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="087a8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="087a8-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="087a8-106">[in] The ID of the thread that has been destroyed.</span><span class="sxs-lookup"><span data-stu-id="087a8-106">[in] The ID of the thread that has been destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="087a8-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="087a8-107">Remarks</span></span>  
 <span data-ttu-id="087a8-108">The `threadId` value is no longer valid at the time of this call.</span><span class="sxs-lookup"><span data-stu-id="087a8-108">The `threadId` value is no longer valid at the time of this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="087a8-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="087a8-109">Requirements</span></span>  
 <span data-ttu-id="087a8-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="087a8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="087a8-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="087a8-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="087a8-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="087a8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="087a8-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="087a8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="087a8-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="087a8-114">See also</span></span>

- [<span data-ttu-id="087a8-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="087a8-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="087a8-116">ThreadCreated (método)</span><span class="sxs-lookup"><span data-stu-id="087a8-116">ThreadCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)
