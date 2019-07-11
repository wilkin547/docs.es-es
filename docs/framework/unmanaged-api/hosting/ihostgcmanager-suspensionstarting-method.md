---
title: IHostGCManager::SuspensionStarting (Método)
ms.date: 03/30/2017
api_name:
- IHostGCManager.SuspensionStarting
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::SuspensionStarting
helpviewer_keywords:
- SuspensionStarting method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionStarting method [.NET Framework hosting]
ms.assetid: c381f524-94cf-4fa2-9298-50f847a03431
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 00322a75c4a15e42c89ff5a8680171a168a37613
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758698"
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="66d97-102">IHostGCManager::SuspensionStarting (Método)</span><span class="sxs-lookup"><span data-stu-id="66d97-102">IHostGCManager::SuspensionStarting Method</span></span>
<span data-ttu-id="66d97-103">Notifica al host que common language runtime (CLR) está suspendiendo la ejecución de tareas para realizar una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="66d97-103">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66d97-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="66d97-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="66d97-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="66d97-105">Return Value</span></span>  
  
|<span data-ttu-id="66d97-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="66d97-106">HRESULT</span></span>|<span data-ttu-id="66d97-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="66d97-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="66d97-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="66d97-108">S_OK</span></span>|<span data-ttu-id="66d97-109">`SuspensionStarting` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="66d97-109">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="66d97-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="66d97-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="66d97-111">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="66d97-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="66d97-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="66d97-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="66d97-113">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="66d97-113">The call timed out.</span></span>|  
|<span data-ttu-id="66d97-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="66d97-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="66d97-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="66d97-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="66d97-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="66d97-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="66d97-117">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="66d97-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="66d97-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="66d97-118">E_FAIL</span></span>|<span data-ttu-id="66d97-119">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="66d97-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="66d97-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="66d97-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="66d97-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="66d97-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66d97-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="66d97-122">Remarks</span></span>  
 <span data-ttu-id="66d97-123">CLR llama a `SuspensionStarting` para informar al host que se está produciendo la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="66d97-123">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="66d97-124">No se vuelva a programar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="66d97-124">Do not reschedule this task.</span></span> <span data-ttu-id="66d97-125">El host debe volver a programar una tarea cuando [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) se llama.</span><span class="sxs-lookup"><span data-stu-id="66d97-125">The host must reschedule a task when [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66d97-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="66d97-126">Requirements</span></span>  
 <span data-ttu-id="66d97-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66d97-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66d97-128">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="66d97-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="66d97-129">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="66d97-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="66d97-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66d97-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66d97-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="66d97-131">See also</span></span>

- [<span data-ttu-id="66d97-132">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="66d97-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="66d97-133">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="66d97-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="66d97-134">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="66d97-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="66d97-135">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="66d97-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="66d97-136">IHostGCManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="66d97-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
