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
ms.openlocfilehash: b2429052173a187297b67c756213e5d27a79298b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792602"
---
# <a name="icordebugprocess-interface"></a><span data-ttu-id="8955a-102">Interfaz ICorDebugProcess</span><span class="sxs-lookup"><span data-stu-id="8955a-102">ICorDebugProcess Interface</span></span>
<span data-ttu-id="8955a-103">Representa un proceso que ejecuta código administrado.</span><span class="sxs-lookup"><span data-stu-id="8955a-103">Represents a process that is executing managed code.</span></span> <span data-ttu-id="8955a-104">Esta interfaz es una subclase de ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="8955a-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8955a-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="8955a-105">Methods</span></span>  
  
|<span data-ttu-id="8955a-106">Método</span><span class="sxs-lookup"><span data-stu-id="8955a-106">Method</span></span>|<span data-ttu-id="8955a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8955a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8955a-108">ClearCurrentException (método)</span><span class="sxs-lookup"><span data-stu-id="8955a-108">ClearCurrentException Method</span></span>](icordebugprocess-clearcurrentexception-method.md)|<span data-ttu-id="8955a-109">Borra la excepción no administrada actual en el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="8955a-109">Clears the current unmanaged exception on the given thread.</span></span>|  
|[<span data-ttu-id="8955a-110">EnableLogMessages (método)</span><span class="sxs-lookup"><span data-stu-id="8955a-110">EnableLogMessages Method</span></span>](icordebugprocess-enablelogmessages-method.md)|<span data-ttu-id="8955a-111">Habilita y deshabilita el envío de mensajes de registro al depurador.</span><span class="sxs-lookup"><span data-stu-id="8955a-111">Enables and disables the sending of log messages to the debugger.</span></span>|  
|[<span data-ttu-id="8955a-112">EnumerateAppDomains (método)</span><span class="sxs-lookup"><span data-stu-id="8955a-112">EnumerateAppDomains Method</span></span>](icordebugprocess-enumerateappdomains-method.md)|<span data-ttu-id="8955a-113">Enumera todos los dominios de aplicación del proceso.</span><span class="sxs-lookup"><span data-stu-id="8955a-113">Enumerates all of the application domains in the process.</span></span>|  
|[<span data-ttu-id="8955a-114">EnumerateObjects (método)</span><span class="sxs-lookup"><span data-stu-id="8955a-114">EnumerateObjects Method</span></span>](icordebugprocess-enumerateobjects-method.md)|<span data-ttu-id="8955a-115">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="8955a-115">Not implemented.</span></span>|  
|[<span data-ttu-id="8955a-116">GetHandle (método)</span><span class="sxs-lookup"><span data-stu-id="8955a-116">GetHandle Method</span></span>](icordebugprocess-gethandle-method.md)|<span data-ttu-id="8955a-117">Obtiene un identificador para el proceso.</span><span class="sxs-lookup"><span data-stu-id="8955a-117">Gets a handle to the process.</span></span>|  
|[<span data-ttu-id="8955a-118">GetHelperThreadID (método)</span><span class="sxs-lookup"><span data-stu-id="8955a-118">GetHelperThreadID Method</span></span>](icordebugprocess-gethelperthreadid-method.md)|<span data-ttu-id="8955a-119">Obtiene el identificador del subproceso del sistema operativo (SO) del subproceso auxiliar interno del depurador.</span><span class="sxs-lookup"><span data-stu-id="8955a-119">Gets the operating system (OS) thread ID for the debugger's internal helper thread.</span></span>|  
|[<span data-ttu-id="8955a-120">GetID (método)</span><span class="sxs-lookup"><span data-stu-id="8955a-120">GetID Method</span></span>](icordebugprocess-getid-method.md)|<span data-ttu-id="8955a-121">Obtiene el identificador del sistema operativo (SO) del proceso.</span><span class="sxs-lookup"><span data-stu-id="8955a-121">Gets the operating system (OS) ID of the process.</span></span>|  
|[<span data-ttu-id="8955a-122">GetObject (método)</span><span class="sxs-lookup"><span data-stu-id="8955a-122">GetObject Method</span></span>](icordebugprocess-getobject-method.md)|<span data-ttu-id="8955a-123">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="8955a-123">Not implemented.</span></span>|  
|[<span data-ttu-id="8955a-124">GetThread (método)</span><span class="sxs-lookup"><span data-stu-id="8955a-124">GetThread Method</span></span>](icordebugprocess-getthread-method.md)|<span data-ttu-id="8955a-125">Obtiene la instancia de ICorDebugThread que tiene el identificador de subproceso de sistema operativo especificado.</span><span class="sxs-lookup"><span data-stu-id="8955a-125">Gets the ICorDebugThread instance that has the specified OS thread ID.</span></span>|  
|[<span data-ttu-id="8955a-126">GetThreadContext (método)</span><span class="sxs-lookup"><span data-stu-id="8955a-126">GetThreadContext Method</span></span>](icordebugprocess-getthreadcontext-method.md)|<span data-ttu-id="8955a-127">Obtiene el contexto para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="8955a-127">Gets the context for the given thread.</span></span>|  
|[<span data-ttu-id="8955a-128">IsOSSuspended (método)</span><span class="sxs-lookup"><span data-stu-id="8955a-128">IsOSSuspended Method</span></span>](icordebugprocess-isossuspended-method.md)|<span data-ttu-id="8955a-129">Determina si el subproceso se ha suspendido como resultado de que el depurador detenga el proceso.</span><span class="sxs-lookup"><span data-stu-id="8955a-129">Determines whether the thread has been suspended as a result of the debugger stopping the process.</span></span>|  
|[<span data-ttu-id="8955a-130">IsTransitionStub (método)</span><span class="sxs-lookup"><span data-stu-id="8955a-130">IsTransitionStub Method</span></span>](icordebugprocess-istransitionstub-method.md)|<span data-ttu-id="8955a-131">Determina si una dirección está dentro de un código auxiliar que producirá una transición a código administrado.</span><span class="sxs-lookup"><span data-stu-id="8955a-131">Determines whether an address is inside a stub that will cause a transition to managed code.</span></span>|  
|[<span data-ttu-id="8955a-132">ModifyLogSwitch (método)</span><span class="sxs-lookup"><span data-stu-id="8955a-132">ModifyLogSwitch Method</span></span>](icordebugprocess-modifylogswitch-method.md)|<span data-ttu-id="8955a-133">Establece el nivel de gravedad del modificador de registro especificado.</span><span class="sxs-lookup"><span data-stu-id="8955a-133">Sets the severity level of the specified log switch.</span></span>|  
|[<span data-ttu-id="8955a-134">ReadMemory (método)</span><span class="sxs-lookup"><span data-stu-id="8955a-134">ReadMemory Method</span></span>](icordebugprocess-readmemory-method.md)|<span data-ttu-id="8955a-135">Lee la memoria del proceso.</span><span class="sxs-lookup"><span data-stu-id="8955a-135">Reads memory from the process.</span></span>|  
|[<span data-ttu-id="8955a-136">SetThreadContext (método)</span><span class="sxs-lookup"><span data-stu-id="8955a-136">SetThreadContext Method</span></span>](icordebugprocess-setthreadcontext-method.md)|<span data-ttu-id="8955a-137">Establece el contexto para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="8955a-137">Sets the context for the given thread.</span></span>|  
|[<span data-ttu-id="8955a-138">ThreadForFiberCookie (método)</span><span class="sxs-lookup"><span data-stu-id="8955a-138">ThreadForFiberCookie Method</span></span>](icordebugprocess-threadforfibercookie-method.md)|<span data-ttu-id="8955a-139">Opción obsoleta.</span><span class="sxs-lookup"><span data-stu-id="8955a-139">Deprecated.</span></span>|  
|[<span data-ttu-id="8955a-140">WriteMemory (método)</span><span class="sxs-lookup"><span data-stu-id="8955a-140">WriteMemory Method</span></span>](icordebugprocess-writememory-method.md)|<span data-ttu-id="8955a-141">Escribe datos en un área de memoria del proceso.</span><span class="sxs-lookup"><span data-stu-id="8955a-141">Writes data to an area of memory in the process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8955a-142">Notas</span><span class="sxs-lookup"><span data-stu-id="8955a-142">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8955a-143">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="8955a-143">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8955a-144">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="8955a-144">Requirements</span></span>  
 <span data-ttu-id="8955a-145">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8955a-145">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8955a-146">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8955a-146">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8955a-147">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8955a-147">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8955a-148">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8955a-148">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8955a-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="8955a-149">See also</span></span>

- [<span data-ttu-id="8955a-150">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8955a-150">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="8955a-151">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="8955a-151">Debugging Interfaces</span></span>](debugging-interfaces.md)
