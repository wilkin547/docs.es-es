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
ms.openlocfilehash: 8e5a0af2d2f3db5b1d44def3af067bc1c3a9e1aa
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485296"
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a><span data-ttu-id="452ff-102">IHostMemoryManager::RegisterMemoryNotificationCallback (Método)</span><span class="sxs-lookup"><span data-stu-id="452ff-102">IHostMemoryManager::RegisterMemoryNotificationCallback Method</span></span>
<span data-ttu-id="452ff-103">Registra un puntero a una función de devolución de llamada que el host invoca para notificar a common language runtime (CLR) de la carga de memoria actual en el equipo.</span><span class="sxs-lookup"><span data-stu-id="452ff-103">Registers a pointer to a callback function that the host invokes to notify the common language runtime (CLR) of the current memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="452ff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="452ff-104">Syntax</span></span>  
  
```  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="452ff-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="452ff-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="452ff-106">[in] Un puntero de interfaz a un [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) instancia que está implementado por CLR.</span><span class="sxs-lookup"><span data-stu-id="452ff-106">[in] An interface pointer to an [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) instance that is implemented by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="452ff-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="452ff-107">Return Value</span></span>  
  
|<span data-ttu-id="452ff-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="452ff-108">HRESULT</span></span>|<span data-ttu-id="452ff-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="452ff-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="452ff-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="452ff-110">S_OK</span></span>|<span data-ttu-id="452ff-111">`RegisterMemoryNotificationCallback` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="452ff-111">`RegisterMemoryNotificationCallback` returned successfully.</span></span>|  
|<span data-ttu-id="452ff-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="452ff-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="452ff-113">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="452ff-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="452ff-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="452ff-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="452ff-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="452ff-115">The call timed out.</span></span>|  
|<span data-ttu-id="452ff-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="452ff-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="452ff-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="452ff-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="452ff-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="452ff-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="452ff-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="452ff-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="452ff-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="452ff-120">E_FAIL</span></span>|<span data-ttu-id="452ff-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="452ff-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="452ff-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="452ff-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="452ff-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="452ff-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="452ff-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="452ff-124">Remarks</span></span>  
 <span data-ttu-id="452ff-125">Dado que el `ICLRMemoryNotificationCallback` interfaz define solo un método ([ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)) y porque `pCallback` es un puntero a un `ICLRMemoryNotificationCallback` instancia proporcionada por CLR, el registro de forma eficaz es para la propia función de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="452ff-125">Because the `ICLRMemoryNotificationCallback` interface defines only one method ([ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)), and because `pCallback` is a pointer to an `ICLRMemoryNotificationCallback` instance provided by the CLR, the registration is effectively for the callback function itself.</span></span> <span data-ttu-id="452ff-126">El host invoca `OnMemoryNotification` a comunicar condiciones de presión de memoria, en lugar de utilizar Win32 estándar `CreateMemoryResourceNotification` función.</span><span class="sxs-lookup"><span data-stu-id="452ff-126">The host invokes `OnMemoryNotification` to report memory pressure conditions, rather than using the standard Win32 `CreateMemoryResourceNotification` function.</span></span> <span data-ttu-id="452ff-127">Para obtener más información, consulte la documentación de la plataforma de Windows.</span><span class="sxs-lookup"><span data-stu-id="452ff-127">For more information, see the Windows Platform documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="452ff-128">Las llamadas a `OnMemoryNotification` nunca se bloqueará.</span><span class="sxs-lookup"><span data-stu-id="452ff-128">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="452ff-129">Siempre devuelven inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="452ff-129">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="452ff-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="452ff-130">Requirements</span></span>  
 <span data-ttu-id="452ff-131">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="452ff-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="452ff-132">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="452ff-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="452ff-133">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="452ff-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="452ff-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="452ff-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="452ff-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="452ff-135">See also</span></span>
- [<span data-ttu-id="452ff-136">ICLRMemoryNotificationCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="452ff-136">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
- [<span data-ttu-id="452ff-137">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="452ff-137">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
