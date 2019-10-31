---
title: ICorDebugThread (Interfaz)
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
ms.openlocfilehash: c7333f4210d0a2ec4ff71a0fac0ea00068fecc57
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133497"
---
# <a name="icordebugthread-interface"></a><span data-ttu-id="45d76-102">ICorDebugThread (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="45d76-102">ICorDebugThread Interface</span></span>
<span data-ttu-id="45d76-103">Representa un subproceso de un proceso.</span><span class="sxs-lookup"><span data-stu-id="45d76-103">Represents a thread in a process.</span></span> <span data-ttu-id="45d76-104">El período de duración de una instancia de `ICorDebugThread` es el mismo que el del subproceso que representa.</span><span class="sxs-lookup"><span data-stu-id="45d76-104">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="45d76-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="45d76-105">Methods</span></span>  
  
|<span data-ttu-id="45d76-106">Método</span><span class="sxs-lookup"><span data-stu-id="45d76-106">Method</span></span>|<span data-ttu-id="45d76-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="45d76-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="45d76-108">ClearCurrentException (método)</span><span class="sxs-lookup"><span data-stu-id="45d76-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|<span data-ttu-id="45d76-109">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="45d76-109">This method is not implemented.</span></span> <span data-ttu-id="45d76-110">No lo utilice.</span><span class="sxs-lookup"><span data-stu-id="45d76-110">Do not use it.</span></span>|  
|[<span data-ttu-id="45d76-111">CreateEval (método)</span><span class="sxs-lookup"><span data-stu-id="45d76-111">CreateEval Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|<span data-ttu-id="45d76-112">Crea un objeto ICorDebugEval que funciona en este `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="45d76-112">Creates an ICorDebugEval object that operates on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="45d76-113">CreateStepper (método)</span><span class="sxs-lookup"><span data-stu-id="45d76-113">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|<span data-ttu-id="45d76-114">Crea un objeto ICorDebugStepper que permite recorrer en iteración el marco activo en este `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="45d76-114">Creates an ICorDebugStepper object that allows stepping through the active frame in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="45d76-115">EnumerateChains (método)</span><span class="sxs-lookup"><span data-stu-id="45d76-115">EnumerateChains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|<span data-ttu-id="45d76-116">Obtiene un puntero de interfaz a un enumerador ICorDebugChainEnum (que contiene todas las cadenas de pila de este `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="45d76-116">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="45d76-117">GetActiveChain (método)</span><span class="sxs-lookup"><span data-stu-id="45d76-117">GetActiveChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|<span data-ttu-id="45d76-118">Obtiene un puntero de interfaz a la ICorDebugChain activa en este `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="45d76-118">Gets an interface pointer to the active ICorDebugChain on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="45d76-119">GetActiveFrame (método)</span><span class="sxs-lookup"><span data-stu-id="45d76-119">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|<span data-ttu-id="45d76-120">Obtiene un puntero de interfaz al ICorDebugFrame activo en este `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="45d76-120">Gets an interface pointer to the active ICorDebugFrame on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="45d76-121">GetAppDomain (método)</span><span class="sxs-lookup"><span data-stu-id="45d76-121">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|<span data-ttu-id="45d76-122">Obtiene un puntero de interfaz al dominio de aplicación en el que se está ejecutando actualmente este `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="45d76-122">Gets an interface pointer to the application domain in which this `ICorDebugThread` is currently executing.</span></span>|  
|[<span data-ttu-id="45d76-123">GetCurrentException (método)</span><span class="sxs-lookup"><span data-stu-id="45d76-123">GetCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|<span data-ttu-id="45d76-124">Obtiene un puntero de interfaz a un objeto ICorDebugValue que representa una excepción que el código administrado está iniciando.</span><span class="sxs-lookup"><span data-stu-id="45d76-124">Gets an interface pointer to an ICorDebugValue object that represents an exception currently being thrown by managed code.</span></span>|  
|[<span data-ttu-id="45d76-125">GetDebugState (método)</span><span class="sxs-lookup"><span data-stu-id="45d76-125">GetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|<span data-ttu-id="45d76-126">Obtiene un valor CorDebugThreadState (que describe el estado de depuración actual de este `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="45d76-126">Gets a CorDebugThreadState value that describes the current debug state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="45d76-127">GetHandle (método)</span><span class="sxs-lookup"><span data-stu-id="45d76-127">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|<span data-ttu-id="45d76-128">Obtiene el identificador actual para la parte activa de este `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="45d76-128">Gets the current handle for the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="45d76-129">GetID (método)</span><span class="sxs-lookup"><span data-stu-id="45d76-129">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|<span data-ttu-id="45d76-130">Obtiene el identificador del sistema operativo actual de la parte activa de este `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="45d76-130">Gets the current operating system identifier of the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="45d76-131">GetObject (método)</span><span class="sxs-lookup"><span data-stu-id="45d76-131">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|<span data-ttu-id="45d76-132">Obtiene un puntero de interfaz al subproceso de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="45d76-132">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>|  
|[<span data-ttu-id="45d76-133">GetProcess (método)</span><span class="sxs-lookup"><span data-stu-id="45d76-133">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|<span data-ttu-id="45d76-134">Obtiene un puntero de interfaz al proceso del que esta `ICorDebugThread` forma una parte.</span><span class="sxs-lookup"><span data-stu-id="45d76-134">Gets an interface pointer to the process of which this `ICorDebugThread` forms a part.</span></span>|  
|[<span data-ttu-id="45d76-135">GetRegisterSet (método)</span><span class="sxs-lookup"><span data-stu-id="45d76-135">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|<span data-ttu-id="45d76-136">Obtiene un puntero de interfaz al conjunto de registros asociado a esta `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="45d76-136">Gets an interface pointer to the register set associated with this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="45d76-137">GetUserState (método)</span><span class="sxs-lookup"><span data-stu-id="45d76-137">GetUserState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|<span data-ttu-id="45d76-138">Obtiene una combinación bit a bit de los valores de CorDebugUserState (que describen el estado actual de este `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="45d76-138">Gets a bitwise combination of CorDebugUserState values that describe the current state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="45d76-139">SetDebugState (método)</span><span class="sxs-lookup"><span data-stu-id="45d76-139">SetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|<span data-ttu-id="45d76-140">Establece una combinación bit a bit de los valores de `CorDebugThreadState` que describen el estado de depuración de este `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="45d76-140">Sets a bitwise combination of `CorDebugThreadState` values that describe the debugging state of this `ICorDebugThread`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45d76-141">Comentarios</span><span class="sxs-lookup"><span data-stu-id="45d76-141">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="45d76-142">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="45d76-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45d76-143">Requisitos</span><span class="sxs-lookup"><span data-stu-id="45d76-143">Requirements</span></span>  
 <span data-ttu-id="45d76-144">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45d76-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45d76-145">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="45d76-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="45d76-146">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45d76-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45d76-147">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45d76-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45d76-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="45d76-148">See also</span></span>

- [<span data-ttu-id="45d76-149">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="45d76-149">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
