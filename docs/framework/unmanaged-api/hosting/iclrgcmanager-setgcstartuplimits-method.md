---
description: 'Más información sobre: ICLRGCManager:: Setgcstartuplimits ((método)'
title: ICLRGCManager::SetGCStartupLimits (Método)
ms.date: 03/30/2017
api_name:
- ICLRGCManager.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: 1c8d9959-95b5-4131-be4a-556d97774014
topic_type:
- apiref
ms.openlocfilehash: 5614b41cfd7a7938cdb653d879119ddbd9560b9d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789988"
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a><span data-ttu-id="d5076-103">ICLRGCManager::SetGCStartupLimits (Método)</span><span class="sxs-lookup"><span data-stu-id="d5076-103">ICLRGCManager::SetGCStartupLimits Method</span></span>

<span data-ttu-id="d5076-104">Establece el tamaño de un segmento de recolección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="d5076-104">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d5076-105">A partir del .NET Framework 4,5, puede establecer el tamaño del segmento y el tamaño máximo de la generación 0 en valores mayores que mediante `DWORD` el método [iclrgcmanager2 (:: setgcstartuplimitsex (](iclrgcmanager2-setgcstartuplimitsex-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d5076-105">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [ICLRGCManager2::SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5076-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d5076-106">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5076-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d5076-107">Parameters</span></span>  

 `SegmentSize`  
 <span data-ttu-id="d5076-108">de Tamaño especificado de un segmento de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="d5076-108">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="d5076-109">El tamaño mínimo del segmento es 4 MB.</span><span class="sxs-lookup"><span data-stu-id="d5076-109">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="d5076-110">Los segmentos se pueden aumentar en incrementos de 1 MB o más.</span><span class="sxs-lookup"><span data-stu-id="d5076-110">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="d5076-111">de Tamaño máximo especificado para la generación 0.</span><span class="sxs-lookup"><span data-stu-id="d5076-111">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="d5076-112">El tamaño mínimo de la generación 0 es 64 KB.</span><span class="sxs-lookup"><span data-stu-id="d5076-112">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d5076-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d5076-113">Return Value</span></span>  
  
|<span data-ttu-id="d5076-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d5076-114">HRESULT</span></span>|<span data-ttu-id="d5076-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="d5076-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d5076-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="d5076-116">S_OK</span></span>|<span data-ttu-id="d5076-117">`SetGCStartupLimits` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="d5076-117">`SetGCStartupLimits` returned successfully.</span></span>|  
|<span data-ttu-id="d5076-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d5076-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d5076-119">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="d5076-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d5076-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d5076-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d5076-121">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d5076-121">The call timed out.</span></span>|  
|<span data-ttu-id="d5076-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d5076-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d5076-123">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="d5076-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d5076-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d5076-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d5076-125">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="d5076-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d5076-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d5076-126">E_FAIL</span></span>|<span data-ttu-id="d5076-127">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="d5076-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d5076-128">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="d5076-128">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d5076-129">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d5076-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5076-130">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d5076-130">Remarks</span></span>  

 <span data-ttu-id="d5076-131">Los valores que `SetGCStartupLimits` establece solo se pueden especificar una vez.</span><span class="sxs-lookup"><span data-stu-id="d5076-131">The values that `SetGCStartupLimits` sets can be specified only once.</span></span> <span data-ttu-id="d5076-132">Las llamadas posteriores a `SetGCStartupLimits` se omiten.</span><span class="sxs-lookup"><span data-stu-id="d5076-132">Later calls to `SetGCStartupLimits` are ignored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5076-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d5076-133">Requirements</span></span>  

 <span data-ttu-id="d5076-134">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5076-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5076-135">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d5076-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d5076-136">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d5076-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d5076-137">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5076-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5076-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5076-138">See also</span></span>

- [<span data-ttu-id="d5076-139">Administración automática de la memoria</span><span class="sxs-lookup"><span data-stu-id="d5076-139">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="d5076-140">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="d5076-140">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="d5076-141">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d5076-141">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="d5076-142">ICLRGCManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d5076-142">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)
