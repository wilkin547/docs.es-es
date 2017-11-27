---
title: "IHostSyncManager::CreateSemaphore (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager.CreateSemaphore
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager::CreateSemaphore
helpviewer_keywords:
- CreateSemaphore method [.NET Framework hosting]
- IHostSyncManager::CreateSemaphore method [.NET Framework hosting]
ms.assetid: 37679e94-5ff9-4173-8fa5-457febeb89bf
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7c7e33e4f178a4fd51ae27912959d0e4edf30ecb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsyncmanagercreatesemaphore-method"></a><span data-ttu-id="8868e-102">IHostSyncManager::CreateSemaphore (Método)</span><span class="sxs-lookup"><span data-stu-id="8868e-102">IHostSyncManager::CreateSemaphore Method</span></span>
<span data-ttu-id="8868e-103">Crea un [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) objeto de common language runtime (CLR) que se usará como un semáforo para los eventos de espera.</span><span class="sxs-lookup"><span data-stu-id="8868e-103">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the common language runtime (CLR) to use as a semaphore for wait events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8868e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8868e-104">Syntax</span></span>  
  
```  
HRESULT CreateSemaphore (  
    [in]  DWORD dwInitial,  
    [in]  DWORD dwMax,  
    [out] IHostSemaphore **ppSemaphore  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8868e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8868e-105">Parameters</span></span>  
 `dwInitial`  
 <span data-ttu-id="8868e-106">[in] El recuento inicial de `ppSemaphore`.</span><span class="sxs-lookup"><span data-stu-id="8868e-106">[in] The initial count for `ppSemaphore`.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="8868e-107">[in] El número máximo para `ppSemaphore`.</span><span class="sxs-lookup"><span data-stu-id="8868e-107">[in] The maximum count for `ppSemaphore`.</span></span>  
  
 `ppSemaphore`  
 <span data-ttu-id="8868e-108">[out] Un puntero a la dirección de un `IHostSemaphore` de instancia o null si no se pudo crear el semáforo.</span><span class="sxs-lookup"><span data-stu-id="8868e-108">[out] A pointer to the address of an `IHostSemaphore` instance, or null if the semaphore could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8868e-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8868e-109">Return Value</span></span>  
  
|<span data-ttu-id="8868e-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8868e-110">HRESULT</span></span>|<span data-ttu-id="8868e-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="8868e-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8868e-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="8868e-112">S_OK</span></span>|<span data-ttu-id="8868e-113">`CreateSemaphore`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="8868e-113">`CreateSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="8868e-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8868e-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8868e-115">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="8868e-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8868e-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8868e-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8868e-117">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="8868e-117">The call timed out.</span></span>|  
|<span data-ttu-id="8868e-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8868e-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8868e-119">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="8868e-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8868e-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8868e-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8868e-121">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="8868e-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8868e-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8868e-122">E_FAIL</span></span>|<span data-ttu-id="8868e-123">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="8868e-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8868e-124">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="8868e-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8868e-125">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8868e-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8868e-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="8868e-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="8868e-127">No había memoria suficiente disponible para crear el objeto de evento solicitado.</span><span class="sxs-lookup"><span data-stu-id="8868e-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8868e-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8868e-128">Remarks</span></span>  
 <span data-ttu-id="8868e-129">`CreateSemaphore`refleja la función de Win32 que tiene el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="8868e-129">`CreateSemaphore` mirrors the Win32 function that has the same name.</span></span> <span data-ttu-id="8868e-130">El `dwInitial` y `dwMax` parámetros utilizan la misma semántica para el recuento del semáforo como Win32 `lInitialCount` y `lMaximumCount` parámetros, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="8868e-130">The `dwInitial` and `dwMax` parameters use the same semantics for the semaphore count as the Win32 `lInitialCount` and `lMaximumCount` parameters, respectively.</span></span> <span data-ttu-id="8868e-131">`dwInitial`debe estar entre cero y `dwMax`, ambos inclusive.</span><span class="sxs-lookup"><span data-stu-id="8868e-131">`dwInitial` must be between zero and `dwMax`, inclusive.</span></span> <span data-ttu-id="8868e-132">`dwMax`debe ser mayor que cero.</span><span class="sxs-lookup"><span data-stu-id="8868e-132">`dwMax` must be greater than zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8868e-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8868e-133">Requirements</span></span>  
 <span data-ttu-id="8868e-134">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8868e-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8868e-135">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8868e-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8868e-136">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8868e-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8868e-137">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8868e-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8868e-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="8868e-138">See Also</span></span>  
 [<span data-ttu-id="8868e-139">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8868e-139">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="8868e-140">IHostSemaphore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8868e-140">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="8868e-141">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8868e-141">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
