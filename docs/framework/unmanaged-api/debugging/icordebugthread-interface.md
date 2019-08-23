---
title: Interfaz ICorDebugThread
ms.date: 03/30/2017
api_name:
- ICorDebugThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread
helpviewer_keywords:
- ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3930fd9b-2bc3-4b72-80a0-b6eeb94d60c6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1517d686c50923f5599e33436e0ad6126e8be140
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923140"
---
# <a name="icordebugthread-interface"></a><span data-ttu-id="8fb3a-102">Interfaz ICorDebugThread</span><span class="sxs-lookup"><span data-stu-id="8fb3a-102">ICorDebugThread Interface</span></span>
<span data-ttu-id="8fb3a-103">Representa un subproceso de un proceso.</span><span class="sxs-lookup"><span data-stu-id="8fb3a-103">Represents a thread in a process.</span></span> <span data-ttu-id="8fb3a-104">El período de duración de una instancia de `ICorDebugThread` es el mismo que el del subproceso que representa.</span><span class="sxs-lookup"><span data-stu-id="8fb3a-104">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8fb3a-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="8fb3a-105">Methods</span></span>  
  
|<span data-ttu-id="8fb3a-106">Método</span><span class="sxs-lookup"><span data-stu-id="8fb3a-106">Method</span></span>|<span data-ttu-id="8fb3a-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8fb3a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8fb3a-108">ClearCurrentException (método)</span><span class="sxs-lookup"><span data-stu-id="8fb3a-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|<span data-ttu-id="8fb3a-109">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="8fb3a-109">This method is not implemented.</span></span> <span data-ttu-id="8fb3a-110">No lo utilice.</span><span class="sxs-lookup"><span data-stu-id="8fb3a-110">Do not use it.</span></span>|  
|[<span data-ttu-id="8fb3a-111">CreateEval (método)</span><span class="sxs-lookup"><span data-stu-id="8fb3a-111">CreateEval Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|<span data-ttu-id="8fb3a-112">Crea un objeto ICorDebugEval que funciona en este `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="8fb3a-112">Creates an ICorDebugEval object that operates on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="8fb3a-113">CreateStepper (método)</span><span class="sxs-lookup"><span data-stu-id="8fb3a-113">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|<span data-ttu-id="8fb3a-114">Crea un objeto ICorDebugStepper que permite recorrer el marco activo en este `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="8fb3a-114">Creates an ICorDebugStepper object that allows stepping through the active frame in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="8fb3a-115">EnumerateChains (método)</span><span class="sxs-lookup"><span data-stu-id="8fb3a-115">EnumerateChains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|<span data-ttu-id="8fb3a-116">Obtiene un puntero de interfaz a un enumerador ICorDebugChainEnum (que contiene todas las cadenas de `ICorDebugThread`pila de este.</span><span class="sxs-lookup"><span data-stu-id="8fb3a-116">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="8fb3a-117">GetActiveChain (método)</span><span class="sxs-lookup"><span data-stu-id="8fb3a-117">GetActiveChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|<span data-ttu-id="8fb3a-118">Obtiene un puntero de interfaz a la ICorDebugChain activa en `ICorDebugThread`este.</span><span class="sxs-lookup"><span data-stu-id="8fb3a-118">Gets an interface pointer to the active ICorDebugChain on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="8fb3a-119">GetActiveFrame (método)</span><span class="sxs-lookup"><span data-stu-id="8fb3a-119">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|<span data-ttu-id="8fb3a-120">Obtiene un puntero de interfaz al ICorDebugFrame activo en este `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="8fb3a-120">Gets an interface pointer to the active ICorDebugFrame on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="8fb3a-121">GetAppDomain (método)</span><span class="sxs-lookup"><span data-stu-id="8fb3a-121">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|<span data-ttu-id="8fb3a-122">Obtiene un puntero de interfaz al dominio de aplicación en el `ICorDebugThread` que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="8fb3a-122">Gets an interface pointer to the application domain in which this `ICorDebugThread` is currently executing.</span></span>|  
|[<span data-ttu-id="8fb3a-123">GetCurrentException (método)</span><span class="sxs-lookup"><span data-stu-id="8fb3a-123">GetCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|<span data-ttu-id="8fb3a-124">Obtiene un puntero de interfaz a un objeto ICorDebugValue que representa una excepción que el código administrado está iniciando.</span><span class="sxs-lookup"><span data-stu-id="8fb3a-124">Gets an interface pointer to an ICorDebugValue object that represents an exception currently being thrown by managed code.</span></span>|  
|[<span data-ttu-id="8fb3a-125">GetDebugState (método)</span><span class="sxs-lookup"><span data-stu-id="8fb3a-125">GetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|<span data-ttu-id="8fb3a-126">Obtiene un valor CorDebugThreadState (que describe el estado de depuración `ICorDebugThread`actual de este.</span><span class="sxs-lookup"><span data-stu-id="8fb3a-126">Gets a CorDebugThreadState value that describes the current debug state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="8fb3a-127">GetHandle (método)</span><span class="sxs-lookup"><span data-stu-id="8fb3a-127">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|<span data-ttu-id="8fb3a-128">Obtiene el identificador actual para la parte activa de este `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="8fb3a-128">Gets the current handle for the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="8fb3a-129">GetID (método)</span><span class="sxs-lookup"><span data-stu-id="8fb3a-129">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|<span data-ttu-id="8fb3a-130">Obtiene el identificador del sistema operativo actual de la parte activa de este `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="8fb3a-130">Gets the current operating system identifier of the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="8fb3a-131">GetObject (método)</span><span class="sxs-lookup"><span data-stu-id="8fb3a-131">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|<span data-ttu-id="8fb3a-132">Obtiene un puntero de interfaz al subproceso de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="8fb3a-132">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>|  
|[<span data-ttu-id="8fb3a-133">GetProcess (método)</span><span class="sxs-lookup"><span data-stu-id="8fb3a-133">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|<span data-ttu-id="8fb3a-134">Obtiene un puntero de interfaz al proceso del que `ICorDebugThread` forma parte.</span><span class="sxs-lookup"><span data-stu-id="8fb3a-134">Gets an interface pointer to the process of which this `ICorDebugThread` forms a part.</span></span>|  
|[<span data-ttu-id="8fb3a-135">GetRegisterSet (método)</span><span class="sxs-lookup"><span data-stu-id="8fb3a-135">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|<span data-ttu-id="8fb3a-136">Obtiene un puntero de interfaz al conjunto de registros asociado a `ICorDebugThread`este.</span><span class="sxs-lookup"><span data-stu-id="8fb3a-136">Gets an interface pointer to the register set associated with this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="8fb3a-137">GetUserState (método)</span><span class="sxs-lookup"><span data-stu-id="8fb3a-137">GetUserState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|<span data-ttu-id="8fb3a-138">Obtiene una combinación bit a bit de los valores de CorDebugUserState (que describen el `ICorDebugThread`estado actual de este.</span><span class="sxs-lookup"><span data-stu-id="8fb3a-138">Gets a bitwise combination of CorDebugUserState values that describe the current state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="8fb3a-139">SetDebugState (método)</span><span class="sxs-lookup"><span data-stu-id="8fb3a-139">SetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|<span data-ttu-id="8fb3a-140">Establece una combinación bit a `CorDebugThreadState` bit de valores que describen el estado de depuración de este. `ICorDebugThread`</span><span class="sxs-lookup"><span data-stu-id="8fb3a-140">Sets a bitwise combination of `CorDebugThreadState` values that describe the debugging state of this `ICorDebugThread`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8fb3a-141">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8fb3a-141">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8fb3a-142">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="8fb3a-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fb3a-143">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8fb3a-143">Requirements</span></span>  
 <span data-ttu-id="8fb3a-144">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8fb3a-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fb3a-145">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="8fb3a-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8fb3a-146">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8fb3a-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8fb3a-147">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fb3a-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fb3a-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="8fb3a-148">See also</span></span>

- [<span data-ttu-id="8fb3a-149">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="8fb3a-149">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
