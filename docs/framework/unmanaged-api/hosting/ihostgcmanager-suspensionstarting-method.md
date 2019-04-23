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
ms.openlocfilehash: 47ef5bb2539820d5a7bcd4ca6b4de86564290709
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59213095"
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="f7edc-102">IHostGCManager::SuspensionStarting (Método)</span><span class="sxs-lookup"><span data-stu-id="f7edc-102">IHostGCManager::SuspensionStarting Method</span></span>
<span data-ttu-id="f7edc-103">Notifica al host que common language runtime (CLR) está suspendiendo la ejecución de tareas para realizar una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="f7edc-103">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7edc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7edc-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f7edc-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f7edc-105">Return Value</span></span>  
  
|<span data-ttu-id="f7edc-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f7edc-106">HRESULT</span></span>|<span data-ttu-id="f7edc-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7edc-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f7edc-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="f7edc-108">S_OK</span></span>|<span data-ttu-id="f7edc-109">`SuspensionStarting` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="f7edc-109">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="f7edc-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f7edc-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f7edc-111">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="f7edc-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f7edc-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f7edc-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f7edc-113">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="f7edc-113">The call timed out.</span></span>|  
|<span data-ttu-id="f7edc-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f7edc-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f7edc-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="f7edc-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f7edc-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f7edc-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f7edc-117">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="f7edc-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f7edc-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f7edc-118">E_FAIL</span></span>|<span data-ttu-id="f7edc-119">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="f7edc-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f7edc-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="f7edc-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f7edc-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f7edc-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7edc-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f7edc-122">Remarks</span></span>  
 <span data-ttu-id="f7edc-123">CLR llama a `SuspensionStarting` para informar al host que se está produciendo la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="f7edc-123">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f7edc-124">No se vuelva a programar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="f7edc-124">Do not reschedule this task.</span></span> <span data-ttu-id="f7edc-125">El host debe volver a programar una tarea cuando [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) se llama.</span><span class="sxs-lookup"><span data-stu-id="f7edc-125">The host must reschedule a task when [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7edc-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f7edc-126">Requirements</span></span>  
 <span data-ttu-id="f7edc-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7edc-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7edc-128">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f7edc-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f7edc-129">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f7edc-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f7edc-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7edc-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7edc-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7edc-131">See also</span></span>

- [<span data-ttu-id="f7edc-132">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f7edc-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="f7edc-133">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f7edc-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="f7edc-134">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f7edc-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="f7edc-135">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f7edc-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="f7edc-136">IHostGCManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f7edc-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
