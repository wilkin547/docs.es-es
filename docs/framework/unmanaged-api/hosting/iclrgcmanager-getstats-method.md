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
ms.openlocfilehash: 9300f67e75d40f041a4fba52f6742741ec9f91de
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187355"
---
# <a name="iclrgcmanagergetstats-method"></a><span data-ttu-id="cecd4-102">ICLRGCManager::GetStats (Método)</span><span class="sxs-lookup"><span data-stu-id="cecd4-102">ICLRGCManager::GetStats Method</span></span>
<span data-ttu-id="cecd4-103">Obtiene un conjunto de estadísticas actuales sobre el sistema de recopilación de elementos no utilizados de common language runtime.</span><span class="sxs-lookup"><span data-stu-id="cecd4-103">Gets a set of current statistics about the common language runtime's garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cecd4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cecd4-104">Syntax</span></span>  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cecd4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cecd4-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="cecd4-106">[in, out] Un [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) instancia que contiene las estadísticas solicitadas.</span><span class="sxs-lookup"><span data-stu-id="cecd4-106">[in, out] A [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) instance that contains the requested statistics.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cecd4-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cecd4-107">Return Value</span></span>  
  
|<span data-ttu-id="cecd4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cecd4-108">HRESULT</span></span>|<span data-ttu-id="cecd4-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="cecd4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cecd4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="cecd4-110">S_OK</span></span>|`GetStats` <span data-ttu-id="cecd4-111">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="cecd4-111">returned successfully.</span></span>|  
|<span data-ttu-id="cecd4-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cecd4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cecd4-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="cecd4-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cecd4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cecd4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cecd4-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="cecd4-115">The call timed out.</span></span>|  
|<span data-ttu-id="cecd4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cecd4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cecd4-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="cecd4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cecd4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cecd4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cecd4-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="cecd4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cecd4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cecd4-120">E_FAIL</span></span>|<span data-ttu-id="cecd4-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="cecd4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cecd4-122">Después de un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="cecd4-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cecd4-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="cecd4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cecd4-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cecd4-124">Remarks</span></span>  
 <span data-ttu-id="cecd4-125">El CLR calcula y devuelve solo las estadísticas que se especifican mediante el `Flags` campo `pStats`.</span><span class="sxs-lookup"><span data-stu-id="cecd4-125">The CLR calculates and returns only those statistics that are specified by the `Flags` field of `pStats`.</span></span>  
  
 <span data-ttu-id="cecd4-126">Establecer el `Flags` campo a uno o más valores de la [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeración para especificar qué estadísticas en el [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) estructura que se va a establecer.</span><span class="sxs-lookup"><span data-stu-id="cecd4-126">Set the `Flags` field to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set.</span></span>  
  
 <span data-ttu-id="cecd4-127">Un ejemplo de uso es como sigue:</span><span class="sxs-lookup"><span data-stu-id="cecd4-127">An example of the usage is as follows:</span></span>  
  
```  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="cecd4-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cecd4-128">Requirements</span></span>  
 <span data-ttu-id="cecd4-129">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cecd4-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cecd4-130">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cecd4-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cecd4-131">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cecd4-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="cecd4-132">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="cecd4-132">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cecd4-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="cecd4-133">See also</span></span>

- [<span data-ttu-id="cecd4-134">Automatic Memory Management</span><span class="sxs-lookup"><span data-stu-id="cecd4-134">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="cecd4-135">COR_GC_STATS (Estructura)</span><span class="sxs-lookup"><span data-stu-id="cecd4-135">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="cecd4-136">COR_GC_STAT_TYPES (enumeración)</span><span class="sxs-lookup"><span data-stu-id="cecd4-136">COR_GC_STAT_TYPES Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)
- [<span data-ttu-id="cecd4-137">recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="cecd4-137">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
- [<span data-ttu-id="cecd4-138">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cecd4-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="cecd4-139">ICLRGCManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cecd4-139">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="cecd4-140">Interfaces de hospedaje de CLR</span><span class="sxs-lookup"><span data-stu-id="cecd4-140">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="cecd4-141">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="cecd4-141">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="cecd4-142">Hospedaje</span><span class="sxs-lookup"><span data-stu-id="cecd4-142">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
