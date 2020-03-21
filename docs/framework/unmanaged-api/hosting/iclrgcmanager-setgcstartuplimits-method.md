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
ms.openlocfilehash: 645b64c8b536029663c350bdcde9a716a715aab3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178080"
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a><span data-ttu-id="708e0-102">ICLRGCManager::SetGCStartupLimits (Método)</span><span class="sxs-lookup"><span data-stu-id="708e0-102">ICLRGCManager::SetGCStartupLimits Method</span></span>
<span data-ttu-id="708e0-103">Establece el tamaño de un segmento de recolección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="708e0-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="708e0-104">A partir de .NET Framework 4.5, puede establecer el tamaño `DWORD` del segmento y el tamaño de generación máxima 0 en valores mayores que mediante el método [ICLRGCManager2::SetGCStartupLimitsEx.](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)</span><span class="sxs-lookup"><span data-stu-id="708e0-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="708e0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="708e0-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="708e0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="708e0-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="708e0-107">[en] El tamaño especificado de un segmento de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="708e0-107">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="708e0-108">El tamaño mínimo del segmento es de 4 MB.</span><span class="sxs-lookup"><span data-stu-id="708e0-108">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="708e0-109">Los segmentos se pueden aumentar en incrementos de 1 MB o más.</span><span class="sxs-lookup"><span data-stu-id="708e0-109">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="708e0-110">[en] El tamaño máximo especificado para la generación 0.</span><span class="sxs-lookup"><span data-stu-id="708e0-110">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="708e0-111">El tamaño mínimo de generación 0 es de 64 KB.</span><span class="sxs-lookup"><span data-stu-id="708e0-111">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="708e0-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="708e0-112">Return Value</span></span>  
  
|<span data-ttu-id="708e0-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="708e0-113">HRESULT</span></span>|<span data-ttu-id="708e0-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="708e0-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="708e0-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="708e0-115">S_OK</span></span>|<span data-ttu-id="708e0-116">`SetGCStartupLimits`regresó con éxito.</span><span class="sxs-lookup"><span data-stu-id="708e0-116">`SetGCStartupLimits` returned successfully.</span></span>|  
|<span data-ttu-id="708e0-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="708e0-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="708e0-118">Common Language Runtime (CLR) no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="708e0-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="708e0-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="708e0-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="708e0-120">Se adelantó la llamada.</span><span class="sxs-lookup"><span data-stu-id="708e0-120">The call timed out.</span></span>|  
|<span data-ttu-id="708e0-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="708e0-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="708e0-122">El autor de la llamada no es el propietario de la cerradura.</span><span class="sxs-lookup"><span data-stu-id="708e0-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="708e0-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="708e0-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="708e0-124">Un evento se canceló mientras un hilo bloqueado o fibra lo esperaba.</span><span class="sxs-lookup"><span data-stu-id="708e0-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="708e0-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="708e0-125">E_FAIL</span></span>|<span data-ttu-id="708e0-126">Se ha producido un fallo catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="708e0-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="708e0-127">Después de que un método devuelve E_FAIL, CLR ya no se puede usar dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="708e0-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="708e0-128">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="708e0-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="708e0-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="708e0-129">Remarks</span></span>  
 <span data-ttu-id="708e0-130">Los valores `SetGCStartupLimits` que establecen solo se pueden especificar una vez.</span><span class="sxs-lookup"><span data-stu-id="708e0-130">The values that `SetGCStartupLimits` sets can be specified only once.</span></span> <span data-ttu-id="708e0-131">Las llamadas posteriores a `SetGCStartupLimits` se omiten.</span><span class="sxs-lookup"><span data-stu-id="708e0-131">Later calls to `SetGCStartupLimits` are ignored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="708e0-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="708e0-132">Requirements</span></span>  
 <span data-ttu-id="708e0-133">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="708e0-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="708e0-134">**Encabezado:** MScorEE.h</span><span class="sxs-lookup"><span data-stu-id="708e0-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="708e0-135">**Biblioteca:** Incluido como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="708e0-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="708e0-136">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="708e0-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="708e0-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="708e0-137">See also</span></span>

- [<span data-ttu-id="708e0-138">Gestión automática de la memoria</span><span class="sxs-lookup"><span data-stu-id="708e0-138">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="708e0-139">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="708e0-139">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="708e0-140">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="708e0-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="708e0-141">ICLRGCManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="708e0-141">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
