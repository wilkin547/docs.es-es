---
title: "ICLRTask::GetMemStats (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.GetMemStats
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::GetMemStats
helpviewer_keywords:
- ICLRTask::GetMemStats method [.NET Framework hosting]
- GetMemStats method [.NET Framework hosting]
ms.assetid: c9e07657-1682-4c30-a336-f8658ff1a125
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 11537989765d721830c33cb137d1814327b02e14
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskgetmemstats-method"></a><span data-ttu-id="9b636-102">ICLRTask::GetMemStats (Método)</span><span class="sxs-lookup"><span data-stu-id="9b636-102">ICLRTask::GetMemStats Method</span></span>
<span data-ttu-id="9b636-103">Obtiene información de uso de memoria estadísticas relacionadas con la tarea que actual [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instancia representa.</span><span class="sxs-lookup"><span data-stu-id="9b636-103">Gets statistical memory usage information related to the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b636-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9b636-104">Syntax</span></span>  
  
```  
HRESULT GetMemStats (  
    [out] COR_GC_THREAD_STATS *pMemUsage  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9b636-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9b636-105">Parameters</span></span>  
 `pMemUsage`  
 <span data-ttu-id="9b636-106">[out] Un puntero a un [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) instancia que contiene detalles sobre el uso de memoria de la tarea, incluido el número de bytes asignados.</span><span class="sxs-lookup"><span data-stu-id="9b636-106">[out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) instance that contains details about the memory usage of the task, including the number of bytes allocated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b636-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9b636-107">Return Value</span></span>  
  
|<span data-ttu-id="9b636-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9b636-108">HRESULT</span></span>|<span data-ttu-id="9b636-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b636-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9b636-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9b636-110">S_OK</span></span>|<span data-ttu-id="9b636-111">`GetMemStats`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="9b636-111">`GetMemStats` returned successfully.</span></span>|  
|<span data-ttu-id="9b636-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9b636-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9b636-113">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="9b636-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9b636-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9b636-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9b636-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="9b636-115">The call timed out.</span></span>|  
|<span data-ttu-id="9b636-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9b636-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9b636-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="9b636-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9b636-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9b636-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9b636-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="9b636-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9b636-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9b636-120">E_FAIL</span></span>|<span data-ttu-id="9b636-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="9b636-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9b636-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="9b636-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9b636-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9b636-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9b636-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9b636-124">Requirements</span></span>  
 <span data-ttu-id="9b636-125">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b636-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b636-126">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9b636-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9b636-127">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9b636-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9b636-128">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b636-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b636-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b636-129">See Also</span></span>  
 [<span data-ttu-id="9b636-130">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9b636-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="9b636-131">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9b636-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="9b636-132">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9b636-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="9b636-133">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9b636-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
