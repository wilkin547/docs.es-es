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
ms.openlocfilehash: 70fe8b132f03925c41b6bc7aae8e60fea1b05202
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678303"
---
# <a name="iclrgcmanagergetstats-method"></a><span data-ttu-id="e9d5e-102">ICLRGCManager::GetStats (Método)</span><span class="sxs-lookup"><span data-stu-id="e9d5e-102">ICLRGCManager::GetStats Method</span></span>

<span data-ttu-id="e9d5e-103">Obtiene un conjunto de estadísticas actuales sobre el sistema de recolección de elementos no utilizados del Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="e9d5e-103">Gets a set of current statistics about the common language runtime's garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9d5e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9d5e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9d5e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e9d5e-105">Parameters</span></span>  

 `pStats`  
 <span data-ttu-id="e9d5e-106">[in, out] [COR_GC_STATS](cor-gc-stats-structure.md) instancia de que contiene las estadísticas solicitadas.</span><span class="sxs-lookup"><span data-stu-id="e9d5e-106">[in, out] A [COR_GC_STATS](cor-gc-stats-structure.md) instance that contains the requested statistics.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e9d5e-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e9d5e-107">Return Value</span></span>  
  
|<span data-ttu-id="e9d5e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e9d5e-108">HRESULT</span></span>|<span data-ttu-id="e9d5e-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="e9d5e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e9d5e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e9d5e-110">S_OK</span></span>|<span data-ttu-id="e9d5e-111">`GetStats` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="e9d5e-111">`GetStats` returned successfully.</span></span>|  
|<span data-ttu-id="e9d5e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e9d5e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e9d5e-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="e9d5e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e9d5e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e9d5e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e9d5e-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="e9d5e-115">The call timed out.</span></span>|  
|<span data-ttu-id="e9d5e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e9d5e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e9d5e-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="e9d5e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e9d5e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e9d5e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e9d5e-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="e9d5e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e9d5e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e9d5e-120">E_FAIL</span></span>|<span data-ttu-id="e9d5e-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="e9d5e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e9d5e-122">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="e9d5e-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e9d5e-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e9d5e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9d5e-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e9d5e-124">Remarks</span></span>  

 <span data-ttu-id="e9d5e-125">CLR calcula y devuelve solo las estadísticas especificadas por el `Flags` campo de `pStats` .</span><span class="sxs-lookup"><span data-stu-id="e9d5e-125">The CLR calculates and returns only those statistics that are specified by the `Flags` field of `pStats`.</span></span>  
  
 <span data-ttu-id="e9d5e-126">Establezca el `Flags` campo en uno o varios valores de la enumeración [COR_GC_STAT_TYPES](cor-gc-stat-types-enumeration.md) para especificar qué estadísticas de la estructura de [COR_GC_STATS](cor-gc-stats-structure.md) se van a establecer.</span><span class="sxs-lookup"><span data-stu-id="e9d5e-126">Set the `Flags` field to one or more values of the [COR_GC_STAT_TYPES](cor-gc-stat-types-enumeration.md) enumeration to specify which statistics in the [COR_GC_STATS](cor-gc-stats-structure.md) structure are to be set.</span></span>  
  
 <span data-ttu-id="e9d5e-127">A continuación se muestra un ejemplo de uso:</span><span class="sxs-lookup"><span data-stu-id="e9d5e-127">An example of the usage is as follows:</span></span>  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="e9d5e-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e9d5e-128">Requirements</span></span>  

 <span data-ttu-id="e9d5e-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9d5e-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9d5e-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e9d5e-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e9d5e-131">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e9d5e-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9d5e-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9d5e-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9d5e-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e9d5e-133">See also</span></span>

- [<span data-ttu-id="e9d5e-134">Administración automática de la memoria</span><span class="sxs-lookup"><span data-stu-id="e9d5e-134">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="e9d5e-135">COR_GC_STATS (Estructura)</span><span class="sxs-lookup"><span data-stu-id="e9d5e-135">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="e9d5e-136">COR_GC_STAT_TYPES (enumeración)</span><span class="sxs-lookup"><span data-stu-id="e9d5e-136">COR_GC_STAT_TYPES Enumeration</span></span>](cor-gc-stat-types-enumeration.md)
- [<span data-ttu-id="e9d5e-137">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="e9d5e-137">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="e9d5e-138">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e9d5e-138">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="e9d5e-139">ICLRGCManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e9d5e-139">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)
- [<span data-ttu-id="e9d5e-140">Interfaces de hospedaje de CLR</span><span class="sxs-lookup"><span data-stu-id="e9d5e-140">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="e9d5e-141">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="e9d5e-141">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="e9d5e-142">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="e9d5e-142">Hosting</span></span>](index.md)
