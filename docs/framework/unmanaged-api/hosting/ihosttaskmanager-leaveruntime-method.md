---
title: "IHostTaskManager::LeaveRuntime (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.LeaveRuntime
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::LeaveRuntime
helpviewer_keywords:
- IHostTaskManager::LeaveRuntime method [.NET Framework hosting]
- LeaveRuntime method [.NET Framework hosting]
ms.assetid: 43689cc4-e48e-46e5-a22d-bafd768b8759
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 326fa3d495cafe187f06e1e6a804cbe90fb12efd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagerleaveruntime-method"></a><span data-ttu-id="9b7fe-102">IHostTaskManager::LeaveRuntime (Método)</span><span class="sxs-lookup"><span data-stu-id="9b7fe-102">IHostTaskManager::LeaveRuntime Method</span></span>
<span data-ttu-id="9b7fe-103">Notifica al host que la tarea está ejecuta actualmente está a punto de abandonar common language runtime (CLR) y entrar en código no administrado.</span><span class="sxs-lookup"><span data-stu-id="9b7fe-103">Notifies the host that the currently executing task is about to leave the common language runtime (CLR) and enter unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9b7fe-104">Una llamada correspondiente a [IHostTaskManager:: EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) notifica al host que la tarea que se ejecuta actualmente es volver a escribir código administrado.</span><span class="sxs-lookup"><span data-stu-id="9b7fe-104">A corresponding call to [IHostTaskManager::EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) notifies the host that the currently executing task is reentering managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b7fe-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9b7fe-105">Syntax</span></span>  
  
```  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9b7fe-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9b7fe-106">Parameters</span></span>  
 `target`  
 <span data-ttu-id="9b7fe-107">[in] La dirección en el archivo ejecutable portable asignado de la función no administrada que se llame a.</span><span class="sxs-lookup"><span data-stu-id="9b7fe-107">[in] The address within the mapped portable executable file of the unmanaged function to be called.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b7fe-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9b7fe-108">Return Value</span></span>  
  
|<span data-ttu-id="9b7fe-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9b7fe-109">HRESULT</span></span>|<span data-ttu-id="9b7fe-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b7fe-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9b7fe-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9b7fe-111">S_OK</span></span>|<span data-ttu-id="9b7fe-112">`LeaveRuntime`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="9b7fe-112">`LeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="9b7fe-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9b7fe-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9b7fe-114">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="9b7fe-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9b7fe-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9b7fe-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9b7fe-116">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="9b7fe-116">The call timed out.</span></span>|  
|<span data-ttu-id="9b7fe-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9b7fe-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9b7fe-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="9b7fe-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9b7fe-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9b7fe-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9b7fe-120">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="9b7fe-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9b7fe-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9b7fe-121">E_FAIL</span></span>|<span data-ttu-id="9b7fe-122">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="9b7fe-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9b7fe-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="9b7fe-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9b7fe-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9b7fe-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9b7fe-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="9b7fe-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="9b7fe-126">No hay suficiente memoria disponible para completar la asignación solicitada.</span><span class="sxs-lookup"><span data-stu-id="9b7fe-126">Not enough memory is available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b7fe-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9b7fe-127">Remarks</span></span>  
 <span data-ttu-id="9b7fe-128">Las secuencias de llamada a y desde el código no administrado se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="9b7fe-128">Call sequences to and from unmanaged code can be nested.</span></span> <span data-ttu-id="9b7fe-129">Por ejemplo, la siguiente lista describe una situación hipotética en la que la secuencia de llamadas a `LeaveRuntime`, [IHostTaskManager:: ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager:: ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), y `IHostTaskManager::EnterRuntime` permite al host identificar las capas anidadas.</span><span class="sxs-lookup"><span data-stu-id="9b7fe-129">For example, the list below describes a hypothetical situation in which the sequence of calls to `LeaveRuntime`, [IHostTaskManager::ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager::ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), and `IHostTaskManager::EnterRuntime` allows the host to identify the nested layers.</span></span>  
  
|<span data-ttu-id="9b7fe-130">Acción</span><span class="sxs-lookup"><span data-stu-id="9b7fe-130">Action</span></span>|<span data-ttu-id="9b7fe-131">Llamada al método correspondiente</span><span class="sxs-lookup"><span data-stu-id="9b7fe-131">Corresponding Method Call</span></span>|  
|------------|-------------------------------|  
|<span data-ttu-id="9b7fe-132">Invocación de una función no administrada escrita en C con la plataforma de un llamadas ejecutable administrado de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9b7fe-132">A managed Visual Basic executable calls an unmanaged function written in C by using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="9b7fe-133">La función de C no administrada llama a un método en una DLL administrada escrita en C#.</span><span class="sxs-lookup"><span data-stu-id="9b7fe-133">The unmanaged C function calls a method in a managed DLL written in C#.</span></span>|`IHostTaskManager::ReverseEnterRuntime`|  
|<span data-ttu-id="9b7fe-134">La función de C# administrada llama a otra función no administrado escrito en C, también con la plataforma de invocación.</span><span class="sxs-lookup"><span data-stu-id="9b7fe-134">The managed C# function calls another unmanaged function written in C, also using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="9b7fe-135">La segunda función no administrada devuelve la ejecución a la función de C#.</span><span class="sxs-lookup"><span data-stu-id="9b7fe-135">The second unmanaged function returns execution to the C# function.</span></span>|`IHostTaskManager::EnterRuntime`|  
|<span data-ttu-id="9b7fe-136">La función de C# devuelve la ejecución a la primera función no administrada.</span><span class="sxs-lookup"><span data-stu-id="9b7fe-136">The C# function returns execution to the first unmanaged function.</span></span>|`IHostTaskManager::ReverseLeaveRuntime`|  
|<span data-ttu-id="9b7fe-137">La primera función no administrada devuelve la ejecución al programa de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9b7fe-137">The first unmanaged function returns execution to the Visual Basic program.</span></span>|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a><span data-ttu-id="9b7fe-138">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9b7fe-138">Requirements</span></span>  
 <span data-ttu-id="9b7fe-139">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b7fe-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b7fe-140">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9b7fe-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9b7fe-141">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9b7fe-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9b7fe-142">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b7fe-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b7fe-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b7fe-143">See Also</span></span>  
 [<span data-ttu-id="9b7fe-144">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9b7fe-144">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="9b7fe-145">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9b7fe-145">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="9b7fe-146">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9b7fe-146">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="9b7fe-147">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9b7fe-147">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
