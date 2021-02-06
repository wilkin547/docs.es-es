---
description: 'Más información sobre: ICorProfilerCallback:: RuntimeThreadSuspended ((método)'
title: ICorProfilerCallback::RuntimeThreadSuspended (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeThreadSuspended
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeThreadSuspended
helpviewer_keywords:
- RuntimeThreadSuspended method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeThreadSuspended method [.NET Framework profiling]
ms.assetid: de830a8b-6ee1-4900-ace3-4237108f6b12
topic_type:
- apiref
ms.openlocfilehash: f7c2f5baf5a320375d9a2606ca05b13d522336be
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657339"
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a><span data-ttu-id="d5e5f-103">ICorProfilerCallback::RuntimeThreadSuspended (Método)</span><span class="sxs-lookup"><span data-stu-id="d5e5f-103">ICorProfilerCallback::RuntimeThreadSuspended Method</span></span>

<span data-ttu-id="d5e5f-104">Notifica al generador de perfiles que el subproceso especificado se ha suspendido o está a punto de ser suspendido.</span><span class="sxs-lookup"><span data-stu-id="d5e5f-104">Notifies the profiler that the specified thread has been suspended or is about to be suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5e5f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d5e5f-105">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5e5f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d5e5f-106">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="d5e5f-107">de IDENTIFICADOR del subproceso que se ha suspendido.</span><span class="sxs-lookup"><span data-stu-id="d5e5f-107">[in] The ID of the thread that has been suspended.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5e5f-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d5e5f-108">Remarks</span></span>  

 <span data-ttu-id="d5e5f-109">La `RuntimeThreadSuspended` notificación puede producirse en cualquier momento entre el [ICorProfilerCallback:: runtimesuspendstarted (](icorprofilercallback-runtimesuspendstarted-method.md) y las devoluciones de llamada [ICorProfilerCallback:: RuntimeResumeStarted (](icorprofilercallback-runtimeresumestarted-method.md) asociadas.</span><span class="sxs-lookup"><span data-stu-id="d5e5f-109">The `RuntimeThreadSuspended` notification can occur any time between the [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) and the associated [ICorProfilerCallback::RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span> <span data-ttu-id="d5e5f-110">Las notificaciones que se producen entre [ICorProfilerCallback:: RuntimeSuspendFinished (](icorprofilercallback-runtimesuspendfinished-method.md) y `RuntimeResumeStarted` son para los subprocesos que se ejecutaron en código no administrado y se suspendieron en la entrada al tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d5e5f-110">Notifications that occur between [ICorProfilerCallback::RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) and `RuntimeResumeStarted` are for threads that had been running in unmanaged code and were suspended upon entry to the runtime.</span></span>  
  
 <span data-ttu-id="d5e5f-111">Normalmente, esta devolución de llamada se produce justo después de suspender un subproceso.</span><span class="sxs-lookup"><span data-stu-id="d5e5f-111">Generally, this callback occurs just after a thread is suspended.</span></span> <span data-ttu-id="d5e5f-112">Sin embargo, si el subproceso que se está ejecutando actualmente (el subproceso que llamó a esta devolución de llamada) es el que se está suspendiendo, esta devolución de llamada se producirá justo antes de que se suspenda el subproceso.</span><span class="sxs-lookup"><span data-stu-id="d5e5f-112">However, if the currently executing thread (the thread that called this callback) is the one that is being suspended, this callback will occur just before the thread is suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5e5f-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d5e5f-113">Requirements</span></span>  

 <span data-ttu-id="d5e5f-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5e5f-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5e5f-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d5e5f-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d5e5f-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5e5f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5e5f-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5e5f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5e5f-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5e5f-118">See also</span></span>

- [<span data-ttu-id="d5e5f-119">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d5e5f-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="d5e5f-120">Método RuntimeThreadResumed</span><span class="sxs-lookup"><span data-stu-id="d5e5f-120">RuntimeThreadResumed Method</span></span>](icorprofilercallback-runtimethreadresumed-method.md)
