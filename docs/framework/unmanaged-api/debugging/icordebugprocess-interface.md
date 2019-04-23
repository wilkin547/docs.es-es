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
ms.openlocfilehash: 46d96d66f16cd956d8fab1afe00486d564e37953
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59216800"
---
# <a name="icordebugprocess-interface"></a><span data-ttu-id="fdaa9-102">Interfaz ICorDebugProcess</span><span class="sxs-lookup"><span data-stu-id="fdaa9-102">ICorDebugProcess Interface</span></span>
<span data-ttu-id="fdaa9-103">Representa un proceso que ejecuta código administrado.</span><span class="sxs-lookup"><span data-stu-id="fdaa9-103">Represents a process that is executing managed code.</span></span> <span data-ttu-id="fdaa9-104">Esta interfaz es una subclase de ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="fdaa9-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fdaa9-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="fdaa9-105">Methods</span></span>  
  
|<span data-ttu-id="fdaa9-106">Método</span><span class="sxs-lookup"><span data-stu-id="fdaa9-106">Method</span></span>|<span data-ttu-id="fdaa9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="fdaa9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fdaa9-108">ClearCurrentException (método)</span><span class="sxs-lookup"><span data-stu-id="fdaa9-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md)|<span data-ttu-id="fdaa9-109">Borra la excepción no administrada actual del subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="fdaa9-109">Clears the current unmanaged exception on the given thread.</span></span>|  
|[<span data-ttu-id="fdaa9-110">EnableLogMessages (método)</span><span class="sxs-lookup"><span data-stu-id="fdaa9-110">EnableLogMessages Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enablelogmessages-method.md)|<span data-ttu-id="fdaa9-111">Habilita y deshabilita el envío de mensajes de registro al depurador.</span><span class="sxs-lookup"><span data-stu-id="fdaa9-111">Enables and disables the sending of log messages to the debugger.</span></span>|  
|[<span data-ttu-id="fdaa9-112">EnumerateAppDomains (método)</span><span class="sxs-lookup"><span data-stu-id="fdaa9-112">EnumerateAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateappdomains-method.md)|<span data-ttu-id="fdaa9-113">Enumera todos los dominios de aplicación en el proceso.</span><span class="sxs-lookup"><span data-stu-id="fdaa9-113">Enumerates all of the application domains in the process.</span></span>|  
|[<span data-ttu-id="fdaa9-114">EnumerateObjects (método)</span><span class="sxs-lookup"><span data-stu-id="fdaa9-114">EnumerateObjects Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateobjects-method.md)|<span data-ttu-id="fdaa9-115">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="fdaa9-115">Not implemented.</span></span>|  
|[<span data-ttu-id="fdaa9-116">GetHandle (método)</span><span class="sxs-lookup"><span data-stu-id="fdaa9-116">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethandle-method.md)|<span data-ttu-id="fdaa9-117">Obtiene un identificador para el proceso.</span><span class="sxs-lookup"><span data-stu-id="fdaa9-117">Gets a handle to the process.</span></span>|  
|[<span data-ttu-id="fdaa9-118">GetHelperThreadID (método)</span><span class="sxs-lookup"><span data-stu-id="fdaa9-118">GetHelperThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethelperthreadid-method.md)|<span data-ttu-id="fdaa9-119">Obtiene el identificador de subproceso del sistema operativo (SO) para el subproceso del depurador auxiliar interno.</span><span class="sxs-lookup"><span data-stu-id="fdaa9-119">Gets the operating system (OS) thread ID for the debugger's internal helper thread.</span></span>|  
|[<span data-ttu-id="fdaa9-120">GetID (método)</span><span class="sxs-lookup"><span data-stu-id="fdaa9-120">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md)|<span data-ttu-id="fdaa9-121">Obtiene el identificador de sistema operativo (SO) del proceso.</span><span class="sxs-lookup"><span data-stu-id="fdaa9-121">Gets the operating system (OS) ID of the process.</span></span>|  
|[<span data-ttu-id="fdaa9-122">GetObject (método)</span><span class="sxs-lookup"><span data-stu-id="fdaa9-122">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getobject-method.md)|<span data-ttu-id="fdaa9-123">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="fdaa9-123">Not implemented.</span></span>|  
|[<span data-ttu-id="fdaa9-124">GetThread (método)</span><span class="sxs-lookup"><span data-stu-id="fdaa9-124">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthread-method.md)|<span data-ttu-id="fdaa9-125">Obtiene la instancia de ICorDebugThread que tiene el subproceso del sistema operativo especificado.</span><span class="sxs-lookup"><span data-stu-id="fdaa9-125">Gets the ICorDebugThread instance that has the specified OS thread ID.</span></span>|  
|[<span data-ttu-id="fdaa9-126">GetThreadContext (método)</span><span class="sxs-lookup"><span data-stu-id="fdaa9-126">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md)|<span data-ttu-id="fdaa9-127">Obtiene el contexto del subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="fdaa9-127">Gets the context for the given thread.</span></span>|  
|[<span data-ttu-id="fdaa9-128">IsOSSuspended (método)</span><span class="sxs-lookup"><span data-stu-id="fdaa9-128">IsOSSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-isossuspended-method.md)|<span data-ttu-id="fdaa9-129">Determina si el subproceso se ha suspendido porque el depurador que detenga el proceso.</span><span class="sxs-lookup"><span data-stu-id="fdaa9-129">Determines whether the thread has been suspended as a result of the debugger stopping the process.</span></span>|  
|[<span data-ttu-id="fdaa9-130">IsTransitionStub (método)</span><span class="sxs-lookup"><span data-stu-id="fdaa9-130">IsTransitionStub Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-istransitionstub-method.md)|<span data-ttu-id="fdaa9-131">Determina si es una dirección dentro de un código auxiliar que provocará una transición a código administrado.</span><span class="sxs-lookup"><span data-stu-id="fdaa9-131">Determines whether an address is inside a stub that will cause a transition to managed code.</span></span>|  
|[<span data-ttu-id="fdaa9-132">ModifyLogSwitch (método)</span><span class="sxs-lookup"><span data-stu-id="fdaa9-132">ModifyLogSwitch Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-modifylogswitch-method.md)|<span data-ttu-id="fdaa9-133">Establece el nivel de gravedad del modificador de registro especificado.</span><span class="sxs-lookup"><span data-stu-id="fdaa9-133">Sets the severity level of the specified log switch.</span></span>|  
|[<span data-ttu-id="fdaa9-134">ReadMemory (método)</span><span class="sxs-lookup"><span data-stu-id="fdaa9-134">ReadMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-readmemory-method.md)|<span data-ttu-id="fdaa9-135">Lee la memoria del proceso.</span><span class="sxs-lookup"><span data-stu-id="fdaa9-135">Reads memory from the process.</span></span>|  
|[<span data-ttu-id="fdaa9-136">SetThreadContext (método)</span><span class="sxs-lookup"><span data-stu-id="fdaa9-136">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md)|<span data-ttu-id="fdaa9-137">Establece el contexto del subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="fdaa9-137">Sets the context for the given thread.</span></span>|  
|[<span data-ttu-id="fdaa9-138">ThreadForFiberCookie (método)</span><span class="sxs-lookup"><span data-stu-id="fdaa9-138">ThreadForFiberCookie Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-threadforfibercookie-method.md)|<span data-ttu-id="fdaa9-139">Desusado.</span><span class="sxs-lookup"><span data-stu-id="fdaa9-139">Deprecated.</span></span>|  
|[<span data-ttu-id="fdaa9-140">WriteMemory (método)</span><span class="sxs-lookup"><span data-stu-id="fdaa9-140">WriteMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-writememory-method.md)|<span data-ttu-id="fdaa9-141">Escribe datos en un área de memoria en el proceso.</span><span class="sxs-lookup"><span data-stu-id="fdaa9-141">Writes data to an area of memory in the process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fdaa9-142">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fdaa9-142">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fdaa9-143">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="fdaa9-143">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdaa9-144">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fdaa9-144">Requirements</span></span>  
 <span data-ttu-id="fdaa9-145">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdaa9-145">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdaa9-146">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fdaa9-146">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fdaa9-147">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fdaa9-147">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fdaa9-148">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdaa9-148">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdaa9-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="fdaa9-149">See also</span></span>

- [<span data-ttu-id="fdaa9-150">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fdaa9-150">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="fdaa9-151">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="fdaa9-151">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
