---
title: ICorProfilerCallback::RuntimeSuspendStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted method [.NET Framework profiling]
- RuntimeSuspendStarted method [.NET Framework profiling]
ms.assetid: c8461cac-e31b-4efa-ad2c-26598173eb96
topic_type:
- apiref
ms.openlocfilehash: b778088f53a3c49def95d715f5fefcb26af81489
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731987"
---
# <a name="icorprofilercallbackruntimesuspendstarted-method"></a><span data-ttu-id="7c84c-102">ICorProfilerCallback::RuntimeSuspendStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="7c84c-102">ICorProfilerCallback::RuntimeSuspendStarted Method</span></span>

<span data-ttu-id="7c84c-103">Notifica al generador de perfiles que el tiempo de ejecución está a punto de suspender todos los subprocesos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7c84c-103">Notifies the profiler that the runtime is about to suspend all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c84c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7c84c-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendStarted(  
    [in] COR_PRF_SUSPEND_REASON suspendReason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c84c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7c84c-105">Parameters</span></span>  

 `suspendReason`  
 <span data-ttu-id="7c84c-106">de Un valor de la enumeración [COR_PRF_SUSPEND_REASON](cor-prf-suspend-reason-enumeration.md) que indica el motivo de la suspensión.</span><span class="sxs-lookup"><span data-stu-id="7c84c-106">[in] A value of the [COR_PRF_SUSPEND_REASON](cor-prf-suspend-reason-enumeration.md) enumeration that indicates the reason for the suspension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c84c-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7c84c-107">Remarks</span></span>  

 <span data-ttu-id="7c84c-108">Todos los subprocesos en tiempo de ejecución que se encuentran en código no administrado pueden continuar ejecutándose hasta que intenten volver a entrar en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7c84c-108">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="7c84c-109">En ese momento, también se suspenderán hasta que se reanude el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7c84c-109">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="7c84c-110">Esto también se aplica a los nuevos subprocesos que entran en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7c84c-110">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="7c84c-111">Todos los subprocesos del tiempo de ejecución se suspenden inmediatamente si ya están en código interrumpido, o se les pide que se suspendan cuando llegan a código interrumpido.</span><span class="sxs-lookup"><span data-stu-id="7c84c-111">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c84c-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7c84c-112">Requirements</span></span>  

 <span data-ttu-id="7c84c-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c84c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c84c-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7c84c-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7c84c-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c84c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c84c-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c84c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c84c-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7c84c-117">See also</span></span>

- [<span data-ttu-id="7c84c-118">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7c84c-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="7c84c-119">Método RuntimeSuspendAborted</span><span class="sxs-lookup"><span data-stu-id="7c84c-119">RuntimeSuspendAborted Method</span></span>](icorprofilercallback-runtimesuspendaborted-method.md)
- [<span data-ttu-id="7c84c-120">Método RuntimeSuspendFinished</span><span class="sxs-lookup"><span data-stu-id="7c84c-120">RuntimeSuspendFinished Method</span></span>](icorprofilercallback-runtimesuspendfinished-method.md)
