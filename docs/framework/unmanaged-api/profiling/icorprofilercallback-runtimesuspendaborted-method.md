---
description: 'Más información sobre: ICorProfilerCallback:: RuntimeSuspendAborted ((método)'
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
ms.openlocfilehash: 892de7ce0b4537f5526a58b6e70f66cd295be2df
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788831"
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a><span data-ttu-id="faee3-103">ICorProfilerCallback::RuntimeSuspendAborted (Método)</span><span class="sxs-lookup"><span data-stu-id="faee3-103">ICorProfilerCallback::RuntimeSuspendAborted Method</span></span>

<span data-ttu-id="faee3-104">Notifica al generador de perfiles que el Runtime ha anulado la suspensión en tiempo de ejecución que se estaba produciendo.</span><span class="sxs-lookup"><span data-stu-id="faee3-104">Notifies the profiler that the runtime has aborted the runtime suspension that was occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="faee3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="faee3-105">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="faee3-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="faee3-106">Remarks</span></span>  

 <span data-ttu-id="faee3-107">La suspensión en tiempo de ejecución se puede anular si dos subprocesos intentan suspender el tiempo de ejecución simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="faee3-107">The run-time suspension might be aborted if two threads simultaneously attempt to suspend the runtime.</span></span>  
  
 <span data-ttu-id="faee3-108">La devolución de llamada [ICorProfilerCallback:: RuntimeSuspendFinished (](icorprofilercallback-runtimesuspendfinished-method.md) o la `RuntimeSuspendAborted` devolución de llamada se producirán en un único subproceso después de una devolución de llamada [ICorProfilerCallback:: runtimesuspendstarted (](icorprofilercallback-runtimesuspendstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="faee3-108">Either the [ICorProfilerCallback::RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) callback or the `RuntimeSuspendAborted` callback will occur on a single thread following a [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
 <span data-ttu-id="faee3-109">`RuntimeSuspendAborted`Se garantiza que la devolución de llamada se produce en el mismo subproceso que la `RuntimeSuspendStarted` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="faee3-109">The `RuntimeSuspendAborted` callback is guaranteed to occur on the same thread as the `RuntimeSuspendStarted` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="faee3-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="faee3-110">Requirements</span></span>  

 <span data-ttu-id="faee3-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="faee3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="faee3-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="faee3-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="faee3-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="faee3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="faee3-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="faee3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faee3-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="faee3-115">See also</span></span>

- [<span data-ttu-id="faee3-116">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="faee3-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
