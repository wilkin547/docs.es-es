---
title: "IHostManualEvent::Wait (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostManualEvent.Wait
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostManualEvent::Wait
helpviewer_keywords:
- IHostManualEvent::Wait method [.NET Framework hosting]
- Wait method, IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 1fbb7d8b-8a23-4c2b-8376-1a70cd2d6030
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2dd456a3901f91fc8598a707a5699637ec450dbd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmanualeventwait-method"></a><span data-ttu-id="8cab2-102">IHostManualEvent::Wait (Método)</span><span class="sxs-lookup"><span data-stu-id="8cab2-102">IHostManualEvent::Wait Method</span></span>
<span data-ttu-id="8cab2-103">Hace que el actual [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instancia espere hasta que encuentre un propietario o una cantidad especificada de tiempo determinado.</span><span class="sxs-lookup"><span data-stu-id="8cab2-103">Causes the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to wait until it is owned, or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cab2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8cab2-104">Syntax</span></span>  
  
```  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8cab2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8cab2-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="8cab2-106">[in] El número de milisegundos que transcurrirán antes de volver, si la actual `IHostManualEvent` no es propiedad de instancia.</span><span class="sxs-lookup"><span data-stu-id="8cab2-106">[in] The number of milliseconds to wait before returning, if the current `IHostManualEvent` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="8cab2-107">[in] Uno de los [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valores, que indica la acción que debe realizar el host si esta operación se bloquea.</span><span class="sxs-lookup"><span data-stu-id="8cab2-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8cab2-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8cab2-108">Return Value</span></span>  
  
|<span data-ttu-id="8cab2-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8cab2-109">HRESULT</span></span>|<span data-ttu-id="8cab2-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="8cab2-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8cab2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="8cab2-111">S_OK</span></span>|<span data-ttu-id="8cab2-112">`Wait`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="8cab2-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="8cab2-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8cab2-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8cab2-114">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="8cab2-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8cab2-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8cab2-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8cab2-116">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="8cab2-116">The call timed out.</span></span>|  
|<span data-ttu-id="8cab2-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8cab2-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8cab2-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="8cab2-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8cab2-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8cab2-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8cab2-120">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="8cab2-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8cab2-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8cab2-121">E_FAIL</span></span>|<span data-ttu-id="8cab2-122">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="8cab2-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8cab2-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="8cab2-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8cab2-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8cab2-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8cab2-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="8cab2-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="8cab2-126">El host detectó un interbloqueo durante el intervalo de espera y eligió actual `IHostManualEvent` instancia como sujeto del interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="8cab2-126">The host detected a deadlock during the wait interval, and chose the current `IHostManualEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8cab2-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8cab2-127">Requirements</span></span>  
 <span data-ttu-id="8cab2-128">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8cab2-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cab2-129">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8cab2-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8cab2-130">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8cab2-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8cab2-131">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cab2-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cab2-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="8cab2-132">See Also</span></span>  
 [<span data-ttu-id="8cab2-133">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8cab2-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="8cab2-134">IHostAutoEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8cab2-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="8cab2-135">IHostManualEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8cab2-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="8cab2-136">IHostSemaphore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8cab2-136">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="8cab2-137">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8cab2-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
