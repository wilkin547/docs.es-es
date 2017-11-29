---
title: ICorDebugThread Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread
helpviewer_keywords: ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3930fd9b-2bc3-4b72-80a0-b6eeb94d60c6
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 25b5c8f0720402cce56c69394c6fbe2fb70a6177
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthread-interface1"></a><span data-ttu-id="c503a-102">ICorDebugThread Interfaz1</span><span class="sxs-lookup"><span data-stu-id="c503a-102">ICorDebugThread Interface1</span></span>
<span data-ttu-id="c503a-103">Representa un subproceso de un proceso.</span><span class="sxs-lookup"><span data-stu-id="c503a-103">Represents a thread in a process.</span></span> <span data-ttu-id="c503a-104">El período de duración de una instancia de `ICorDebugThread` es el mismo que el del subproceso que representa.</span><span class="sxs-lookup"><span data-stu-id="c503a-104">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c503a-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="c503a-105">Methods</span></span>  
  
|<span data-ttu-id="c503a-106">Método</span><span class="sxs-lookup"><span data-stu-id="c503a-106">Method</span></span>|<span data-ttu-id="c503a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c503a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c503a-108">ClearCurrentException (método)</span><span class="sxs-lookup"><span data-stu-id="c503a-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|<span data-ttu-id="c503a-109">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="c503a-109">This method is not implemented.</span></span> <span data-ttu-id="c503a-110">No lo utilice.</span><span class="sxs-lookup"><span data-stu-id="c503a-110">Do not use it.</span></span>|  
|[<span data-ttu-id="c503a-111">CreateEval (método)</span><span class="sxs-lookup"><span data-stu-id="c503a-111">CreateEval Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|<span data-ttu-id="c503a-112">Crea un objeto ICorDebugEval que opera en el objeto `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="c503a-112">Creates an ICorDebugEval object that operates on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="c503a-113">CreateStepper (método)</span><span class="sxs-lookup"><span data-stu-id="c503a-113">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|<span data-ttu-id="c503a-114">Crea un objeto ICorDebugStepper que permite recorrer el fotograma activo en este `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="c503a-114">Creates an ICorDebugStepper object that allows stepping through the active frame in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="c503a-115">EnumerateChains (método)</span><span class="sxs-lookup"><span data-stu-id="c503a-115">EnumerateChains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|<span data-ttu-id="c503a-116">Obtiene un puntero de interfaz a un enumerador ICorDebugChainEnum que contiene todas las cadenas de pila en este `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="c503a-116">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="c503a-117">GetActiveChain (método)</span><span class="sxs-lookup"><span data-stu-id="c503a-117">GetActiveChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|<span data-ttu-id="c503a-118">Obtiene un puntero de interfaz a la ICorDebugChain activa en el objeto `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="c503a-118">Gets an interface pointer to the active ICorDebugChain on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="c503a-119">GetActiveFrame (método)</span><span class="sxs-lookup"><span data-stu-id="c503a-119">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|<span data-ttu-id="c503a-120">Obtiene un puntero de interfaz a la ICorDebugFrame activo en el objeto `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="c503a-120">Gets an interface pointer to the active ICorDebugFrame on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="c503a-121">GetAppDomain (método)</span><span class="sxs-lookup"><span data-stu-id="c503a-121">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|<span data-ttu-id="c503a-122">Obtiene un puntero de interfaz al dominio de aplicación en la que `ICorDebugThread` se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="c503a-122">Gets an interface pointer to the application domain in which this `ICorDebugThread` is currently executing.</span></span>|  
|[<span data-ttu-id="c503a-123">GetCurrentException (método)</span><span class="sxs-lookup"><span data-stu-id="c503a-123">GetCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|<span data-ttu-id="c503a-124">Obtiene un puntero de interfaz a un objeto ICorDebugValue que representa una excepción producida por el código administrado.</span><span class="sxs-lookup"><span data-stu-id="c503a-124">Gets an interface pointer to an ICorDebugValue object that represents an exception currently being thrown by managed code.</span></span>|  
|[<span data-ttu-id="c503a-125">GetDebugState (método)</span><span class="sxs-lookup"><span data-stu-id="c503a-125">GetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|<span data-ttu-id="c503a-126">Obtiene un valor de CorDebugThreadState que describe el estado de depuración actual de este `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="c503a-126">Gets a CorDebugThreadState value that describes the current debug state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="c503a-127">GetHandle (método)</span><span class="sxs-lookup"><span data-stu-id="c503a-127">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|<span data-ttu-id="c503a-128">Obtiene el identificador actual para la parte activa de este `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="c503a-128">Gets the current handle for the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="c503a-129">GetID (método)</span><span class="sxs-lookup"><span data-stu-id="c503a-129">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|<span data-ttu-id="c503a-130">Obtiene el identificador de sistema operativo actual de la parte activa de este `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="c503a-130">Gets the current operating system identifier of the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="c503a-131">GetObject (método)</span><span class="sxs-lookup"><span data-stu-id="c503a-131">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|<span data-ttu-id="c503a-132">Obtiene un puntero de interfaz para el subproceso de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="c503a-132">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>|  
|[<span data-ttu-id="c503a-133">GetProcess (método)</span><span class="sxs-lookup"><span data-stu-id="c503a-133">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|<span data-ttu-id="c503a-134">Obtiene un puntero de interfaz al proceso de que este `ICorDebugThread` constituye una parte.</span><span class="sxs-lookup"><span data-stu-id="c503a-134">Gets an interface pointer to the process of which this `ICorDebugThread` forms a part.</span></span>|  
|[<span data-ttu-id="c503a-135">GetRegisterSet (método)</span><span class="sxs-lookup"><span data-stu-id="c503a-135">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|<span data-ttu-id="c503a-136">Obtiene un puntero de interfaz al conjunto de registros asociado a este `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="c503a-136">Gets an interface pointer to the register set associated with this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="c503a-137">GetUserState (método)</span><span class="sxs-lookup"><span data-stu-id="c503a-137">GetUserState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|<span data-ttu-id="c503a-138">Obtiene una combinación bit a bit de valores de CorDebugUserState que describen el estado actual de este `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="c503a-138">Gets a bitwise combination of CorDebugUserState values that describe the current state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="c503a-139">SetDebugState (método)</span><span class="sxs-lookup"><span data-stu-id="c503a-139">SetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|<span data-ttu-id="c503a-140">Establece una combinación bit a bit de `CorDebugThreadState` valores que describen el estado de depuración de este `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="c503a-140">Sets a bitwise combination of `CorDebugThreadState` values that describe the debugging state of this `ICorDebugThread`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c503a-141">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c503a-141">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c503a-142">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="c503a-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c503a-143">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c503a-143">Requirements</span></span>  
 <span data-ttu-id="c503a-144">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c503a-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c503a-145">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c503a-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c503a-146">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c503a-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c503a-147">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c503a-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c503a-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="c503a-148">See Also</span></span>  
 [<span data-ttu-id="c503a-149">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c503a-149">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
