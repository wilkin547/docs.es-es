---
title: "IHostGCManager::SuspensionStarting (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 30f6c611dc719fa6f1162498082cc9a60fb5059b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="79603-102">IHostGCManager::SuspensionStarting (Método)</span><span class="sxs-lookup"><span data-stu-id="79603-102">IHostGCManager::SuspensionStarting Method</span></span>
<span data-ttu-id="79603-103">Notifica al host que common language runtime (CLR) está suspendiendo la ejecución de tareas para realizar una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="79603-103">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79603-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="79603-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="79603-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="79603-105">Return Value</span></span>  
  
|<span data-ttu-id="79603-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="79603-106">HRESULT</span></span>|<span data-ttu-id="79603-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="79603-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="79603-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="79603-108">S_OK</span></span>|<span data-ttu-id="79603-109">`SuspensionStarting`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="79603-109">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="79603-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="79603-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="79603-111">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="79603-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="79603-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="79603-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="79603-113">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="79603-113">The call timed out.</span></span>|  
|<span data-ttu-id="79603-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="79603-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="79603-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="79603-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="79603-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="79603-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="79603-117">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="79603-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="79603-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="79603-118">E_FAIL</span></span>|<span data-ttu-id="79603-119">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="79603-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="79603-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="79603-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="79603-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="79603-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79603-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="79603-122">Remarks</span></span>  
 <span data-ttu-id="79603-123">CLR llama `SuspensionStarting` para informar al host que se está produciendo la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="79603-123">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="79603-124">No volver a programar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="79603-124">Do not reschedule this task.</span></span> <span data-ttu-id="79603-125">El host debe volver a programar una tarea cuando [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) se llama.</span><span class="sxs-lookup"><span data-stu-id="79603-125">The host must reschedule a task when [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79603-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="79603-126">Requirements</span></span>  
 <span data-ttu-id="79603-127">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79603-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79603-128">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="79603-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="79603-129">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="79603-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="79603-130">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79603-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79603-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="79603-131">See Also</span></span>  
 [<span data-ttu-id="79603-132">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="79603-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="79603-133">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="79603-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="79603-134">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="79603-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="79603-135">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="79603-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="79603-136">IHostGCManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="79603-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
