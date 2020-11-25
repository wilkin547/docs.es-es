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
ms.openlocfilehash: 4b6eb59dd771e4013106e6a77fc7475b77b2b007
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732026"
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a><span data-ttu-id="e1bcd-102">ICorProfilerCallback::RuntimeSuspendAborted (Método)</span><span class="sxs-lookup"><span data-stu-id="e1bcd-102">ICorProfilerCallback::RuntimeSuspendAborted Method</span></span>

<span data-ttu-id="e1bcd-103">Notifica al generador de perfiles que el Runtime ha anulado la suspensión en tiempo de ejecución que se estaba produciendo.</span><span class="sxs-lookup"><span data-stu-id="e1bcd-103">Notifies the profiler that the runtime has aborted the runtime suspension that was occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1bcd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e1bcd-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="e1bcd-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e1bcd-105">Remarks</span></span>  

 <span data-ttu-id="e1bcd-106">La suspensión en tiempo de ejecución se puede anular si dos subprocesos intentan suspender el tiempo de ejecución simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="e1bcd-106">The run-time suspension might be aborted if two threads simultaneously attempt to suspend the runtime.</span></span>  
  
 <span data-ttu-id="e1bcd-107">La devolución de llamada [ICorProfilerCallback:: RuntimeSuspendFinished (](icorprofilercallback-runtimesuspendfinished-method.md) o la `RuntimeSuspendAborted` devolución de llamada se producirán en un único subproceso después de una devolución de llamada [ICorProfilerCallback:: runtimesuspendstarted (](icorprofilercallback-runtimesuspendstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e1bcd-107">Either the [ICorProfilerCallback::RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) callback or the `RuntimeSuspendAborted` callback will occur on a single thread following a [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
 <span data-ttu-id="e1bcd-108">`RuntimeSuspendAborted`Se garantiza que la devolución de llamada se produce en el mismo subproceso que la `RuntimeSuspendStarted` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="e1bcd-108">The `RuntimeSuspendAborted` callback is guaranteed to occur on the same thread as the `RuntimeSuspendStarted` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1bcd-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e1bcd-109">Requirements</span></span>  

 <span data-ttu-id="e1bcd-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1bcd-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1bcd-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e1bcd-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e1bcd-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1bcd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1bcd-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1bcd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1bcd-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e1bcd-114">See also</span></span>

- [<span data-ttu-id="e1bcd-115">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1bcd-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
