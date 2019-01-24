---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bb93dbf35501d44bb21d3d689aebeba3acd19f79
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54616814"
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a><span data-ttu-id="40c82-102">ICorProfilerCallback::RuntimeThreadSuspended (Método)</span><span class="sxs-lookup"><span data-stu-id="40c82-102">ICorProfilerCallback::RuntimeThreadSuspended Method</span></span>
<span data-ttu-id="40c82-103">Notifica al generador de perfiles que el subproceso especificado se ha suspendido o está a punto de suspenderse.</span><span class="sxs-lookup"><span data-stu-id="40c82-103">Notifies the profiler that the specified thread has been suspended or is about to be suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40c82-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40c82-104">Syntax</span></span>  
  
```  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="40c82-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="40c82-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="40c82-106">[in] El identificador del subproceso que se ha suspendido.</span><span class="sxs-lookup"><span data-stu-id="40c82-106">[in] The ID of the thread that has been suspended.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40c82-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="40c82-107">Remarks</span></span>  
 <span data-ttu-id="40c82-108">El `RuntimeThreadSuspended` notificación puede producirse en cualquier momento entre el [RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) y asociado [RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) devoluciones de llamada.</span><span class="sxs-lookup"><span data-stu-id="40c82-108">The `RuntimeThreadSuspended` notification can occur any time between the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) and the associated [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span> <span data-ttu-id="40c82-109">Las notificaciones que se producen entre [RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) y `RuntimeResumeStarted` son de subprocesos que estaban en ejecución en código no administrado y se suspendieron al entrar en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="40c82-109">Notifications that occur between [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) and `RuntimeResumeStarted` are for threads that had been running in unmanaged code and were suspended upon entry to the runtime.</span></span>  
  
 <span data-ttu-id="40c82-110">Por lo general, esta devolución de llamada se produce justo después de que un subproceso está suspendido.</span><span class="sxs-lookup"><span data-stu-id="40c82-110">Generally, this callback occurs just after a thread is suspended.</span></span> <span data-ttu-id="40c82-111">Sin embargo, si el subproceso actualmente en ejecución (el subproceso que llamó a esta devolución de llamada) es la que se ha suspendido, se producirá esta devolución de llamada antes de que el subproceso está suspendido.</span><span class="sxs-lookup"><span data-stu-id="40c82-111">However, if the currently executing thread (the thread that called this callback) is the one that is being suspended, this callback will occur just before the thread is suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40c82-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="40c82-112">Requirements</span></span>  
 <span data-ttu-id="40c82-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40c82-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40c82-114">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="40c82-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="40c82-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40c82-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40c82-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40c82-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40c82-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="40c82-117">See also</span></span>
- [<span data-ttu-id="40c82-118">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="40c82-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="40c82-119">RuntimeThreadResumed (método)</span><span class="sxs-lookup"><span data-stu-id="40c82-119">RuntimeThreadResumed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)
