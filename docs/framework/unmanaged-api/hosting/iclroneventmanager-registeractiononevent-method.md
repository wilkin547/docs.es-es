---
title: "ICLROnEventManager::RegisterActionOnEvent (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLROnEventManager.RegisterActionOnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager::RegisterActionOnEvent
helpviewer_keywords:
- ICLROnEventManager::RegisterActionOnEvent method [.NET Framework hosting]
- RegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: b944cf49-918d-4c4e-993b-77d097a52550
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 008bdc856c9fbede7398f467674ac191c1860128
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclroneventmanagerregisteractiononevent-method"></a><span data-ttu-id="4e058-102">ICLROnEventManager::RegisterActionOnEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="4e058-102">ICLROnEventManager::RegisterActionOnEvent Method</span></span>
<span data-ttu-id="4e058-103">Registra un puntero de devolución de llamada para el evento especificado.</span><span class="sxs-lookup"><span data-stu-id="4e058-103">Registers a callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e058-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4e058-104">Syntax</span></span>  
  
```  
HRESULT RegisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4e058-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4e058-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="4e058-106">[in] Uno de los [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) valores, que indica el evento para el que se va a registrar el puntero de devolución de llamada descrito por `pAction`.</span><span class="sxs-lookup"><span data-stu-id="4e058-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, indicating the event for which to register the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="4e058-107">[in] Un puntero a un [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) objeto al que se llama cuando se desencadene el evento registrado.</span><span class="sxs-lookup"><span data-stu-id="4e058-107">[in] A pointer to an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) object that is called when the registered event fires.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e058-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4e058-108">Return Value</span></span>  
  
|<span data-ttu-id="4e058-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4e058-109">HRESULT</span></span>|<span data-ttu-id="4e058-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="4e058-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4e058-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4e058-111">S_OK</span></span>|<span data-ttu-id="4e058-112">`RegisterActionOnEvent`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="4e058-112">`RegisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="4e058-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4e058-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4e058-114">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="4e058-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4e058-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4e058-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4e058-116">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="4e058-116">The call timed out.</span></span>|  
|<span data-ttu-id="4e058-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4e058-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4e058-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="4e058-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4e058-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4e058-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4e058-120">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="4e058-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4e058-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4e058-121">E_FAIL</span></span>|<span data-ttu-id="4e058-122">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="4e058-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4e058-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="4e058-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4e058-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4e058-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e058-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4e058-125">Remarks</span></span>  
 <span data-ttu-id="4e058-126">El host puede registrar devoluciones de llamada para uno o ambos de los dos tipos de eventos descritos por `EClrEvent`.</span><span class="sxs-lookup"><span data-stu-id="4e058-126">The host can register callbacks for either or both of the two event types described by `EClrEvent`.</span></span> <span data-ttu-id="4e058-127">El host obtiene el `ICLROnEventManager` interfaz mediante una llamada a la [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="4e058-127">The host gets the `ICLROnEventManager` interface by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4e058-128">Los eventos que `RegisterActionOnEvent` registros pueden desencadenarse varias veces y desde subprocesos diferentes para indicar una descarga o la deshabilitación de CLR.</span><span class="sxs-lookup"><span data-stu-id="4e058-128">The events that `RegisterActionOnEvent` registers can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e058-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4e058-129">Requirements</span></span>  
 <span data-ttu-id="4e058-130">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e058-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e058-131">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4e058-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4e058-132">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4e058-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4e058-133">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e058-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e058-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e058-134">See Also</span></span>  
 [<span data-ttu-id="4e058-135">EClrEvent (enumeración)</span><span class="sxs-lookup"><span data-stu-id="4e058-135">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [<span data-ttu-id="4e058-136">IActionOnCLREvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e058-136">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [<span data-ttu-id="4e058-137">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e058-137">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="4e058-138">ICLROnEventManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e058-138">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
