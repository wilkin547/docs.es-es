---
title: ICorProfilerCallback::RuntimeSuspendAborted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendAborted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted method [.NET Framework profiling]
- RuntimeSuspendAborted method [.NET Framework profiling]
ms.assetid: 5a8a4277-345b-448b-a028-fc8cff9998aa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e9aaf7325b8e7e65aa98904513cc7efe94e35087
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041813"
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a><span data-ttu-id="416b1-102">ICorProfilerCallback::RuntimeSuspendAborted (Método)</span><span class="sxs-lookup"><span data-stu-id="416b1-102">ICorProfilerCallback::RuntimeSuspendAborted Method</span></span>
<span data-ttu-id="416b1-103">Notifica al generador de perfiles que el tiempo de ejecución ha anulado la suspensión en tiempo de ejecución que se está produciendo.</span><span class="sxs-lookup"><span data-stu-id="416b1-103">Notifies the profiler that the runtime has aborted the runtime suspension that was occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="416b1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="416b1-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="416b1-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="416b1-105">Remarks</span></span>  
 <span data-ttu-id="416b1-106">Si dos subprocesos intentan suspender el tiempo de ejecución al mismo tiempo, se podría anular la suspensión de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="416b1-106">The run-time suspension might be aborted if two threads simultaneously attempt to suspend the runtime.</span></span>  
  
 <span data-ttu-id="416b1-107">Ya sea el [RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) devolución de llamada o el `RuntimeSuspendAborted` se producirá la devolución de llamada siguiente a un único subproceso un [RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="416b1-107">Either the [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) callback or the `RuntimeSuspendAborted` callback will occur on a single thread following a [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
 <span data-ttu-id="416b1-108">El `RuntimeSuspendAborted` devolución de llamada se garantiza que se producen en el mismo subproceso que la `RuntimeSuspendStarted` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="416b1-108">The `RuntimeSuspendAborted` callback is guaranteed to occur on the same thread as the `RuntimeSuspendStarted` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="416b1-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="416b1-109">Requirements</span></span>  
 <span data-ttu-id="416b1-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="416b1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="416b1-111">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="416b1-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="416b1-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="416b1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="416b1-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="416b1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="416b1-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="416b1-114">See also</span></span>

- [<span data-ttu-id="416b1-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="416b1-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
