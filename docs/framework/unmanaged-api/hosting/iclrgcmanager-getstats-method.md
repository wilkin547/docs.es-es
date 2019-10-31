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
ms.openlocfilehash: 9e8b65c735028029f4fb44c2640df74ef171d9de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141144"
---
# <a name="iclrgcmanagergetstats-method"></a><span data-ttu-id="79cc1-102">ICLRGCManager::GetStats (Método)</span><span class="sxs-lookup"><span data-stu-id="79cc1-102">ICLRGCManager::GetStats Method</span></span>
<span data-ttu-id="79cc1-103">Obtiene un conjunto de estadísticas actuales sobre el sistema de recolección de elementos no utilizados del Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="79cc1-103">Gets a set of current statistics about the common language runtime's garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79cc1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="79cc1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79cc1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="79cc1-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="79cc1-106">[in, out] Instancia de [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) que contiene las estadísticas solicitadas.</span><span class="sxs-lookup"><span data-stu-id="79cc1-106">[in, out] A [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) instance that contains the requested statistics.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="79cc1-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="79cc1-107">Return Value</span></span>  
  
|<span data-ttu-id="79cc1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="79cc1-108">HRESULT</span></span>|<span data-ttu-id="79cc1-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="79cc1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="79cc1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="79cc1-110">S_OK</span></span>|<span data-ttu-id="79cc1-111">`GetStats` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="79cc1-111">`GetStats` returned successfully.</span></span>|  
|<span data-ttu-id="79cc1-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="79cc1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="79cc1-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="79cc1-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="79cc1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="79cc1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="79cc1-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="79cc1-115">The call timed out.</span></span>|  
|<span data-ttu-id="79cc1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="79cc1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="79cc1-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="79cc1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="79cc1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="79cc1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="79cc1-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="79cc1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="79cc1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="79cc1-120">E_FAIL</span></span>|<span data-ttu-id="79cc1-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="79cc1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="79cc1-122">Una vez que un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="79cc1-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="79cc1-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="79cc1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79cc1-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="79cc1-124">Remarks</span></span>  
 <span data-ttu-id="79cc1-125">CLR calcula y devuelve solo las estadísticas especificadas por el campo `Flags` de `pStats`.</span><span class="sxs-lookup"><span data-stu-id="79cc1-125">The CLR calculates and returns only those statistics that are specified by the `Flags` field of `pStats`.</span></span>  
  
 <span data-ttu-id="79cc1-126">Establezca el campo `Flags` en uno o varios valores de la enumeración [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) para especificar qué estadísticas de la estructura [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) se van a establecer.</span><span class="sxs-lookup"><span data-stu-id="79cc1-126">Set the `Flags` field to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set.</span></span>  
  
 <span data-ttu-id="79cc1-127">A continuación se muestra un ejemplo de uso:</span><span class="sxs-lookup"><span data-stu-id="79cc1-127">An example of the usage is as follows:</span></span>  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="79cc1-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="79cc1-128">Requirements</span></span>  
 <span data-ttu-id="79cc1-129">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79cc1-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79cc1-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="79cc1-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="79cc1-131">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="79cc1-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="79cc1-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79cc1-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79cc1-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="79cc1-133">See also</span></span>

- [<span data-ttu-id="79cc1-134">Administración automática de la memoria</span><span class="sxs-lookup"><span data-stu-id="79cc1-134">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="79cc1-135">COR_GC_STATS (estructura)</span><span class="sxs-lookup"><span data-stu-id="79cc1-135">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="79cc1-136">COR_GC_STAT_TYPES (enumeración)</span><span class="sxs-lookup"><span data-stu-id="79cc1-136">COR_GC_STAT_TYPES Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)
- [<span data-ttu-id="79cc1-137">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="79cc1-137">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="79cc1-138">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="79cc1-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="79cc1-139">ICLRGCManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="79cc1-139">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="79cc1-140">Interfaces de hospedaje de CLR</span><span class="sxs-lookup"><span data-stu-id="79cc1-140">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="79cc1-141">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="79cc1-141">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="79cc1-142">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="79cc1-142">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
