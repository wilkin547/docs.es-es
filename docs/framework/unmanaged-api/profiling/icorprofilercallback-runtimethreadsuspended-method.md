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
ms.openlocfilehash: 509d6cd2e65c2eb8c92f6d79deae9e01e75298f6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433445"
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a><span data-ttu-id="d3e4b-102">ICorProfilerCallback::RuntimeThreadSuspended (Método)</span><span class="sxs-lookup"><span data-stu-id="d3e4b-102">ICorProfilerCallback::RuntimeThreadSuspended Method</span></span>
<span data-ttu-id="d3e4b-103">Notifica al generador de perfiles que el subproceso especificado se ha suspendido o está a punto de ser suspendido.</span><span class="sxs-lookup"><span data-stu-id="d3e4b-103">Notifies the profiler that the specified thread has been suspended or is about to be suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3e4b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d3e4b-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3e4b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d3e4b-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="d3e4b-106">de IDENTIFICADOR del subproceso que se ha suspendido.</span><span class="sxs-lookup"><span data-stu-id="d3e4b-106">[in] The ID of the thread that has been suspended.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3e4b-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d3e4b-107">Remarks</span></span>  
 <span data-ttu-id="d3e4b-108">La notificación de `RuntimeThreadSuspended` puede producirse en cualquier momento entre el [ICorProfilerCallback:: runtimesuspendstarted (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) y las devoluciones de llamada [ICorProfilerCallback:: RuntimeResumeStarted (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) asociadas.</span><span class="sxs-lookup"><span data-stu-id="d3e4b-108">The `RuntimeThreadSuspended` notification can occur any time between the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) and the associated [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span> <span data-ttu-id="d3e4b-109">Las notificaciones que se producen entre [ICorProfilerCallback:: RuntimeSuspendFinished (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) y `RuntimeResumeStarted` son para los subprocesos que se ejecutaron en código no administrado y se suspendieron en la entrada al tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d3e4b-109">Notifications that occur between [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) and `RuntimeResumeStarted` are for threads that had been running in unmanaged code and were suspended upon entry to the runtime.</span></span>  
  
 <span data-ttu-id="d3e4b-110">Normalmente, esta devolución de llamada se produce justo después de suspender un subproceso.</span><span class="sxs-lookup"><span data-stu-id="d3e4b-110">Generally, this callback occurs just after a thread is suspended.</span></span> <span data-ttu-id="d3e4b-111">Sin embargo, si el subproceso que se está ejecutando actualmente (el subproceso que llamó a esta devolución de llamada) es el que se está suspendiendo, esta devolución de llamada se producirá justo antes de que se suspenda el subproceso.</span><span class="sxs-lookup"><span data-stu-id="d3e4b-111">However, if the currently executing thread (the thread that called this callback) is the one that is being suspended, this callback will occur just before the thread is suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3e4b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d3e4b-112">Requirements</span></span>  
 <span data-ttu-id="d3e4b-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3e4b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3e4b-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d3e4b-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d3e4b-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3e4b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3e4b-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3e4b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3e4b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3e4b-117">See also</span></span>

- [<span data-ttu-id="d3e4b-118">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d3e4b-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="d3e4b-119">RuntimeThreadResumed (método)</span><span class="sxs-lookup"><span data-stu-id="d3e4b-119">RuntimeThreadResumed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)
