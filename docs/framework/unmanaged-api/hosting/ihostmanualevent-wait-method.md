---
title: IHostManualEvent::Wait (Método)
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Wait
helpviewer_keywords:
- IHostManualEvent::Wait method [.NET Framework hosting]
- Wait method, IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 1fbb7d8b-8a23-4c2b-8376-1a70cd2d6030
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a70d5daf6626a26842d91ff6a35d0abf26d79ad1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492574"
---
# <a name="ihostmanualeventwait-method"></a><span data-ttu-id="5fc49-102">IHostManualEvent::Wait (Método)</span><span class="sxs-lookup"><span data-stu-id="5fc49-102">IHostManualEvent::Wait Method</span></span>
<span data-ttu-id="5fc49-103">Hace que el actual [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instancia espere hasta que sea propiedad o un período de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="5fc49-103">Causes the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to wait until it is owned, or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fc49-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5fc49-104">Syntax</span></span>  
  
```  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fc49-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5fc49-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="5fc49-106">[in] El número de milisegundos que transcurrirán antes de volver, si el actual `IHostManualEvent` no es propiedad de instancia.</span><span class="sxs-lookup"><span data-stu-id="5fc49-106">[in] The number of milliseconds to wait before returning, if the current `IHostManualEvent` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="5fc49-107">[in] Uno de los [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valores, que indica la acción que debe realizar el host si esta operación se bloquea.</span><span class="sxs-lookup"><span data-stu-id="5fc49-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5fc49-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5fc49-108">Return Value</span></span>  
  
|<span data-ttu-id="5fc49-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5fc49-109">HRESULT</span></span>|<span data-ttu-id="5fc49-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="5fc49-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5fc49-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5fc49-111">S_OK</span></span>|<span data-ttu-id="5fc49-112">`Wait` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="5fc49-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="5fc49-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5fc49-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5fc49-114">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="5fc49-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5fc49-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5fc49-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5fc49-116">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="5fc49-116">The call timed out.</span></span>|  
|<span data-ttu-id="5fc49-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5fc49-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5fc49-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="5fc49-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5fc49-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5fc49-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5fc49-120">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="5fc49-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5fc49-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5fc49-121">E_FAIL</span></span>|<span data-ttu-id="5fc49-122">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="5fc49-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5fc49-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="5fc49-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5fc49-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5fc49-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5fc49-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="5fc49-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="5fc49-126">El host detectó un interbloqueo durante el intervalo de espera y eligió actual `IHostManualEvent` instancia como sujeto del interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="5fc49-126">The host detected a deadlock during the wait interval, and chose the current `IHostManualEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5fc49-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5fc49-127">Requirements</span></span>  
 <span data-ttu-id="5fc49-128">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fc49-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fc49-129">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5fc49-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5fc49-130">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5fc49-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5fc49-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fc49-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fc49-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="5fc49-132">See also</span></span>
- [<span data-ttu-id="5fc49-133">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5fc49-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="5fc49-134">IHostAutoEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5fc49-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="5fc49-135">IHostManualEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5fc49-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="5fc49-136">IHostSemaphore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5fc49-136">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="5fc49-137">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5fc49-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
