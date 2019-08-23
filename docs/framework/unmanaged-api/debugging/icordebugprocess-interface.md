---
title: Interfaz ICorDebugProcess
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
ms.openlocfilehash: b99630ba60cd84254024b91dba9ef9922fd7e041
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943313"
---
# <a name="icordebugprocess-interface"></a><span data-ttu-id="ff76e-102">Interfaz ICorDebugProcess</span><span class="sxs-lookup"><span data-stu-id="ff76e-102">ICorDebugProcess Interface</span></span>
<span data-ttu-id="ff76e-103">Representa un proceso que ejecuta código administrado.</span><span class="sxs-lookup"><span data-stu-id="ff76e-103">Represents a process that is executing managed code.</span></span> <span data-ttu-id="ff76e-104">Esta interfaz es una subclase de ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="ff76e-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ff76e-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="ff76e-105">Methods</span></span>  
  
|<span data-ttu-id="ff76e-106">Método</span><span class="sxs-lookup"><span data-stu-id="ff76e-106">Method</span></span>|<span data-ttu-id="ff76e-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ff76e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ff76e-108">ClearCurrentException (método)</span><span class="sxs-lookup"><span data-stu-id="ff76e-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md)|<span data-ttu-id="ff76e-109">Borra la excepción no administrada actual en el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="ff76e-109">Clears the current unmanaged exception on the given thread.</span></span>|  
|[<span data-ttu-id="ff76e-110">EnableLogMessages (método)</span><span class="sxs-lookup"><span data-stu-id="ff76e-110">EnableLogMessages Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enablelogmessages-method.md)|<span data-ttu-id="ff76e-111">Habilita y deshabilita el envío de mensajes de registro al depurador.</span><span class="sxs-lookup"><span data-stu-id="ff76e-111">Enables and disables the sending of log messages to the debugger.</span></span>|  
|[<span data-ttu-id="ff76e-112">EnumerateAppDomains (método)</span><span class="sxs-lookup"><span data-stu-id="ff76e-112">EnumerateAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateappdomains-method.md)|<span data-ttu-id="ff76e-113">Enumera todos los dominios de aplicación del proceso.</span><span class="sxs-lookup"><span data-stu-id="ff76e-113">Enumerates all of the application domains in the process.</span></span>|  
|[<span data-ttu-id="ff76e-114">EnumerateObjects (método)</span><span class="sxs-lookup"><span data-stu-id="ff76e-114">EnumerateObjects Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateobjects-method.md)|<span data-ttu-id="ff76e-115">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="ff76e-115">Not implemented.</span></span>|  
|[<span data-ttu-id="ff76e-116">GetHandle (método)</span><span class="sxs-lookup"><span data-stu-id="ff76e-116">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethandle-method.md)|<span data-ttu-id="ff76e-117">Obtiene un identificador para el proceso.</span><span class="sxs-lookup"><span data-stu-id="ff76e-117">Gets a handle to the process.</span></span>|  
|[<span data-ttu-id="ff76e-118">GetHelperThreadID (método)</span><span class="sxs-lookup"><span data-stu-id="ff76e-118">GetHelperThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethelperthreadid-method.md)|<span data-ttu-id="ff76e-119">Obtiene el identificador del subproceso del sistema operativo (SO) del subproceso auxiliar interno del depurador.</span><span class="sxs-lookup"><span data-stu-id="ff76e-119">Gets the operating system (OS) thread ID for the debugger's internal helper thread.</span></span>|  
|[<span data-ttu-id="ff76e-120">GetID (método)</span><span class="sxs-lookup"><span data-stu-id="ff76e-120">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md)|<span data-ttu-id="ff76e-121">Obtiene el identificador del sistema operativo (SO) del proceso.</span><span class="sxs-lookup"><span data-stu-id="ff76e-121">Gets the operating system (OS) ID of the process.</span></span>|  
|[<span data-ttu-id="ff76e-122">GetObject (método)</span><span class="sxs-lookup"><span data-stu-id="ff76e-122">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getobject-method.md)|<span data-ttu-id="ff76e-123">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="ff76e-123">Not implemented.</span></span>|  
|[<span data-ttu-id="ff76e-124">GetThread (método)</span><span class="sxs-lookup"><span data-stu-id="ff76e-124">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthread-method.md)|<span data-ttu-id="ff76e-125">Obtiene la instancia de ICorDebugThread que tiene el identificador de subproceso de sistema operativo especificado.</span><span class="sxs-lookup"><span data-stu-id="ff76e-125">Gets the ICorDebugThread instance that has the specified OS thread ID.</span></span>|  
|[<span data-ttu-id="ff76e-126">GetThreadContext (método)</span><span class="sxs-lookup"><span data-stu-id="ff76e-126">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md)|<span data-ttu-id="ff76e-127">Obtiene el contexto para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="ff76e-127">Gets the context for the given thread.</span></span>|  
|[<span data-ttu-id="ff76e-128">IsOSSuspended (método)</span><span class="sxs-lookup"><span data-stu-id="ff76e-128">IsOSSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-isossuspended-method.md)|<span data-ttu-id="ff76e-129">Determina si el subproceso se ha suspendido como resultado de que el depurador detenga el proceso.</span><span class="sxs-lookup"><span data-stu-id="ff76e-129">Determines whether the thread has been suspended as a result of the debugger stopping the process.</span></span>|  
|[<span data-ttu-id="ff76e-130">IsTransitionStub (método)</span><span class="sxs-lookup"><span data-stu-id="ff76e-130">IsTransitionStub Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-istransitionstub-method.md)|<span data-ttu-id="ff76e-131">Determina si una dirección está dentro de un código auxiliar que producirá una transición a código administrado.</span><span class="sxs-lookup"><span data-stu-id="ff76e-131">Determines whether an address is inside a stub that will cause a transition to managed code.</span></span>|  
|[<span data-ttu-id="ff76e-132">ModifyLogSwitch (método)</span><span class="sxs-lookup"><span data-stu-id="ff76e-132">ModifyLogSwitch Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-modifylogswitch-method.md)|<span data-ttu-id="ff76e-133">Establece el nivel de gravedad del modificador de registro especificado.</span><span class="sxs-lookup"><span data-stu-id="ff76e-133">Sets the severity level of the specified log switch.</span></span>|  
|[<span data-ttu-id="ff76e-134">ReadMemory (método)</span><span class="sxs-lookup"><span data-stu-id="ff76e-134">ReadMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-readmemory-method.md)|<span data-ttu-id="ff76e-135">Lee la memoria del proceso.</span><span class="sxs-lookup"><span data-stu-id="ff76e-135">Reads memory from the process.</span></span>|  
|[<span data-ttu-id="ff76e-136">SetThreadContext (método)</span><span class="sxs-lookup"><span data-stu-id="ff76e-136">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md)|<span data-ttu-id="ff76e-137">Establece el contexto para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="ff76e-137">Sets the context for the given thread.</span></span>|  
|[<span data-ttu-id="ff76e-138">ThreadForFiberCookie (método)</span><span class="sxs-lookup"><span data-stu-id="ff76e-138">ThreadForFiberCookie Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-threadforfibercookie-method.md)|<span data-ttu-id="ff76e-139">En desuso.</span><span class="sxs-lookup"><span data-stu-id="ff76e-139">Deprecated.</span></span>|  
|[<span data-ttu-id="ff76e-140">WriteMemory (método)</span><span class="sxs-lookup"><span data-stu-id="ff76e-140">WriteMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-writememory-method.md)|<span data-ttu-id="ff76e-141">Escribe datos en un área de memoria del proceso.</span><span class="sxs-lookup"><span data-stu-id="ff76e-141">Writes data to an area of memory in the process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff76e-142">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ff76e-142">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ff76e-143">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="ff76e-143">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff76e-144">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ff76e-144">Requirements</span></span>  
 <span data-ttu-id="ff76e-145">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff76e-145">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff76e-146">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="ff76e-146">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ff76e-147">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff76e-147">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff76e-148">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff76e-148">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff76e-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff76e-149">See also</span></span>

- [<span data-ttu-id="ff76e-150">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ff76e-150">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="ff76e-151">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="ff76e-151">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
