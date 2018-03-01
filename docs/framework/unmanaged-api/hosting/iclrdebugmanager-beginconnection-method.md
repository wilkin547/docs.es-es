---
title: "ICLRDebugManager::BeginConnection (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRDebugManager.BeginConnection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::BeginConnection
helpviewer_keywords:
- ICLRDebugManager::BeginConnection method [.NET Framework hosting]
- BeginConnection method [.NET Framework hosting]
ms.assetid: bdd98146-ff4d-4150-a264-a4c1a32d31f3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a637ba71dc966cf311526f468393ef4207e10460
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdebugmanagerbeginconnection-method"></a><span data-ttu-id="fc81b-102">ICLRDebugManager::BeginConnection (Método)</span><span class="sxs-lookup"><span data-stu-id="fc81b-102">ICLRDebugManager::BeginConnection Method</span></span>
<span data-ttu-id="fc81b-103">Establece una nueva conexión entre el host y el depurador para asociar una lista de tareas con un identificador y un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="fc81b-103">Establishes a new connection between the host and the debugger to associate a list of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc81b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc81b-104">Syntax</span></span>  
  
```  
HRESULT BeginConnection (  
    [in] CONNID dwConnectionId,  
    [in, string] wchar_t* szConnectionName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fc81b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fc81b-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="fc81b-106">[in] Un identificador para asociar a la lista de common language runtime (CLR) tareas.</span><span class="sxs-lookup"><span data-stu-id="fc81b-106">[in] An identifier to associate with the list of common language runtime (CLR) tasks.</span></span>  
  
 `szConnectionName`  
 <span data-ttu-id="fc81b-107">[in] Un nombre descriptivo para asociar a la lista de tareas CLR.</span><span class="sxs-lookup"><span data-stu-id="fc81b-107">[in] A friendly name to associate with the list of CLR tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fc81b-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fc81b-108">Return Value</span></span>  
  
|<span data-ttu-id="fc81b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fc81b-109">HRESULT</span></span>|<span data-ttu-id="fc81b-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc81b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fc81b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="fc81b-111">S_OK</span></span>|<span data-ttu-id="fc81b-112">`BeginConnection`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="fc81b-112">`BeginConnection` returned successfully.</span></span>|  
|<span data-ttu-id="fc81b-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fc81b-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fc81b-114">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="fc81b-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fc81b-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fc81b-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fc81b-116">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="fc81b-116">The call timed out.</span></span>|  
|<span data-ttu-id="fc81b-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fc81b-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fc81b-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="fc81b-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fc81b-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fc81b-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fc81b-120">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="fc81b-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fc81b-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fc81b-121">E_FAIL</span></span>|<span data-ttu-id="fc81b-122">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="fc81b-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fc81b-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="fc81b-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fc81b-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fc81b-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fc81b-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="fc81b-125">E_INVALIDARG</span></span>|<span data-ttu-id="fc81b-126">`dwConnectionId`es cero, o `BeginConnection` ya se ha llamado con este `dwConnectionId` valor, o `szConnectionName` era null.</span><span class="sxs-lookup"><span data-stu-id="fc81b-126">`dwConnectionId` was zero, or `BeginConnection` was already called using this `dwConnectionId` value, or `szConnectionName` was null.</span></span>|  
|<span data-ttu-id="fc81b-127">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="fc81b-127">E_OUTOFMEMORY</span></span>|<span data-ttu-id="fc81b-128">No hay suficiente memoria podría asignarse para albergar la lista de tareas asociadas con esta conexión.</span><span class="sxs-lookup"><span data-stu-id="fc81b-128">Not enough memory could be allocated to hold the list of tasks associated with this connection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc81b-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fc81b-129">Remarks</span></span>  
 <span data-ttu-id="fc81b-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) proporciona tres métodos, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), y [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), para asociar listas de tareas con identificadores y nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="fc81b-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fc81b-131">Estos tres métodos deben llamarse en un orden específico para cada conjunto de tareas.</span><span class="sxs-lookup"><span data-stu-id="fc81b-131">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="fc81b-132">`BeginConnection`se llama en primer lugar para establecer una nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="fc81b-132">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="fc81b-133">`SetConnectionTasks`se llama a continuación para proporcionar el conjunto de tareas que se asociará con esa conexión.</span><span class="sxs-lookup"><span data-stu-id="fc81b-133">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="fc81b-134">`EndConnection`se llama última para quitar la asociación entre la lista de tareas y el identificador y el nombre descriptivo. Sin embargo, se pueden anidar las llamadas para conexiones diferentes.</span><span class="sxs-lookup"><span data-stu-id="fc81b-134">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc81b-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fc81b-135">Requirements</span></span>  
 <span data-ttu-id="fc81b-136">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc81b-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc81b-137">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fc81b-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fc81b-138">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fc81b-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fc81b-139">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc81b-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc81b-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc81b-140">See Also</span></span>  
 [<span data-ttu-id="fc81b-141">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fc81b-141">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="fc81b-142">ICLRDebugManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fc81b-142">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="fc81b-143">EndConnection (método)</span><span class="sxs-lookup"><span data-stu-id="fc81b-143">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)  
 [<span data-ttu-id="fc81b-144">SetConnectionTasks (método)</span><span class="sxs-lookup"><span data-stu-id="fc81b-144">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)  
 [<span data-ttu-id="fc81b-145">IHostControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fc81b-145">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
