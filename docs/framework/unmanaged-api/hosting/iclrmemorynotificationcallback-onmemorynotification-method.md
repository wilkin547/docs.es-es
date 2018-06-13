---
title: ICLRMemoryNotificationCallback::OnMemoryNotification (Método)
ms.date: 03/30/2017
api_name:
- ICLRMemoryNotificationCallback.OnMemoryNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification
helpviewer_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification method [.NET Framework hosting]
- OnMemoryNotification method [.NET Framework hosting]
ms.assetid: 5612a44d-56cc-4f34-af31-8c9809ba9431
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 187c0a8d929958b7eaf1e99771da6a0d29c3d5f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434192"
---
# <a name="iclrmemorynotificationcallbackonmemorynotification-method"></a><span data-ttu-id="027f0-102">ICLRMemoryNotificationCallback::OnMemoryNotification (Método)</span><span class="sxs-lookup"><span data-stu-id="027f0-102">ICLRMemoryNotificationCallback::OnMemoryNotification Method</span></span>
<span data-ttu-id="027f0-103">Notifica a common language runtime (CLR) de la carga de memoria en el equipo.</span><span class="sxs-lookup"><span data-stu-id="027f0-103">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="027f0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="027f0-104">Syntax</span></span>  
  
```  
HRESULT OnMemoryNotification (  
    [in] EMemoryAvailable eMemoryAvailable  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="027f0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="027f0-105">Parameters</span></span>  
 `eMemoryAvailable`  
 <span data-ttu-id="027f0-106">[in] Uno de los [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) valores, que indica la presión de memoria del equipo está experimentando actualmente.</span><span class="sxs-lookup"><span data-stu-id="027f0-106">[in] One of the [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) values, indicating the memory pressure the computer is currently experiencing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="027f0-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="027f0-107">Return Value</span></span>  
  
|<span data-ttu-id="027f0-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="027f0-108">HRESULT</span></span>|<span data-ttu-id="027f0-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="027f0-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="027f0-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="027f0-110">S_OK</span></span>|<span data-ttu-id="027f0-111">`OnMemoryNotification` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="027f0-111">`OnMemoryNotification` returned successfully.</span></span>|  
|<span data-ttu-id="027f0-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="027f0-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="027f0-113">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="027f0-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="027f0-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="027f0-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="027f0-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="027f0-115">The call timed out.</span></span>|  
|<span data-ttu-id="027f0-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="027f0-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="027f0-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="027f0-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="027f0-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="027f0-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="027f0-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="027f0-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="027f0-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="027f0-120">E_FAIL</span></span>|<span data-ttu-id="027f0-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="027f0-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="027f0-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="027f0-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="027f0-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="027f0-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="027f0-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="027f0-124">Remarks</span></span>  
 <span data-ttu-id="027f0-125">CLR registra una devolución de llamada `OnMemoryNotification` con una llamada a la [IHostMemoryManager:: RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="027f0-125">The CLR registers a callback to `OnMemoryNotification` by using a call to the [IHostMemoryManager::RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) method.</span></span> <span data-ttu-id="027f0-126">El runtime usa la información devuelta en la devolución de llamada para liberar memoria adicional cuando el host informa de que los recursos se ejecutan bajo la memoria.</span><span class="sxs-lookup"><span data-stu-id="027f0-126">The runtime uses the information returned in the callback to free additional memory when the host reports that memory resources are running low.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="027f0-127">Las llamadas a `OnMemoryNotification` nunca se bloquean.</span><span class="sxs-lookup"><span data-stu-id="027f0-127">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="027f0-128">Siempre devuelven inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="027f0-128">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="027f0-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="027f0-129">Requirements</span></span>  
 <span data-ttu-id="027f0-130">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="027f0-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="027f0-131">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="027f0-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="027f0-132">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="027f0-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="027f0-133">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="027f0-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="027f0-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="027f0-134">See Also</span></span>  
 [<span data-ttu-id="027f0-135">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="027f0-135">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="027f0-136">RegisterMemoryNotificationCallback (método)</span><span class="sxs-lookup"><span data-stu-id="027f0-136">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)  
 [<span data-ttu-id="027f0-137">ICLRMemoryNotificationCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="027f0-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
