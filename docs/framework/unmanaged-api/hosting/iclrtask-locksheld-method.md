---
title: "ICLRTask::LocksHeld (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.LocksHeld
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::LocksHeld
helpviewer_keywords:
- LocksHeld method [.NET Framework hosting]
- ICLRTask::LocksHeld method [.NET Framework hosting]
ms.assetid: e88a4dc3-02cc-4703-a474-292b71c40657
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f985295dcc54816fc0ee31b40115360602f1afd9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtasklocksheld-method"></a><span data-ttu-id="886ea-102">ICLRTask::LocksHeld (Método)</span><span class="sxs-lookup"><span data-stu-id="886ea-102">ICLRTask::LocksHeld Method</span></span>
<span data-ttu-id="886ea-103">Obtiene el número de bloqueos mantenidos en la tarea.</span><span class="sxs-lookup"><span data-stu-id="886ea-103">Gets the number of locks currently held on the task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="886ea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="886ea-104">Syntax</span></span>  
  
```  
HRESULT LocksHeld (  
    [out] SIZE_T *pLockCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="886ea-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="886ea-105">Parameters</span></span>  
 `pLockCount`  
 <span data-ttu-id="886ea-106">[out] El número de bloqueos mantenidos en la tarea en el momento de la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="886ea-106">[out] The number of locks held on the task at the time of the method call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="886ea-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="886ea-107">Return Value</span></span>  
  
|<span data-ttu-id="886ea-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="886ea-108">HRESULT</span></span>|<span data-ttu-id="886ea-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="886ea-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="886ea-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="886ea-110">S_OK</span></span>|<span data-ttu-id="886ea-111">`LocksHeld`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="886ea-111">`LocksHeld` returned successfully.</span></span>|  
|<span data-ttu-id="886ea-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="886ea-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="886ea-113">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="886ea-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="886ea-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="886ea-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="886ea-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="886ea-115">The call timed out.</span></span>|  
|<span data-ttu-id="886ea-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="886ea-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="886ea-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="886ea-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="886ea-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="886ea-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="886ea-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="886ea-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="886ea-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="886ea-120">E_FAIL</span></span>|<span data-ttu-id="886ea-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="886ea-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="886ea-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="886ea-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="886ea-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="886ea-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="886ea-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="886ea-124">Requirements</span></span>  
 <span data-ttu-id="886ea-125">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="886ea-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="886ea-126">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="886ea-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="886ea-127">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="886ea-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="886ea-128">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="886ea-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="886ea-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="886ea-129">See Also</span></span>  
 [<span data-ttu-id="886ea-130">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="886ea-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="886ea-131">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="886ea-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="886ea-132">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="886ea-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="886ea-133">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="886ea-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
