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
ms.openlocfilehash: b365aaa13b3070662a74ebcfc914f5ed3d291d76
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133996"
---
# <a name="iclrdebugmanagerbeginconnection-method"></a><span data-ttu-id="15eaf-102">ICLRDebugManager::BeginConnection (Método)</span><span class="sxs-lookup"><span data-stu-id="15eaf-102">ICLRDebugManager::BeginConnection Method</span></span>
<span data-ttu-id="15eaf-103">Establece una nueva conexión entre el host y el depurador para asociar una lista de tareas con un identificador y un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="15eaf-103">Establishes a new connection between the host and the debugger to associate a list of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15eaf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15eaf-104">Syntax</span></span>  
  
```  
HRESULT BeginConnection (  
    [in] CONNID dwConnectionId,  
    [in, string] wchar_t* szConnectionName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15eaf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="15eaf-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="15eaf-106">[in] Un identificador para asociar a la lista de tareas de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="15eaf-106">[in] An identifier to associate with the list of common language runtime (CLR) tasks.</span></span>  
  
 `szConnectionName`  
 <span data-ttu-id="15eaf-107">[in] Un nombre descriptivo para asociar a la lista de tareas CLR.</span><span class="sxs-lookup"><span data-stu-id="15eaf-107">[in] A friendly name to associate with the list of CLR tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15eaf-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="15eaf-108">Return Value</span></span>  
  
|<span data-ttu-id="15eaf-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="15eaf-109">HRESULT</span></span>|<span data-ttu-id="15eaf-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="15eaf-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="15eaf-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="15eaf-111">S_OK</span></span>|`BeginConnection` <span data-ttu-id="15eaf-112">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="15eaf-112">returned successfully.</span></span>|  
|<span data-ttu-id="15eaf-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="15eaf-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="15eaf-114">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="15eaf-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="15eaf-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="15eaf-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="15eaf-116">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="15eaf-116">The call timed out.</span></span>|  
|<span data-ttu-id="15eaf-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="15eaf-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="15eaf-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="15eaf-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="15eaf-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="15eaf-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="15eaf-120">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="15eaf-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="15eaf-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="15eaf-121">E_FAIL</span></span>|<span data-ttu-id="15eaf-122">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="15eaf-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="15eaf-123">Después de un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="15eaf-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="15eaf-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="15eaf-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="15eaf-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="15eaf-125">E_INVALIDARG</span></span>|`dwConnectionId` <span data-ttu-id="15eaf-126">es cero, o `BeginConnection` ya se ha llamado mediante este `dwConnectionId` valor, o `szConnectionName` era null.</span><span class="sxs-lookup"><span data-stu-id="15eaf-126">was zero, or `BeginConnection` was already called using this `dwConnectionId` value, or `szConnectionName` was null.</span></span>|  
|<span data-ttu-id="15eaf-127">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="15eaf-127">E_OUTOFMEMORY</span></span>|<span data-ttu-id="15eaf-128">No hay suficiente memoria podría asignar para contener la lista de tareas asociadas con esta conexión.</span><span class="sxs-lookup"><span data-stu-id="15eaf-128">Not enough memory could be allocated to hold the list of tasks associated with this connection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15eaf-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="15eaf-129">Remarks</span></span>  
 <span data-ttu-id="15eaf-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) proporciona tres métodos, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), y [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), para asociar listas de tareas con identificadores y nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="15eaf-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="15eaf-131">Estos tres métodos deben llamarse en un orden específico para cada conjunto de tareas.</span><span class="sxs-lookup"><span data-stu-id="15eaf-131">These three methods must be called in a specific order for each set of tasks.</span></span> `BeginConnection` <span data-ttu-id="15eaf-132">se llama en primer lugar para establecer una conexión nueva.</span><span class="sxs-lookup"><span data-stu-id="15eaf-132">is called first to establish a new connection.</span></span> `SetConnectionTasks` <span data-ttu-id="15eaf-133">se llama a continuación para proporcionar el conjunto de tareas que se asociará con esa conexión.</span><span class="sxs-lookup"><span data-stu-id="15eaf-133">is called next to provide the set of tasks to be associated with that connection.</span></span> `EndConnection` <span data-ttu-id="15eaf-134">se llama en último lugar para quitar la asociación entre la lista de tareas y el identificador y el nombre descriptivo. Sin embargo, se pueden anidar llamadas para las conexiones diferentes.</span><span class="sxs-lookup"><span data-stu-id="15eaf-134">is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15eaf-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15eaf-135">Requirements</span></span>  
 <span data-ttu-id="15eaf-136">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15eaf-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15eaf-137">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="15eaf-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="15eaf-138">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="15eaf-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="15eaf-139">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="15eaf-139">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="15eaf-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="15eaf-140">See also</span></span>

- [<span data-ttu-id="15eaf-141">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="15eaf-141">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="15eaf-142">ICLRDebugManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="15eaf-142">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="15eaf-143">Método EndConnection</span><span class="sxs-lookup"><span data-stu-id="15eaf-143">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)
- [<span data-ttu-id="15eaf-144">Método SetConnectionTasks</span><span class="sxs-lookup"><span data-stu-id="15eaf-144">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="15eaf-145">IHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="15eaf-145">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
