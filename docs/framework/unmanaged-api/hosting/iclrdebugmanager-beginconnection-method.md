---
description: 'Más información acerca de: ICLRDebugManager:: BeginConnection (método)'
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
ms.openlocfilehash: 9b4ee64ad96bddfd5d7d650b657c6691b27d8c69
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746144"
---
# <a name="iclrdebugmanagerbeginconnection-method"></a><span data-ttu-id="ce7af-103">ICLRDebugManager::BeginConnection (Método)</span><span class="sxs-lookup"><span data-stu-id="ce7af-103">ICLRDebugManager::BeginConnection Method</span></span>

<span data-ttu-id="ce7af-104">Establece una nueva conexión entre el host y el depurador para asociar una lista de tareas con un identificador y un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="ce7af-104">Establishes a new connection between the host and the debugger to associate a list of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce7af-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ce7af-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginConnection (  
    [in] CONNID dwConnectionId,  
    [in, string] wchar_t* szConnectionName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce7af-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ce7af-106">Parameters</span></span>  

 `dwConnectionId`  
 <span data-ttu-id="ce7af-107">de Identificador que se va a asociar a la lista de tareas de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="ce7af-107">[in] An identifier to associate with the list of common language runtime (CLR) tasks.</span></span>  
  
 `szConnectionName`  
 <span data-ttu-id="ce7af-108">de Nombre descriptivo que se va a asociar a la lista de tareas CLR.</span><span class="sxs-lookup"><span data-stu-id="ce7af-108">[in] A friendly name to associate with the list of CLR tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ce7af-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ce7af-109">Return Value</span></span>  
  
|<span data-ttu-id="ce7af-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ce7af-110">HRESULT</span></span>|<span data-ttu-id="ce7af-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="ce7af-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ce7af-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="ce7af-112">S_OK</span></span>|<span data-ttu-id="ce7af-113">`BeginConnection` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ce7af-113">`BeginConnection` returned successfully.</span></span>|  
|<span data-ttu-id="ce7af-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ce7af-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ce7af-115">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="ce7af-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ce7af-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ce7af-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ce7af-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ce7af-117">The call timed out.</span></span>|  
|<span data-ttu-id="ce7af-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ce7af-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ce7af-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ce7af-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ce7af-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ce7af-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ce7af-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="ce7af-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ce7af-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ce7af-122">E_FAIL</span></span>|<span data-ttu-id="ce7af-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="ce7af-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ce7af-124">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="ce7af-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ce7af-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ce7af-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ce7af-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ce7af-126">E_INVALIDARG</span></span>|<span data-ttu-id="ce7af-127">`dwConnectionId` era cero o `BeginConnection` ya se llamó con este `dwConnectionId` valor, o `szConnectionName` era null.</span><span class="sxs-lookup"><span data-stu-id="ce7af-127">`dwConnectionId` was zero, or `BeginConnection` was already called using this `dwConnectionId` value, or `szConnectionName` was null.</span></span>|  
|<span data-ttu-id="ce7af-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ce7af-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="ce7af-129">No se pudo asignar memoria suficiente para contener la lista de tareas asociadas a esta conexión.</span><span class="sxs-lookup"><span data-stu-id="ce7af-129">Not enough memory could be allocated to hold the list of tasks associated with this connection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce7af-130">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ce7af-130">Remarks</span></span>  

 <span data-ttu-id="ce7af-131">[ICLRDebugManager](iclrdebugmanager-interface.md) proporciona tres métodos, `BeginConnection` , [SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md)y [EndConnection](iclrdebugmanager-endconnection-method.md), para asociar listas de tareas con identificadores y nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="ce7af-131">[ICLRDebugManager](iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md), and [EndConnection](iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ce7af-132">Se debe llamar a estos tres métodos en un orden específico para cada conjunto de tareas.</span><span class="sxs-lookup"><span data-stu-id="ce7af-132">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="ce7af-133">`BeginConnection` se llama primero a para establecer una nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="ce7af-133">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="ce7af-134">`SetConnectionTasks` se llama a junto a para proporcionar el conjunto de tareas que se van a asociar a esa conexión.</span><span class="sxs-lookup"><span data-stu-id="ce7af-134">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="ce7af-135">`EndConnection` se llama a Last para quitar la asociación entre la lista de tareas y el identificador y el nombre descriptivo. Sin embargo, se pueden anidar las llamadas para las distintas conexiones.</span><span class="sxs-lookup"><span data-stu-id="ce7af-135">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce7af-136">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ce7af-136">Requirements</span></span>  

 <span data-ttu-id="ce7af-137">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce7af-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce7af-138">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ce7af-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ce7af-139">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ce7af-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ce7af-140">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce7af-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce7af-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce7af-141">See also</span></span>

- [<span data-ttu-id="ce7af-142">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ce7af-142">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="ce7af-143">ICLRDebugManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ce7af-143">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="ce7af-144">Método EndConnection</span><span class="sxs-lookup"><span data-stu-id="ce7af-144">EndConnection Method</span></span>](iclrdebugmanager-endconnection-method.md)
- [<span data-ttu-id="ce7af-145">Método SetConnectionTasks</span><span class="sxs-lookup"><span data-stu-id="ce7af-145">SetConnectionTasks Method</span></span>](iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="ce7af-146">IHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ce7af-146">IHostControl Interface</span></span>](ihostcontrol-interface.md)
