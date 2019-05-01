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
ms.openlocfilehash: 5c7866e0ecc62f037284a5329cb5785be90088f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61984625"
---
# <a name="iclrmemorynotificationcallbackonmemorynotification-method"></a><span data-ttu-id="ac396-102">ICLRMemoryNotificationCallback::OnMemoryNotification (Método)</span><span class="sxs-lookup"><span data-stu-id="ac396-102">ICLRMemoryNotificationCallback::OnMemoryNotification Method</span></span>
<span data-ttu-id="ac396-103">Notifica a common language runtime (CLR) de la carga de memoria en el equipo.</span><span class="sxs-lookup"><span data-stu-id="ac396-103">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac396-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac396-104">Syntax</span></span>  
  
```  
HRESULT OnMemoryNotification (  
    [in] EMemoryAvailable eMemoryAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac396-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ac396-105">Parameters</span></span>  
 `eMemoryAvailable`  
 <span data-ttu-id="ac396-106">[in] Uno de los [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) valores, que indica la presión de memoria del equipo está experimentando.</span><span class="sxs-lookup"><span data-stu-id="ac396-106">[in] One of the [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) values, indicating the memory pressure the computer is currently experiencing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac396-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ac396-107">Return Value</span></span>  
  
|<span data-ttu-id="ac396-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ac396-108">HRESULT</span></span>|<span data-ttu-id="ac396-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="ac396-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ac396-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ac396-110">S_OK</span></span>|<span data-ttu-id="ac396-111">`OnMemoryNotification` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ac396-111">`OnMemoryNotification` returned successfully.</span></span>|  
|<span data-ttu-id="ac396-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ac396-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ac396-113">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="ac396-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ac396-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ac396-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ac396-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="ac396-115">The call timed out.</span></span>|  
|<span data-ttu-id="ac396-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ac396-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ac396-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ac396-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ac396-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ac396-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ac396-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="ac396-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ac396-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ac396-120">E_FAIL</span></span>|<span data-ttu-id="ac396-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="ac396-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ac396-122">Después de un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="ac396-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ac396-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ac396-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac396-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ac396-124">Remarks</span></span>  
 <span data-ttu-id="ac396-125">El CLR registra una devolución de llamada `OnMemoryNotification` mediante una llamada a la [IHostMemoryManager:: RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="ac396-125">The CLR registers a callback to `OnMemoryNotification` by using a call to the [IHostMemoryManager::RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) method.</span></span> <span data-ttu-id="ac396-126">El runtime usa la información devuelta en la devolución de llamada para liberar memoria adicional cuando el host informa de que los recursos se ejecutan bajo la memoria.</span><span class="sxs-lookup"><span data-stu-id="ac396-126">The runtime uses the information returned in the callback to free additional memory when the host reports that memory resources are running low.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac396-127">Las llamadas a `OnMemoryNotification` nunca se bloqueará.</span><span class="sxs-lookup"><span data-stu-id="ac396-127">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="ac396-128">Siempre devuelven inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="ac396-128">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac396-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac396-129">Requirements</span></span>  
 <span data-ttu-id="ac396-130">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac396-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac396-131">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ac396-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ac396-132">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ac396-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ac396-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac396-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac396-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac396-134">See also</span></span>

- [<span data-ttu-id="ac396-135">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ac396-135">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="ac396-136">RegisterMemoryNotificationCallback (método)</span><span class="sxs-lookup"><span data-stu-id="ac396-136">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)
- [<span data-ttu-id="ac396-137">ICLRMemoryNotificationCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ac396-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
