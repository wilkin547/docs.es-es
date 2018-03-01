---
title: "ICorProfilerCallback::RuntimeSuspendAborted (Método)"
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4d62df6fc90a2601997aeb7ecbe410f1a35d7012
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a><span data-ttu-id="3ca28-102">ICorProfilerCallback::RuntimeSuspendAborted (Método)</span><span class="sxs-lookup"><span data-stu-id="3ca28-102">ICorProfilerCallback::RuntimeSuspendAborted Method</span></span>
<span data-ttu-id="3ca28-103">Notifica al generador de perfiles que el tiempo de ejecución ha anulado la suspensión en tiempo de ejecución que se estaba produciendo.</span><span class="sxs-lookup"><span data-stu-id="3ca28-103">Notifies the profiler that the runtime has aborted the runtime suspension that was occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ca28-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3ca28-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="3ca28-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3ca28-105">Remarks</span></span>  
 <span data-ttu-id="3ca28-106">La suspensión de tiempo de ejecución se podría anular si dos subprocesos intentan suspender el tiempo de ejecución al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="3ca28-106">The run-time suspension might be aborted if two threads simultaneously attempt to suspend the runtime.</span></span>  
  
 <span data-ttu-id="3ca28-107">Ya sea la [ICorProfilerCallback:: RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) devolución de llamada o el `RuntimeSuspendAborted` devolución de llamada se producirá en una continuación de subproceso único un [ICorProfilerCallback:: RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="3ca28-107">Either the [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) callback or the `RuntimeSuspendAborted` callback will occur on a single thread following a [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
 <span data-ttu-id="3ca28-108">El `RuntimeSuspendAborted` devolución de llamada se garantiza que se producen en el mismo subproceso que el `RuntimeSuspendStarted` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="3ca28-108">The `RuntimeSuspendAborted` callback is guaranteed to occur on the same thread as the `RuntimeSuspendStarted` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ca28-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3ca28-109">Requirements</span></span>  
 <span data-ttu-id="3ca28-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ca28-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ca28-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3ca28-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3ca28-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ca28-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ca28-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ca28-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ca28-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ca28-114">See Also</span></span>  
 [<span data-ttu-id="3ca28-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3ca28-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
