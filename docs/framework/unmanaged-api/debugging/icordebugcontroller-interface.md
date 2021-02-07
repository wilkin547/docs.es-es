---
description: 'Más información sobre: interfaz ICorDebugController'
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
ms.openlocfilehash: 588c41b5b8d87589facd6085655ed0ad415ec3aa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710756"
---
# <a name="icordebugcontroller-interface"></a><span data-ttu-id="f9ad6-103">Interfaz ICorDebugController</span><span class="sxs-lookup"><span data-stu-id="f9ad6-103">ICorDebugController Interface</span></span>

<span data-ttu-id="f9ad6-104">Representa un ámbito, <xref:System.Diagnostics.Process> o <xref:System.AppDomain>, en el que se puede controlar el contexto de ejecución de código.</span><span class="sxs-lookup"><span data-stu-id="f9ad6-104">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f9ad6-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="f9ad6-105">Methods</span></span>  
  
|<span data-ttu-id="f9ad6-106">Método</span><span class="sxs-lookup"><span data-stu-id="f9ad6-106">Method</span></span>|<span data-ttu-id="f9ad6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f9ad6-107">Description</span></span>|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|<span data-ttu-id="f9ad6-108">Este método está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f9ad6-108">This method is obsolete.</span></span>|  
|`ICorDebugController::CommitChanges`|<span data-ttu-id="f9ad6-109">Este método está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f9ad6-109">This method is obsolete.</span></span>|  
|[<span data-ttu-id="f9ad6-110">Método Continue</span><span class="sxs-lookup"><span data-stu-id="f9ad6-110">Continue Method</span></span>](icordebugcontroller-continue-method.md)|<span data-ttu-id="f9ad6-111">Reanuda la ejecución de subprocesos administrados después de una llamada a [ICorDebugController:: Stop](icordebugcontroller-stop-method.md).</span><span class="sxs-lookup"><span data-stu-id="f9ad6-111">Resumes execution of managed threads after a call to [ICorDebugController::Stop](icordebugcontroller-stop-method.md).</span></span>|  
|[<span data-ttu-id="f9ad6-112">Método Detach</span><span class="sxs-lookup"><span data-stu-id="f9ad6-112">Detach Method</span></span>](icordebugcontroller-detach-method.md)|<span data-ttu-id="f9ad6-113">Desasocia el depurador del dominio del proceso o de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f9ad6-113">Detaches the debugger from the process or application domain.</span></span>|  
|[<span data-ttu-id="f9ad6-114">Método EnumerateThreads</span><span class="sxs-lookup"><span data-stu-id="f9ad6-114">EnumerateThreads Method</span></span>](icordebugcontroller-enumeratethreads-method.md)|<span data-ttu-id="f9ad6-115">Obtiene un enumerador para los subprocesos administrados activos en el proceso.</span><span class="sxs-lookup"><span data-stu-id="f9ad6-115">Gets an enumerator for the active managed threads in the process.</span></span>|  
|[<span data-ttu-id="f9ad6-116">Método HasQueuedCallbacks</span><span class="sxs-lookup"><span data-stu-id="f9ad6-116">HasQueuedCallbacks Method</span></span>](icordebugcontroller-hasqueuedcallbacks-method.md)|<span data-ttu-id="f9ad6-117">Obtiene un valor que indica si las devoluciones de llamada administradas están actualmente en la cola del subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="f9ad6-117">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>|  
|[<span data-ttu-id="f9ad6-118">Método IsRunning</span><span class="sxs-lookup"><span data-stu-id="f9ad6-118">IsRunning Method</span></span>](icordebugcontroller-isrunning-method.md)|<span data-ttu-id="f9ad6-119">Obtiene un valor que indica si los subprocesos del proceso se están ejecutando libremente.</span><span class="sxs-lookup"><span data-stu-id="f9ad6-119">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>|  
|[<span data-ttu-id="f9ad6-120">Método SetAllThreadsDebugState</span><span class="sxs-lookup"><span data-stu-id="f9ad6-120">SetAllThreadsDebugState Method</span></span>](icordebugcontroller-setallthreadsdebugstate-method.md)|<span data-ttu-id="f9ad6-121">Establece el estado de depuración de todos los subprocesos administrados en el proceso.</span><span class="sxs-lookup"><span data-stu-id="f9ad6-121">Sets the debug state of all managed threads in the process.</span></span>|  
|[<span data-ttu-id="f9ad6-122">STOP (método)</span><span class="sxs-lookup"><span data-stu-id="f9ad6-122">Stop Method</span></span>](icordebugcontroller-stop-method.md)|<span data-ttu-id="f9ad6-123">Realiza una detención cooperativa en todos los subprocesos que ejecutan código administrado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="f9ad6-123">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>|  
|[<span data-ttu-id="f9ad6-124">Terminate (Método)</span><span class="sxs-lookup"><span data-stu-id="f9ad6-124">Terminate Method</span></span>](icordebugcontroller-terminate-method.md)|<span data-ttu-id="f9ad6-125">Finaliza el proceso con el código de salida especificado.</span><span class="sxs-lookup"><span data-stu-id="f9ad6-125">Terminates the process with the specified exit code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9ad6-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f9ad6-126">Remarks</span></span>  

 <span data-ttu-id="f9ad6-127">Si `ICorDebugController` controla un proceso, el ámbito incluye todos los subprocesos del proceso.</span><span class="sxs-lookup"><span data-stu-id="f9ad6-127">If `ICorDebugController` is controlling a process, the scope includes all threads of the process.</span></span> <span data-ttu-id="f9ad6-128">Si `ICorDebugController` está controlando un dominio de aplicación, el ámbito incluye solo los subprocesos de ese dominio de aplicación concreto.</span><span class="sxs-lookup"><span data-stu-id="f9ad6-128">If `ICorDebugController` is controlling an application domain, the scope includes only the threads of that particular application domain.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f9ad6-129">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="f9ad6-129">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9ad6-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f9ad6-130">Requirements</span></span>  

 <span data-ttu-id="f9ad6-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9ad6-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9ad6-132">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f9ad6-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f9ad6-133">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9ad6-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9ad6-134">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9ad6-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9ad6-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9ad6-135">See also</span></span>

- [<span data-ttu-id="f9ad6-136">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="f9ad6-136">Debugging Interfaces</span></span>](debugging-interfaces.md)
