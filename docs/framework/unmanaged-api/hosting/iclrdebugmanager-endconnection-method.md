---
description: 'Más información acerca de: ICLRDebugManager:: EndConnection (método)'
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
ms.openlocfilehash: 06dc9e20ec02c3e3040090babcc443a2ae59848b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746059"
---
# <a name="iclrdebugmanagerendconnection-method"></a><span data-ttu-id="ff253-103">ICLRDebugManager::EndConnection (Método)</span><span class="sxs-lookup"><span data-stu-id="ff253-103">ICLRDebugManager::EndConnection Method</span></span>

<span data-ttu-id="ff253-104">Quita la asociación entre una lista de tareas y un identificador y un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="ff253-104">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff253-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff253-105">Syntax</span></span>  
  
```cpp  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff253-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ff253-106">Parameters</span></span>  

 `dwConnectionId`  
 <span data-ttu-id="ff253-107">de El identificador específico del host para la conexión y la lista asociada de tareas de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="ff253-107">[in] The host-specific identifier for the connection and the associated list of common language runtime (CLR) tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff253-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ff253-108">Return Value</span></span>  
  
|<span data-ttu-id="ff253-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ff253-109">HRESULT</span></span>|<span data-ttu-id="ff253-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="ff253-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ff253-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ff253-111">S_OK</span></span>|<span data-ttu-id="ff253-112">`EndConnection` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ff253-112">`EndConnection` returned successfully.</span></span>|  
|<span data-ttu-id="ff253-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ff253-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ff253-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="ff253-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ff253-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ff253-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ff253-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ff253-116">The call timed out.</span></span>|  
|<span data-ttu-id="ff253-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ff253-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ff253-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ff253-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ff253-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ff253-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ff253-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="ff253-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ff253-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ff253-121">E_FAIL</span></span>|<span data-ttu-id="ff253-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="ff253-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ff253-123">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="ff253-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ff253-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ff253-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ff253-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ff253-125">E_INVALIDARG</span></span>|<span data-ttu-id="ff253-126">No se ha llamado a [BeginConnection](iclrdebugmanager-beginconnection-method.md) nunca mediante `dwConnectionId` o `dwConnectionId` era cero.</span><span class="sxs-lookup"><span data-stu-id="ff253-126">[BeginConnection](iclrdebugmanager-beginconnection-method.md) was never called using `dwConnectionId`, or `dwConnectionId` was zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff253-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ff253-127">Remarks</span></span>  

 <span data-ttu-id="ff253-128">[ICLRDebugManager](iclrdebugmanager-interface.md) proporciona tres métodos, `BeginConnection` , [SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md)y `EndConnection` , para asociar listas de tareas con identificadores y nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="ff253-128">[ICLRDebugManager](iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md), and `EndConnection`, for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ff253-129">Se debe llamar a estos tres métodos en un orden específico para cada conjunto de tareas.</span><span class="sxs-lookup"><span data-stu-id="ff253-129">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="ff253-130">`BeginConnection` se llama primero a para establecer una nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="ff253-130">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="ff253-131">`SetConnectionTasks` se llama a junto a para proporcionar el conjunto de tareas que se van a asociar a esa conexión.</span><span class="sxs-lookup"><span data-stu-id="ff253-131">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="ff253-132">`EndConnection` se llama a Last para quitar la asociación entre la lista de tareas y el identificador y el nombre descriptivo. Sin embargo, se pueden anidar las llamadas para las distintas conexiones.</span><span class="sxs-lookup"><span data-stu-id="ff253-132">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff253-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ff253-133">Requirements</span></span>  

 <span data-ttu-id="ff253-134">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff253-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff253-135">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ff253-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ff253-136">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ff253-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ff253-137">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff253-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff253-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff253-138">See also</span></span>

- [<span data-ttu-id="ff253-139">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ff253-139">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="ff253-140">ICLRDebugManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ff253-140">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="ff253-141">Método BeginConnection</span><span class="sxs-lookup"><span data-stu-id="ff253-141">BeginConnection Method</span></span>](iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="ff253-142">Método SetConnectionTasks</span><span class="sxs-lookup"><span data-stu-id="ff253-142">SetConnectionTasks Method</span></span>](iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="ff253-143">IHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ff253-143">IHostControl Interface</span></span>](ihostcontrol-interface.md)
