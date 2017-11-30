---
title: "ICorProfilerCallback::RuntimeSuspendFinished (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RuntimeSuspendFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RuntimeSuspendFinished
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished method [.NET Framework profiling]
- RuntimeSuspendFinished method [.NET Framework profiling]
ms.assetid: b7723f58-c55c-4399-9972-1bbf3b866694
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c922ee4f986df22f213820b8aed60ea28a76377c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a><span data-ttu-id="a2df4-102">ICorProfilerCallback::RuntimeSuspendFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="a2df4-102">ICorProfilerCallback::RuntimeSuspendFinished Method</span></span>
<span data-ttu-id="a2df4-103">Notifica al generador de perfiles que el tiempo de ejecución ha finalizado la suspensión de todos los subprocesos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a2df4-103">Notifies the profiler that the runtime has completed suspension of all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2df4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a2df4-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="a2df4-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a2df4-105">Remarks</span></span>  
 <span data-ttu-id="a2df4-106">Todos los subprocesos en tiempo de ejecución que están en código no administrado se pueden continuar ejecutándose hasta que intentan volver a escribir el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a2df4-106">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="a2df4-107">En ese momento también se suspenderán hasta que el tiempo de ejecución se reanuda.</span><span class="sxs-lookup"><span data-stu-id="a2df4-107">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="a2df4-108">Esto también se aplica a nuevos subprocesos que entran en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a2df4-108">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="a2df4-109">Todos los subprocesos en el tiempo de ejecución están suspenden inmediatamente si ya están en código interrumpible, o se les solicita que se suspendan cuando alcanzan código interrumpible.</span><span class="sxs-lookup"><span data-stu-id="a2df4-109">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
 <span data-ttu-id="a2df4-110">El `RuntimeSuspendFinished` devolución de llamada se garantiza que se producen en el mismo subproceso que el [ICorProfilerCallback:: RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="a2df4-110">The `RuntimeSuspendFinished` callback is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2df4-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a2df4-111">Requirements</span></span>  
 <span data-ttu-id="a2df4-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2df4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2df4-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a2df4-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a2df4-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2df4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2df4-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2df4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2df4-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2df4-116">See Also</span></span>  
 [<span data-ttu-id="a2df4-117">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a2df4-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="a2df4-118">RuntimeSuspendAborted (método)</span><span class="sxs-lookup"><span data-stu-id="a2df4-118">RuntimeSuspendAborted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
