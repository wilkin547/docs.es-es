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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7628aa0ad10398f92d475c4c776810e13fac22b7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59107554"
---
# <a name="icordebugcontroller-interface"></a><span data-ttu-id="c09cd-102">Interfaz ICorDebugController</span><span class="sxs-lookup"><span data-stu-id="c09cd-102">ICorDebugController Interface</span></span>

<span data-ttu-id="c09cd-103">Representa un ámbito, <xref:System.Diagnostics.Process> o <xref:System.AppDomain>, en el que se puede controlar el contexto de ejecución de código.</span><span class="sxs-lookup"><span data-stu-id="c09cd-103">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c09cd-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c09cd-104">Methods</span></span>  
  
|<span data-ttu-id="c09cd-105">Método</span><span class="sxs-lookup"><span data-stu-id="c09cd-105">Method</span></span>|<span data-ttu-id="c09cd-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c09cd-106">Description</span></span>|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|<span data-ttu-id="c09cd-107">Este método está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="c09cd-107">This method is obsolete.</span></span>|  
|`ICorDebugController::CommitChanges`|<span data-ttu-id="c09cd-108">Este método está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="c09cd-108">This method is obsolete.</span></span>|  
|[<span data-ttu-id="c09cd-109">Continue (método)</span><span class="sxs-lookup"><span data-stu-id="c09cd-109">Continue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)|<span data-ttu-id="c09cd-110">Reanuda la ejecución de subprocesos administrados después de llamar a [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span><span class="sxs-lookup"><span data-stu-id="c09cd-110">Resumes execution of managed threads after a call to [ICorDebugController::Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span></span>|  
|[<span data-ttu-id="c09cd-111">Detach (método)</span><span class="sxs-lookup"><span data-stu-id="c09cd-111">Detach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-detach-method.md)|<span data-ttu-id="c09cd-112">Desasocia al depurador desde el dominio de aplicación o proceso.</span><span class="sxs-lookup"><span data-stu-id="c09cd-112">Detaches the debugger from the process or application domain.</span></span>|  
|[<span data-ttu-id="c09cd-113">EnumerateThreads (método)</span><span class="sxs-lookup"><span data-stu-id="c09cd-113">EnumerateThreads Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)|<span data-ttu-id="c09cd-114">Obtiene un enumerador para los subprocesos administrados activos en el proceso.</span><span class="sxs-lookup"><span data-stu-id="c09cd-114">Gets an enumerator for the active managed threads in the process.</span></span>|  
|[<span data-ttu-id="c09cd-115">HasQueuedCallbacks (método)</span><span class="sxs-lookup"><span data-stu-id="c09cd-115">HasQueuedCallbacks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)|<span data-ttu-id="c09cd-116">Obtiene un valor que indica si las devoluciones de llamada administradas actualmente están en cola para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="c09cd-116">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>|  
|[<span data-ttu-id="c09cd-117">IsRunning (método)</span><span class="sxs-lookup"><span data-stu-id="c09cd-117">IsRunning Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-isrunning-method.md)|<span data-ttu-id="c09cd-118">Obtiene un valor que indica si los subprocesos del proceso se están ejecutando libremente.</span><span class="sxs-lookup"><span data-stu-id="c09cd-118">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>|  
|[<span data-ttu-id="c09cd-119">SetAllThreadsDebugState (método)</span><span class="sxs-lookup"><span data-stu-id="c09cd-119">SetAllThreadsDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md)|<span data-ttu-id="c09cd-120">Establece el estado de depuración de todos los subprocesos administrados en el proceso.</span><span class="sxs-lookup"><span data-stu-id="c09cd-120">Sets the debug state of all managed threads in the process.</span></span>|  
|[<span data-ttu-id="c09cd-121">Stop (método)</span><span class="sxs-lookup"><span data-stu-id="c09cd-121">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)|<span data-ttu-id="c09cd-122">Realiza una detención cooperativa de todos los subprocesos que ejecutan código administrado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="c09cd-122">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>|  
|[<span data-ttu-id="c09cd-123">Terminate (método)</span><span class="sxs-lookup"><span data-stu-id="c09cd-123">Terminate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-terminate-method.md)|<span data-ttu-id="c09cd-124">Finaliza el proceso con el código de salida especificado.</span><span class="sxs-lookup"><span data-stu-id="c09cd-124">Terminates the process with the specified exit code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c09cd-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c09cd-125">Remarks</span></span>  
 <span data-ttu-id="c09cd-126">Si `ICorDebugController` es controlar un proceso, el ámbito incluye todos los subprocesos del proceso.</span><span class="sxs-lookup"><span data-stu-id="c09cd-126">If `ICorDebugController` is controlling a process, the scope includes all threads of the process.</span></span> <span data-ttu-id="c09cd-127">Si `ICorDebugController` es controlar un dominio de aplicación, el ámbito incluye solo los subprocesos de ese dominio de aplicación determinado.</span><span class="sxs-lookup"><span data-stu-id="c09cd-127">If `ICorDebugController` is controlling an application domain, the scope includes only the threads of that particular application domain.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c09cd-128">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="c09cd-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c09cd-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c09cd-129">Requirements</span></span>  
 <span data-ttu-id="c09cd-130">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c09cd-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c09cd-131">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c09cd-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c09cd-132">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c09cd-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c09cd-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c09cd-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c09cd-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="c09cd-134">See also</span></span>

- [<span data-ttu-id="c09cd-135">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c09cd-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
