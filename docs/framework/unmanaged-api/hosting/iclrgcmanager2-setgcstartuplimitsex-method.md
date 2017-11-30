---
title: "ICLRGCManager2::SetGCStartupLimitsEx (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager2.SetGCStartupLimitsEx
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager2::SetCLRGCStartupLimitsEx
helpviewer_keywords:
- ICLRGCManager2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 6c3a08a9-5d65-48d4-8bbf-2a86ed7d356a
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 73f5678008354b312964f0cb32d768d36a641fd9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a><span data-ttu-id="b5467-102">ICLRGCManager2::SetGCStartupLimitsEx (Método)</span><span class="sxs-lookup"><span data-stu-id="b5467-102">ICLRGCManager2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="b5467-103">Establece el tamaño de un segmento de la colección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b5467-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5467-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b5467-104">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,   
    [in] SIZE_T MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b5467-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b5467-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="b5467-106">[in] El tamaño especificado de un segmento de la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b5467-106">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="b5467-107">El tamaño mínimo de segmento es 4 MB.</span><span class="sxs-lookup"><span data-stu-id="b5467-107">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="b5467-108">Segmentos pueden aumentar en incrementos de 1 MB o superior.</span><span class="sxs-lookup"><span data-stu-id="b5467-108">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="b5467-109">[in] El tamaño máximo especificado para la generación 0.</span><span class="sxs-lookup"><span data-stu-id="b5467-109">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="b5467-110">El tamaño mínimo de generación 0 es 64 KB.</span><span class="sxs-lookup"><span data-stu-id="b5467-110">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5467-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b5467-111">Return Value</span></span>  
  
|<span data-ttu-id="b5467-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b5467-112">HRESULT</span></span>|<span data-ttu-id="b5467-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5467-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b5467-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="b5467-114">S_OK</span></span>|<span data-ttu-id="b5467-115">`SetGCStartupLimitsEx`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b5467-115">`SetGCStartupLimitsEx` returned successfully.</span></span>|  
|<span data-ttu-id="b5467-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b5467-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b5467-117">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="b5467-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b5467-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b5467-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b5467-119">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="b5467-119">The call timed out.</span></span>|  
|<span data-ttu-id="b5467-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b5467-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b5467-121">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="b5467-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b5467-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b5467-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b5467-123">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="b5467-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b5467-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b5467-124">E_FAIL</span></span>|<span data-ttu-id="b5467-125">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="b5467-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b5467-126">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="b5467-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b5467-127">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b5467-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5467-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b5467-128">Remarks</span></span>  
 <span data-ttu-id="b5467-129">Los valores que `SetGCStartupLimitsEx` se pueden especificar conjuntos sólo antes de que se inicie el host.</span><span class="sxs-lookup"><span data-stu-id="b5467-129">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="b5467-130">Llamadas posteriores a `SetGCStartupLimitsEx` se omiten.</span><span class="sxs-lookup"><span data-stu-id="b5467-130">Later calls to `SetGCStartupLimitsEx` are ignored.</span></span>  
  
 <span data-ttu-id="b5467-131">Para establecer un parámetro sin afectar a los demás, especifique 0 (cero) para el parámetro que no desee cambiar.</span><span class="sxs-lookup"><span data-stu-id="b5467-131">To set either parameter without affecting the other, specify 0 (zero) for the parameter you don't want to change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5467-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b5467-132">Requirements</span></span>  
 <span data-ttu-id="b5467-133">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5467-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5467-134">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b5467-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b5467-135">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b5467-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b5467-136">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5467-136">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5467-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5467-137">See Also</span></span>  
 [<span data-ttu-id="b5467-138">Administración automática de la memoria</span><span class="sxs-lookup"><span data-stu-id="b5467-138">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="b5467-139">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="b5467-139">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)  
 [<span data-ttu-id="b5467-140">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b5467-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="b5467-141">ICLRGCManager2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b5467-141">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)
