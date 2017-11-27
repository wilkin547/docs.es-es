---
title: "ICLRGCManager::SetGCStartupLimits (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager.SetGCStartupLimits
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager::SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: 1c8d9959-95b5-4131-be4a-556d97774014
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1fd0c31fd6f988d4ee36bfe140b95ec258d4214e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a><span data-ttu-id="1a28c-102">ICLRGCManager::SetGCStartupLimits (Método)</span><span class="sxs-lookup"><span data-stu-id="1a28c-102">ICLRGCManager::SetGCStartupLimits Method</span></span>
<span data-ttu-id="1a28c-103">Establece el tamaño de un segmento de la colección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="1a28c-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1a28c-104">A partir de la [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], puede establecer un tamaño de segmento y mayor que los valores de tamaño máximo de generación 0 a `DWORD` mediante el uso de la [iclrgcmanager2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="1a28c-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a28c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1a28c-105">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,   
    [in] DWORD MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1a28c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1a28c-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="1a28c-107">[in] El tamaño especificado de un segmento de la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="1a28c-107">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="1a28c-108">El tamaño mínimo de segmento es 4 MB.</span><span class="sxs-lookup"><span data-stu-id="1a28c-108">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="1a28c-109">Segmentos pueden aumentar en incrementos de 1 MB o superior.</span><span class="sxs-lookup"><span data-stu-id="1a28c-109">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="1a28c-110">[in] El tamaño máximo especificado para la generación 0.</span><span class="sxs-lookup"><span data-stu-id="1a28c-110">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="1a28c-111">El tamaño mínimo de generación 0 es 64 KB.</span><span class="sxs-lookup"><span data-stu-id="1a28c-111">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1a28c-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1a28c-112">Return Value</span></span>  
  
|<span data-ttu-id="1a28c-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1a28c-113">HRESULT</span></span>|<span data-ttu-id="1a28c-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="1a28c-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1a28c-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="1a28c-115">S_OK</span></span>|<span data-ttu-id="1a28c-116">`SetGCStartupLimits`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="1a28c-116">`SetGCStartupLimits` returned successfully.</span></span>|  
|<span data-ttu-id="1a28c-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1a28c-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1a28c-118">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="1a28c-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1a28c-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1a28c-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1a28c-120">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="1a28c-120">The call timed out.</span></span>|  
|<span data-ttu-id="1a28c-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1a28c-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1a28c-122">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="1a28c-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1a28c-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1a28c-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1a28c-124">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="1a28c-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1a28c-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1a28c-125">E_FAIL</span></span>|<span data-ttu-id="1a28c-126">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="1a28c-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1a28c-127">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="1a28c-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1a28c-128">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1a28c-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a28c-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1a28c-129">Remarks</span></span>  
 <span data-ttu-id="1a28c-130">Los valores que `SetGCStartupLimits` conjuntos pueden especificarse una sola vez.</span><span class="sxs-lookup"><span data-stu-id="1a28c-130">The values that `SetGCStartupLimits` sets can be specified only once.</span></span> <span data-ttu-id="1a28c-131">Llamadas posteriores a `SetGCStartupLimits` se omiten.</span><span class="sxs-lookup"><span data-stu-id="1a28c-131">Later calls to `SetGCStartupLimits` are ignored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a28c-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1a28c-132">Requirements</span></span>  
 <span data-ttu-id="1a28c-133">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a28c-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a28c-134">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1a28c-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1a28c-135">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1a28c-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1a28c-136">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a28c-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a28c-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a28c-137">See Also</span></span>  
 [<span data-ttu-id="1a28c-138">Administración automática de la memoria</span><span class="sxs-lookup"><span data-stu-id="1a28c-138">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="1a28c-139">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="1a28c-139">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)  
 [<span data-ttu-id="1a28c-140">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1a28c-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="1a28c-141">ICLRGCManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1a28c-141">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
