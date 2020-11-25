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
ms.openlocfilehash: c5b41e4209141c0396ec8a1da766b80043be8807
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726163"
---
# <a name="iclrdebugmanagerbeginconnection-method"></a><span data-ttu-id="20b87-102">ICLRDebugManager::BeginConnection (Método)</span><span class="sxs-lookup"><span data-stu-id="20b87-102">ICLRDebugManager::BeginConnection Method</span></span>

<span data-ttu-id="20b87-103">Establece una nueva conexión entre el host y el depurador para asociar una lista de tareas con un identificador y un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="20b87-103">Establishes a new connection between the host and the debugger to associate a list of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20b87-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="20b87-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginConnection (  
    [in] CONNID dwConnectionId,  
    [in, string] wchar_t* szConnectionName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20b87-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="20b87-105">Parameters</span></span>  

 `dwConnectionId`  
 <span data-ttu-id="20b87-106">de Identificador que se va a asociar a la lista de tareas de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="20b87-106">[in] An identifier to associate with the list of common language runtime (CLR) tasks.</span></span>  
  
 `szConnectionName`  
 <span data-ttu-id="20b87-107">de Nombre descriptivo que se va a asociar a la lista de tareas CLR.</span><span class="sxs-lookup"><span data-stu-id="20b87-107">[in] A friendly name to associate with the list of CLR tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="20b87-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="20b87-108">Return Value</span></span>  
  
|<span data-ttu-id="20b87-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="20b87-109">HRESULT</span></span>|<span data-ttu-id="20b87-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="20b87-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="20b87-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="20b87-111">S_OK</span></span>|<span data-ttu-id="20b87-112">`BeginConnection` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="20b87-112">`BeginConnection` returned successfully.</span></span>|  
|<span data-ttu-id="20b87-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="20b87-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="20b87-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="20b87-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="20b87-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="20b87-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="20b87-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="20b87-116">The call timed out.</span></span>|  
|<span data-ttu-id="20b87-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="20b87-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="20b87-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="20b87-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="20b87-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="20b87-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="20b87-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="20b87-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="20b87-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="20b87-121">E_FAIL</span></span>|<span data-ttu-id="20b87-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="20b87-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="20b87-123">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="20b87-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="20b87-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="20b87-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="20b87-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="20b87-125">E_INVALIDARG</span></span>|<span data-ttu-id="20b87-126">`dwConnectionId` era cero o `BeginConnection` ya se llamó con este `dwConnectionId` valor, o `szConnectionName` era null.</span><span class="sxs-lookup"><span data-stu-id="20b87-126">`dwConnectionId` was zero, or `BeginConnection` was already called using this `dwConnectionId` value, or `szConnectionName` was null.</span></span>|  
|<span data-ttu-id="20b87-127">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="20b87-127">E_OUTOFMEMORY</span></span>|<span data-ttu-id="20b87-128">No se pudo asignar memoria suficiente para contener la lista de tareas asociadas a esta conexión.</span><span class="sxs-lookup"><span data-stu-id="20b87-128">Not enough memory could be allocated to hold the list of tasks associated with this connection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20b87-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="20b87-129">Remarks</span></span>  

 <span data-ttu-id="20b87-130">[ICLRDebugManager](iclrdebugmanager-interface.md) proporciona tres métodos, `BeginConnection` , [SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md)y [EndConnection](iclrdebugmanager-endconnection-method.md), para asociar listas de tareas con identificadores y nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="20b87-130">[ICLRDebugManager](iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md), and [EndConnection](iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="20b87-131">Se debe llamar a estos tres métodos en un orden específico para cada conjunto de tareas.</span><span class="sxs-lookup"><span data-stu-id="20b87-131">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="20b87-132">`BeginConnection` se llama primero a para establecer una nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="20b87-132">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="20b87-133">`SetConnectionTasks` se llama a junto a para proporcionar el conjunto de tareas que se van a asociar a esa conexión.</span><span class="sxs-lookup"><span data-stu-id="20b87-133">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="20b87-134">`EndConnection` se llama a Last para quitar la asociación entre la lista de tareas y el identificador y el nombre descriptivo. Sin embargo, se pueden anidar las llamadas para las distintas conexiones.</span><span class="sxs-lookup"><span data-stu-id="20b87-134">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20b87-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="20b87-135">Requirements</span></span>  

 <span data-ttu-id="20b87-136">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20b87-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20b87-137">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="20b87-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="20b87-138">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="20b87-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="20b87-139">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20b87-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20b87-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="20b87-140">See also</span></span>

- [<span data-ttu-id="20b87-141">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20b87-141">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="20b87-142">ICLRDebugManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20b87-142">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="20b87-143">Método EndConnection</span><span class="sxs-lookup"><span data-stu-id="20b87-143">EndConnection Method</span></span>](iclrdebugmanager-endconnection-method.md)
- [<span data-ttu-id="20b87-144">Método SetConnectionTasks</span><span class="sxs-lookup"><span data-stu-id="20b87-144">SetConnectionTasks Method</span></span>](iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="20b87-145">IHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="20b87-145">IHostControl Interface</span></span>](ihostcontrol-interface.md)
