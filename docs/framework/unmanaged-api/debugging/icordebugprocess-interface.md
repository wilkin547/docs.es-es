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
ms.openlocfilehash: 7f9d4ac99234545ef75d9b91e6e84f79a133ffef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95694924"
---
# <a name="icordebugprocess-interface"></a><span data-ttu-id="eb30f-102">Interfaz ICorDebugProcess</span><span class="sxs-lookup"><span data-stu-id="eb30f-102">ICorDebugProcess Interface</span></span>

<span data-ttu-id="eb30f-103">Representa un proceso que ejecuta código administrado.</span><span class="sxs-lookup"><span data-stu-id="eb30f-103">Represents a process that is executing managed code.</span></span> <span data-ttu-id="eb30f-104">Esta interfaz es una subclase de ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="eb30f-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="eb30f-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="eb30f-105">Methods</span></span>  
  
|<span data-ttu-id="eb30f-106">Método</span><span class="sxs-lookup"><span data-stu-id="eb30f-106">Method</span></span>|<span data-ttu-id="eb30f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="eb30f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eb30f-108">Método ClearCurrentException</span><span class="sxs-lookup"><span data-stu-id="eb30f-108">ClearCurrentException Method</span></span>](icordebugprocess-clearcurrentexception-method.md)|<span data-ttu-id="eb30f-109">Borra la excepción no administrada actual en el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="eb30f-109">Clears the current unmanaged exception on the given thread.</span></span>|  
|[<span data-ttu-id="eb30f-110">Método EnableLogMessages</span><span class="sxs-lookup"><span data-stu-id="eb30f-110">EnableLogMessages Method</span></span>](icordebugprocess-enablelogmessages-method.md)|<span data-ttu-id="eb30f-111">Habilita y deshabilita el envío de mensajes de registro al depurador.</span><span class="sxs-lookup"><span data-stu-id="eb30f-111">Enables and disables the sending of log messages to the debugger.</span></span>|  
|[<span data-ttu-id="eb30f-112">Método EnumerateAppDomains</span><span class="sxs-lookup"><span data-stu-id="eb30f-112">EnumerateAppDomains Method</span></span>](icordebugprocess-enumerateappdomains-method.md)|<span data-ttu-id="eb30f-113">Enumera todos los dominios de aplicación del proceso.</span><span class="sxs-lookup"><span data-stu-id="eb30f-113">Enumerates all of the application domains in the process.</span></span>|  
|[<span data-ttu-id="eb30f-114">Método EnumerateObjects</span><span class="sxs-lookup"><span data-stu-id="eb30f-114">EnumerateObjects Method</span></span>](icordebugprocess-enumerateobjects-method.md)|<span data-ttu-id="eb30f-115">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="eb30f-115">Not implemented.</span></span>|  
|[<span data-ttu-id="eb30f-116">Método GetHandle</span><span class="sxs-lookup"><span data-stu-id="eb30f-116">GetHandle Method</span></span>](icordebugprocess-gethandle-method.md)|<span data-ttu-id="eb30f-117">Obtiene un identificador para el proceso.</span><span class="sxs-lookup"><span data-stu-id="eb30f-117">Gets a handle to the process.</span></span>|  
|[<span data-ttu-id="eb30f-118">Método GetHelperThreadID</span><span class="sxs-lookup"><span data-stu-id="eb30f-118">GetHelperThreadID Method</span></span>](icordebugprocess-gethelperthreadid-method.md)|<span data-ttu-id="eb30f-119">Obtiene el identificador del subproceso del sistema operativo (SO) del subproceso auxiliar interno del depurador.</span><span class="sxs-lookup"><span data-stu-id="eb30f-119">Gets the operating system (OS) thread ID for the debugger's internal helper thread.</span></span>|  
|[<span data-ttu-id="eb30f-120">Método GetID</span><span class="sxs-lookup"><span data-stu-id="eb30f-120">GetID Method</span></span>](icordebugprocess-getid-method.md)|<span data-ttu-id="eb30f-121">Obtiene el identificador del sistema operativo (SO) del proceso.</span><span class="sxs-lookup"><span data-stu-id="eb30f-121">Gets the operating system (OS) ID of the process.</span></span>|  
|[<span data-ttu-id="eb30f-122">GetObject (Método)</span><span class="sxs-lookup"><span data-stu-id="eb30f-122">GetObject Method</span></span>](icordebugprocess-getobject-method.md)|<span data-ttu-id="eb30f-123">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="eb30f-123">Not implemented.</span></span>|  
|[<span data-ttu-id="eb30f-124">Método GetThread</span><span class="sxs-lookup"><span data-stu-id="eb30f-124">GetThread Method</span></span>](icordebugprocess-getthread-method.md)|<span data-ttu-id="eb30f-125">Obtiene la instancia de ICorDebugThread que tiene el identificador de subproceso de sistema operativo especificado.</span><span class="sxs-lookup"><span data-stu-id="eb30f-125">Gets the ICorDebugThread instance that has the specified OS thread ID.</span></span>|  
|[<span data-ttu-id="eb30f-126">GetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="eb30f-126">GetThreadContext Method</span></span>](icordebugprocess-getthreadcontext-method.md)|<span data-ttu-id="eb30f-127">Obtiene el contexto para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="eb30f-127">Gets the context for the given thread.</span></span>|  
|[<span data-ttu-id="eb30f-128">Método IsOSSuspended</span><span class="sxs-lookup"><span data-stu-id="eb30f-128">IsOSSuspended Method</span></span>](icordebugprocess-isossuspended-method.md)|<span data-ttu-id="eb30f-129">Determina si el subproceso se ha suspendido como resultado de que el depurador detenga el proceso.</span><span class="sxs-lookup"><span data-stu-id="eb30f-129">Determines whether the thread has been suspended as a result of the debugger stopping the process.</span></span>|  
|[<span data-ttu-id="eb30f-130">Método IsTransitionStub</span><span class="sxs-lookup"><span data-stu-id="eb30f-130">IsTransitionStub Method</span></span>](icordebugprocess-istransitionstub-method.md)|<span data-ttu-id="eb30f-131">Determina si una dirección está dentro de un código auxiliar que producirá una transición a código administrado.</span><span class="sxs-lookup"><span data-stu-id="eb30f-131">Determines whether an address is inside a stub that will cause a transition to managed code.</span></span>|  
|[<span data-ttu-id="eb30f-132">Método ModifyLogSwitch</span><span class="sxs-lookup"><span data-stu-id="eb30f-132">ModifyLogSwitch Method</span></span>](icordebugprocess-modifylogswitch-method.md)|<span data-ttu-id="eb30f-133">Establece el nivel de gravedad del modificador de registro especificado.</span><span class="sxs-lookup"><span data-stu-id="eb30f-133">Sets the severity level of the specified log switch.</span></span>|  
|[<span data-ttu-id="eb30f-134">Método ReadMemory</span><span class="sxs-lookup"><span data-stu-id="eb30f-134">ReadMemory Method</span></span>](icordebugprocess-readmemory-method.md)|<span data-ttu-id="eb30f-135">Lee la memoria del proceso.</span><span class="sxs-lookup"><span data-stu-id="eb30f-135">Reads memory from the process.</span></span>|  
|[<span data-ttu-id="eb30f-136">Método SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="eb30f-136">SetThreadContext Method</span></span>](icordebugprocess-setthreadcontext-method.md)|<span data-ttu-id="eb30f-137">Establece el contexto para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="eb30f-137">Sets the context for the given thread.</span></span>|  
|[<span data-ttu-id="eb30f-138">Método ThreadForFiberCookie</span><span class="sxs-lookup"><span data-stu-id="eb30f-138">ThreadForFiberCookie Method</span></span>](icordebugprocess-threadforfibercookie-method.md)|<span data-ttu-id="eb30f-139">Desusado.</span><span class="sxs-lookup"><span data-stu-id="eb30f-139">Deprecated.</span></span>|  
|[<span data-ttu-id="eb30f-140">Método WriteMemory</span><span class="sxs-lookup"><span data-stu-id="eb30f-140">WriteMemory Method</span></span>](icordebugprocess-writememory-method.md)|<span data-ttu-id="eb30f-141">Escribe datos en un área de memoria del proceso.</span><span class="sxs-lookup"><span data-stu-id="eb30f-141">Writes data to an area of memory in the process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb30f-142">Comentarios</span><span class="sxs-lookup"><span data-stu-id="eb30f-142">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eb30f-143">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="eb30f-143">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb30f-144">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eb30f-144">Requirements</span></span>  

 <span data-ttu-id="eb30f-145">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb30f-145">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb30f-146">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eb30f-146">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eb30f-147">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb30f-147">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb30f-148">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb30f-148">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb30f-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eb30f-149">See also</span></span>

- [<span data-ttu-id="eb30f-150">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="eb30f-150">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="eb30f-151">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="eb30f-151">Debugging Interfaces</span></span>](debugging-interfaces.md)
