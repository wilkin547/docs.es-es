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
ms.openlocfilehash: 33a92365e7765befe669439eabefac607232ff15
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139470"
---
# <a name="ihostsemaphorereleasesemaphore-method"></a><span data-ttu-id="2235a-102">IHostSemaphore::ReleaseSemaphore (Método)</span><span class="sxs-lookup"><span data-stu-id="2235a-102">IHostSemaphore::ReleaseSemaphore Method</span></span>
<span data-ttu-id="2235a-103">Aumenta el recuento de la instancia actual de [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) en la cantidad especificada.</span><span class="sxs-lookup"><span data-stu-id="2235a-103">Increases the count of the current [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instance by the specified amount.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2235a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2235a-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleaseSemaphore (  
    [in]  LONG  lReleaseCount,  
    [out] LONG  *lpPreviousCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2235a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2235a-105">Parameters</span></span>  
 `lReleaseCount`  
 <span data-ttu-id="2235a-106">de Cantidad que se va a aumentar el número de la instancia de `IHostSemaphore` actual.</span><span class="sxs-lookup"><span data-stu-id="2235a-106">[in] The amount by which to increase the count of the current `IHostSemaphore` instance.</span></span> <span data-ttu-id="2235a-107">Esta cantidad debe ser mayor que cero.</span><span class="sxs-lookup"><span data-stu-id="2235a-107">This amount must be greater than zero.</span></span>  
  
 `lpPreviousCount`  
 <span data-ttu-id="2235a-108">enuncia Puntero al recuento anterior, o null si el llamador no requiere el recuento anterior.</span><span class="sxs-lookup"><span data-stu-id="2235a-108">[out] A pointer to the previous count, or null if the caller does not require the previous count.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2235a-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2235a-109">Return Value</span></span>  
  
|<span data-ttu-id="2235a-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2235a-110">HRESULT</span></span>|<span data-ttu-id="2235a-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="2235a-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2235a-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="2235a-112">S_OK</span></span>|<span data-ttu-id="2235a-113">`ReleaseSemaphore` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="2235a-113">`ReleaseSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="2235a-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2235a-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2235a-115">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="2235a-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2235a-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2235a-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2235a-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2235a-117">The call timed out.</span></span>|  
|<span data-ttu-id="2235a-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2235a-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2235a-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="2235a-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2235a-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2235a-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2235a-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="2235a-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2235a-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2235a-122">E_FAIL</span></span>|<span data-ttu-id="2235a-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="2235a-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2235a-124">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="2235a-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2235a-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2235a-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2235a-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2235a-126">Remarks</span></span>  
 <span data-ttu-id="2235a-127">CLR normalmente llama a `ReleaseSemaphore` para notificar al host que ha terminado de usar un recurso, pasando un valor de 1 para el parámetro `lReleaseCount`.</span><span class="sxs-lookup"><span data-stu-id="2235a-127">The CLR typically calls `ReleaseSemaphore` to notify the host that it has finished using a resource, passing a value of 1 for the `lReleaseCount` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2235a-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2235a-128">Requirements</span></span>  
 <span data-ttu-id="2235a-129">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2235a-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2235a-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2235a-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2235a-131">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2235a-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2235a-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2235a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2235a-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="2235a-133">See also</span></span>

- [<span data-ttu-id="2235a-134">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2235a-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="2235a-135">IHostAutoEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2235a-135">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="2235a-136">IHostManualEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2235a-136">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="2235a-137">IHostSemaphore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2235a-137">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="2235a-138">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2235a-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
