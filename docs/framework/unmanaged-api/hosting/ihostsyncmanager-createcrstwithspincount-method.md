---
title: "IHostSyncManager::CreateCrstWithSpinCount (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager.CreateCrstWithSpinCount
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager::CreateCrstWithSpinCount
helpviewer_keywords:
- CreateCrstWithSpinCount method [.NET Framework hosting]
- IHostSyncManager::CreateCrstWithSpinCount method [.NET Framework hosting]
ms.assetid: 7280fa8c-3639-4abf-91cb-bc343da742d1
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 31830f97cff1c302ee573b8248eb1d83e696ac48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsyncmanagercreatecrstwithspincount-method"></a><span data-ttu-id="dc997-102">IHostSyncManager::CreateCrstWithSpinCount (Método)</span><span class="sxs-lookup"><span data-stu-id="dc997-102">IHostSyncManager::CreateCrstWithSpinCount Method</span></span>
<span data-ttu-id="dc997-103">Crea un objeto de sección crítica con recuento circular para la sincronización.</span><span class="sxs-lookup"><span data-stu-id="dc997-103">Creates a critical section object with spin count for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc997-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc997-104">Syntax</span></span>  
  
```  
HRESULT CreateCrstWithSpinCount (  
    [in]  DWORD dwSpinCount,  
    [out] IHostCrst** ppCrst  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dc997-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dc997-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="dc997-106">[in] Especifica el número de número para el objeto de sección crítica.</span><span class="sxs-lookup"><span data-stu-id="dc997-106">[in] Specifies the spin count for the critical section object.</span></span>  
  
 `ppCrst`  
 <span data-ttu-id="dc997-107">[out] Un puntero a la dirección de un [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instancia o null si no se pudo crear la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="dc997-107">[out] A pointer to the address of an [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dc997-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="dc997-108">Return Value</span></span>  
  
|<span data-ttu-id="dc997-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dc997-109">HRESULT</span></span>|<span data-ttu-id="dc997-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="dc997-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dc997-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="dc997-111">S_OK</span></span>|<span data-ttu-id="dc997-112">`CreateCrstWithSpinCount`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="dc997-112">`CreateCrstWithSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="dc997-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dc997-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dc997-114">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="dc997-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dc997-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dc997-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dc997-116">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="dc997-116">The call timed out.</span></span>|  
|<span data-ttu-id="dc997-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dc997-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dc997-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="dc997-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dc997-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dc997-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dc997-120">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="dc997-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dc997-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dc997-121">E_FAIL</span></span>|<span data-ttu-id="dc997-122">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="dc997-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dc997-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="dc997-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dc997-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="dc997-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="dc997-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="dc997-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="dc997-126">No había memoria suficiente disponible para crear la sección crítica solicitada.</span><span class="sxs-lookup"><span data-stu-id="dc997-126">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc997-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dc997-127">Remarks</span></span>  
 <span data-ttu-id="dc997-128">Un recuento del número se utiliza únicamente en un sistema de varios procesador.</span><span class="sxs-lookup"><span data-stu-id="dc997-128">A spin count is used only on a multi-processor system.</span></span> <span data-ttu-id="dc997-129">El recuento circular especifica el número de veces que se debe poner en un subproceso que realiza la llamada antes de realizar una operación de espera en un semáforo que está asociado a una sección crítica no está disponible.</span><span class="sxs-lookup"><span data-stu-id="dc997-129">The spin count specifies the number of times a calling thread must spin before it performs a wait operation on a semaphore that is associated with an unavailable critical section.</span></span> <span data-ttu-id="dc997-130">Si la sección crítica deja de estar disponible durante la operación circular, el subproceso que realiza la llamada evita la operación de espera.</span><span class="sxs-lookup"><span data-stu-id="dc997-130">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span> <span data-ttu-id="dc997-131">`CreateCrstWithSpinCount`refleja el Win32 `InitializeCriticalSectionAndSpinCount` función.</span><span class="sxs-lookup"><span data-stu-id="dc997-131">`CreateCrstWithSpinCount` mirrors the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc997-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dc997-132">Requirements</span></span>  
 <span data-ttu-id="dc997-133">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc997-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc997-134">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dc997-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dc997-135">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dc997-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dc997-136">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc997-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc997-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc997-137">See Also</span></span>  
 [<span data-ttu-id="dc997-138">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dc997-138">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="dc997-139">IHostSemaphore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dc997-139">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="dc997-140">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dc997-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
