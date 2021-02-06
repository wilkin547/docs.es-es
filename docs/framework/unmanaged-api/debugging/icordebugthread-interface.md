---
description: 'Más información acerca de: ICorDebugThread (interfaz)'
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
ms.openlocfilehash: 7e16fa2a82a004a5c85d60a278cdd14df6ab2300
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658833"
---
# <a name="icordebugthread-interface"></a><span data-ttu-id="65ad1-103">Interfaz ICorDebugThread</span><span class="sxs-lookup"><span data-stu-id="65ad1-103">ICorDebugThread Interface</span></span>

<span data-ttu-id="65ad1-104">Representa un subproceso de un proceso.</span><span class="sxs-lookup"><span data-stu-id="65ad1-104">Represents a thread in a process.</span></span> <span data-ttu-id="65ad1-105">El período de duración de una instancia de `ICorDebugThread` es el mismo que el del subproceso que representa.</span><span class="sxs-lookup"><span data-stu-id="65ad1-105">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="65ad1-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="65ad1-106">Methods</span></span>  
  
|<span data-ttu-id="65ad1-107">Método</span><span class="sxs-lookup"><span data-stu-id="65ad1-107">Method</span></span>|<span data-ttu-id="65ad1-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="65ad1-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="65ad1-109">Método ClearCurrentException</span><span class="sxs-lookup"><span data-stu-id="65ad1-109">ClearCurrentException Method</span></span>](icordebugthread-clearcurrentexception-method.md)|<span data-ttu-id="65ad1-110">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="65ad1-110">This method is not implemented.</span></span> <span data-ttu-id="65ad1-111">No lo utilice.</span><span class="sxs-lookup"><span data-stu-id="65ad1-111">Do not use it.</span></span>|  
|[<span data-ttu-id="65ad1-112">Método CreateEval</span><span class="sxs-lookup"><span data-stu-id="65ad1-112">CreateEval Method</span></span>](icordebugthread-createeval-method.md)|<span data-ttu-id="65ad1-113">Crea un objeto ICorDebugEval que funciona en este `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="65ad1-113">Creates an ICorDebugEval object that operates on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="65ad1-114">CreateStepper (Método)</span><span class="sxs-lookup"><span data-stu-id="65ad1-114">CreateStepper Method</span></span>](icordebugthread-createstepper-method.md)|<span data-ttu-id="65ad1-115">Crea un objeto ICorDebugStepper que permite recorrer el marco activo en este `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="65ad1-115">Creates an ICorDebugStepper object that allows stepping through the active frame in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="65ad1-116">Método EnumerateChains</span><span class="sxs-lookup"><span data-stu-id="65ad1-116">EnumerateChains Method</span></span>](icordebugthread-enumeratechains-method.md)|<span data-ttu-id="65ad1-117">Obtiene un puntero de interfaz a un enumerador ICorDebugChainEnum (que contiene todas las cadenas de pila de este `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="65ad1-117">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="65ad1-118">Método GetActiveChain</span><span class="sxs-lookup"><span data-stu-id="65ad1-118">GetActiveChain Method</span></span>](icordebugthread-getactivechain-method.md)|<span data-ttu-id="65ad1-119">Obtiene un puntero de interfaz a la ICorDebugChain activa en este `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="65ad1-119">Gets an interface pointer to the active ICorDebugChain on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="65ad1-120">GetActiveFrame (Método)</span><span class="sxs-lookup"><span data-stu-id="65ad1-120">GetActiveFrame Method</span></span>](icordebugthread-getactiveframe-method.md)|<span data-ttu-id="65ad1-121">Obtiene un puntero de interfaz al ICorDebugFrame activo en este `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="65ad1-121">Gets an interface pointer to the active ICorDebugFrame on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="65ad1-122">Método GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="65ad1-122">GetAppDomain Method</span></span>](icordebugthread-getappdomain-method.md)|<span data-ttu-id="65ad1-123">Obtiene un puntero de interfaz al dominio de aplicación en el que `ICorDebugThread` se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="65ad1-123">Gets an interface pointer to the application domain in which this `ICorDebugThread` is currently executing.</span></span>|  
|[<span data-ttu-id="65ad1-124">Método GetCurrentException</span><span class="sxs-lookup"><span data-stu-id="65ad1-124">GetCurrentException Method</span></span>](icordebugthread-getcurrentexception-method.md)|<span data-ttu-id="65ad1-125">Obtiene un puntero de interfaz a un objeto ICorDebugValue que representa una excepción que el código administrado está iniciando.</span><span class="sxs-lookup"><span data-stu-id="65ad1-125">Gets an interface pointer to an ICorDebugValue object that represents an exception currently being thrown by managed code.</span></span>|  
|[<span data-ttu-id="65ad1-126">Método GetDebugState</span><span class="sxs-lookup"><span data-stu-id="65ad1-126">GetDebugState Method</span></span>](icordebugthread-getdebugstate-method.md)|<span data-ttu-id="65ad1-127">Obtiene un valor CorDebugThreadState (que describe el estado de depuración actual de este `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="65ad1-127">Gets a CorDebugThreadState value that describes the current debug state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="65ad1-128">Método GetHandle</span><span class="sxs-lookup"><span data-stu-id="65ad1-128">GetHandle Method</span></span>](icordebugthread-gethandle-method.md)|<span data-ttu-id="65ad1-129">Obtiene el identificador actual para la parte activa de este `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="65ad1-129">Gets the current handle for the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="65ad1-130">Método GetID</span><span class="sxs-lookup"><span data-stu-id="65ad1-130">GetID Method</span></span>](icordebugthread-getid-method.md)|<span data-ttu-id="65ad1-131">Obtiene el identificador del sistema operativo actual de la parte activa de este `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="65ad1-131">Gets the current operating system identifier of the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="65ad1-132">GetObject (Método)</span><span class="sxs-lookup"><span data-stu-id="65ad1-132">GetObject Method</span></span>](icordebugthread-getobject-method.md)|<span data-ttu-id="65ad1-133">Obtiene un puntero de interfaz al subproceso de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="65ad1-133">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>|  
|[<span data-ttu-id="65ad1-134">Método GetProcess</span><span class="sxs-lookup"><span data-stu-id="65ad1-134">GetProcess Method</span></span>](icordebugthread-getprocess-method.md)|<span data-ttu-id="65ad1-135">Obtiene un puntero de interfaz al proceso del que `ICorDebugThread` forma parte.</span><span class="sxs-lookup"><span data-stu-id="65ad1-135">Gets an interface pointer to the process of which this `ICorDebugThread` forms a part.</span></span>|  
|[<span data-ttu-id="65ad1-136">GetRegisterSet (Método)</span><span class="sxs-lookup"><span data-stu-id="65ad1-136">GetRegisterSet Method</span></span>](icordebugthread-getregisterset-method.md)|<span data-ttu-id="65ad1-137">Obtiene un puntero de interfaz al conjunto de registros asociado a este `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="65ad1-137">Gets an interface pointer to the register set associated with this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="65ad1-138">Método GetUserState</span><span class="sxs-lookup"><span data-stu-id="65ad1-138">GetUserState Method</span></span>](icordebugthread-getuserstate-method.md)|<span data-ttu-id="65ad1-139">Obtiene una combinación bit a bit de los valores de CorDebugUserState (que describen el estado actual de este `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="65ad1-139">Gets a bitwise combination of CorDebugUserState values that describe the current state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="65ad1-140">Método SetDebugState</span><span class="sxs-lookup"><span data-stu-id="65ad1-140">SetDebugState Method</span></span>](icordebugthread-setdebugstate-method.md)|<span data-ttu-id="65ad1-141">Establece una combinación bit a bit de `CorDebugThreadState` valores que describen el estado de depuración de este `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="65ad1-141">Sets a bitwise combination of `CorDebugThreadState` values that describe the debugging state of this `ICorDebugThread`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65ad1-142">Observaciones</span><span class="sxs-lookup"><span data-stu-id="65ad1-142">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="65ad1-143">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="65ad1-143">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65ad1-144">Requisitos</span><span class="sxs-lookup"><span data-stu-id="65ad1-144">Requirements</span></span>  

 <span data-ttu-id="65ad1-145">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65ad1-145">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65ad1-146">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="65ad1-146">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="65ad1-147">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65ad1-147">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65ad1-148">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65ad1-148">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65ad1-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="65ad1-149">See also</span></span>

- [<span data-ttu-id="65ad1-150">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="65ad1-150">Debugging Interfaces</span></span>](debugging-interfaces.md)
