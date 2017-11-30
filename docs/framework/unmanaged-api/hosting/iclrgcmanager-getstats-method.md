---
title: "ICLRGCManager::GetStats (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager.GetStats
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager::GetStats
helpviewer_keywords:
- GetStats method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::GetStats method [.NET Framework hosting]
ms.assetid: ce259d1d-cd81-4490-a7a1-0d0ea0804872
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 06d52bd0348e4667f1e3ec43a371021922f12ded
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrgcmanagergetstats-method"></a><span data-ttu-id="3791f-102">ICLRGCManager::GetStats (Método)</span><span class="sxs-lookup"><span data-stu-id="3791f-102">ICLRGCManager::GetStats Method</span></span>
<span data-ttu-id="3791f-103">Obtiene un conjunto de estadísticas actuales sobre el sistema de recopilación de elementos no utilizados de common language runtime.</span><span class="sxs-lookup"><span data-stu-id="3791f-103">Gets a set of current statistics about the common language runtime's garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3791f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3791f-104">Syntax</span></span>  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3791f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3791f-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="3791f-106">[entrada, salida] A [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) instancia que contiene las estadísticas solicitadas.</span><span class="sxs-lookup"><span data-stu-id="3791f-106">[in, out] A [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) instance that contains the requested statistics.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3791f-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3791f-107">Return Value</span></span>  
  
|<span data-ttu-id="3791f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3791f-108">HRESULT</span></span>|<span data-ttu-id="3791f-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="3791f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3791f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3791f-110">S_OK</span></span>|<span data-ttu-id="3791f-111">`GetStats`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3791f-111">`GetStats` returned successfully.</span></span>|  
|<span data-ttu-id="3791f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3791f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3791f-113">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="3791f-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3791f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3791f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3791f-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="3791f-115">The call timed out.</span></span>|  
|<span data-ttu-id="3791f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3791f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3791f-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="3791f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3791f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3791f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3791f-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="3791f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3791f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3791f-120">E_FAIL</span></span>|<span data-ttu-id="3791f-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="3791f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3791f-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="3791f-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3791f-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3791f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3791f-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3791f-124">Remarks</span></span>  
 <span data-ttu-id="3791f-125">El CLR calcula y devuelve las estadísticas especificadas por el `Flags` campo de `pStats`.</span><span class="sxs-lookup"><span data-stu-id="3791f-125">The CLR calculates and returns only those statistics that are specified by the `Flags` field of `pStats`.</span></span>  
  
 <span data-ttu-id="3791f-126">Establecer el `Flags` campo a uno o más valores de la [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeración para especificar qué estadísticas en el [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) estructura que se va a establecer.</span><span class="sxs-lookup"><span data-stu-id="3791f-126">Set the `Flags` field to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set.</span></span>  
  
 <span data-ttu-id="3791f-127">Un ejemplo del uso es como sigue:</span><span class="sxs-lookup"><span data-stu-id="3791f-127">An example of the usage is as follows:</span></span>  
  
```  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="3791f-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3791f-128">Requirements</span></span>  
 <span data-ttu-id="3791f-129">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3791f-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3791f-130">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3791f-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3791f-131">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3791f-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3791f-132">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3791f-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3791f-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="3791f-133">See Also</span></span>  
 [<span data-ttu-id="3791f-134">Administración automática de la memoria</span><span class="sxs-lookup"><span data-stu-id="3791f-134">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="3791f-135">COR_GC_STATS (estructura)</span><span class="sxs-lookup"><span data-stu-id="3791f-135">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [<span data-ttu-id="3791f-136">COR_GC_STAT_TYPES (enumeración)</span><span class="sxs-lookup"><span data-stu-id="3791f-136">COR_GC_STAT_TYPES Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)  
 [<span data-ttu-id="3791f-137">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="3791f-137">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)  
 [<span data-ttu-id="3791f-138">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3791f-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="3791f-139">ICLRGCManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3791f-139">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 [<span data-ttu-id="3791f-140">Interfaces de hospedaje de CLR</span><span class="sxs-lookup"><span data-stu-id="3791f-140">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="3791f-141">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="3791f-141">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="3791f-142">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="3791f-142">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
