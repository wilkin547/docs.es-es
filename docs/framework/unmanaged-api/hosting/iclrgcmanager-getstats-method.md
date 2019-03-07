---
title: ICLRGCManager::GetStats (Método)
ms.date: 03/30/2017
api_name:
- ICLRGCManager.GetStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::GetStats
helpviewer_keywords:
- GetStats method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::GetStats method [.NET Framework hosting]
ms.assetid: ce259d1d-cd81-4490-a7a1-0d0ea0804872
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3e92707e7b24709d64915e29823196bb0f827175
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485245"
---
# <a name="iclrgcmanagergetstats-method"></a><span data-ttu-id="14d32-102">ICLRGCManager::GetStats (Método)</span><span class="sxs-lookup"><span data-stu-id="14d32-102">ICLRGCManager::GetStats Method</span></span>
<span data-ttu-id="14d32-103">Obtiene un conjunto de estadísticas actuales sobre el sistema de recopilación de elementos no utilizados de common language runtime.</span><span class="sxs-lookup"><span data-stu-id="14d32-103">Gets a set of current statistics about the common language runtime's garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14d32-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="14d32-104">Syntax</span></span>  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14d32-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="14d32-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="14d32-106">[in, out] Un [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) instancia que contiene las estadísticas solicitadas.</span><span class="sxs-lookup"><span data-stu-id="14d32-106">[in, out] A [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) instance that contains the requested statistics.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="14d32-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="14d32-107">Return Value</span></span>  
  
|<span data-ttu-id="14d32-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="14d32-108">HRESULT</span></span>|<span data-ttu-id="14d32-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="14d32-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="14d32-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="14d32-110">S_OK</span></span>|<span data-ttu-id="14d32-111">`GetStats` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="14d32-111">`GetStats` returned successfully.</span></span>|  
|<span data-ttu-id="14d32-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="14d32-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="14d32-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="14d32-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="14d32-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="14d32-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="14d32-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="14d32-115">The call timed out.</span></span>|  
|<span data-ttu-id="14d32-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="14d32-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="14d32-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="14d32-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="14d32-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="14d32-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="14d32-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="14d32-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="14d32-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="14d32-120">E_FAIL</span></span>|<span data-ttu-id="14d32-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="14d32-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="14d32-122">Después de un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="14d32-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="14d32-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="14d32-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14d32-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="14d32-124">Remarks</span></span>  
 <span data-ttu-id="14d32-125">El CLR calcula y devuelve solo las estadísticas que se especifican mediante el `Flags` campo `pStats`.</span><span class="sxs-lookup"><span data-stu-id="14d32-125">The CLR calculates and returns only those statistics that are specified by the `Flags` field of `pStats`.</span></span>  
  
 <span data-ttu-id="14d32-126">Establecer el `Flags` campo a uno o más valores de la [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeración para especificar qué estadísticas en el [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) estructura que se va a establecer.</span><span class="sxs-lookup"><span data-stu-id="14d32-126">Set the `Flags` field to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set.</span></span>  
  
 <span data-ttu-id="14d32-127">Un ejemplo de uso es como sigue:</span><span class="sxs-lookup"><span data-stu-id="14d32-127">An example of the usage is as follows:</span></span>  
  
```  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="14d32-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="14d32-128">Requirements</span></span>  
 <span data-ttu-id="14d32-129">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14d32-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14d32-130">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="14d32-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="14d32-131">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="14d32-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="14d32-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14d32-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14d32-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="14d32-133">See also</span></span>
- [<span data-ttu-id="14d32-134">Administración automática de la memoria</span><span class="sxs-lookup"><span data-stu-id="14d32-134">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="14d32-135">COR_GC_STATS (estructura)</span><span class="sxs-lookup"><span data-stu-id="14d32-135">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="14d32-136">COR_GC_STAT_TYPES (enumeración)</span><span class="sxs-lookup"><span data-stu-id="14d32-136">COR_GC_STAT_TYPES Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)
- [<span data-ttu-id="14d32-137">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="14d32-137">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
- [<span data-ttu-id="14d32-138">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="14d32-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="14d32-139">ICLRGCManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="14d32-139">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="14d32-140">Interfaces de hospedaje de CLR</span><span class="sxs-lookup"><span data-stu-id="14d32-140">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="14d32-141">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="14d32-141">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="14d32-142">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="14d32-142">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
