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
ms.openlocfilehash: 0e977133d722edc7d090d07cd117ee282a8d29cb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753582"
---
# <a name="ihostsemaphorereleasesemaphore-method"></a><span data-ttu-id="6ec39-102">IHostSemaphore::ReleaseSemaphore (Método)</span><span class="sxs-lookup"><span data-stu-id="6ec39-102">IHostSemaphore::ReleaseSemaphore Method</span></span>
<span data-ttu-id="6ec39-103">Aumenta el recuento de actual [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instancia en la cantidad especificada.</span><span class="sxs-lookup"><span data-stu-id="6ec39-103">Increases the count of the current [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instance by the specified amount.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ec39-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6ec39-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleaseSemaphore (  
    [in]  LONG  lReleaseCount,  
    [out] LONG  *lpPreviousCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ec39-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6ec39-105">Parameters</span></span>  
 `lReleaseCount`  
 <span data-ttu-id="6ec39-106">[in] Cantidad por la que se va a aumentar el número del elemento actual `IHostSemaphore` instancia.</span><span class="sxs-lookup"><span data-stu-id="6ec39-106">[in] The amount by which to increase the count of the current `IHostSemaphore` instance.</span></span> <span data-ttu-id="6ec39-107">Esta cantidad debe ser mayor que cero.</span><span class="sxs-lookup"><span data-stu-id="6ec39-107">This amount must be greater than zero.</span></span>  
  
 `lpPreviousCount`  
 <span data-ttu-id="6ec39-108">[out] Un puntero al recuento anterior, o null si el llamador no requiere el recuento anterior.</span><span class="sxs-lookup"><span data-stu-id="6ec39-108">[out] A pointer to the previous count, or null if the caller does not require the previous count.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6ec39-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6ec39-109">Return Value</span></span>  
  
|<span data-ttu-id="6ec39-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6ec39-110">HRESULT</span></span>|<span data-ttu-id="6ec39-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6ec39-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6ec39-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="6ec39-112">S_OK</span></span>|<span data-ttu-id="6ec39-113">`ReleaseSemaphore` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="6ec39-113">`ReleaseSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="6ec39-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6ec39-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6ec39-115">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="6ec39-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6ec39-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6ec39-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6ec39-117">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="6ec39-117">The call timed out.</span></span>|  
|<span data-ttu-id="6ec39-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6ec39-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6ec39-119">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="6ec39-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6ec39-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6ec39-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6ec39-121">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="6ec39-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6ec39-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6ec39-122">E_FAIL</span></span>|<span data-ttu-id="6ec39-123">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="6ec39-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6ec39-124">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="6ec39-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6ec39-125">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6ec39-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ec39-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6ec39-126">Remarks</span></span>  
 <span data-ttu-id="6ec39-127">CLR llama normalmente `ReleaseSemaphore` para notificar al host que ha terminado de usar un recurso, pasando el valor 1 para el `lReleaseCount` parámetro.</span><span class="sxs-lookup"><span data-stu-id="6ec39-127">The CLR typically calls `ReleaseSemaphore` to notify the host that it has finished using a resource, passing a value of 1 for the `lReleaseCount` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ec39-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6ec39-128">Requirements</span></span>  
 <span data-ttu-id="6ec39-129">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ec39-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ec39-130">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6ec39-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6ec39-131">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6ec39-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6ec39-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ec39-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ec39-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ec39-133">See also</span></span>

- [<span data-ttu-id="6ec39-134">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6ec39-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="6ec39-135">IHostAutoEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6ec39-135">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="6ec39-136">IHostManualEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6ec39-136">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="6ec39-137">IHostSemaphore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6ec39-137">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="6ec39-138">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6ec39-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
