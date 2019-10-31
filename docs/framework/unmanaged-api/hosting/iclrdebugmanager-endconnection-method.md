---
title: ICLRDebugManager::EndConnection (Método)
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.EndConnection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::EndConnection
helpviewer_keywords:
- ICLRDebugManager::EndConnection method [.NET Framework hosting]
- EndConnection method [.NET Framework hosting]
ms.assetid: 89dc7363-2f29-4eb2-8f23-fccdda6a76a6
topic_type:
- apiref
ms.openlocfilehash: 425f40da7a53aa4af1bd14964a8136add2f59f0b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135216"
---
# <a name="iclrdebugmanagerendconnection-method"></a><span data-ttu-id="6567d-102">ICLRDebugManager::EndConnection (Método)</span><span class="sxs-lookup"><span data-stu-id="6567d-102">ICLRDebugManager::EndConnection Method</span></span>
<span data-ttu-id="6567d-103">Quita la asociación entre una lista de tareas y un identificador y un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="6567d-103">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6567d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6567d-104">Syntax</span></span>  
  
```cpp  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6567d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6567d-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="6567d-106">de El identificador específico del host para la conexión y la lista asociada de tareas de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="6567d-106">[in] The host-specific identifier for the connection and the associated list of common language runtime (CLR) tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6567d-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6567d-107">Return Value</span></span>  
  
|<span data-ttu-id="6567d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6567d-108">HRESULT</span></span>|<span data-ttu-id="6567d-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="6567d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6567d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6567d-110">S_OK</span></span>|<span data-ttu-id="6567d-111">`EndConnection` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="6567d-111">`EndConnection` returned successfully.</span></span>|  
|<span data-ttu-id="6567d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6567d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6567d-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="6567d-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6567d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6567d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6567d-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="6567d-115">The call timed out.</span></span>|  
|<span data-ttu-id="6567d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6567d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6567d-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="6567d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6567d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6567d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6567d-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="6567d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6567d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6567d-120">E_FAIL</span></span>|<span data-ttu-id="6567d-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="6567d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6567d-122">Una vez que un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="6567d-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6567d-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6567d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6567d-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="6567d-124">E_INVALIDARG</span></span>|<span data-ttu-id="6567d-125">No se llamó nunca a [BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) con `dwConnectionId`o `dwConnectionId` era cero.</span><span class="sxs-lookup"><span data-stu-id="6567d-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) was never called using `dwConnectionId`, or `dwConnectionId` was zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6567d-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6567d-126">Remarks</span></span>  
 <span data-ttu-id="6567d-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) proporciona tres métodos, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)y `EndConnection`, para asociar listas de tareas con identificadores y nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="6567d-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and `EndConnection`, for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6567d-128">Se debe llamar a estos tres métodos en un orden específico para cada conjunto de tareas.</span><span class="sxs-lookup"><span data-stu-id="6567d-128">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="6567d-129">primero se llama a `BeginConnection` para establecer una nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="6567d-129">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="6567d-130">a continuación, se llama a `SetConnectionTasks` a continuación para proporcionar el conjunto de tareas que se van a asociar a esa conexión.</span><span class="sxs-lookup"><span data-stu-id="6567d-130">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="6567d-131">`EndConnection` se llama Last para quitar la asociación entre la lista de tareas y el identificador y el nombre descriptivo. Sin embargo, se pueden anidar las llamadas para las distintas conexiones.</span><span class="sxs-lookup"><span data-stu-id="6567d-131">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6567d-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6567d-132">Requirements</span></span>  
 <span data-ttu-id="6567d-133">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6567d-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6567d-134">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6567d-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6567d-135">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6567d-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6567d-136">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6567d-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6567d-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="6567d-137">See also</span></span>

- [<span data-ttu-id="6567d-138">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6567d-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="6567d-139">ICLRDebugManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6567d-139">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="6567d-140">BeginConnection (método)</span><span class="sxs-lookup"><span data-stu-id="6567d-140">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="6567d-141">SetConnectionTasks (método)</span><span class="sxs-lookup"><span data-stu-id="6567d-141">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="6567d-142">IHostControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6567d-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
