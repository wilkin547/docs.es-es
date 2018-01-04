---
title: "ICLRGCManager::Collect (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager.Collect
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager::Collect
helpviewer_keywords:
- ICLRGCManager::Collect method [.NET Framework hosting]
- Collect method, ICLRGCManager interface [.NET Framework hosting]
ms.assetid: 0c6cbbea-c27c-4695-bda3-17c1910d8ddb
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e2fdb66008a6bbe315f39a0d3fae293219d6b6c2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrgcmanagercollect-method"></a><span data-ttu-id="92860-102">ICLRGCManager::Collect (Método)</span><span class="sxs-lookup"><span data-stu-id="92860-102">ICLRGCManager::Collect Method</span></span>
<span data-ttu-id="92860-103">Fuerza una recolección de elementos no utilizados para la generación especificada.</span><span class="sxs-lookup"><span data-stu-id="92860-103">Forces a garbage collection for the specified generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92860-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="92860-104">Syntax</span></span>  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="92860-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="92860-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="92860-106">[in] La generación para recopilar.</span><span class="sxs-lookup"><span data-stu-id="92860-106">[in] The generation to collect.</span></span> <span data-ttu-id="92860-107">Un valor de -1 fuerza una colección de todas las generaciones.</span><span class="sxs-lookup"><span data-stu-id="92860-107">A value of -1 forces a collection of all generations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="92860-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="92860-108">Return Value</span></span>  
  
|<span data-ttu-id="92860-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="92860-109">HRESULT</span></span>|<span data-ttu-id="92860-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="92860-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="92860-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="92860-111">S_OK</span></span>|<span data-ttu-id="92860-112">`Collect`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="92860-112">`Collect` returned successfully.</span></span>|  
|<span data-ttu-id="92860-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="92860-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="92860-114">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="92860-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="92860-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="92860-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="92860-116">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="92860-116">The call timed out.</span></span>|  
|<span data-ttu-id="92860-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="92860-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="92860-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="92860-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="92860-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="92860-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="92860-120">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="92860-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="92860-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="92860-121">E_FAIL</span></span>|<span data-ttu-id="92860-122">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="92860-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="92860-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="92860-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="92860-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="92860-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92860-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="92860-125">Remarks</span></span>  
 <span data-ttu-id="92860-126">El `Collect` método fuerza el recolector de elementos no utilizados de CLR para realizar una recolección, independientemente de su estado actual.</span><span class="sxs-lookup"><span data-stu-id="92860-126">The `Collect` method forces the CLR's garbage collector to perform a collection regardless of its current state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92860-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="92860-127">Requirements</span></span>  
 <span data-ttu-id="92860-128">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92860-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92860-129">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="92860-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="92860-130">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="92860-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="92860-131">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92860-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92860-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="92860-132">See Also</span></span>  
 [<span data-ttu-id="92860-133">Administración automática de la memoria</span><span class="sxs-lookup"><span data-stu-id="92860-133">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="92860-134">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="92860-134">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)  
 [<span data-ttu-id="92860-135">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="92860-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="92860-136">ICLRGCManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="92860-136">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 [<span data-ttu-id="92860-137">Interfaces de hospedaje de CLR</span><span class="sxs-lookup"><span data-stu-id="92860-137">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="92860-138">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="92860-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="92860-139">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="92860-139">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
