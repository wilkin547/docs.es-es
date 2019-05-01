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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d29f5cefd22592fa8949ff5361109c09c0972b24
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987147"
---
# <a name="icordebugthreadsetdebugstate-method"></a><span data-ttu-id="306b5-102">ICorDebugThread::SetDebugState (Método)</span><span class="sxs-lookup"><span data-stu-id="306b5-102">ICorDebugThread::SetDebugState Method</span></span>
<span data-ttu-id="306b5-103">Establece las marcas que describen el estado de depuración de este ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="306b5-103">Sets flags that describe the debugging state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="306b5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="306b5-104">Syntax</span></span>  
  
```  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="306b5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="306b5-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="306b5-106">[in] Una combinación bit a bit de valores de enumeración CorDebugThreadState que especifican el estado de depuración de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="306b5-106">[in] A bitwise combination of CorDebugThreadState enumeration values that specify the debugging state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="306b5-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="306b5-107">Remarks</span></span>  
 <span data-ttu-id="306b5-108">`SetDebugState` establece el estado de depuración actual del subproceso.</span><span class="sxs-lookup"><span data-stu-id="306b5-108">`SetDebugState` sets the current debug state of the thread.</span></span> <span data-ttu-id="306b5-109">(El "estado de depuración actual" representa el estado de depuración si el proceso se puede continuar, no el estado actual real). El valor normal es THREAD_RUNNING.</span><span class="sxs-lookup"><span data-stu-id="306b5-109">(The "current debug state" represents the debug state if the process were to be continued, not the actual current state.) The normal value for this is THREAD_RUNNING.</span></span> <span data-ttu-id="306b5-110">Solo el depurador puede afectar el estado de depuración de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="306b5-110">Only the debugger can affect the debug state of a thread.</span></span> <span data-ttu-id="306b5-111">Estados de depuración continuaciones, por lo que si desea mantener un subproceso THREAD_SUSPENDed en varias continuaciones, puede configurarla una vez y no volver a preocuparse.</span><span class="sxs-lookup"><span data-stu-id="306b5-111">Debug states do last across continues, so if you want to keep a thread THREAD_SUSPENDed over multiple continues, you can set it once and thereafter not have to worry about it.</span></span> <span data-ttu-id="306b5-112">Subprocesos de suspender y reanudar el proceso pueden provocar interbloqueos, aunque es poco probable que normalmente.</span><span class="sxs-lookup"><span data-stu-id="306b5-112">Suspending threads and resuming the process can cause deadlocks, though it's usually unlikely.</span></span> <span data-ttu-id="306b5-113">Esto es una cualidad intrínseca de procesos y subprocesos y es por diseño.</span><span class="sxs-lookup"><span data-stu-id="306b5-113">This is an intrinsic quality of threads and processes and is by-design.</span></span> <span data-ttu-id="306b5-114">Forma asincrónica, un depurador puede interrumpir y reanudar los subprocesos para interrumpir el interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="306b5-114">A debugger can asynchronously break and resume the threads to break the deadlock.</span></span> <span data-ttu-id="306b5-115">Si el estado de usuario del subproceso incluye USER_UNSAFE_POINT, el subproceso puede bloquear una colección de elementos no utilizados (GC).</span><span class="sxs-lookup"><span data-stu-id="306b5-115">If the thread's user state includes USER_UNSAFE_POINT, then the thread may block a garbage collection (GC).</span></span> <span data-ttu-id="306b5-116">Esto significa que el subproceso suspendido tiene una probabilidad mucho más alta de producir un interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="306b5-116">This means the suspended thread has a much higher chance of causing a deadlock.</span></span> <span data-ttu-id="306b5-117">Esto puede no afectar a ya está en cola los eventos de depuración.</span><span class="sxs-lookup"><span data-stu-id="306b5-117">This may not affect debug events already queued.</span></span> <span data-ttu-id="306b5-118">Por lo tanto, un depurador debe purgar la cola de eventos completo (mediante una llamada a [HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) antes de suspender o reanudar subprocesos.</span><span class="sxs-lookup"><span data-stu-id="306b5-118">Thus a debugger should drain the entire event queue (by calling [ICorDebugController::HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) before suspending or resuming threads.</span></span> <span data-ttu-id="306b5-119">Lo contrario, pueden obtener los eventos de un subproceso que cree que ya ha suspendido.</span><span class="sxs-lookup"><span data-stu-id="306b5-119">Else it may get events on a thread that it believes it has already suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="306b5-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="306b5-120">Requirements</span></span>  
 <span data-ttu-id="306b5-121">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="306b5-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="306b5-122">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="306b5-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="306b5-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="306b5-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="306b5-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="306b5-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
