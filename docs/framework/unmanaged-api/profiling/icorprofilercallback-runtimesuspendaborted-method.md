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
ms.openlocfilehash: 285bdd3f2a96d3c6cb0039382d9944e48c49971a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865914"
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a><span data-ttu-id="ddbf1-102">ICorProfilerCallback::RuntimeSuspendAborted (Método)</span><span class="sxs-lookup"><span data-stu-id="ddbf1-102">ICorProfilerCallback::RuntimeSuspendAborted Method</span></span>
<span data-ttu-id="ddbf1-103">Notifica al generador de perfiles que el Runtime ha anulado la suspensión en tiempo de ejecución que se estaba produciendo.</span><span class="sxs-lookup"><span data-stu-id="ddbf1-103">Notifies the profiler that the runtime has aborted the runtime suspension that was occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddbf1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ddbf1-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="ddbf1-105">Notas</span><span class="sxs-lookup"><span data-stu-id="ddbf1-105">Remarks</span></span>  
 <span data-ttu-id="ddbf1-106">La suspensión en tiempo de ejecución se puede anular si dos subprocesos intentan suspender el tiempo de ejecución simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="ddbf1-106">The run-time suspension might be aborted if two threads simultaneously attempt to suspend the runtime.</span></span>  
  
 <span data-ttu-id="ddbf1-107">La devolución de llamada [ICorProfilerCallback:: RuntimeSuspendFinished (](icorprofilercallback-runtimesuspendfinished-method.md) o la devolución de llamada `RuntimeSuspendAborted` se producirán en un único subproceso después de una devolución de llamada [ICorProfilerCallback:: runtimesuspendstarted (](icorprofilercallback-runtimesuspendstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ddbf1-107">Either the [ICorProfilerCallback::RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) callback or the `RuntimeSuspendAborted` callback will occur on a single thread following a [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
 <span data-ttu-id="ddbf1-108">Se garantiza que la devolución de llamada de `RuntimeSuspendAborted` se produce en el mismo subproceso que la devolución de llamada de `RuntimeSuspendStarted`.</span><span class="sxs-lookup"><span data-stu-id="ddbf1-108">The `RuntimeSuspendAborted` callback is guaranteed to occur on the same thread as the `RuntimeSuspendStarted` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddbf1-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="ddbf1-109">Requirements</span></span>  
 <span data-ttu-id="ddbf1-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ddbf1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddbf1-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ddbf1-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ddbf1-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ddbf1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ddbf1-113">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddbf1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddbf1-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ddbf1-114">See also</span></span>

- [<span data-ttu-id="ddbf1-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ddbf1-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
