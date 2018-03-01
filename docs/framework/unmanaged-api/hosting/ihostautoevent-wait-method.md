---
title: "IHostAutoEvent::Wait (Método)"
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
- IHostAutoEvent.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent::Wait
helpviewer_keywords:
- Wait method, IHostAutoEvent interface [.NET Framework hosting]
- IHostAutoEvent::Wait method [.NET Framework hosting]
ms.assetid: 535d51c5-9112-401b-8c36-85f35d7ee609
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e4646e0bd04d69e7fe0125740c9c6e0c1b014071
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostautoeventwait-method"></a><span data-ttu-id="bce7c-102">IHostAutoEvent::Wait (Método)</span><span class="sxs-lookup"><span data-stu-id="bce7c-102">IHostAutoEvent::Wait Method</span></span>
<span data-ttu-id="bce7c-103">Hace que el actual [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instancia espere hasta que encuentre un propietario o una cantidad especificada de tiempo determinado.</span><span class="sxs-lookup"><span data-stu-id="bce7c-103">Causes the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to wait until it is owned or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bce7c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bce7c-104">Syntax</span></span>  
  
```  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bce7c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bce7c-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="bce7c-106">[in] El número de milisegundos actual `IHostAutoEvent` instancia debe esperar antes de volver, si ningún subproceso o fibra toma la propiedad.</span><span class="sxs-lookup"><span data-stu-id="bce7c-106">[in] The number of milliseconds the current `IHostAutoEvent` instance should wait before returning, if no thread or fiber takes ownership.</span></span>  
  
 `option`  
 <span data-ttu-id="bce7c-107">[in] Uno de los [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valores, que especifican la acción que debe realizar el host si esta operación se bloquea.</span><span class="sxs-lookup"><span data-stu-id="bce7c-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, specifying the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bce7c-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bce7c-108">Return Value</span></span>  
  
|<span data-ttu-id="bce7c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bce7c-109">HRESULT</span></span>|<span data-ttu-id="bce7c-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="bce7c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bce7c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="bce7c-111">S_OK</span></span>|<span data-ttu-id="bce7c-112">`Wait`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="bce7c-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="bce7c-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bce7c-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bce7c-114">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="bce7c-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bce7c-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bce7c-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bce7c-116">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="bce7c-116">The call timed out.</span></span>|  
|<span data-ttu-id="bce7c-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bce7c-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bce7c-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="bce7c-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bce7c-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bce7c-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bce7c-120">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="bce7c-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bce7c-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bce7c-121">E_FAIL</span></span>|<span data-ttu-id="bce7c-122">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="bce7c-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bce7c-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="bce7c-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bce7c-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="bce7c-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="bce7c-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="bce7c-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="bce7c-126">El host detectó un interbloqueo durante el intervalo de espera y eligió el evento representado por el actual `IHostAutoEvent` instancia como sujeto del interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="bce7c-126">The host detected a deadlock during the wait interval, and chose the event represented by the current `IHostAutoEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bce7c-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bce7c-127">Requirements</span></span>  
 <span data-ttu-id="bce7c-128">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bce7c-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bce7c-129">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bce7c-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bce7c-130">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bce7c-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bce7c-131">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bce7c-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bce7c-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="bce7c-132">See Also</span></span>  
 [<span data-ttu-id="bce7c-133">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bce7c-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="bce7c-134">IHostAutoEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bce7c-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="bce7c-135">IHostManualEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bce7c-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="bce7c-136">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bce7c-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
