---
title: ICorProfilerCallback::RuntimeSuspendFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished method [.NET Framework profiling]
- RuntimeSuspendFinished method [.NET Framework profiling]
ms.assetid: b7723f58-c55c-4399-9972-1bbf3b866694
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 07e2ebe8afe6002dee6c45f56fa1f11a4083d6bb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145605"
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a><span data-ttu-id="4c2dd-102">ICorProfilerCallback::RuntimeSuspendFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="4c2dd-102">ICorProfilerCallback::RuntimeSuspendFinished Method</span></span>
<span data-ttu-id="4c2dd-103">Notifica al generador de perfiles que el tiempo de ejecución ha finalizado la suspensión de todos los subprocesos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4c2dd-103">Notifies the profiler that the runtime has completed suspension of all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c2dd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4c2dd-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="4c2dd-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4c2dd-105">Remarks</span></span>  
 <span data-ttu-id="4c2dd-106">Todos los subprocesos en tiempo de ejecución que se encuentran en código no administrado se pueden seguir ejecutándose hasta que intenten volver a escribir el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4c2dd-106">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="4c2dd-107">En ese momento también se suspenderá hasta que se reanuda el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4c2dd-107">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="4c2dd-108">Esto también se aplica a nuevos subprocesos que entran en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4c2dd-108">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="4c2dd-109">Todos los subprocesos en tiempo de ejecución son suspenden inmediatamente si ya están en el código puede interrumpir o se les pide que suspender cuando alcanzan código interrumpible.</span><span class="sxs-lookup"><span data-stu-id="4c2dd-109">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
 <span data-ttu-id="4c2dd-110">El `RuntimeSuspendFinished` devolución de llamada se garantiza que se producen en el mismo subproceso que la [RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="4c2dd-110">The `RuntimeSuspendFinished` callback is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c2dd-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4c2dd-111">Requirements</span></span>  
 <span data-ttu-id="4c2dd-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c2dd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c2dd-113">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4c2dd-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4c2dd-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4c2dd-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="4c2dd-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="4c2dd-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4c2dd-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c2dd-116">See also</span></span>

- [<span data-ttu-id="4c2dd-117">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4c2dd-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="4c2dd-118">Método RuntimeSuspendAborted</span><span class="sxs-lookup"><span data-stu-id="4c2dd-118">RuntimeSuspendAborted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
