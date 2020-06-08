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
ms.openlocfilehash: d3d081e389e29833f24063ba75289f3db8c5504a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504282"
---
# <a name="iclrdebugmanagerendconnection-method"></a><span data-ttu-id="f5a66-102">ICLRDebugManager::EndConnection (Método)</span><span class="sxs-lookup"><span data-stu-id="f5a66-102">ICLRDebugManager::EndConnection Method</span></span>
<span data-ttu-id="f5a66-103">Quita la asociación entre una lista de tareas y un identificador y un nombre descriptivo.</span><span class="sxs-lookup"><span data-stu-id="f5a66-103">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5a66-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f5a66-104">Syntax</span></span>  
  
```cpp  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5a66-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f5a66-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="f5a66-106">de El identificador específico del host para la conexión y la lista asociada de tareas de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="f5a66-106">[in] The host-specific identifier for the connection and the associated list of common language runtime (CLR) tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f5a66-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f5a66-107">Return Value</span></span>  
  
|<span data-ttu-id="f5a66-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f5a66-108">HRESULT</span></span>|<span data-ttu-id="f5a66-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5a66-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f5a66-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f5a66-110">S_OK</span></span>|<span data-ttu-id="f5a66-111">`EndConnection`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="f5a66-111">`EndConnection` returned successfully.</span></span>|  
|<span data-ttu-id="f5a66-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f5a66-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f5a66-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="f5a66-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f5a66-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f5a66-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f5a66-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f5a66-115">The call timed out.</span></span>|  
|<span data-ttu-id="f5a66-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f5a66-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f5a66-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="f5a66-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f5a66-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f5a66-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f5a66-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="f5a66-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f5a66-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f5a66-120">E_FAIL</span></span>|<span data-ttu-id="f5a66-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="f5a66-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f5a66-122">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="f5a66-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f5a66-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f5a66-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f5a66-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f5a66-124">E_INVALIDARG</span></span>|<span data-ttu-id="f5a66-125">No se ha llamado a [BeginConnection](iclrdebugmanager-beginconnection-method.md) nunca mediante `dwConnectionId` o `dwConnectionId` era cero.</span><span class="sxs-lookup"><span data-stu-id="f5a66-125">[BeginConnection](iclrdebugmanager-beginconnection-method.md) was never called using `dwConnectionId`, or `dwConnectionId` was zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5a66-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f5a66-126">Remarks</span></span>  
 <span data-ttu-id="f5a66-127">[ICLRDebugManager](iclrdebugmanager-interface.md) proporciona tres métodos, `BeginConnection` , [SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md)y `EndConnection` , para asociar listas de tareas con identificadores y nombres descriptivos.</span><span class="sxs-lookup"><span data-stu-id="f5a66-127">[ICLRDebugManager](iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md), and `EndConnection`, for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f5a66-128">Se debe llamar a estos tres métodos en un orden específico para cada conjunto de tareas.</span><span class="sxs-lookup"><span data-stu-id="f5a66-128">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="f5a66-129">`BeginConnection`se llama primero a para establecer una nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="f5a66-129">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="f5a66-130">`SetConnectionTasks`se llama a junto a para proporcionar el conjunto de tareas que se van a asociar a esa conexión.</span><span class="sxs-lookup"><span data-stu-id="f5a66-130">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="f5a66-131">`EndConnection`se llama a Last para quitar la asociación entre la lista de tareas y el identificador y el nombre descriptivo. Sin embargo, se pueden anidar las llamadas para las distintas conexiones.</span><span class="sxs-lookup"><span data-stu-id="f5a66-131">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5a66-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f5a66-132">Requirements</span></span>  
 <span data-ttu-id="f5a66-133">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5a66-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5a66-134">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f5a66-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f5a66-135">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f5a66-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f5a66-136">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5a66-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5a66-137">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="f5a66-137">See also</span></span>

- [<span data-ttu-id="f5a66-138">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f5a66-138">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="f5a66-139">ICLRDebugManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f5a66-139">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="f5a66-140">Método BeginConnection</span><span class="sxs-lookup"><span data-stu-id="f5a66-140">BeginConnection Method</span></span>](iclrdebugmanager-beginconnection-method.md)
- [<span data-ttu-id="f5a66-141">Método SetConnectionTasks</span><span class="sxs-lookup"><span data-stu-id="f5a66-141">SetConnectionTasks Method</span></span>](iclrdebugmanager-setconnectiontasks-method.md)
- [<span data-ttu-id="f5a66-142">IHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f5a66-142">IHostControl Interface</span></span>](ihostcontrol-interface.md)
