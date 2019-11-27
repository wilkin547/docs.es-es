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
ms.openlocfilehash: 8bad09ddb2b821d0e02d43c1e3d1585b3473ec98
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446962"
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a><span data-ttu-id="1c7a4-102">ICorProfilerCallback::RuntimeSuspendFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="1c7a4-102">ICorProfilerCallback::RuntimeSuspendFinished Method</span></span>
<span data-ttu-id="1c7a4-103">Notifica al generador de perfiles que el Runtime ha completado la suspensión de todos los subprocesos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1c7a4-103">Notifies the profiler that the runtime has completed suspension of all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c7a4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c7a4-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="1c7a4-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1c7a4-105">Remarks</span></span>  
 <span data-ttu-id="1c7a4-106">Todos los subprocesos en tiempo de ejecución que se encuentran en código no administrado pueden continuar ejecutándose hasta que intenten volver a entrar en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1c7a4-106">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="1c7a4-107">En ese momento, también se suspenderán hasta que se reanude el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1c7a4-107">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="1c7a4-108">Esto también se aplica a los nuevos subprocesos que entran en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1c7a4-108">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="1c7a4-109">Todos los subprocesos del tiempo de ejecución se suspenden inmediatamente si ya están en código interrumpido, o se les pide que se suspendan cuando llegan a código interrumpido.</span><span class="sxs-lookup"><span data-stu-id="1c7a4-109">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
 <span data-ttu-id="1c7a4-110">Se garantiza que la devolución de llamada de `RuntimeSuspendFinished` se produce en el mismo subproceso que la devolución de llamada [ICorProfilerCallback:: runtimesuspendstarted (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1c7a4-110">The `RuntimeSuspendFinished` callback is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c7a4-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c7a4-111">Requirements</span></span>  
 <span data-ttu-id="1c7a4-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c7a4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c7a4-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1c7a4-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1c7a4-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c7a4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c7a4-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c7a4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c7a4-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c7a4-116">See also</span></span>

- [<span data-ttu-id="1c7a4-117">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1c7a4-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="1c7a4-118">RuntimeSuspendAborted (método)</span><span class="sxs-lookup"><span data-stu-id="1c7a4-118">RuntimeSuspendAborted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
