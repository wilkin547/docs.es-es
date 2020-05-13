---
title: ICorDebugThread::SetDebugState (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.SetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::SetDebugState
helpviewer_keywords:
- ICorDebugThread::SetDebugState method [.NET Framework debugging]
- SetDebugState method [.NET Framework debugging]
ms.assetid: 6382bdf6-d488-4952-b653-cb09b6e1c6c2
topic_type:
- apiref
ms.openlocfilehash: 05ae2791ee7f8bd31be38ec4d2117ddc3c2ea2bc
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83377945"
---
# <a name="icordebugthreadsetdebugstate-method"></a><span data-ttu-id="7b11a-102">ICorDebugThread::SetDebugState (Método)</span><span class="sxs-lookup"><span data-stu-id="7b11a-102">ICorDebugThread::SetDebugState Method</span></span>
<span data-ttu-id="7b11a-103">Establece marcas que describen el estado de depuración de esta ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="7b11a-103">Sets flags that describe the debugging state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b11a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b11a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b11a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7b11a-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="7b11a-106">de Combinación bit a bit de los valores de enumeración CorDebugThreadState (que especifican el estado de depuración de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="7b11a-106">[in] A bitwise combination of CorDebugThreadState enumeration values that specify the debugging state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b11a-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7b11a-107">Remarks</span></span>  
 <span data-ttu-id="7b11a-108">`SetDebugState`establece el estado de depuración actual del subproceso.</span><span class="sxs-lookup"><span data-stu-id="7b11a-108">`SetDebugState` sets the current debug state of the thread.</span></span> <span data-ttu-id="7b11a-109">(El "estado de depuración actual" representa el estado de depuración si se va a continuar el proceso, no el estado actual real). El valor normal es THREAD_RUN.</span><span class="sxs-lookup"><span data-stu-id="7b11a-109">(The "current debug state" represents the debug state if the process were to be continued, not the actual current state.) The normal value for this is THREAD_RUN.</span></span> <span data-ttu-id="7b11a-110">Solo el depurador puede afectar al estado de depuración de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="7b11a-110">Only the debugger can affect the debug state of a thread.</span></span> <span data-ttu-id="7b11a-111">Los Estados de depuración continúan en el pasado, por lo que si desea mantener una THREAD_SUSPENDed de subprocesos en varias continuaciones, puede establecerla una vez y, a partir de ese momento, no tendrá que preocuparse por ella.</span><span class="sxs-lookup"><span data-stu-id="7b11a-111">Debug states do last across continues, so if you want to keep a thread THREAD_SUSPENDed over multiple continues, you can set it once and thereafter not have to worry about it.</span></span> <span data-ttu-id="7b11a-112">La suspensión de subprocesos y la reanudación del proceso pueden provocar interbloqueos, aunque normalmente es improbable.</span><span class="sxs-lookup"><span data-stu-id="7b11a-112">Suspending threads and resuming the process can cause deadlocks, though it's usually unlikely.</span></span> <span data-ttu-id="7b11a-113">Se trata de una calidad intrínseca de subprocesos y procesos y es por diseño.</span><span class="sxs-lookup"><span data-stu-id="7b11a-113">This is an intrinsic quality of threads and processes and is by-design.</span></span> <span data-ttu-id="7b11a-114">Un depurador puede interrumpir y reanudar asincrónicamente los subprocesos para interrumpir el interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="7b11a-114">A debugger can asynchronously break and resume the threads to break the deadlock.</span></span> <span data-ttu-id="7b11a-115">Si el estado de usuario del subproceso incluye USER_UNSAFE_POINT, el subproceso puede bloquear una recolección de elementos no utilizados (GC).</span><span class="sxs-lookup"><span data-stu-id="7b11a-115">If the thread's user state includes USER_UNSAFE_POINT, then the thread may block a garbage collection (GC).</span></span> <span data-ttu-id="7b11a-116">Esto significa que el subproceso suspendido tiene una probabilidad mucho mayor de provocar un interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="7b11a-116">This means the suspended thread has a much higher chance of causing a deadlock.</span></span> <span data-ttu-id="7b11a-117">Esto puede no afectar a los eventos de depuración ya en cola.</span><span class="sxs-lookup"><span data-stu-id="7b11a-117">This may not affect debug events already queued.</span></span> <span data-ttu-id="7b11a-118">Por lo tanto, un depurador debe purgar toda la cola de eventos (llamando a [ICorDebugController:: HasQueuedCallbacks (](icordebugcontroller-hasqueuedcallbacks-method.md)) antes de suspender o reanudar los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="7b11a-118">Thus a debugger should drain the entire event queue (by calling [ICorDebugController::HasQueuedCallbacks](icordebugcontroller-hasqueuedcallbacks-method.md)) before suspending or resuming threads.</span></span> <span data-ttu-id="7b11a-119">En caso contrario, puede recibir eventos en un subproceso que cree que ya se ha suspendido.</span><span class="sxs-lookup"><span data-stu-id="7b11a-119">Else it may get events on a thread that it believes it has already suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b11a-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b11a-120">Requirements</span></span>  
 <span data-ttu-id="7b11a-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b11a-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b11a-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b11a-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b11a-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b11a-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b11a-124">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b11a-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
