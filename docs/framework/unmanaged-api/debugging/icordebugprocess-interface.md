---
title: ICorDebugProcess Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess
helpviewer_keywords: ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: be86f4b5-418a-4c5c-a67c-97148c65ed8c
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ee526a79d89a9e4e3483daa07a512b6b7f920e70
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess-interface1"></a><span data-ttu-id="ba6c3-102">ICorDebugProcess Interfaz1</span><span class="sxs-lookup"><span data-stu-id="ba6c3-102">ICorDebugProcess Interface1</span></span>
<span data-ttu-id="ba6c3-103">Representa un proceso que ejecuta código administrado.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-103">Represents a process that is executing managed code.</span></span> <span data-ttu-id="ba6c3-104">Esta interfaz es una subclase de ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ba6c3-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="ba6c3-105">Methods</span></span>  
  
|<span data-ttu-id="ba6c3-106">Método</span><span class="sxs-lookup"><span data-stu-id="ba6c3-106">Method</span></span>|<span data-ttu-id="ba6c3-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba6c3-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ba6c3-108">ClearCurrentException (método)</span><span class="sxs-lookup"><span data-stu-id="ba6c3-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md)|<span data-ttu-id="ba6c3-109">Borra la excepción no administrada actual del subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-109">Clears the current unmanaged exception on the given thread.</span></span>|  
|[<span data-ttu-id="ba6c3-110">EnableLogMessages (método)</span><span class="sxs-lookup"><span data-stu-id="ba6c3-110">EnableLogMessages Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enablelogmessages-method.md)|<span data-ttu-id="ba6c3-111">Habilita y deshabilita el envío de mensajes de registro al depurador.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-111">Enables and disables the sending of log messages to the debugger.</span></span>|  
|[<span data-ttu-id="ba6c3-112">EnumerateAppDomains (método)</span><span class="sxs-lookup"><span data-stu-id="ba6c3-112">EnumerateAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateappdomains-method.md)|<span data-ttu-id="ba6c3-113">Enumera todos los dominios de aplicación en el proceso.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-113">Enumerates all of the application domains in the process.</span></span>|  
|[<span data-ttu-id="ba6c3-114">EnumerateObjects (método)</span><span class="sxs-lookup"><span data-stu-id="ba6c3-114">EnumerateObjects Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateobjects-method.md)|<span data-ttu-id="ba6c3-115">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-115">Not implemented.</span></span>|  
|[<span data-ttu-id="ba6c3-116">GetHandle (método)</span><span class="sxs-lookup"><span data-stu-id="ba6c3-116">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethandle-method.md)|<span data-ttu-id="ba6c3-117">Obtiene un identificador para el proceso.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-117">Gets a handle to the process.</span></span>|  
|[<span data-ttu-id="ba6c3-118">GetHelperThreadID (método)</span><span class="sxs-lookup"><span data-stu-id="ba6c3-118">GetHelperThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethelperthreadid-method.md)|<span data-ttu-id="ba6c3-119">Obtiene el identificador de subproceso del sistema operativo (SO) para el subproceso del depurador auxiliar interno.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-119">Gets the operating system (OS) thread ID for the debugger's internal helper thread.</span></span>|  
|[<span data-ttu-id="ba6c3-120">GetID (método)</span><span class="sxs-lookup"><span data-stu-id="ba6c3-120">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md)|<span data-ttu-id="ba6c3-121">Obtiene el identificador de sistema operativo (SO) del proceso.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-121">Gets the operating system (OS) ID of the process.</span></span>|  
|[<span data-ttu-id="ba6c3-122">GetObject (método)</span><span class="sxs-lookup"><span data-stu-id="ba6c3-122">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getobject-method.md)|<span data-ttu-id="ba6c3-123">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-123">Not implemented.</span></span>|  
|[<span data-ttu-id="ba6c3-124">GetThread (método)</span><span class="sxs-lookup"><span data-stu-id="ba6c3-124">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthread-method.md)|<span data-ttu-id="ba6c3-125">Obtiene la instancia de ICorDebugThread que tiene el subproceso de sistema operativo especificado.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-125">Gets the ICorDebugThread instance that has the specified OS thread ID.</span></span>|  
|[<span data-ttu-id="ba6c3-126">GetThreadContext (método)</span><span class="sxs-lookup"><span data-stu-id="ba6c3-126">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md)|<span data-ttu-id="ba6c3-127">Obtiene el contexto para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-127">Gets the context for the given thread.</span></span>|  
|[<span data-ttu-id="ba6c3-128">IsOSSuspended (método)</span><span class="sxs-lookup"><span data-stu-id="ba6c3-128">IsOSSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-isossuspended-method.md)|<span data-ttu-id="ba6c3-129">Determina si el subproceso se ha suspendido porque el depurador que detenga el proceso.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-129">Determines whether the thread has been suspended as a result of the debugger stopping the process.</span></span>|  
|[<span data-ttu-id="ba6c3-130">IsTransitionStub (método)</span><span class="sxs-lookup"><span data-stu-id="ba6c3-130">IsTransitionStub Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-istransitionstub-method.md)|<span data-ttu-id="ba6c3-131">Determina si una dirección está dentro de un código auxiliar que provocará una transición a código administrado.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-131">Determines whether an address is inside a stub that will cause a transition to managed code.</span></span>|  
|[<span data-ttu-id="ba6c3-132">ModifyLogSwitch (método)</span><span class="sxs-lookup"><span data-stu-id="ba6c3-132">ModifyLogSwitch Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-modifylogswitch-method.md)|<span data-ttu-id="ba6c3-133">Establece el nivel de gravedad del modificador de registro especificado.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-133">Sets the severity level of the specified log switch.</span></span>|  
|[<span data-ttu-id="ba6c3-134">ReadMemory (método)</span><span class="sxs-lookup"><span data-stu-id="ba6c3-134">ReadMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-readmemory-method.md)|<span data-ttu-id="ba6c3-135">Lee la memoria del proceso.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-135">Reads memory from the process.</span></span>|  
|[<span data-ttu-id="ba6c3-136">SetThreadContext (método)</span><span class="sxs-lookup"><span data-stu-id="ba6c3-136">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md)|<span data-ttu-id="ba6c3-137">Establece el contexto para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-137">Sets the context for the given thread.</span></span>|  
|[<span data-ttu-id="ba6c3-138">ThreadForFiberCookie (método)</span><span class="sxs-lookup"><span data-stu-id="ba6c3-138">ThreadForFiberCookie Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-threadforfibercookie-method.md)|<span data-ttu-id="ba6c3-139">Desusado.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-139">Deprecated.</span></span>|  
|[<span data-ttu-id="ba6c3-140">WriteMemory (método)</span><span class="sxs-lookup"><span data-stu-id="ba6c3-140">WriteMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-writememory-method.md)|<span data-ttu-id="ba6c3-141">Escribe datos en un área de memoria en el proceso.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-141">Writes data to an area of memory in the process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba6c3-142">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ba6c3-142">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba6c3-143">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-143">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba6c3-144">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ba6c3-144">Requirements</span></span>  
 <span data-ttu-id="ba6c3-145">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba6c3-145">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba6c3-146">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ba6c3-146">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ba6c3-147">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba6c3-147">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba6c3-148">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba6c3-148">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba6c3-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba6c3-149">See Also</span></span>  
 [<span data-ttu-id="ba6c3-150">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba6c3-150">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [<span data-ttu-id="ba6c3-151">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="ba6c3-151">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
