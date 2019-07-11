---
title: IHostSemaphore::Wait (Método)
ms.date: 03/30/2017
api_name:
- IHostSemaphore.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore::Wait
helpviewer_keywords:
- IHostSemaphore::Wait method [.NET Framework hosting]
- Wait method, IHostSemaphore interface [.NET Framework hosting]
ms.assetid: 0da962a3-ce55-44dd-ab7a-14ad7105af4a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1d578fa0f8e80ae2c8fbada9e383bcd849ff2f8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753610"
---
# <a name="ihostsemaphorewait-method"></a><span data-ttu-id="48895-102">IHostSemaphore::Wait (Método)</span><span class="sxs-lookup"><span data-stu-id="48895-102">IHostSemaphore::Wait Method</span></span>
<span data-ttu-id="48895-103">Hace que el actual [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instancia espere hasta que es propietario o la cantidad de tiempo especificada.</span><span class="sxs-lookup"><span data-stu-id="48895-103">Causes the current [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instance to wait until it is owned or the specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48895-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="48895-104">Syntax</span></span>  
  
```cpp  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48895-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="48895-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="48895-106">[in] El número de milisegundos que transcurrirán antes de volver, si el actual `IHostSemaphore` no es propiedad de instancia.</span><span class="sxs-lookup"><span data-stu-id="48895-106">[in] The number of milliseconds to wait before returning, if the current `IHostSemaphore` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="48895-107">[in] Uno de los [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valores, que especifican qué medidas debe tomar el host si esta operación se bloquea.</span><span class="sxs-lookup"><span data-stu-id="48895-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, specifying what action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48895-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="48895-108">Return Value</span></span>  
  
|<span data-ttu-id="48895-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="48895-109">HRESULT</span></span>|<span data-ttu-id="48895-110">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="48895-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="48895-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="48895-111">S_OK</span></span>|<span data-ttu-id="48895-112">`Wait` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="48895-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="48895-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="48895-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="48895-114">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="48895-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="48895-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="48895-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="48895-116">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="48895-116">The call timed out.</span></span>|  
|<span data-ttu-id="48895-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="48895-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="48895-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="48895-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="48895-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="48895-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="48895-120">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="48895-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="48895-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="48895-121">E_FAIL</span></span>|<span data-ttu-id="48895-122">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="48895-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="48895-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="48895-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="48895-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="48895-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="48895-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="48895-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="48895-126">El host detectó un interbloqueo durante el intervalo de espera y eligió actual `IHostSemaphore` instancia como sujeto del interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="48895-126">The host detected a deadlock during the wait interval, and chose the current `IHostSemaphore` instance as a deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="48895-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="48895-127">Requirements</span></span>  
 <span data-ttu-id="48895-128">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48895-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48895-129">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="48895-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="48895-130">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="48895-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="48895-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48895-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48895-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="48895-132">See also</span></span>

- [<span data-ttu-id="48895-133">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="48895-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="48895-134">IHostAutoEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="48895-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="48895-135">IHostManualEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="48895-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="48895-136">IHostSemaphore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="48895-136">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="48895-137">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="48895-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
