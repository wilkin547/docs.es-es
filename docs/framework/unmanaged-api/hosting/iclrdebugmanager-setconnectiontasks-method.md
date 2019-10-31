---
title: ICLRDebugManager::SetConnectionTasks (Método)
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.SetConnectionTasks
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::SetConnectionTasks
helpviewer_keywords:
- SetConnectionTasks method [.NET Framework hosting]
- ICLRDebugManager::SetConnectionTasks method [.NET Framework hosting]
ms.assetid: b38bbc9a-872c-41a9-b8c3-ca011d25456a
topic_type:
- apiref
ms.openlocfilehash: d6092f16804fae39dd9496e8572edd64e1b7e9bd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129383"
---
# <a name="iclrdebugmanagersetconnectiontasks-method"></a><span data-ttu-id="ca315-102">ICLRDebugManager::SetConnectionTasks (Método)</span><span class="sxs-lookup"><span data-stu-id="ca315-102">ICLRDebugManager::SetConnectionTasks Method</span></span>
<span data-ttu-id="ca315-103">Asocia una lista de instancias de [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) con un identificador y un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="ca315-103">Associates a list of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca315-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca315-104">Syntax</span></span>  
  
```cpp  
HRESULT SetConnectionTasks (  
    [in] CONNID id,  
    [in] DWORD dwCount,  
    [in, size_is(dwCount)] ICLRTask **ppCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca315-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ca315-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="ca315-106">de El identificador específico del host para la conexión a la que se va a asociar la `ppCLRTask` matriz.</span><span class="sxs-lookup"><span data-stu-id="ca315-106">[in] The host-specific identifier for the connection with which to associate the `ppCLRTask` array.</span></span>  
  
 `dwCount`  
 <span data-ttu-id="ca315-107">de Número de miembros de `ppCLRTask`.</span><span class="sxs-lookup"><span data-stu-id="ca315-107">[in] The number of members of `ppCLRTask`.</span></span> <span data-ttu-id="ca315-108">Este número debe ser mayor que cero.</span><span class="sxs-lookup"><span data-stu-id="ca315-108">This number must be greater than zero.</span></span>  
  
 `ppCLRTask`  
 <span data-ttu-id="ca315-109">de Matriz de punteros `ICLRTask` que se van a asociar a la conexión identificada por `id`.</span><span class="sxs-lookup"><span data-stu-id="ca315-109">[in] An array of `ICLRTask` pointers to associate with the connection identified by `id`.</span></span> <span data-ttu-id="ca315-110">Esta matriz debe contener al menos un miembro.</span><span class="sxs-lookup"><span data-stu-id="ca315-110">This array must contain at least one member.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca315-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ca315-111">Return Value</span></span>  
  
|<span data-ttu-id="ca315-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ca315-112">HRESULT</span></span>|<span data-ttu-id="ca315-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca315-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ca315-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ca315-114">S_OK</span></span>|<span data-ttu-id="ca315-115">`SetConnectionTasks` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ca315-115">`SetConnectionTasks` returned successfully.</span></span>|  
|<span data-ttu-id="ca315-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ca315-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ca315-117">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="ca315-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ca315-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ca315-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ca315-119">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ca315-119">The call timed out.</span></span>|  
|<span data-ttu-id="ca315-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ca315-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ca315-121">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ca315-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ca315-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ca315-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ca315-123">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="ca315-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ca315-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ca315-124">E_FAIL</span></span>|<span data-ttu-id="ca315-125">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="ca315-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ca315-126">Una vez que un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="ca315-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ca315-127">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ca315-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ca315-128">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ca315-128">E_INVALIDARG</span></span>|<span data-ttu-id="ca315-129">No se ha llamado a [BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) con este valor de `id`, o `dwCount` o `id` es cero, o uno de los elementos de `ppCLRTask` es NULL.</span><span class="sxs-lookup"><span data-stu-id="ca315-129">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) has not been called using this value of `id`, or `dwCount` or `id` is zero, or one of the elements of `ppCLRTask` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca315-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ca315-130">Remarks</span></span>  
 <span data-ttu-id="ca315-131">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) proporciona tres métodos, `BeginConnection`, `SetConnectionTasks`y [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), para asociar listas de tareas con identificadores y nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="ca315-131">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, `SetConnectionTasks`, and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ca315-132">Se debe llamar a estos tres métodos en un orden específico para cada conjunto de tareas.</span><span class="sxs-lookup"><span data-stu-id="ca315-132">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="ca315-133">primero se llama a `BeginConnection` para establecer una nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="ca315-133">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="ca315-134">a continuación, se llama a `SetConnectionTasks` a continuación para proporcionar el conjunto de tareas que se van a asociar a esa conexión.</span><span class="sxs-lookup"><span data-stu-id="ca315-134">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="ca315-135">`EndConnection` se llama Last para quitar la asociación entre la lista de tareas y el identificador y el nombre descriptivo. Sin embargo, se pueden anidar las llamadas para las distintas conexiones.</span><span class="sxs-lookup"><span data-stu-id="ca315-135">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca315-136">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ca315-136">Requirements</span></span>  
 <span data-ttu-id="ca315-137">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca315-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca315-138">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ca315-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ca315-139">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ca315-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca315-140">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca315-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca315-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca315-141">See also</span></span>

- [<span data-ttu-id="ca315-142">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ca315-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="ca315-143">ICLRDebugManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ca315-143">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="ca315-144">BeginConnection (método)</span><span class="sxs-lookup"><span data-stu-id="ca315-144">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="ca315-145">EndConnection (método)</span><span class="sxs-lookup"><span data-stu-id="ca315-145">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)
- [<span data-ttu-id="ca315-146">IHostControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ca315-146">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
