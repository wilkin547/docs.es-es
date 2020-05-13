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
ms.openlocfilehash: edcc0ebcadc1bd95574b0276bfd0e2d42e5474fd
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379820"
---
# <a name="icordebugthread-interface"></a><span data-ttu-id="f89ea-102">Interfaz ICorDebugThread</span><span class="sxs-lookup"><span data-stu-id="f89ea-102">ICorDebugThread Interface</span></span>
<span data-ttu-id="f89ea-103">Representa un subproceso de un proceso.</span><span class="sxs-lookup"><span data-stu-id="f89ea-103">Represents a thread in a process.</span></span> <span data-ttu-id="f89ea-104">El período de duración de una instancia de `ICorDebugThread` es el mismo que el del subproceso que representa.</span><span class="sxs-lookup"><span data-stu-id="f89ea-104">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f89ea-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="f89ea-105">Methods</span></span>  
  
|<span data-ttu-id="f89ea-106">Método</span><span class="sxs-lookup"><span data-stu-id="f89ea-106">Method</span></span>|<span data-ttu-id="f89ea-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f89ea-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f89ea-108">Método ClearCurrentException</span><span class="sxs-lookup"><span data-stu-id="f89ea-108">ClearCurrentException Method</span></span>](icordebugthread-clearcurrentexception-method.md)|<span data-ttu-id="f89ea-109">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="f89ea-109">This method is not implemented.</span></span> <span data-ttu-id="f89ea-110">No lo utilice.</span><span class="sxs-lookup"><span data-stu-id="f89ea-110">Do not use it.</span></span>|  
|[<span data-ttu-id="f89ea-111">Método CreateEval</span><span class="sxs-lookup"><span data-stu-id="f89ea-111">CreateEval Method</span></span>](icordebugthread-createeval-method.md)|<span data-ttu-id="f89ea-112">Crea un objeto ICorDebugEval que funciona en este `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="f89ea-112">Creates an ICorDebugEval object that operates on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="f89ea-113">CreateStepper (Método)</span><span class="sxs-lookup"><span data-stu-id="f89ea-113">CreateStepper Method</span></span>](icordebugthread-createstepper-method.md)|<span data-ttu-id="f89ea-114">Crea un objeto ICorDebugStepper que permite recorrer el marco activo en este `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="f89ea-114">Creates an ICorDebugStepper object that allows stepping through the active frame in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="f89ea-115">Método EnumerateChains</span><span class="sxs-lookup"><span data-stu-id="f89ea-115">EnumerateChains Method</span></span>](icordebugthread-enumeratechains-method.md)|<span data-ttu-id="f89ea-116">Obtiene un puntero de interfaz a un enumerador ICorDebugChainEnum (que contiene todas las cadenas de pila de este `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="f89ea-116">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="f89ea-117">Método GetActiveChain</span><span class="sxs-lookup"><span data-stu-id="f89ea-117">GetActiveChain Method</span></span>](icordebugthread-getactivechain-method.md)|<span data-ttu-id="f89ea-118">Obtiene un puntero de interfaz a la ICorDebugChain activa en este `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="f89ea-118">Gets an interface pointer to the active ICorDebugChain on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="f89ea-119">GetActiveFrame (Método)</span><span class="sxs-lookup"><span data-stu-id="f89ea-119">GetActiveFrame Method</span></span>](icordebugthread-getactiveframe-method.md)|<span data-ttu-id="f89ea-120">Obtiene un puntero de interfaz al ICorDebugFrame activo en este `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="f89ea-120">Gets an interface pointer to the active ICorDebugFrame on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="f89ea-121">Método GetAppDomain</span><span class="sxs-lookup"><span data-stu-id="f89ea-121">GetAppDomain Method</span></span>](icordebugthread-getappdomain-method.md)|<span data-ttu-id="f89ea-122">Obtiene un puntero de interfaz al dominio de aplicación en el que `ICorDebugThread` se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="f89ea-122">Gets an interface pointer to the application domain in which this `ICorDebugThread` is currently executing.</span></span>|  
|[<span data-ttu-id="f89ea-123">Método GetCurrentException</span><span class="sxs-lookup"><span data-stu-id="f89ea-123">GetCurrentException Method</span></span>](icordebugthread-getcurrentexception-method.md)|<span data-ttu-id="f89ea-124">Obtiene un puntero de interfaz a un objeto ICorDebugValue que representa una excepción que el código administrado está iniciando.</span><span class="sxs-lookup"><span data-stu-id="f89ea-124">Gets an interface pointer to an ICorDebugValue object that represents an exception currently being thrown by managed code.</span></span>|  
|[<span data-ttu-id="f89ea-125">Método GetDebugState</span><span class="sxs-lookup"><span data-stu-id="f89ea-125">GetDebugState Method</span></span>](icordebugthread-getdebugstate-method.md)|<span data-ttu-id="f89ea-126">Obtiene un valor CorDebugThreadState (que describe el estado de depuración actual de este `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="f89ea-126">Gets a CorDebugThreadState value that describes the current debug state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="f89ea-127">Método GetHandle</span><span class="sxs-lookup"><span data-stu-id="f89ea-127">GetHandle Method</span></span>](icordebugthread-gethandle-method.md)|<span data-ttu-id="f89ea-128">Obtiene el identificador actual para la parte activa de este `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="f89ea-128">Gets the current handle for the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="f89ea-129">Método GetID</span><span class="sxs-lookup"><span data-stu-id="f89ea-129">GetID Method</span></span>](icordebugthread-getid-method.md)|<span data-ttu-id="f89ea-130">Obtiene el identificador del sistema operativo actual de la parte activa de este `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="f89ea-130">Gets the current operating system identifier of the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="f89ea-131">GetObject (Método)</span><span class="sxs-lookup"><span data-stu-id="f89ea-131">GetObject Method</span></span>](icordebugthread-getobject-method.md)|<span data-ttu-id="f89ea-132">Obtiene un puntero de interfaz al subproceso de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="f89ea-132">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>|  
|[<span data-ttu-id="f89ea-133">Método GetProcess</span><span class="sxs-lookup"><span data-stu-id="f89ea-133">GetProcess Method</span></span>](icordebugthread-getprocess-method.md)|<span data-ttu-id="f89ea-134">Obtiene un puntero de interfaz al proceso del que `ICorDebugThread` forma parte.</span><span class="sxs-lookup"><span data-stu-id="f89ea-134">Gets an interface pointer to the process of which this `ICorDebugThread` forms a part.</span></span>|  
|[<span data-ttu-id="f89ea-135">GetRegisterSet (Método)</span><span class="sxs-lookup"><span data-stu-id="f89ea-135">GetRegisterSet Method</span></span>](icordebugthread-getregisterset-method.md)|<span data-ttu-id="f89ea-136">Obtiene un puntero de interfaz al conjunto de registros asociado a este `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="f89ea-136">Gets an interface pointer to the register set associated with this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="f89ea-137">Método GetUserState</span><span class="sxs-lookup"><span data-stu-id="f89ea-137">GetUserState Method</span></span>](icordebugthread-getuserstate-method.md)|<span data-ttu-id="f89ea-138">Obtiene una combinación bit a bit de los valores de CorDebugUserState (que describen el estado actual de este `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="f89ea-138">Gets a bitwise combination of CorDebugUserState values that describe the current state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="f89ea-139">Método SetDebugState</span><span class="sxs-lookup"><span data-stu-id="f89ea-139">SetDebugState Method</span></span>](icordebugthread-setdebugstate-method.md)|<span data-ttu-id="f89ea-140">Establece una combinación bit a bit de `CorDebugThreadState` valores que describen el estado de depuración de este `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="f89ea-140">Sets a bitwise combination of `CorDebugThreadState` values that describe the debugging state of this `ICorDebugThread`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f89ea-141">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f89ea-141">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f89ea-142">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="f89ea-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f89ea-143">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f89ea-143">Requirements</span></span>  
 <span data-ttu-id="f89ea-144">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f89ea-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f89ea-145">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f89ea-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f89ea-146">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f89ea-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f89ea-147">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f89ea-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f89ea-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f89ea-148">See also</span></span>

- [<span data-ttu-id="f89ea-149">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="f89ea-149">Debugging Interfaces</span></span>](debugging-interfaces.md)
