---
title: Interfaz ICorDebugController
ms.date: 03/30/2017
api_name:
- ICorDebugController
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController
helpviewer_keywords:
- ICorDebugController interface [.NET Framework debugging]
ms.assetid: dbb1c4dc-269a-459b-ab1d-6c70788782ce
topic_type:
- apiref
ms.openlocfilehash: e494bbb24e8f2245593e7945625e72e70ae1dde5
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892767"
---
# <a name="icordebugcontroller-interface"></a><span data-ttu-id="b6a07-102">Interfaz ICorDebugController</span><span class="sxs-lookup"><span data-stu-id="b6a07-102">ICorDebugController Interface</span></span>

<span data-ttu-id="b6a07-103">Representa un ámbito, <xref:System.Diagnostics.Process> o <xref:System.AppDomain>, en el que se puede controlar el contexto de ejecución de código.</span><span class="sxs-lookup"><span data-stu-id="b6a07-103">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b6a07-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="b6a07-104">Methods</span></span>  
  
|<span data-ttu-id="b6a07-105">Método</span><span class="sxs-lookup"><span data-stu-id="b6a07-105">Method</span></span>|<span data-ttu-id="b6a07-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b6a07-106">Description</span></span>|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|<span data-ttu-id="b6a07-107">Este método está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="b6a07-107">This method is obsolete.</span></span>|  
|`ICorDebugController::CommitChanges`|<span data-ttu-id="b6a07-108">Este método está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="b6a07-108">This method is obsolete.</span></span>|  
|[<span data-ttu-id="b6a07-109">Método Continue</span><span class="sxs-lookup"><span data-stu-id="b6a07-109">Continue Method</span></span>](icordebugcontroller-continue-method.md)|<span data-ttu-id="b6a07-110">Reanuda la ejecución de subprocesos administrados después de una llamada a [ICorDebugController:: Stop](icordebugcontroller-stop-method.md).</span><span class="sxs-lookup"><span data-stu-id="b6a07-110">Resumes execution of managed threads after a call to [ICorDebugController::Stop](icordebugcontroller-stop-method.md).</span></span>|  
|[<span data-ttu-id="b6a07-111">Método Detach</span><span class="sxs-lookup"><span data-stu-id="b6a07-111">Detach Method</span></span>](icordebugcontroller-detach-method.md)|<span data-ttu-id="b6a07-112">Desasocia el depurador del dominio del proceso o de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b6a07-112">Detaches the debugger from the process or application domain.</span></span>|  
|[<span data-ttu-id="b6a07-113">Método EnumerateThreads</span><span class="sxs-lookup"><span data-stu-id="b6a07-113">EnumerateThreads Method</span></span>](icordebugcontroller-enumeratethreads-method.md)|<span data-ttu-id="b6a07-114">Obtiene un enumerador para los subprocesos administrados activos en el proceso.</span><span class="sxs-lookup"><span data-stu-id="b6a07-114">Gets an enumerator for the active managed threads in the process.</span></span>|  
|[<span data-ttu-id="b6a07-115">Método HasQueuedCallbacks</span><span class="sxs-lookup"><span data-stu-id="b6a07-115">HasQueuedCallbacks Method</span></span>](icordebugcontroller-hasqueuedcallbacks-method.md)|<span data-ttu-id="b6a07-116">Obtiene un valor que indica si las devoluciones de llamada administradas están actualmente en la cola del subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="b6a07-116">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>|  
|[<span data-ttu-id="b6a07-117">Método IsRunning</span><span class="sxs-lookup"><span data-stu-id="b6a07-117">IsRunning Method</span></span>](icordebugcontroller-isrunning-method.md)|<span data-ttu-id="b6a07-118">Obtiene un valor que indica si los subprocesos del proceso se están ejecutando libremente.</span><span class="sxs-lookup"><span data-stu-id="b6a07-118">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>|  
|[<span data-ttu-id="b6a07-119">Método SetAllThreadsDebugState</span><span class="sxs-lookup"><span data-stu-id="b6a07-119">SetAllThreadsDebugState Method</span></span>](icordebugcontroller-setallthreadsdebugstate-method.md)|<span data-ttu-id="b6a07-120">Establece el estado de depuración de todos los subprocesos administrados en el proceso.</span><span class="sxs-lookup"><span data-stu-id="b6a07-120">Sets the debug state of all managed threads in the process.</span></span>|  
|[<span data-ttu-id="b6a07-121">Stop (Método)</span><span class="sxs-lookup"><span data-stu-id="b6a07-121">Stop Method</span></span>](icordebugcontroller-stop-method.md)|<span data-ttu-id="b6a07-122">Realiza una detención cooperativa en todos los subprocesos que ejecutan código administrado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="b6a07-122">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>|  
|[<span data-ttu-id="b6a07-123">Terminate (Método)</span><span class="sxs-lookup"><span data-stu-id="b6a07-123">Terminate Method</span></span>](icordebugcontroller-terminate-method.md)|<span data-ttu-id="b6a07-124">Finaliza el proceso con el código de salida especificado.</span><span class="sxs-lookup"><span data-stu-id="b6a07-124">Terminates the process with the specified exit code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6a07-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b6a07-125">Remarks</span></span>  
 <span data-ttu-id="b6a07-126">Si `ICorDebugController` controla un proceso, el ámbito incluye todos los subprocesos del proceso.</span><span class="sxs-lookup"><span data-stu-id="b6a07-126">If `ICorDebugController` is controlling a process, the scope includes all threads of the process.</span></span> <span data-ttu-id="b6a07-127">Si `ICorDebugController` está controlando un dominio de aplicación, el ámbito incluye solo los subprocesos de ese dominio de aplicación concreto.</span><span class="sxs-lookup"><span data-stu-id="b6a07-127">If `ICorDebugController` is controlling an application domain, the scope includes only the threads of that particular application domain.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b6a07-128">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="b6a07-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6a07-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b6a07-129">Requirements</span></span>  
 <span data-ttu-id="b6a07-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6a07-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6a07-131">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6a07-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6a07-132">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6a07-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6a07-133">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6a07-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6a07-134">Consulta también</span><span class="sxs-lookup"><span data-stu-id="b6a07-134">See also</span></span>

- [<span data-ttu-id="b6a07-135">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="b6a07-135">Debugging Interfaces</span></span>](debugging-interfaces.md)
