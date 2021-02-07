---
description: 'Más información acerca de: IHostTaskManager (interfaz)'
title: IHostTaskManager (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager
helpviewer_keywords:
- IHostTaskManager interface [.NET Framework hosting]
ms.assetid: 4a0b05b9-3ef1-4607-b7c8-bd4dd43647a0
topic_type:
- apiref
ms.openlocfilehash: 67574550ba26970189ea53b8e6bdb867fea8549b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707491"
---
# <a name="ihosttaskmanager-interface"></a><span data-ttu-id="c4869-103">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c4869-103">IHostTaskManager Interface</span></span>

<span data-ttu-id="c4869-104">Proporciona métodos que permiten al Common Language Runtime (CLR) trabajar con tareas a través del host en lugar de usar las funciones de fibra o de subprocesos estándar del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c4869-104">Provides methods that allow the common language runtime (CLR) to work with tasks through the host instead of using the standard operating system threading or fiber functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c4869-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="c4869-105">Methods</span></span>  
  
|<span data-ttu-id="c4869-106">Método</span><span class="sxs-lookup"><span data-stu-id="c4869-106">Method</span></span>|<span data-ttu-id="c4869-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c4869-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c4869-108">Método BeginDelayAbort</span><span class="sxs-lookup"><span data-stu-id="c4869-108">BeginDelayAbort Method</span></span>](ihosttaskmanager-begindelayabort-method.md)|<span data-ttu-id="c4869-109">Notifica al host que el código administrado está entrando en un período en el que la tarea actual no se debe anular.</span><span class="sxs-lookup"><span data-stu-id="c4869-109">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>|  
|[<span data-ttu-id="c4869-110">Método BeginThreadAffinity</span><span class="sxs-lookup"><span data-stu-id="c4869-110">BeginThreadAffinity Method</span></span>](ihosttaskmanager-beginthreadaffinity-method.md)|<span data-ttu-id="c4869-111">Notifica al host que el código administrado está entrando en un período en el que la tarea actual no se debe pasar a otro subproceso del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c4869-111">Notifies the host that managed code is entering a period in which the current task must not be moved to another operating system thread.</span></span>|  
|[<span data-ttu-id="c4869-112">Método CallNeedsHostHook</span><span class="sxs-lookup"><span data-stu-id="c4869-112">CallNeedsHostHook Method</span></span>](ihosttaskmanager-callneedshosthook-method.md)|<span data-ttu-id="c4869-113">Permite al host especificar si el Common Language Runtime puede alinear la llamada especificada a una función no administrada.</span><span class="sxs-lookup"><span data-stu-id="c4869-113">Enables the host to specify whether the common language runtime can inline the specified call to an unmanaged function.</span></span>|  
|[<span data-ttu-id="c4869-114">CreateTask (Método)</span><span class="sxs-lookup"><span data-stu-id="c4869-114">CreateTask Method</span></span>](ihosttaskmanager-createtask-method.md)|<span data-ttu-id="c4869-115">Solicita que el host cree una nueva tarea.</span><span class="sxs-lookup"><span data-stu-id="c4869-115">Requests that the host create a new task.</span></span>|  
|[<span data-ttu-id="c4869-116">Método EndDelayAbort</span><span class="sxs-lookup"><span data-stu-id="c4869-116">EndDelayAbort Method</span></span>](ihosttaskmanager-enddelayabort-method.md)|<span data-ttu-id="c4869-117">Notifica al host que el código administrado está saliendo del período en el que la tarea actual no se debe anular, siguiendo una llamada anterior a `BeginDelayAbort` .</span><span class="sxs-lookup"><span data-stu-id="c4869-117">Notifies the host that managed code is exiting the period in which the current task must not be aborted, following an earlier call to `BeginDelayAbort`.</span></span>|  
|[<span data-ttu-id="c4869-118">Método EndThreadAffinity</span><span class="sxs-lookup"><span data-stu-id="c4869-118">EndThreadAffinity Method</span></span>](ihosttaskmanager-endthreadaffinity-method.md)|<span data-ttu-id="c4869-119">Notifica al host que el código administrado está saliendo del período en el que la tarea actual no se debe pasar a otro subproceso del sistema operativo, siguiendo una llamada anterior a `BeginThreadAffinity` .</span><span class="sxs-lookup"><span data-stu-id="c4869-119">Notifies the host that managed code is exiting the period in which the current task must not be moved to another operating system thread, following an earlier call to `BeginThreadAffinity`.</span></span>|  
|[<span data-ttu-id="c4869-120">Método EnterRuntime</span><span class="sxs-lookup"><span data-stu-id="c4869-120">EnterRuntime Method</span></span>](ihosttaskmanager-enterruntime-method.md)|<span data-ttu-id="c4869-121">Notifica al host que una llamada a un método no administrado, como un método de invocación de plataforma, devuelve el control de la ejecución a CLR.</span><span class="sxs-lookup"><span data-stu-id="c4869-121">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the CLR.</span></span>|  
|[<span data-ttu-id="c4869-122">Método GetCurrentTask</span><span class="sxs-lookup"><span data-stu-id="c4869-122">GetCurrentTask Method</span></span>](ihosttaskmanager-getcurrenttask-method.md)|<span data-ttu-id="c4869-123">Obtiene un puntero de interfaz a la tarea que se está ejecutando actualmente en el subproceso del sistema operativo desde el que se realiza esta llamada.</span><span class="sxs-lookup"><span data-stu-id="c4869-123">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>|  
|[<span data-ttu-id="c4869-124">Método GetStackGuarantee</span><span class="sxs-lookup"><span data-stu-id="c4869-124">GetStackGuarantee Method</span></span>](ihosttaskmanager-getstackguarantee-method.md)|<span data-ttu-id="c4869-125">Obtiene la cantidad de espacio de pila que se garantiza que está disponible después de que se complete una operación de pila, pero antes del cierre de un proceso.</span><span class="sxs-lookup"><span data-stu-id="c4869-125">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>|  
|[<span data-ttu-id="c4869-126">Método LeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="c4869-126">LeaveRuntime Method</span></span>](ihosttaskmanager-leaveruntime-method.md)|<span data-ttu-id="c4869-127">Notifica al host que el código administrado está a punto de hacer una llamada a una función no administrada.</span><span class="sxs-lookup"><span data-stu-id="c4869-127">Notifies the host that managed code is about to make a call to an unmanaged function.</span></span>|  
|[<span data-ttu-id="c4869-128">Método ReverseEnterRuntime</span><span class="sxs-lookup"><span data-stu-id="c4869-128">ReverseEnterRuntime Method</span></span>](ihosttaskmanager-reverseenterruntime-method.md)|<span data-ttu-id="c4869-129">Notifica al host que se está realizando una llamada en el Common Language Runtime (CLR) desde el código no administrado.</span><span class="sxs-lookup"><span data-stu-id="c4869-129">Notifies the host that a call is being made into the common language runtime (CLR) from unmanaged code.</span></span>|  
|[<span data-ttu-id="c4869-130">Método ReverseLeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="c4869-130">ReverseLeaveRuntime Method</span></span>](ihosttaskmanager-reverseleaveruntime-method.md)|<span data-ttu-id="c4869-131">Notifica al host que el control está saliendo del CLR y entra en una función no administrada que, a su vez, se llama desde el código administrado.</span><span class="sxs-lookup"><span data-stu-id="c4869-131">Notifies the host that control is leaving the CLR and entering an unmanaged function that was, in turn, called from managed code.</span></span>|  
|[<span data-ttu-id="c4869-132">Método SetCLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="c4869-132">SetCLRTaskManager Method</span></span>](ihosttaskmanager-setclrtaskmanager-method.md)|<span data-ttu-id="c4869-133">Proporciona al host un puntero de interfaz a una instancia de [ICLRTaskManager](iclrtaskmanager-interface.md) implementada por CLR.</span><span class="sxs-lookup"><span data-stu-id="c4869-133">Provides the host with an interface pointer to an [ICLRTaskManager](iclrtaskmanager-interface.md) instance implemented by the CLR.</span></span>|  
|[<span data-ttu-id="c4869-134">Método SetLocale</span><span class="sxs-lookup"><span data-stu-id="c4869-134">SetLocale Method</span></span>](ihosttaskmanager-setlocale-method.md)|<span data-ttu-id="c4869-135">Notifica al host que CLR ha cambiado la configuración regional en la tarea actual.</span><span class="sxs-lookup"><span data-stu-id="c4869-135">Notifies the host that the CLR has changed the locale on the current task.</span></span>|  
|[<span data-ttu-id="c4869-136">Método SetStackGuarantee</span><span class="sxs-lookup"><span data-stu-id="c4869-136">SetStackGuarantee Method</span></span>](ihosttaskmanager-setstackguarantee-method.md)|<span data-ttu-id="c4869-137">Reservado para uso interno.</span><span class="sxs-lookup"><span data-stu-id="c4869-137">Reserved for internal use only.</span></span>|  
|[<span data-ttu-id="c4869-138">Método SetUILocale</span><span class="sxs-lookup"><span data-stu-id="c4869-138">SetUILocale Method</span></span>](ihosttaskmanager-setuilocale-method.md)|<span data-ttu-id="c4869-139">Notifica al host que se ha cambiado la configuración regional de la interfaz de usuario en la tarea actual.</span><span class="sxs-lookup"><span data-stu-id="c4869-139">Notifies the host that the user interface locale has been changed on the current task.</span></span>|  
|[<span data-ttu-id="c4869-140">Método Sleep</span><span class="sxs-lookup"><span data-stu-id="c4869-140">Sleep Method</span></span>](ihosttaskmanager-sleep-method.md)|<span data-ttu-id="c4869-141">Notifica al host que la tarea actual va a entrar en suspensión.</span><span class="sxs-lookup"><span data-stu-id="c4869-141">Notifies the host that the current task is going to sleep.</span></span>|  
|[<span data-ttu-id="c4869-142">Método SwitchToTask</span><span class="sxs-lookup"><span data-stu-id="c4869-142">SwitchToTask Method</span></span>](ihosttaskmanager-switchtotask-method.md)|<span data-ttu-id="c4869-143">Notifica al host que debe desactivar la tarea actual.</span><span class="sxs-lookup"><span data-stu-id="c4869-143">Notifies the host that it should switch out the current task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4869-144">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c4869-144">Remarks</span></span>  

 <span data-ttu-id="c4869-145">`IHostTaskManager` permite que CLR cree y administre tareas, para proporcionar enlaces para que el host tome medidas cuando el control se transfiere del código administrado al código no administrado y viceversa, y para especificar determinadas acciones que el host puede y no puede realizar durante la ejecución del código.</span><span class="sxs-lookup"><span data-stu-id="c4869-145">`IHostTaskManager` allows the CLR to create and manage tasks, to provide hooks for the host to take action when control transfers from managed to unmanaged code and vice versa, and to specify certain actions the host can and cannot take during code execution.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4869-146">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c4869-146">Requirements</span></span>  

 <span data-ttu-id="c4869-147">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4869-147">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4869-148">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c4869-148">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c4869-149">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c4869-149">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c4869-150">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4869-150">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4869-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4869-151">See also</span></span>

- [<span data-ttu-id="c4869-152">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c4869-152">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="c4869-153">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c4869-153">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="c4869-154">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c4869-154">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="c4869-155">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="c4869-155">Hosting Interfaces</span></span>](hosting-interfaces.md)
