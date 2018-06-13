---
title: ICorDebugProcess Interfaz1
ms.date: 03/30/2017
api_name:
- ICorDebugProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess
helpviewer_keywords:
- ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: be86f4b5-418a-4c5c-a67c-97148c65ed8c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06e4e3854a850c9639e93c8db2ec8ccd567b242b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423174"
---
# <a name="icordebugprocess-interface1"></a><span data-ttu-id="855a4-102">ICorDebugProcess Interfaz1</span><span class="sxs-lookup"><span data-stu-id="855a4-102">ICorDebugProcess Interface1</span></span>
<span data-ttu-id="855a4-103">Representa un proceso que ejecuta código administrado.</span><span class="sxs-lookup"><span data-stu-id="855a4-103">Represents a process that is executing managed code.</span></span> <span data-ttu-id="855a4-104">Esta interfaz es una subclase de ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="855a4-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="855a4-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="855a4-105">Methods</span></span>  
  
|<span data-ttu-id="855a4-106">Método</span><span class="sxs-lookup"><span data-stu-id="855a4-106">Method</span></span>|<span data-ttu-id="855a4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="855a4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="855a4-108">ClearCurrentException (método)</span><span class="sxs-lookup"><span data-stu-id="855a4-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md)|<span data-ttu-id="855a4-109">Borra la excepción no administrada actual del subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="855a4-109">Clears the current unmanaged exception on the given thread.</span></span>|  
|[<span data-ttu-id="855a4-110">EnableLogMessages (método)</span><span class="sxs-lookup"><span data-stu-id="855a4-110">EnableLogMessages Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enablelogmessages-method.md)|<span data-ttu-id="855a4-111">Habilita y deshabilita el envío de mensajes de registro al depurador.</span><span class="sxs-lookup"><span data-stu-id="855a4-111">Enables and disables the sending of log messages to the debugger.</span></span>|  
|[<span data-ttu-id="855a4-112">EnumerateAppDomains (método)</span><span class="sxs-lookup"><span data-stu-id="855a4-112">EnumerateAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateappdomains-method.md)|<span data-ttu-id="855a4-113">Enumera todos los dominios de aplicación en el proceso.</span><span class="sxs-lookup"><span data-stu-id="855a4-113">Enumerates all of the application domains in the process.</span></span>|  
|[<span data-ttu-id="855a4-114">EnumerateObjects (método)</span><span class="sxs-lookup"><span data-stu-id="855a4-114">EnumerateObjects Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateobjects-method.md)|<span data-ttu-id="855a4-115">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="855a4-115">Not implemented.</span></span>|  
|[<span data-ttu-id="855a4-116">GetHandle (método)</span><span class="sxs-lookup"><span data-stu-id="855a4-116">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethandle-method.md)|<span data-ttu-id="855a4-117">Obtiene un identificador para el proceso.</span><span class="sxs-lookup"><span data-stu-id="855a4-117">Gets a handle to the process.</span></span>|  
|[<span data-ttu-id="855a4-118">GetHelperThreadID (método)</span><span class="sxs-lookup"><span data-stu-id="855a4-118">GetHelperThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethelperthreadid-method.md)|<span data-ttu-id="855a4-119">Obtiene el identificador de subproceso del sistema operativo (SO) para el subproceso del depurador auxiliar interno.</span><span class="sxs-lookup"><span data-stu-id="855a4-119">Gets the operating system (OS) thread ID for the debugger's internal helper thread.</span></span>|  
|[<span data-ttu-id="855a4-120">GetID (método)</span><span class="sxs-lookup"><span data-stu-id="855a4-120">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md)|<span data-ttu-id="855a4-121">Obtiene el identificador de sistema operativo (SO) del proceso.</span><span class="sxs-lookup"><span data-stu-id="855a4-121">Gets the operating system (OS) ID of the process.</span></span>|  
|[<span data-ttu-id="855a4-122">GetObject (método)</span><span class="sxs-lookup"><span data-stu-id="855a4-122">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getobject-method.md)|<span data-ttu-id="855a4-123">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="855a4-123">Not implemented.</span></span>|  
|[<span data-ttu-id="855a4-124">GetThread (método)</span><span class="sxs-lookup"><span data-stu-id="855a4-124">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthread-method.md)|<span data-ttu-id="855a4-125">Obtiene la instancia de ICorDebugThread que tiene el subproceso de sistema operativo especificado.</span><span class="sxs-lookup"><span data-stu-id="855a4-125">Gets the ICorDebugThread instance that has the specified OS thread ID.</span></span>|  
|[<span data-ttu-id="855a4-126">GetThreadContext (método)</span><span class="sxs-lookup"><span data-stu-id="855a4-126">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md)|<span data-ttu-id="855a4-127">Obtiene el contexto para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="855a4-127">Gets the context for the given thread.</span></span>|  
|[<span data-ttu-id="855a4-128">IsOSSuspended (método)</span><span class="sxs-lookup"><span data-stu-id="855a4-128">IsOSSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-isossuspended-method.md)|<span data-ttu-id="855a4-129">Determina si el subproceso se ha suspendido porque el depurador que detenga el proceso.</span><span class="sxs-lookup"><span data-stu-id="855a4-129">Determines whether the thread has been suspended as a result of the debugger stopping the process.</span></span>|  
|[<span data-ttu-id="855a4-130">IsTransitionStub (método)</span><span class="sxs-lookup"><span data-stu-id="855a4-130">IsTransitionStub Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-istransitionstub-method.md)|<span data-ttu-id="855a4-131">Determina si una dirección está dentro de un código auxiliar que provocará una transición a código administrado.</span><span class="sxs-lookup"><span data-stu-id="855a4-131">Determines whether an address is inside a stub that will cause a transition to managed code.</span></span>|  
|[<span data-ttu-id="855a4-132">ModifyLogSwitch (método)</span><span class="sxs-lookup"><span data-stu-id="855a4-132">ModifyLogSwitch Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-modifylogswitch-method.md)|<span data-ttu-id="855a4-133">Establece el nivel de gravedad del modificador de registro especificado.</span><span class="sxs-lookup"><span data-stu-id="855a4-133">Sets the severity level of the specified log switch.</span></span>|  
|[<span data-ttu-id="855a4-134">ReadMemory (método)</span><span class="sxs-lookup"><span data-stu-id="855a4-134">ReadMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-readmemory-method.md)|<span data-ttu-id="855a4-135">Lee la memoria del proceso.</span><span class="sxs-lookup"><span data-stu-id="855a4-135">Reads memory from the process.</span></span>|  
|[<span data-ttu-id="855a4-136">SetThreadContext (método)</span><span class="sxs-lookup"><span data-stu-id="855a4-136">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md)|<span data-ttu-id="855a4-137">Establece el contexto para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="855a4-137">Sets the context for the given thread.</span></span>|  
|[<span data-ttu-id="855a4-138">ThreadForFiberCookie (método)</span><span class="sxs-lookup"><span data-stu-id="855a4-138">ThreadForFiberCookie Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-threadforfibercookie-method.md)|<span data-ttu-id="855a4-139">Desusado.</span><span class="sxs-lookup"><span data-stu-id="855a4-139">Deprecated.</span></span>|  
|[<span data-ttu-id="855a4-140">WriteMemory (método)</span><span class="sxs-lookup"><span data-stu-id="855a4-140">WriteMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-writememory-method.md)|<span data-ttu-id="855a4-141">Escribe datos en un área de memoria en el proceso.</span><span class="sxs-lookup"><span data-stu-id="855a4-141">Writes data to an area of memory in the process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="855a4-142">Comentarios</span><span class="sxs-lookup"><span data-stu-id="855a4-142">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="855a4-143">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="855a4-143">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="855a4-144">Requisitos</span><span class="sxs-lookup"><span data-stu-id="855a4-144">Requirements</span></span>  
 <span data-ttu-id="855a4-145">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="855a4-145">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="855a4-146">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="855a4-146">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="855a4-147">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="855a4-147">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="855a4-148">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="855a4-148">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="855a4-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="855a4-149">See Also</span></span>  
 [<span data-ttu-id="855a4-150">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="855a4-150">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [<span data-ttu-id="855a4-151">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="855a4-151">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
