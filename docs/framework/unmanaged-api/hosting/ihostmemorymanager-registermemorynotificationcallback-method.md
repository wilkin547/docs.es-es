---
title: IHostMemoryManager::RegisterMemoryNotificationCallback (Método)
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.RegisterMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback
helpviewer_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback method [.NET Framework hosting]
- RegisterMemoryNotificationCallback method [.NET Framework hosting]
ms.assetid: 65d301f6-4dbb-4b5f-8eff-82540e2b6465
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 34701642a9e76ec52141e00fe9dde92878faccd2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945435"
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a><span data-ttu-id="da134-102">IHostMemoryManager::RegisterMemoryNotificationCallback (Método)</span><span class="sxs-lookup"><span data-stu-id="da134-102">IHostMemoryManager::RegisterMemoryNotificationCallback Method</span></span>
<span data-ttu-id="da134-103">Registra un puntero a una función de devolución de llamada que invoca el host para notificar a la Common Language Runtime (CLR) de la carga de memoria actual en el equipo.</span><span class="sxs-lookup"><span data-stu-id="da134-103">Registers a pointer to a callback function that the host invokes to notify the common language runtime (CLR) of the current memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da134-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="da134-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da134-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="da134-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="da134-106">de Puntero de interfaz a una instancia de [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) implementada por CLR.</span><span class="sxs-lookup"><span data-stu-id="da134-106">[in] An interface pointer to an [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) instance that is implemented by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="da134-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="da134-107">Return Value</span></span>  
  
|<span data-ttu-id="da134-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="da134-108">HRESULT</span></span>|<span data-ttu-id="da134-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="da134-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="da134-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="da134-110">S_OK</span></span>|<span data-ttu-id="da134-111">`RegisterMemoryNotificationCallback`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="da134-111">`RegisterMemoryNotificationCallback` returned successfully.</span></span>|  
|<span data-ttu-id="da134-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="da134-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="da134-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="da134-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="da134-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="da134-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="da134-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="da134-115">The call timed out.</span></span>|  
|<span data-ttu-id="da134-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="da134-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="da134-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="da134-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="da134-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="da134-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="da134-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="da134-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="da134-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="da134-120">E_FAIL</span></span>|<span data-ttu-id="da134-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="da134-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="da134-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="da134-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="da134-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="da134-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da134-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="da134-124">Remarks</span></span>  
 <span data-ttu-id="da134-125">Dado que `ICLRMemoryNotificationCallback` la interfaz define solo un método ([ICLRMemoryNotificationCallback:: OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)), y `pCallback` dado que es un puntero `ICLRMemoryNotificationCallback` a una instancia proporcionada por CLR, el registro es eficaz para la propia función de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="da134-125">Because the `ICLRMemoryNotificationCallback` interface defines only one method ([ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)), and because `pCallback` is a pointer to an `ICLRMemoryNotificationCallback` instance provided by the CLR, the registration is effectively for the callback function itself.</span></span> <span data-ttu-id="da134-126">El host invoca `OnMemoryNotification` para informar de las condiciones de presión de memoria, en lugar de `CreateMemoryResourceNotification` utilizar la función estándar de Win32.</span><span class="sxs-lookup"><span data-stu-id="da134-126">The host invokes `OnMemoryNotification` to report memory pressure conditions, rather than using the standard Win32 `CreateMemoryResourceNotification` function.</span></span> <span data-ttu-id="da134-127">Para obtener más información, vea la documentación de la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="da134-127">For more information, see the Windows Platform documentation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="da134-128">Las llamadas `OnMemoryNotification` a no se bloquean nunca.</span><span class="sxs-lookup"><span data-stu-id="da134-128">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="da134-129">Siempre devuelven inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="da134-129">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da134-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="da134-130">Requirements</span></span>  
 <span data-ttu-id="da134-131">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da134-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da134-132">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="da134-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="da134-133">**Biblioteca** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="da134-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="da134-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da134-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da134-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="da134-135">See also</span></span>

- [<span data-ttu-id="da134-136">ICLRMemoryNotificationCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="da134-136">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
- [<span data-ttu-id="da134-137">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="da134-137">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
