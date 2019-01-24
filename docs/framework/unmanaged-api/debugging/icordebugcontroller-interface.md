---
title: ICorDebugController (Interfaz1)
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
ms.openlocfilehash: c0651f8cd63f2ebdc6b81e92c0b55d94fe51316b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645306"
---
# <a name="icordebugcontroller-interface1"></a><span data-ttu-id="f549c-102">ICorDebugController (Interfaz1)</span><span class="sxs-lookup"><span data-stu-id="f549c-102">ICorDebugController Interface1</span></span>
<span data-ttu-id="f549c-103">Representa un ámbito, <xref:System.Diagnostics.Process> o <xref:System.AppDomain>, en el que se puede controlar el contexto de ejecución de código.</span><span class="sxs-lookup"><span data-stu-id="f549c-103">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f549c-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f549c-104">Methods</span></span>  
  
|<span data-ttu-id="f549c-105">Método</span><span class="sxs-lookup"><span data-stu-id="f549c-105">Method</span></span>|<span data-ttu-id="f549c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f549c-106">Description</span></span>|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|<span data-ttu-id="f549c-107">Este método está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f549c-107">This method is obsolete.</span></span>|  
|`ICorDebugController::CommitChanges`|<span data-ttu-id="f549c-108">Este método está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f549c-108">This method is obsolete.</span></span>|  
|[<span data-ttu-id="f549c-109">Continue (método)</span><span class="sxs-lookup"><span data-stu-id="f549c-109">Continue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)|<span data-ttu-id="f549c-110">Reanuda la ejecución de subprocesos administrados después de llamar a [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span><span class="sxs-lookup"><span data-stu-id="f549c-110">Resumes execution of managed threads after a call to [ICorDebugController::Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span></span>|  
|[<span data-ttu-id="f549c-111">Detach (método)</span><span class="sxs-lookup"><span data-stu-id="f549c-111">Detach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-detach-method.md)|<span data-ttu-id="f549c-112">Desasocia al depurador desde el dominio de aplicación o proceso.</span><span class="sxs-lookup"><span data-stu-id="f549c-112">Detaches the debugger from the process or application domain.</span></span>|  
|[<span data-ttu-id="f549c-113">EnumerateThreads (método)</span><span class="sxs-lookup"><span data-stu-id="f549c-113">EnumerateThreads Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)|<span data-ttu-id="f549c-114">Obtiene un enumerador para los subprocesos administrados activos en el proceso.</span><span class="sxs-lookup"><span data-stu-id="f549c-114">Gets an enumerator for the active managed threads in the process.</span></span>|  
|[<span data-ttu-id="f549c-115">HasQueuedCallbacks (método)</span><span class="sxs-lookup"><span data-stu-id="f549c-115">HasQueuedCallbacks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)|<span data-ttu-id="f549c-116">Obtiene un valor que indica si las devoluciones de llamada administradas actualmente están en cola para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="f549c-116">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>|  
|[<span data-ttu-id="f549c-117">IsRunning (método)</span><span class="sxs-lookup"><span data-stu-id="f549c-117">IsRunning Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-isrunning-method.md)|<span data-ttu-id="f549c-118">Obtiene un valor que indica si los subprocesos del proceso se están ejecutando libremente.</span><span class="sxs-lookup"><span data-stu-id="f549c-118">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>|  
|[<span data-ttu-id="f549c-119">SetAllThreadsDebugState (método)</span><span class="sxs-lookup"><span data-stu-id="f549c-119">SetAllThreadsDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md)|<span data-ttu-id="f549c-120">Establece el estado de depuración de todos los subprocesos administrados en el proceso.</span><span class="sxs-lookup"><span data-stu-id="f549c-120">Sets the debug state of all managed threads in the process.</span></span>|  
|[<span data-ttu-id="f549c-121">Stop (método)</span><span class="sxs-lookup"><span data-stu-id="f549c-121">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)|<span data-ttu-id="f549c-122">Realiza una detención cooperativa de todos los subprocesos que ejecutan código administrado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="f549c-122">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>|  
|[<span data-ttu-id="f549c-123">Terminate (método)</span><span class="sxs-lookup"><span data-stu-id="f549c-123">Terminate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-terminate-method.md)|<span data-ttu-id="f549c-124">Finaliza el proceso con el código de salida especificado.</span><span class="sxs-lookup"><span data-stu-id="f549c-124">Terminates the process with the specified exit code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f549c-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f549c-125">Remarks</span></span>  
 <span data-ttu-id="f549c-126">Si `ICorDebugController` es controlar un proceso, el ámbito incluye todos los subprocesos del proceso.</span><span class="sxs-lookup"><span data-stu-id="f549c-126">If `ICorDebugController` is controlling a process, the scope includes all threads of the process.</span></span> <span data-ttu-id="f549c-127">Si `ICorDebugController` es controlar un dominio de aplicación, el ámbito incluye solo los subprocesos de ese dominio de aplicación determinado.</span><span class="sxs-lookup"><span data-stu-id="f549c-127">If `ICorDebugController` is controlling an application domain, the scope includes only the threads of that particular application domain.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f549c-128">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="f549c-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f549c-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f549c-129">Requirements</span></span>  
 <span data-ttu-id="f549c-130">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f549c-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f549c-131">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f549c-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f549c-132">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f549c-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f549c-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f549c-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f549c-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="f549c-134">See also</span></span>
- [<span data-ttu-id="f549c-135">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f549c-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
