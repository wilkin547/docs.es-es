---
title: ICLRDebugManager::BeginConnection (Método)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5938f916dfab9434c40b43fa8dfc5a1ef263db80
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552884"
---
# <a name="iclrdebugmanagerbeginconnection-method"></a><span data-ttu-id="7394b-102">ICLRDebugManager::BeginConnection (Método)</span><span class="sxs-lookup"><span data-stu-id="7394b-102">ICLRDebugManager::BeginConnection Method</span></span>
<span data-ttu-id="7394b-103">Establece una nueva conexión entre el host y el depurador para asociar una lista de tareas con un identificador y un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="7394b-103">Establishes a new connection between the host and the debugger to associate a list of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7394b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7394b-104">Syntax</span></span>  
  
```  
HRESULT BeginConnection (  
    [in] CONNID dwConnectionId,  
    [in, string] wchar_t* szConnectionName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7394b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7394b-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="7394b-106">[in] Un identificador para asociar a la lista de tareas de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="7394b-106">[in] An identifier to associate with the list of common language runtime (CLR) tasks.</span></span>  
  
 `szConnectionName`  
 <span data-ttu-id="7394b-107">[in] Un nombre descriptivo para asociar a la lista de tareas CLR.</span><span class="sxs-lookup"><span data-stu-id="7394b-107">[in] A friendly name to associate with the list of CLR tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7394b-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7394b-108">Return Value</span></span>  
  
|<span data-ttu-id="7394b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7394b-109">HRESULT</span></span>|<span data-ttu-id="7394b-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="7394b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7394b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7394b-111">S_OK</span></span>|<span data-ttu-id="7394b-112">`BeginConnection` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="7394b-112">`BeginConnection` returned successfully.</span></span>|  
|<span data-ttu-id="7394b-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7394b-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7394b-114">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="7394b-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7394b-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7394b-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7394b-116">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="7394b-116">The call timed out.</span></span>|  
|<span data-ttu-id="7394b-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7394b-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7394b-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="7394b-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7394b-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7394b-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7394b-120">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="7394b-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7394b-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7394b-121">E_FAIL</span></span>|<span data-ttu-id="7394b-122">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="7394b-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7394b-123">Después de un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="7394b-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7394b-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7394b-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7394b-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="7394b-125">E_INVALIDARG</span></span>|<span data-ttu-id="7394b-126">`dwConnectionId` es cero, o `BeginConnection` ya se ha llamado mediante este `dwConnectionId` valor, o `szConnectionName` era null.</span><span class="sxs-lookup"><span data-stu-id="7394b-126">`dwConnectionId` was zero, or `BeginConnection` was already called using this `dwConnectionId` value, or `szConnectionName` was null.</span></span>|  
|<span data-ttu-id="7394b-127">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="7394b-127">E_OUTOFMEMORY</span></span>|<span data-ttu-id="7394b-128">No hay suficiente memoria podría asignar para contener la lista de tareas asociadas con esta conexión.</span><span class="sxs-lookup"><span data-stu-id="7394b-128">Not enough memory could be allocated to hold the list of tasks associated with this connection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7394b-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7394b-129">Remarks</span></span>  
 <span data-ttu-id="7394b-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) proporciona tres métodos, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), y [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), para asociar listas de tareas con identificadores y nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="7394b-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7394b-131">Estos tres métodos deben llamarse en un orden específico para cada conjunto de tareas.</span><span class="sxs-lookup"><span data-stu-id="7394b-131">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="7394b-132">`BeginConnection` se llama en primer lugar para establecer una conexión nueva.</span><span class="sxs-lookup"><span data-stu-id="7394b-132">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="7394b-133">`SetConnectionTasks` se llama a continuación para proporcionar el conjunto de tareas que se asociará con esa conexión.</span><span class="sxs-lookup"><span data-stu-id="7394b-133">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="7394b-134">`EndConnection` se llama en último lugar para quitar la asociación entre la lista de tareas y el identificador y el nombre descriptivo. Sin embargo, se pueden anidar llamadas para las conexiones diferentes.</span><span class="sxs-lookup"><span data-stu-id="7394b-134">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7394b-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7394b-135">Requirements</span></span>  
 <span data-ttu-id="7394b-136">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7394b-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7394b-137">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7394b-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7394b-138">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7394b-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7394b-139">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7394b-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7394b-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="7394b-140">See also</span></span>
- [<span data-ttu-id="7394b-141">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7394b-141">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="7394b-142">ICLRDebugManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7394b-142">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="7394b-143">EndConnection (método)</span><span class="sxs-lookup"><span data-stu-id="7394b-143">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)
- [<span data-ttu-id="7394b-144">SetConnectionTasks (método)</span><span class="sxs-lookup"><span data-stu-id="7394b-144">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="7394b-145">IHostControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7394b-145">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
