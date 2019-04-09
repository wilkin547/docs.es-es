---
title: IHostSemaphore::ReleaseSemaphore (Método)
ms.date: 03/30/2017
api_name:
- IHostSemaphore.ReleaseSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore::ReleaseSemaphore
helpviewer_keywords:
- ReleaseSemaphore method [.NET Framework hosting]
- IHostSemaphore::ReleaseSemaphore method [.NET Framework hosting]
ms.assetid: a343d197-979a-4ac6-ab8c-cb8a05f3120e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24ec56345a5b48540d2451769f739a236a85e47b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100618"
---
# <a name="ihostsemaphorereleasesemaphore-method"></a><span data-ttu-id="109a0-102">IHostSemaphore::ReleaseSemaphore (Método)</span><span class="sxs-lookup"><span data-stu-id="109a0-102">IHostSemaphore::ReleaseSemaphore Method</span></span>
<span data-ttu-id="109a0-103">Aumenta el recuento de actual [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instancia en la cantidad especificada.</span><span class="sxs-lookup"><span data-stu-id="109a0-103">Increases the count of the current [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instance by the specified amount.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="109a0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="109a0-104">Syntax</span></span>  
  
```  
HRESULT ReleaseSemaphore (  
    [in]  LONG  lReleaseCount,  
    [out] LONG  *lpPreviousCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="109a0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="109a0-105">Parameters</span></span>  
 `lReleaseCount`  
 <span data-ttu-id="109a0-106">[in] Cantidad por la que se va a aumentar el número del elemento actual `IHostSemaphore` instancia.</span><span class="sxs-lookup"><span data-stu-id="109a0-106">[in] The amount by which to increase the count of the current `IHostSemaphore` instance.</span></span> <span data-ttu-id="109a0-107">Esta cantidad debe ser mayor que cero.</span><span class="sxs-lookup"><span data-stu-id="109a0-107">This amount must be greater than zero.</span></span>  
  
 `lpPreviousCount`  
 <span data-ttu-id="109a0-108">[out] Un puntero al recuento anterior, o null si el llamador no requiere el recuento anterior.</span><span class="sxs-lookup"><span data-stu-id="109a0-108">[out] A pointer to the previous count, or null if the caller does not require the previous count.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="109a0-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="109a0-109">Return Value</span></span>  
  
|<span data-ttu-id="109a0-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="109a0-110">HRESULT</span></span>|<span data-ttu-id="109a0-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="109a0-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="109a0-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="109a0-112">S_OK</span></span>|`ReleaseSemaphore` <span data-ttu-id="109a0-113">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="109a0-113">returned successfully.</span></span>|  
|<span data-ttu-id="109a0-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="109a0-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="109a0-115">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="109a0-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="109a0-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="109a0-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="109a0-117">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="109a0-117">The call timed out.</span></span>|  
|<span data-ttu-id="109a0-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="109a0-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="109a0-119">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="109a0-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="109a0-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="109a0-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="109a0-121">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="109a0-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="109a0-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="109a0-122">E_FAIL</span></span>|<span data-ttu-id="109a0-123">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="109a0-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="109a0-124">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="109a0-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="109a0-125">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="109a0-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="109a0-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="109a0-126">Remarks</span></span>  
 <span data-ttu-id="109a0-127">CLR llama normalmente `ReleaseSemaphore` para notificar al host que ha terminado de usar un recurso, pasando el valor 1 para el `lReleaseCount` parámetro.</span><span class="sxs-lookup"><span data-stu-id="109a0-127">The CLR typically calls `ReleaseSemaphore` to notify the host that it has finished using a resource, passing a value of 1 for the `lReleaseCount` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="109a0-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="109a0-128">Requirements</span></span>  
 <span data-ttu-id="109a0-129">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="109a0-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="109a0-130">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="109a0-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="109a0-131">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="109a0-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="109a0-132">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="109a0-132">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="109a0-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="109a0-133">See also</span></span>

- [<span data-ttu-id="109a0-134">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="109a0-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="109a0-135">IHostAutoEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="109a0-135">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="109a0-136">IHostManualEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="109a0-136">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="109a0-137">IHostSemaphore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="109a0-137">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="109a0-138">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="109a0-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
