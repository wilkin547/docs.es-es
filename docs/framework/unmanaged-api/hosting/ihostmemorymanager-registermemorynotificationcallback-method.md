---
description: 'Más información acerca de: IHostMemoryManager:: RegisterMemoryNotificationCallback ((método)'
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
ms.openlocfilehash: 26a7468aba4f473eebff78a8c67eeb5b3e866e9c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707772"
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a><span data-ttu-id="a0850-103">IHostMemoryManager::RegisterMemoryNotificationCallback (Método)</span><span class="sxs-lookup"><span data-stu-id="a0850-103">IHostMemoryManager::RegisterMemoryNotificationCallback Method</span></span>

<span data-ttu-id="a0850-104">Registra un puntero a una función de devolución de llamada que invoca el host para notificar a la Common Language Runtime (CLR) de la carga de memoria actual en el equipo.</span><span class="sxs-lookup"><span data-stu-id="a0850-104">Registers a pointer to a callback function that the host invokes to notify the common language runtime (CLR) of the current memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0850-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a0850-105">Syntax</span></span>  
  
```cpp  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0850-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a0850-106">Parameters</span></span>  

 `pCallback`  
 <span data-ttu-id="a0850-107">de Puntero de interfaz a una instancia de [ICLRMemoryNotificationCallback](iclrmemorynotificationcallback-interface.md) implementada por CLR.</span><span class="sxs-lookup"><span data-stu-id="a0850-107">[in] An interface pointer to an [ICLRMemoryNotificationCallback](iclrmemorynotificationcallback-interface.md) instance that is implemented by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0850-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a0850-108">Return Value</span></span>  
  
|<span data-ttu-id="a0850-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a0850-109">HRESULT</span></span>|<span data-ttu-id="a0850-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0850-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a0850-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a0850-111">S_OK</span></span>|<span data-ttu-id="a0850-112">`RegisterMemoryNotificationCallback` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a0850-112">`RegisterMemoryNotificationCallback` returned successfully.</span></span>|  
|<span data-ttu-id="a0850-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a0850-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a0850-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="a0850-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a0850-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a0850-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a0850-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a0850-116">The call timed out.</span></span>|  
|<span data-ttu-id="a0850-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a0850-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a0850-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a0850-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a0850-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a0850-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a0850-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="a0850-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a0850-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a0850-121">E_FAIL</span></span>|<span data-ttu-id="a0850-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="a0850-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a0850-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a0850-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a0850-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a0850-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0850-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a0850-125">Remarks</span></span>  

 <span data-ttu-id="a0850-126">Dado que la `ICLRMemoryNotificationCallback` interfaz define solo un método ([ICLRMemoryNotificationCallback:: OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md)), y dado `pCallback` que es un puntero a una `ICLRMemoryNotificationCallback` instancia proporcionada por CLR, el registro es eficaz para la función de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="a0850-126">Because the `ICLRMemoryNotificationCallback` interface defines only one method ([ICLRMemoryNotificationCallback::OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md)), and because `pCallback` is a pointer to an `ICLRMemoryNotificationCallback` instance provided by the CLR, the registration is effectively for the callback function itself.</span></span> <span data-ttu-id="a0850-127">El host invoca `OnMemoryNotification` para informar de las condiciones de presión de memoria, en lugar de utilizar la función estándar de Win32 `CreateMemoryResourceNotification` .</span><span class="sxs-lookup"><span data-stu-id="a0850-127">The host invokes `OnMemoryNotification` to report memory pressure conditions, rather than using the standard Win32 `CreateMemoryResourceNotification` function.</span></span> <span data-ttu-id="a0850-128">Para obtener más información, vea la documentación de la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="a0850-128">For more information, see the Windows Platform documentation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a0850-129">Las llamadas a no se `OnMemoryNotification` bloquean nunca.</span><span class="sxs-lookup"><span data-stu-id="a0850-129">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="a0850-130">Siempre devuelven inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="a0850-130">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0850-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a0850-131">Requirements</span></span>  

 <span data-ttu-id="a0850-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0850-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0850-133">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a0850-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a0850-134">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a0850-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0850-135">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0850-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0850-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0850-136">See also</span></span>

- [<span data-ttu-id="a0850-137">ICLRMemoryNotificationCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a0850-137">ICLRMemoryNotificationCallback Interface</span></span>](iclrmemorynotificationcallback-interface.md)
- [<span data-ttu-id="a0850-138">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a0850-138">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
