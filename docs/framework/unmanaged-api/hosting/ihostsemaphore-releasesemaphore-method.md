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
ms.openlocfilehash: aa67aabbe8a7a47a9b3036f508e2f8bb6082c3e0
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803554"
---
# <a name="ihostsemaphorereleasesemaphore-method"></a><span data-ttu-id="4e2b2-102">IHostSemaphore::ReleaseSemaphore (Método)</span><span class="sxs-lookup"><span data-stu-id="4e2b2-102">IHostSemaphore::ReleaseSemaphore Method</span></span>
<span data-ttu-id="4e2b2-103">Aumenta el recuento de la instancia actual de [IHostSemaphore](ihostsemaphore-interface.md) en la cantidad especificada.</span><span class="sxs-lookup"><span data-stu-id="4e2b2-103">Increases the count of the current [IHostSemaphore](ihostsemaphore-interface.md) instance by the specified amount.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e2b2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4e2b2-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleaseSemaphore (  
    [in]  LONG  lReleaseCount,  
    [out] LONG  *lpPreviousCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e2b2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4e2b2-105">Parameters</span></span>  
 `lReleaseCount`  
 <span data-ttu-id="4e2b2-106">de Cantidad en la que se va a aumentar el recuento de la `IHostSemaphore` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="4e2b2-106">[in] The amount by which to increase the count of the current `IHostSemaphore` instance.</span></span> <span data-ttu-id="4e2b2-107">Esta cantidad debe ser mayor que cero.</span><span class="sxs-lookup"><span data-stu-id="4e2b2-107">This amount must be greater than zero.</span></span>  
  
 `lpPreviousCount`  
 <span data-ttu-id="4e2b2-108">enuncia Puntero al recuento anterior, o null si el llamador no requiere el recuento anterior.</span><span class="sxs-lookup"><span data-stu-id="4e2b2-108">[out] A pointer to the previous count, or null if the caller does not require the previous count.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e2b2-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4e2b2-109">Return Value</span></span>  
  
|<span data-ttu-id="4e2b2-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4e2b2-110">HRESULT</span></span>|<span data-ttu-id="4e2b2-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="4e2b2-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4e2b2-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="4e2b2-112">S_OK</span></span>|<span data-ttu-id="4e2b2-113">`ReleaseSemaphore`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="4e2b2-113">`ReleaseSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="4e2b2-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4e2b2-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4e2b2-115">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="4e2b2-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4e2b2-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4e2b2-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4e2b2-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="4e2b2-117">The call timed out.</span></span>|  
|<span data-ttu-id="4e2b2-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4e2b2-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4e2b2-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="4e2b2-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4e2b2-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4e2b2-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4e2b2-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="4e2b2-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4e2b2-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4e2b2-122">E_FAIL</span></span>|<span data-ttu-id="4e2b2-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="4e2b2-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4e2b2-124">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="4e2b2-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4e2b2-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4e2b2-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e2b2-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4e2b2-126">Remarks</span></span>  
 <span data-ttu-id="4e2b2-127">El CLR normalmente llama `ReleaseSemaphore` a para notificar al host que ha terminado de usar un recurso, pasando un valor de 1 para el `lReleaseCount` parámetro.</span><span class="sxs-lookup"><span data-stu-id="4e2b2-127">The CLR typically calls `ReleaseSemaphore` to notify the host that it has finished using a resource, passing a value of 1 for the `lReleaseCount` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e2b2-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4e2b2-128">Requirements</span></span>  
 <span data-ttu-id="4e2b2-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e2b2-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e2b2-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4e2b2-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4e2b2-131">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4e2b2-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4e2b2-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e2b2-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e2b2-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4e2b2-133">See also</span></span>

- [<span data-ttu-id="4e2b2-134">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e2b2-134">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="4e2b2-135">IHostAutoEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e2b2-135">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="4e2b2-136">IHostManualEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e2b2-136">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="4e2b2-137">IHostSemaphore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e2b2-137">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="4e2b2-138">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e2b2-138">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
