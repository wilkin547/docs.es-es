---
description: 'Más información sobre: ICLRDebugManager:: SetConnectionTasks (método)'
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
ms.openlocfilehash: 851b3f54cc5599781596314dfb70296a3d86491a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728748"
---
# <a name="iclrdebugmanagersetconnectiontasks-method"></a><span data-ttu-id="33fc3-103">ICLRDebugManager::SetConnectionTasks (Método)</span><span class="sxs-lookup"><span data-stu-id="33fc3-103">ICLRDebugManager::SetConnectionTasks Method</span></span>

<span data-ttu-id="33fc3-104">Asocia una lista de instancias de [ICLRTask](iclrtask-interface.md) con un identificador y un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="33fc3-104">Associates a list of [ICLRTask](iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33fc3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33fc3-105">Syntax</span></span>  
  
```cpp  
HRESULT SetConnectionTasks (  
    [in] CONNID id,  
    [in] DWORD dwCount,  
    [in, size_is(dwCount)] ICLRTask **ppCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33fc3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="33fc3-106">Parameters</span></span>  

 `id`  
 <span data-ttu-id="33fc3-107">de Identificador específico del host para la conexión a la que se va a asociar la `ppCLRTask` matriz.</span><span class="sxs-lookup"><span data-stu-id="33fc3-107">[in] The host-specific identifier for the connection with which to associate the `ppCLRTask` array.</span></span>  
  
 `dwCount`  
 <span data-ttu-id="33fc3-108">de Número de miembros de `ppCLRTask` .</span><span class="sxs-lookup"><span data-stu-id="33fc3-108">[in] The number of members of `ppCLRTask`.</span></span> <span data-ttu-id="33fc3-109">Este número debe ser mayor que cero.</span><span class="sxs-lookup"><span data-stu-id="33fc3-109">This number must be greater than zero.</span></span>  
  
 `ppCLRTask`  
 <span data-ttu-id="33fc3-110">de Matriz de `ICLRTask` punteros que se va a asociar a la conexión identificada por `id` .</span><span class="sxs-lookup"><span data-stu-id="33fc3-110">[in] An array of `ICLRTask` pointers to associate with the connection identified by `id`.</span></span> <span data-ttu-id="33fc3-111">Esta matriz debe contener al menos un miembro.</span><span class="sxs-lookup"><span data-stu-id="33fc3-111">This array must contain at least one member.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="33fc3-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="33fc3-112">Return Value</span></span>  
  
|<span data-ttu-id="33fc3-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="33fc3-113">HRESULT</span></span>|<span data-ttu-id="33fc3-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="33fc3-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="33fc3-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="33fc3-115">S_OK</span></span>|<span data-ttu-id="33fc3-116">`SetConnectionTasks` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="33fc3-116">`SetConnectionTasks` returned successfully.</span></span>|  
|<span data-ttu-id="33fc3-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="33fc3-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="33fc3-118">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="33fc3-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="33fc3-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="33fc3-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="33fc3-120">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="33fc3-120">The call timed out.</span></span>|  
|<span data-ttu-id="33fc3-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="33fc3-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="33fc3-122">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="33fc3-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="33fc3-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="33fc3-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="33fc3-124">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="33fc3-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="33fc3-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="33fc3-125">E_FAIL</span></span>|<span data-ttu-id="33fc3-126">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="33fc3-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="33fc3-127">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="33fc3-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="33fc3-128">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="33fc3-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="33fc3-129">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="33fc3-129">E_INVALIDARG</span></span>|<span data-ttu-id="33fc3-130">No se ha llamado a [BeginConnection](iclrdebugmanager-beginconnection-method.md) con este valor de `id` , o `dwCount` o `id` es cero, o uno de los elementos de `ppCLRTask` es NULL.</span><span class="sxs-lookup"><span data-stu-id="33fc3-130">[BeginConnection](iclrdebugmanager-beginconnection-method.md) has not been called using this value of `id`, or `dwCount` or `id` is zero, or one of the elements of `ppCLRTask` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33fc3-131">Observaciones</span><span class="sxs-lookup"><span data-stu-id="33fc3-131">Remarks</span></span>  

 <span data-ttu-id="33fc3-132">[ICLRDebugManager](iclrdebugmanager-interface.md) proporciona tres métodos, `BeginConnection` , `SetConnectionTasks` y [EndConnection](iclrdebugmanager-endconnection-method.md), para asociar listas de tareas con identificadores y nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="33fc3-132">[ICLRDebugManager](iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, `SetConnectionTasks`, and [EndConnection](iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="33fc3-133">Se debe llamar a estos tres métodos en un orden específico para cada conjunto de tareas.</span><span class="sxs-lookup"><span data-stu-id="33fc3-133">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="33fc3-134">`BeginConnection` se llama primero a para establecer una nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="33fc3-134">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="33fc3-135">`SetConnectionTasks` se llama a junto a para proporcionar el conjunto de tareas que se van a asociar a esa conexión.</span><span class="sxs-lookup"><span data-stu-id="33fc3-135">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="33fc3-136">`EndConnection` se llama a Last para quitar la asociación entre la lista de tareas y el identificador y el nombre descriptivo. Sin embargo, se pueden anidar las llamadas para las distintas conexiones.</span><span class="sxs-lookup"><span data-stu-id="33fc3-136">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33fc3-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33fc3-137">Requirements</span></span>  

 <span data-ttu-id="33fc3-138">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33fc3-138">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33fc3-139">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="33fc3-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="33fc3-140">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="33fc3-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="33fc3-141">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33fc3-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33fc3-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="33fc3-142">See also</span></span>

- [<span data-ttu-id="33fc3-143">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="33fc3-143">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="33fc3-144">ICLRDebugManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="33fc3-144">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="33fc3-145">Método BeginConnection</span><span class="sxs-lookup"><span data-stu-id="33fc3-145">BeginConnection Method</span></span>](iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="33fc3-146">Método EndConnection</span><span class="sxs-lookup"><span data-stu-id="33fc3-146">EndConnection Method</span></span>](iclrdebugmanager-endconnection-method.md)
- [<span data-ttu-id="33fc3-147">IHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="33fc3-147">IHostControl Interface</span></span>](ihostcontrol-interface.md)
