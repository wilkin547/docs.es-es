---
title: IHostAutoEvent::Wait (Método)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7921f0361d7369cddf14dd1ab477529d1bbac481
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439366"
---
# <a name="ihostautoeventwait-method"></a><span data-ttu-id="87d51-102">IHostAutoEvent::Wait (Método)</span><span class="sxs-lookup"><span data-stu-id="87d51-102">IHostAutoEvent::Wait Method</span></span>
<span data-ttu-id="87d51-103">Hace que el actual [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instancia espere hasta que encuentre un propietario o una cantidad especificada de tiempo determinado.</span><span class="sxs-lookup"><span data-stu-id="87d51-103">Causes the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to wait until it is owned or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87d51-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="87d51-104">Syntax</span></span>  
  
```  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="87d51-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="87d51-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="87d51-106">[in] El número de milisegundos actual `IHostAutoEvent` instancia debe esperar antes de volver, si ningún subproceso o fibra toma la propiedad.</span><span class="sxs-lookup"><span data-stu-id="87d51-106">[in] The number of milliseconds the current `IHostAutoEvent` instance should wait before returning, if no thread or fiber takes ownership.</span></span>  
  
 `option`  
 <span data-ttu-id="87d51-107">[in] Uno de los [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valores, que especifican la acción que debe realizar el host si esta operación se bloquea.</span><span class="sxs-lookup"><span data-stu-id="87d51-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, specifying the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87d51-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="87d51-108">Return Value</span></span>  
  
|<span data-ttu-id="87d51-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="87d51-109">HRESULT</span></span>|<span data-ttu-id="87d51-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="87d51-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="87d51-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="87d51-111">S_OK</span></span>|<span data-ttu-id="87d51-112">`Wait` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="87d51-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="87d51-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="87d51-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="87d51-114">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="87d51-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="87d51-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="87d51-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="87d51-116">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="87d51-116">The call timed out.</span></span>|  
|<span data-ttu-id="87d51-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="87d51-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="87d51-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="87d51-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="87d51-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="87d51-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="87d51-120">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="87d51-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="87d51-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="87d51-121">E_FAIL</span></span>|<span data-ttu-id="87d51-122">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="87d51-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="87d51-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="87d51-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="87d51-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="87d51-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="87d51-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="87d51-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="87d51-126">El host detectó un interbloqueo durante el intervalo de espera y eligió el evento representado por el actual `IHostAutoEvent` instancia como sujeto del interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="87d51-126">The host detected a deadlock during the wait interval, and chose the event represented by the current `IHostAutoEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="87d51-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="87d51-127">Requirements</span></span>  
 <span data-ttu-id="87d51-128">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87d51-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87d51-129">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="87d51-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="87d51-130">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="87d51-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87d51-131">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87d51-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87d51-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="87d51-132">See Also</span></span>  
 [<span data-ttu-id="87d51-133">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="87d51-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="87d51-134">IHostAutoEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="87d51-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="87d51-135">IHostManualEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="87d51-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="87d51-136">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="87d51-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
