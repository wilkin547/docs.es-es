---
description: 'Más información sobre: ICLRGCManager:: Getstats ((método)'
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
ms.openlocfilehash: 94b20fb313f06d73f1e7fafd1f46fefb0da3fe95
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790027"
---
# <a name="iclrgcmanagergetstats-method"></a><span data-ttu-id="e6174-103">ICLRGCManager::GetStats (Método)</span><span class="sxs-lookup"><span data-stu-id="e6174-103">ICLRGCManager::GetStats Method</span></span>

<span data-ttu-id="e6174-104">Obtiene un conjunto de estadísticas actuales sobre el sistema de recolección de elementos no utilizados del Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="e6174-104">Gets a set of current statistics about the common language runtime's garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6174-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6174-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6174-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e6174-106">Parameters</span></span>  

 `pStats`  
 <span data-ttu-id="e6174-107">[in, out] [COR_GC_STATS](cor-gc-stats-structure.md) instancia de que contiene las estadísticas solicitadas.</span><span class="sxs-lookup"><span data-stu-id="e6174-107">[in, out] A [COR_GC_STATS](cor-gc-stats-structure.md) instance that contains the requested statistics.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6174-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e6174-108">Return Value</span></span>  
  
|<span data-ttu-id="e6174-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e6174-109">HRESULT</span></span>|<span data-ttu-id="e6174-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6174-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e6174-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e6174-111">S_OK</span></span>|<span data-ttu-id="e6174-112">`GetStats` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="e6174-112">`GetStats` returned successfully.</span></span>|  
|<span data-ttu-id="e6174-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e6174-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e6174-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="e6174-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e6174-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e6174-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e6174-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="e6174-116">The call timed out.</span></span>|  
|<span data-ttu-id="e6174-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e6174-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e6174-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="e6174-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e6174-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e6174-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e6174-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="e6174-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e6174-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e6174-121">E_FAIL</span></span>|<span data-ttu-id="e6174-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="e6174-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e6174-123">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="e6174-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e6174-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e6174-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6174-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e6174-125">Remarks</span></span>  

 <span data-ttu-id="e6174-126">CLR calcula y devuelve solo las estadísticas especificadas por el `Flags` campo de `pStats` .</span><span class="sxs-lookup"><span data-stu-id="e6174-126">The CLR calculates and returns only those statistics that are specified by the `Flags` field of `pStats`.</span></span>  
  
 <span data-ttu-id="e6174-127">Establezca el `Flags` campo en uno o varios valores de la enumeración [COR_GC_STAT_TYPES](cor-gc-stat-types-enumeration.md) para especificar qué estadísticas de la estructura de [COR_GC_STATS](cor-gc-stats-structure.md) se van a establecer.</span><span class="sxs-lookup"><span data-stu-id="e6174-127">Set the `Flags` field to one or more values of the [COR_GC_STAT_TYPES](cor-gc-stat-types-enumeration.md) enumeration to specify which statistics in the [COR_GC_STATS](cor-gc-stats-structure.md) structure are to be set.</span></span>  
  
 <span data-ttu-id="e6174-128">A continuación se muestra un ejemplo de uso:</span><span class="sxs-lookup"><span data-stu-id="e6174-128">An example of the usage is as follows:</span></span>  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="e6174-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e6174-129">Requirements</span></span>  

 <span data-ttu-id="e6174-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6174-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6174-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e6174-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e6174-132">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e6174-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6174-133">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6174-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6174-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6174-134">See also</span></span>

- [<span data-ttu-id="e6174-135">Administración automática de la memoria</span><span class="sxs-lookup"><span data-stu-id="e6174-135">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="e6174-136">COR_GC_STATS (Estructura)</span><span class="sxs-lookup"><span data-stu-id="e6174-136">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="e6174-137">COR_GC_STAT_TYPES (enumeración)</span><span class="sxs-lookup"><span data-stu-id="e6174-137">COR_GC_STAT_TYPES Enumeration</span></span>](cor-gc-stat-types-enumeration.md)
- [<span data-ttu-id="e6174-138">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="e6174-138">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="e6174-139">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6174-139">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="e6174-140">ICLRGCManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6174-140">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)
- [<span data-ttu-id="e6174-141">Interfaces de hospedaje de CLR</span><span class="sxs-lookup"><span data-stu-id="e6174-141">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="e6174-142">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="e6174-142">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="e6174-143">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="e6174-143">Hosting</span></span>](index.md)
