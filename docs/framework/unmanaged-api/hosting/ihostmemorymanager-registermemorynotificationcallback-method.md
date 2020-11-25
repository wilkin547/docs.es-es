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
ms.openlocfilehash: edb29378412583d7cdec804b08f8f622d642b02f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731311"
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a><span data-ttu-id="0b7e4-102">IHostMemoryManager::RegisterMemoryNotificationCallback (Método)</span><span class="sxs-lookup"><span data-stu-id="0b7e4-102">IHostMemoryManager::RegisterMemoryNotificationCallback Method</span></span>

<span data-ttu-id="0b7e4-103">Registra un puntero a una función de devolución de llamada que invoca el host para notificar a la Common Language Runtime (CLR) de la carga de memoria actual en el equipo.</span><span class="sxs-lookup"><span data-stu-id="0b7e4-103">Registers a pointer to a callback function that the host invokes to notify the common language runtime (CLR) of the current memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b7e4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0b7e4-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b7e4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0b7e4-105">Parameters</span></span>  

 `pCallback`  
 <span data-ttu-id="0b7e4-106">de Puntero de interfaz a una instancia de [ICLRMemoryNotificationCallback](iclrmemorynotificationcallback-interface.md) implementada por CLR.</span><span class="sxs-lookup"><span data-stu-id="0b7e4-106">[in] An interface pointer to an [ICLRMemoryNotificationCallback](iclrmemorynotificationcallback-interface.md) instance that is implemented by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0b7e4-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0b7e4-107">Return Value</span></span>  
  
|<span data-ttu-id="0b7e4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0b7e4-108">HRESULT</span></span>|<span data-ttu-id="0b7e4-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="0b7e4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0b7e4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0b7e4-110">S_OK</span></span>|<span data-ttu-id="0b7e4-111">`RegisterMemoryNotificationCallback` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="0b7e4-111">`RegisterMemoryNotificationCallback` returned successfully.</span></span>|  
|<span data-ttu-id="0b7e4-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0b7e4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0b7e4-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="0b7e4-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0b7e4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0b7e4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0b7e4-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0b7e4-115">The call timed out.</span></span>|  
|<span data-ttu-id="0b7e4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0b7e4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0b7e4-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="0b7e4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0b7e4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0b7e4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0b7e4-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="0b7e4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0b7e4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0b7e4-120">E_FAIL</span></span>|<span data-ttu-id="0b7e4-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="0b7e4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0b7e4-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="0b7e4-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0b7e4-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0b7e4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b7e4-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0b7e4-124">Remarks</span></span>  

 <span data-ttu-id="0b7e4-125">Dado que la `ICLRMemoryNotificationCallback` interfaz define solo un método ([ICLRMemoryNotificationCallback:: OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md)), y dado `pCallback` que es un puntero a una `ICLRMemoryNotificationCallback` instancia proporcionada por CLR, el registro es eficaz para la función de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="0b7e4-125">Because the `ICLRMemoryNotificationCallback` interface defines only one method ([ICLRMemoryNotificationCallback::OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md)), and because `pCallback` is a pointer to an `ICLRMemoryNotificationCallback` instance provided by the CLR, the registration is effectively for the callback function itself.</span></span> <span data-ttu-id="0b7e4-126">El host invoca `OnMemoryNotification` para informar de las condiciones de presión de memoria, en lugar de utilizar la función estándar de Win32 `CreateMemoryResourceNotification` .</span><span class="sxs-lookup"><span data-stu-id="0b7e4-126">The host invokes `OnMemoryNotification` to report memory pressure conditions, rather than using the standard Win32 `CreateMemoryResourceNotification` function.</span></span> <span data-ttu-id="0b7e4-127">Para obtener más información, vea la documentación de la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="0b7e4-127">For more information, see the Windows Platform documentation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0b7e4-128">Las llamadas a no se `OnMemoryNotification` bloquean nunca.</span><span class="sxs-lookup"><span data-stu-id="0b7e4-128">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="0b7e4-129">Siempre devuelven inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="0b7e4-129">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b7e4-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0b7e4-130">Requirements</span></span>  

 <span data-ttu-id="0b7e4-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b7e4-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b7e4-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0b7e4-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0b7e4-133">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0b7e4-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0b7e4-134">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b7e4-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b7e4-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0b7e4-135">See also</span></span>

- [<span data-ttu-id="0b7e4-136">ICLRMemoryNotificationCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0b7e4-136">ICLRMemoryNotificationCallback Interface</span></span>](iclrmemorynotificationcallback-interface.md)
- [<span data-ttu-id="0b7e4-137">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0b7e4-137">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
