---
description: 'Más información acerca de: ICorDebugProcess (interfaz)'
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
ms.openlocfilehash: 7172ee12bf450235db1c18601c8ff7de51435520
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746794"
---
# <a name="icordebugprocess-interface"></a><span data-ttu-id="1de6b-103">Interfaz ICorDebugProcess</span><span class="sxs-lookup"><span data-stu-id="1de6b-103">ICorDebugProcess Interface</span></span>

<span data-ttu-id="1de6b-104">Representa un proceso que ejecuta código administrado.</span><span class="sxs-lookup"><span data-stu-id="1de6b-104">Represents a process that is executing managed code.</span></span> <span data-ttu-id="1de6b-105">Esta interfaz es una subclase de ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="1de6b-105">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1de6b-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="1de6b-106">Methods</span></span>  
  
|<span data-ttu-id="1de6b-107">Método</span><span class="sxs-lookup"><span data-stu-id="1de6b-107">Method</span></span>|<span data-ttu-id="1de6b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="1de6b-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1de6b-109">Método ClearCurrentException</span><span class="sxs-lookup"><span data-stu-id="1de6b-109">ClearCurrentException Method</span></span>](icordebugprocess-clearcurrentexception-method.md)|<span data-ttu-id="1de6b-110">Borra la excepción no administrada actual en el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="1de6b-110">Clears the current unmanaged exception on the given thread.</span></span>|  
|[<span data-ttu-id="1de6b-111">Método EnableLogMessages</span><span class="sxs-lookup"><span data-stu-id="1de6b-111">EnableLogMessages Method</span></span>](icordebugprocess-enablelogmessages-method.md)|<span data-ttu-id="1de6b-112">Habilita y deshabilita el envío de mensajes de registro al depurador.</span><span class="sxs-lookup"><span data-stu-id="1de6b-112">Enables and disables the sending of log messages to the debugger.</span></span>|  
|[<span data-ttu-id="1de6b-113">Método EnumerateAppDomains</span><span class="sxs-lookup"><span data-stu-id="1de6b-113">EnumerateAppDomains Method</span></span>](icordebugprocess-enumerateappdomains-method.md)|<span data-ttu-id="1de6b-114">Enumera todos los dominios de aplicación del proceso.</span><span class="sxs-lookup"><span data-stu-id="1de6b-114">Enumerates all of the application domains in the process.</span></span>|  
|[<span data-ttu-id="1de6b-115">Método EnumerateObjects</span><span class="sxs-lookup"><span data-stu-id="1de6b-115">EnumerateObjects Method</span></span>](icordebugprocess-enumerateobjects-method.md)|<span data-ttu-id="1de6b-116">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="1de6b-116">Not implemented.</span></span>|  
|[<span data-ttu-id="1de6b-117">Método GetHandle</span><span class="sxs-lookup"><span data-stu-id="1de6b-117">GetHandle Method</span></span>](icordebugprocess-gethandle-method.md)|<span data-ttu-id="1de6b-118">Obtiene un identificador para el proceso.</span><span class="sxs-lookup"><span data-stu-id="1de6b-118">Gets a handle to the process.</span></span>|  
|[<span data-ttu-id="1de6b-119">Método GetHelperThreadID</span><span class="sxs-lookup"><span data-stu-id="1de6b-119">GetHelperThreadID Method</span></span>](icordebugprocess-gethelperthreadid-method.md)|<span data-ttu-id="1de6b-120">Obtiene el identificador del subproceso del sistema operativo (SO) del subproceso auxiliar interno del depurador.</span><span class="sxs-lookup"><span data-stu-id="1de6b-120">Gets the operating system (OS) thread ID for the debugger's internal helper thread.</span></span>|  
|[<span data-ttu-id="1de6b-121">Método GetID</span><span class="sxs-lookup"><span data-stu-id="1de6b-121">GetID Method</span></span>](icordebugprocess-getid-method.md)|<span data-ttu-id="1de6b-122">Obtiene el identificador del sistema operativo (SO) del proceso.</span><span class="sxs-lookup"><span data-stu-id="1de6b-122">Gets the operating system (OS) ID of the process.</span></span>|  
|[<span data-ttu-id="1de6b-123">GetObject (Método)</span><span class="sxs-lookup"><span data-stu-id="1de6b-123">GetObject Method</span></span>](icordebugprocess-getobject-method.md)|<span data-ttu-id="1de6b-124">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="1de6b-124">Not implemented.</span></span>|  
|[<span data-ttu-id="1de6b-125">Método GetThread</span><span class="sxs-lookup"><span data-stu-id="1de6b-125">GetThread Method</span></span>](icordebugprocess-getthread-method.md)|<span data-ttu-id="1de6b-126">Obtiene la instancia de ICorDebugThread que tiene el identificador de subproceso de sistema operativo especificado.</span><span class="sxs-lookup"><span data-stu-id="1de6b-126">Gets the ICorDebugThread instance that has the specified OS thread ID.</span></span>|  
|[<span data-ttu-id="1de6b-127">GetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="1de6b-127">GetThreadContext Method</span></span>](icordebugprocess-getthreadcontext-method.md)|<span data-ttu-id="1de6b-128">Obtiene el contexto para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="1de6b-128">Gets the context for the given thread.</span></span>|  
|[<span data-ttu-id="1de6b-129">Método IsOSSuspended</span><span class="sxs-lookup"><span data-stu-id="1de6b-129">IsOSSuspended Method</span></span>](icordebugprocess-isossuspended-method.md)|<span data-ttu-id="1de6b-130">Determina si el subproceso se ha suspendido como resultado de que el depurador detenga el proceso.</span><span class="sxs-lookup"><span data-stu-id="1de6b-130">Determines whether the thread has been suspended as a result of the debugger stopping the process.</span></span>|  
|[<span data-ttu-id="1de6b-131">Método IsTransitionStub</span><span class="sxs-lookup"><span data-stu-id="1de6b-131">IsTransitionStub Method</span></span>](icordebugprocess-istransitionstub-method.md)|<span data-ttu-id="1de6b-132">Determina si una dirección está dentro de un código auxiliar que producirá una transición a código administrado.</span><span class="sxs-lookup"><span data-stu-id="1de6b-132">Determines whether an address is inside a stub that will cause a transition to managed code.</span></span>|  
|[<span data-ttu-id="1de6b-133">Método ModifyLogSwitch</span><span class="sxs-lookup"><span data-stu-id="1de6b-133">ModifyLogSwitch Method</span></span>](icordebugprocess-modifylogswitch-method.md)|<span data-ttu-id="1de6b-134">Establece el nivel de gravedad del modificador de registro especificado.</span><span class="sxs-lookup"><span data-stu-id="1de6b-134">Sets the severity level of the specified log switch.</span></span>|  
|[<span data-ttu-id="1de6b-135">Método ReadMemory</span><span class="sxs-lookup"><span data-stu-id="1de6b-135">ReadMemory Method</span></span>](icordebugprocess-readmemory-method.md)|<span data-ttu-id="1de6b-136">Lee la memoria del proceso.</span><span class="sxs-lookup"><span data-stu-id="1de6b-136">Reads memory from the process.</span></span>|  
|[<span data-ttu-id="1de6b-137">Método SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="1de6b-137">SetThreadContext Method</span></span>](icordebugprocess-setthreadcontext-method.md)|<span data-ttu-id="1de6b-138">Establece el contexto para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="1de6b-138">Sets the context for the given thread.</span></span>|  
|[<span data-ttu-id="1de6b-139">Método ThreadForFiberCookie</span><span class="sxs-lookup"><span data-stu-id="1de6b-139">ThreadForFiberCookie Method</span></span>](icordebugprocess-threadforfibercookie-method.md)|<span data-ttu-id="1de6b-140">En desuso.</span><span class="sxs-lookup"><span data-stu-id="1de6b-140">Deprecated.</span></span>|  
|[<span data-ttu-id="1de6b-141">Método WriteMemory</span><span class="sxs-lookup"><span data-stu-id="1de6b-141">WriteMemory Method</span></span>](icordebugprocess-writememory-method.md)|<span data-ttu-id="1de6b-142">Escribe datos en un área de memoria del proceso.</span><span class="sxs-lookup"><span data-stu-id="1de6b-142">Writes data to an area of memory in the process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1de6b-143">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1de6b-143">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1de6b-144">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="1de6b-144">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1de6b-145">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1de6b-145">Requirements</span></span>  

 <span data-ttu-id="1de6b-146">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1de6b-146">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1de6b-147">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1de6b-147">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1de6b-148">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1de6b-148">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1de6b-149">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1de6b-149">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1de6b-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="1de6b-150">See also</span></span>

- [<span data-ttu-id="1de6b-151">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1de6b-151">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="1de6b-152">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="1de6b-152">Debugging Interfaces</span></span>](debugging-interfaces.md)
