---
title: "ICorProfilerCallback::RuntimeSuspendStarted (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RuntimeSuspendStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RuntimeSuspendStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted method [.NET Framework profiling]
- RuntimeSuspendStarted method [.NET Framework profiling]
ms.assetid: c8461cac-e31b-4efa-ad2c-26598173eb96
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 358536aa51dfef2d079813b34eddbd1b01294bcc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackruntimesuspendstarted-method"></a><span data-ttu-id="1bef2-102">ICorProfilerCallback::RuntimeSuspendStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="1bef2-102">ICorProfilerCallback::RuntimeSuspendStarted Method</span></span>
<span data-ttu-id="1bef2-103">Notifica al generador de perfiles que el tiempo de ejecución está a punto de suspender todos los subprocesos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1bef2-103">Notifies the profiler that the runtime is about to suspend all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bef2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1bef2-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendStarted(  
    [in] COR_PRF_SUSPEND_REASON suspendReason);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1bef2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1bef2-105">Parameters</span></span>  
 `suspendReason`  
 <span data-ttu-id="1bef2-106">[in] Un valor de la [COR_PRF_SUSPEND_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md) enumeración que indica el motivo de la suspensión.</span><span class="sxs-lookup"><span data-stu-id="1bef2-106">[in] A value of the [COR_PRF_SUSPEND_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md) enumeration that indicates the reason for the suspension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1bef2-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1bef2-107">Remarks</span></span>  
 <span data-ttu-id="1bef2-108">Todos los subprocesos en tiempo de ejecución que están en código no administrado se pueden continuar ejecutándose hasta que intentan volver a escribir el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1bef2-108">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="1bef2-109">En ese momento también se suspenderán hasta que el tiempo de ejecución se reanuda.</span><span class="sxs-lookup"><span data-stu-id="1bef2-109">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="1bef2-110">Esto también se aplica a nuevos subprocesos que entran en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1bef2-110">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="1bef2-111">Todos los subprocesos en el tiempo de ejecución están suspenden inmediatamente si ya están en código interrumpible, o se les solicita que se suspendan cuando alcanzan código interrumpible.</span><span class="sxs-lookup"><span data-stu-id="1bef2-111">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bef2-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1bef2-112">Requirements</span></span>  
 <span data-ttu-id="1bef2-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bef2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bef2-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1bef2-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1bef2-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1bef2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1bef2-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bef2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bef2-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="1bef2-117">See Also</span></span>  
 [<span data-ttu-id="1bef2-118">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1bef2-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="1bef2-119">RuntimeSuspendAborted (método)</span><span class="sxs-lookup"><span data-stu-id="1bef2-119">RuntimeSuspendAborted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)  
 [<span data-ttu-id="1bef2-120">RuntimeSuspendFinished (método)</span><span class="sxs-lookup"><span data-stu-id="1bef2-120">RuntimeSuspendFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)
