---
title: "ICLRTask::SwitchOut (Método)"
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
- ICLRTask.SwitchOut
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchOut
helpviewer_keywords:
- ICLRTask::SwitchOut method [.NET Framework hosting]
- SwitchOut method [.NET Framework hosting]
ms.assetid: b6fb168c-b24b-4ecf-a390-2b5ba3317ae6
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8fc8fcc5550981b2b8f4a51877d9e6571954f48b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskswitchout-method"></a><span data-ttu-id="f60b5-102">ICLRTask::SwitchOut (Método)</span><span class="sxs-lookup"><span data-stu-id="f60b5-102">ICLRTask::SwitchOut Method</span></span>
<span data-ttu-id="f60b5-103">Notifica a common language runtime (CLR) que la tarea representa el actual [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instancia ya no está en un estado operativo.</span><span class="sxs-lookup"><span data-stu-id="f60b5-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is no longer in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f60b5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f60b5-104">Syntax</span></span>  
  
```  
HRESULT SwitchOut ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f60b5-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f60b5-105">Return Value</span></span>  
  
|<span data-ttu-id="f60b5-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f60b5-106">HRESULT</span></span>|<span data-ttu-id="f60b5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f60b5-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f60b5-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="f60b5-108">S_OK</span></span>|<span data-ttu-id="f60b5-109">`SwitchOut`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="f60b5-109">`SwitchOut` returned successfully.</span></span>|  
|<span data-ttu-id="f60b5-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f60b5-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f60b5-111">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="f60b5-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f60b5-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f60b5-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f60b5-113">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="f60b5-113">The call timed out.</span></span>|  
|<span data-ttu-id="f60b5-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f60b5-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f60b5-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="f60b5-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f60b5-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f60b5-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f60b5-117">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="f60b5-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f60b5-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f60b5-118">E_FAIL</span></span>|<span data-ttu-id="f60b5-119">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="f60b5-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f60b5-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="f60b5-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f60b5-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f60b5-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f60b5-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f60b5-122">Remarks</span></span>  
 <span data-ttu-id="f60b5-123">Un host llama al método `SwitchOut` para informar a CLR que ha detenido temporalmente ejecutando la tarea que actual `ICLRTask` representa la instancia y volverá a programar la tarea.</span><span class="sxs-lookup"><span data-stu-id="f60b5-123">A host calls `SwitchOut` to inform the CLR that it has temporarily stopped executing the task that the current `ICLRTask` instance represents, and will reschedule the task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f60b5-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f60b5-124">Requirements</span></span>  
 <span data-ttu-id="f60b5-125">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f60b5-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f60b5-126">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f60b5-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f60b5-127">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f60b5-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f60b5-128">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f60b5-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f60b5-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="f60b5-129">See Also</span></span>  
 [<span data-ttu-id="f60b5-130">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f60b5-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="f60b5-131">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f60b5-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="f60b5-132">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f60b5-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="f60b5-133">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f60b5-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
