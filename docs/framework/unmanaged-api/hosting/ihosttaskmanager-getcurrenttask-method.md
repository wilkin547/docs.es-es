---
title: "IHostTaskManager::GetCurrentTask (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.GetCurrentTask
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: f17bca49-90bd-4dee-a5e1-b9a57ea46f85
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b3ba8cbaac28df49a2df70492c1a292ee8cd287e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanagergetcurrenttask-method"></a><span data-ttu-id="8adfb-102">IHostTaskManager::GetCurrentTask (Método)</span><span class="sxs-lookup"><span data-stu-id="8adfb-102">IHostTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="8adfb-103">Obtiene un puntero de interfaz a la tarea que se está ejecutando actualmente en el subproceso de sistema operativo desde el que se realiza esta llamada.</span><span class="sxs-lookup"><span data-stu-id="8adfb-103">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8adfb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8adfb-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentTask (  
    [out] IHostTask **pTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8adfb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8adfb-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="8adfb-106">[out] Un puntero a la dirección de un [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instancia que representa la tarea está ejecutando actualmente, o null, si no hay ninguna tarea se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="8adfb-106">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the currently executing task, or null, if no task is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8adfb-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8adfb-107">Return Value</span></span>  
  
|<span data-ttu-id="8adfb-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8adfb-108">HRESULT</span></span>|<span data-ttu-id="8adfb-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="8adfb-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8adfb-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8adfb-110">S_OK</span></span>|<span data-ttu-id="8adfb-111">`GetCurrentTask`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="8adfb-111">`GetCurrentTask` returned successfully.</span></span>|  
|<span data-ttu-id="8adfb-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8adfb-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8adfb-113">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="8adfb-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8adfb-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8adfb-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8adfb-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="8adfb-115">The call timed out.</span></span>|  
|<span data-ttu-id="8adfb-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8adfb-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8adfb-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="8adfb-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8adfb-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8adfb-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8adfb-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="8adfb-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8adfb-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8adfb-120">E_FAIL</span></span>|<span data-ttu-id="8adfb-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="8adfb-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8adfb-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="8adfb-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8adfb-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8adfb-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8adfb-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="8adfb-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="8adfb-125">`GetCurrentTask`se llamó en un subproceso del sistema operativo fuera del control del host.</span><span class="sxs-lookup"><span data-stu-id="8adfb-125">`GetCurrentTask` was called on an operating system thread outside the control of the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8adfb-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8adfb-126">Remarks</span></span>  
 <span data-ttu-id="8adfb-127">El host también puede establecer el `pTask` parámetro en null para evitar que una tarea que no se ha iniciado entraran en CLR.</span><span class="sxs-lookup"><span data-stu-id="8adfb-127">The host can also set the `pTask` parameter to null to prevent a task that it did not initiate from entering the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8adfb-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8adfb-128">Requirements</span></span>  
 <span data-ttu-id="8adfb-129">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8adfb-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8adfb-130">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8adfb-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8adfb-131">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8adfb-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8adfb-132">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8adfb-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8adfb-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="8adfb-133">See Also</span></span>  
 [<span data-ttu-id="8adfb-134">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8adfb-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="8adfb-135">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8adfb-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="8adfb-136">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8adfb-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="8adfb-137">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8adfb-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
