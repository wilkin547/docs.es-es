---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 29311f00f5ac4b61380b57cdd9fda07ec7de1b23
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966199"
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a><span data-ttu-id="a4d3c-102">ICLRGCManager::SetGCStartupLimits (Método)</span><span class="sxs-lookup"><span data-stu-id="a4d3c-102">ICLRGCManager::SetGCStartupLimits Method</span></span>
<span data-ttu-id="a4d3c-103">Establece el tamaño de un segmento de recolección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a4d3c-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a4d3c-104">A partir del .NET Framework 4,5, puede establecer el tamaño del segmento y el tamaño máximo de la generación 0 `DWORD` en valores mayores que mediante el método [iclrgcmanager2 (:: setgcstartuplimitsex (](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a4d3c-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4d3c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a4d3c-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,   
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4d3c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a4d3c-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="a4d3c-107">de Tamaño especificado de un segmento de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a4d3c-107">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="a4d3c-108">El tamaño mínimo del segmento es 4 MB.</span><span class="sxs-lookup"><span data-stu-id="a4d3c-108">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="a4d3c-109">Los segmentos se pueden aumentar en incrementos de 1 MB o más.</span><span class="sxs-lookup"><span data-stu-id="a4d3c-109">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="a4d3c-110">de Tamaño máximo especificado para la generación 0.</span><span class="sxs-lookup"><span data-stu-id="a4d3c-110">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="a4d3c-111">El tamaño mínimo de la generación 0 es 64 KB.</span><span class="sxs-lookup"><span data-stu-id="a4d3c-111">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a4d3c-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a4d3c-112">Return Value</span></span>  
  
|<span data-ttu-id="a4d3c-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a4d3c-113">HRESULT</span></span>|<span data-ttu-id="a4d3c-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a4d3c-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a4d3c-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="a4d3c-115">S_OK</span></span>|<span data-ttu-id="a4d3c-116">`SetGCStartupLimits`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a4d3c-116">`SetGCStartupLimits` returned successfully.</span></span>|  
|<span data-ttu-id="a4d3c-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a4d3c-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a4d3c-118">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="a4d3c-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a4d3c-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a4d3c-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a4d3c-120">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a4d3c-120">The call timed out.</span></span>|  
|<span data-ttu-id="a4d3c-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a4d3c-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a4d3c-122">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a4d3c-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a4d3c-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a4d3c-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a4d3c-124">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="a4d3c-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a4d3c-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a4d3c-125">E_FAIL</span></span>|<span data-ttu-id="a4d3c-126">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="a4d3c-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a4d3c-127">Una vez que un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a4d3c-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a4d3c-128">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a4d3c-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4d3c-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a4d3c-129">Remarks</span></span>  
 <span data-ttu-id="a4d3c-130">Los valores que `SetGCStartupLimits` establece solo se pueden especificar una vez.</span><span class="sxs-lookup"><span data-stu-id="a4d3c-130">The values that `SetGCStartupLimits` sets can be specified only once.</span></span> <span data-ttu-id="a4d3c-131">Las llamadas posteriores `SetGCStartupLimits` a se omiten.</span><span class="sxs-lookup"><span data-stu-id="a4d3c-131">Later calls to `SetGCStartupLimits` are ignored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4d3c-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a4d3c-132">Requirements</span></span>  
 <span data-ttu-id="a4d3c-133">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4d3c-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4d3c-134">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a4d3c-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a4d3c-135">**Biblioteca** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a4d3c-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a4d3c-136">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4d3c-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4d3c-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4d3c-137">See also</span></span>

- [<span data-ttu-id="a4d3c-138">Administración automática de la memoria</span><span class="sxs-lookup"><span data-stu-id="a4d3c-138">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="a4d3c-139">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="a4d3c-139">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="a4d3c-140">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a4d3c-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="a4d3c-141">ICLRGCManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a4d3c-141">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
