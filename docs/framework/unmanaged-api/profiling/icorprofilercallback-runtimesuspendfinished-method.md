---
description: 'Más información sobre: ICorProfilerCallback:: RuntimeSuspendFinished ((método)'
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
ms.openlocfilehash: eab7111f28c77f1440c0e392a36fb2b083c138e2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657546"
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a><span data-ttu-id="53278-103">ICorProfilerCallback::RuntimeSuspendFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="53278-103">ICorProfilerCallback::RuntimeSuspendFinished Method</span></span>

<span data-ttu-id="53278-104">Notifica al generador de perfiles que el Runtime ha completado la suspensión de todos los subprocesos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="53278-104">Notifies the profiler that the runtime has completed suspension of all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53278-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53278-105">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="53278-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="53278-106">Remarks</span></span>  

 <span data-ttu-id="53278-107">Todos los subprocesos en tiempo de ejecución que se encuentran en código no administrado pueden continuar ejecutándose hasta que intenten volver a entrar en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="53278-107">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="53278-108">En ese momento, también se suspenderán hasta que se reanude el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="53278-108">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="53278-109">Esto también se aplica a los nuevos subprocesos que entran en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="53278-109">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="53278-110">Todos los subprocesos del tiempo de ejecución se suspenden inmediatamente si ya están en código interrumpido, o se les pide que se suspendan cuando llegan a código interrumpido.</span><span class="sxs-lookup"><span data-stu-id="53278-110">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
 <span data-ttu-id="53278-111">`RuntimeSuspendFinished`Se garantiza que la devolución de llamada se produce en el mismo subproceso que la devolución de llamada [ICorProfilerCallback:: runtimesuspendstarted (](icorprofilercallback-runtimesuspendstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="53278-111">The `RuntimeSuspendFinished` callback is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53278-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="53278-112">Requirements</span></span>  

 <span data-ttu-id="53278-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53278-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53278-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="53278-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="53278-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53278-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53278-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53278-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53278-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="53278-117">See also</span></span>

- [<span data-ttu-id="53278-118">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="53278-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="53278-119">Método RuntimeSuspendAborted</span><span class="sxs-lookup"><span data-stu-id="53278-119">RuntimeSuspendAborted Method</span></span>](icorprofilercallback-runtimesuspendaborted-method.md)
