---
title: "IHostGCManager::SuspensionEnding (Método)"
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
- IHostGCManager.SuspensionEnding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::SuspensionEnding
helpviewer_keywords:
- SuspensionEnding method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionEnding method [.NET Framework hosting]
ms.assetid: 8849a1db-17f0-44b7-880a-bd36d431eb91
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b9660a0aa755e297721679bcf6db798384f12abd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostgcmanagersuspensionending-method"></a><span data-ttu-id="8d617-102">IHostGCManager::SuspensionEnding (Método)</span><span class="sxs-lookup"><span data-stu-id="8d617-102">IHostGCManager::SuspensionEnding Method</span></span>
<span data-ttu-id="8d617-103">Notifica al host que common language runtime (CLR) está reanudando la ejecución de tareas en subprocesos que se habían suspendidos para una colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="8d617-103">Notifies the host that the common language runtime (CLR) is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d617-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8d617-104">Syntax</span></span>  
  
```  
HRESULT SuspensionEnding (  
    [in] DWORD generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8d617-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8d617-105">Parameters</span></span>  
 `generation`  
 <span data-ttu-id="8d617-106">[in] La generación de la colección de elementos no utilizados que está finalizando, desde la que se reanuda el subproceso.</span><span class="sxs-lookup"><span data-stu-id="8d617-106">[in] The garbage collection generation that is just finishing, from which the thread is resuming.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8d617-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8d617-107">Return Value</span></span>  
  
|<span data-ttu-id="8d617-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8d617-108">HRESULT</span></span>|<span data-ttu-id="8d617-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d617-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8d617-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8d617-110">S_OK</span></span>|<span data-ttu-id="8d617-111">`SuspensionEnding`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="8d617-111">`SuspensionEnding` returned successfully.</span></span>|  
|<span data-ttu-id="8d617-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8d617-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8d617-113">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="8d617-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8d617-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8d617-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8d617-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="8d617-115">The call timed out.</span></span>|  
|<span data-ttu-id="8d617-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8d617-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8d617-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="8d617-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8d617-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8d617-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8d617-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="8d617-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8d617-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8d617-120">E_FAIL</span></span>|<span data-ttu-id="8d617-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="8d617-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8d617-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="8d617-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8d617-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8d617-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d617-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8d617-124">Remarks</span></span>  
 <span data-ttu-id="8d617-125">CLR llama `SuspensionEnding` después de que realiza una recolección de elementos no utilizados, para informar al host que el subproceso está reanudando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="8d617-125">The CLR calls `SuspensionEnding` after it performs a garbage collection, to inform the host that the thread is resuming execution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8d617-126">No volver a programar el subproceso de que la llamada al método se realizó desde.</span><span class="sxs-lookup"><span data-stu-id="8d617-126">Do not reschedule the thread the method call was made from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d617-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8d617-127">Requirements</span></span>  
 <span data-ttu-id="8d617-128">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d617-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d617-129">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8d617-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8d617-130">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8d617-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8d617-131">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d617-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d617-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d617-132">See Also</span></span>  
 [<span data-ttu-id="8d617-133">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d617-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="8d617-134">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d617-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="8d617-135">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d617-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="8d617-136">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d617-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="8d617-137">IHostGCManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d617-137">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
