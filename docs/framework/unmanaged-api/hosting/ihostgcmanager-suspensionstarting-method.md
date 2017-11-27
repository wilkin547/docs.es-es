---
title: "IHostGCManager::SuspensionStarting (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostGCManager.SuspensionStarting
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostGCManager::SuspensionStarting
helpviewer_keywords:
- SuspensionStarting method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionStarting method [.NET Framework hosting]
ms.assetid: c381f524-94cf-4fa2-9298-50f847a03431
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9c807a124570f38922509d27e52936b980e36fba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="27883-102">IHostGCManager::SuspensionStarting (Método)</span><span class="sxs-lookup"><span data-stu-id="27883-102">IHostGCManager::SuspensionStarting Method</span></span>
<span data-ttu-id="27883-103">Notifica al host que common language runtime (CLR) está suspendiendo la ejecución de tareas para realizar una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="27883-103">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27883-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="27883-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="27883-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="27883-105">Return Value</span></span>  
  
|<span data-ttu-id="27883-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="27883-106">HRESULT</span></span>|<span data-ttu-id="27883-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="27883-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="27883-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="27883-108">S_OK</span></span>|<span data-ttu-id="27883-109">`SuspensionStarting`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="27883-109">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="27883-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="27883-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="27883-111">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="27883-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="27883-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="27883-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="27883-113">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="27883-113">The call timed out.</span></span>|  
|<span data-ttu-id="27883-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="27883-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="27883-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="27883-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="27883-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="27883-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="27883-117">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="27883-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="27883-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="27883-118">E_FAIL</span></span>|<span data-ttu-id="27883-119">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="27883-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="27883-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="27883-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="27883-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="27883-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27883-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="27883-122">Remarks</span></span>  
 <span data-ttu-id="27883-123">CLR llama `SuspensionStarting` para informar al host que se está produciendo la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="27883-123">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="27883-124">No volver a programar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="27883-124">Do not reschedule this task.</span></span> <span data-ttu-id="27883-125">El host debe volver a programar una tarea cuando [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) se llama.</span><span class="sxs-lookup"><span data-stu-id="27883-125">The host must reschedule a task when [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27883-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="27883-126">Requirements</span></span>  
 <span data-ttu-id="27883-127">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27883-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27883-128">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="27883-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="27883-129">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="27883-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="27883-130">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27883-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27883-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="27883-131">See Also</span></span>  
 [<span data-ttu-id="27883-132">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="27883-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="27883-133">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="27883-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="27883-134">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="27883-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="27883-135">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="27883-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="27883-136">IHostGCManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="27883-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
