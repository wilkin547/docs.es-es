---
title: "IHostGCManager::SuspensionEnding (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostGCManager.SuspensionEnding
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostGCManager::SuspensionEnding
helpviewer_keywords:
- SuspensionEnding method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionEnding method [.NET Framework hosting]
ms.assetid: 8849a1db-17f0-44b7-880a-bd36d431eb91
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9952e62d4979efa0d07b19f183ca71adcc643365
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ihostgcmanagersuspensionending-method"></a><span data-ttu-id="5965d-102">IHostGCManager::SuspensionEnding (Método)</span><span class="sxs-lookup"><span data-stu-id="5965d-102">IHostGCManager::SuspensionEnding Method</span></span>
<span data-ttu-id="5965d-103">Notifica al host que common language runtime (CLR) está reanudando la ejecución de tareas en subprocesos que se habían suspendidos para una colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="5965d-103">Notifies the host that the common language runtime (CLR) is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5965d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5965d-104">Syntax</span></span>  
  
```  
HRESULT SuspensionEnding (  
    [in] DWORD generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5965d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5965d-105">Parameters</span></span>  
 `generation`  
 <span data-ttu-id="5965d-106">[in] La generación de la colección de elementos no utilizados que está finalizando, desde la que se reanuda el subproceso.</span><span class="sxs-lookup"><span data-stu-id="5965d-106">[in] The garbage collection generation that is just finishing, from which the thread is resuming.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5965d-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5965d-107">Return Value</span></span>  
  
|<span data-ttu-id="5965d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5965d-108">HRESULT</span></span>|<span data-ttu-id="5965d-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="5965d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5965d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5965d-110">S_OK</span></span>|<span data-ttu-id="5965d-111">`SuspensionEnding`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="5965d-111">`SuspensionEnding` returned successfully.</span></span>|  
|<span data-ttu-id="5965d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5965d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5965d-113">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="5965d-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5965d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5965d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5965d-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="5965d-115">The call timed out.</span></span>|  
|<span data-ttu-id="5965d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5965d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5965d-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="5965d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5965d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5965d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5965d-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="5965d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5965d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5965d-120">E_FAIL</span></span>|<span data-ttu-id="5965d-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="5965d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5965d-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="5965d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5965d-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5965d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5965d-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5965d-124">Remarks</span></span>  
 <span data-ttu-id="5965d-125">CLR llama `SuspensionEnding` después de que realiza una recolección de elementos no utilizados, para informar al host que el subproceso está reanudando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="5965d-125">The CLR calls `SuspensionEnding` after it performs a garbage collection, to inform the host that the thread is resuming execution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5965d-126">No volver a programar el subproceso de que la llamada al método se realizó desde.</span><span class="sxs-lookup"><span data-stu-id="5965d-126">Do not reschedule the thread the method call was made from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5965d-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5965d-127">Requirements</span></span>  
 <span data-ttu-id="5965d-128">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5965d-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5965d-129">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5965d-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5965d-130">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5965d-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5965d-131">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5965d-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5965d-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="5965d-132">See Also</span></span>  
 [<span data-ttu-id="5965d-133">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5965d-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="5965d-134">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5965d-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="5965d-135">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5965d-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="5965d-136">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5965d-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="5965d-137">IHostGCManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5965d-137">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
