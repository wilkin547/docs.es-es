---
title: "IHostSyncManager::CreateAutoEvent (Método)"
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
- IHostSyncManager.CreateAutoEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateAutoEvent
helpviewer_keywords:
- IHostSyncManager::CreateAutoEvent method [.NET Framework hosting]
- CreateAutoEvent method [.NET Framework hosting]
ms.assetid: 3153643e-cf5c-4b44-8e0e-c2b22cb08208
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b7874839d04af89f2fa512f82213862f34408001
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsyncmanagercreateautoevent-method"></a><span data-ttu-id="b15bb-102">IHostSyncManager::CreateAutoEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="b15bb-102">IHostSyncManager::CreateAutoEvent Method</span></span>
<span data-ttu-id="b15bb-103">Crea un objeto de evento de restablecimiento automático.</span><span class="sxs-lookup"><span data-stu-id="b15bb-103">Creates an auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b15bb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b15bb-104">Syntax</span></span>  
  
```  
HRESULT CreateAutoEvent (  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b15bb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b15bb-105">Parameters</span></span>  
 `ppEvent`  
 <span data-ttu-id="b15bb-106">[out] Un puntero a la dirección de un [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instancia implementada por el host, o null si no se pudo crear el objeto de evento.</span><span class="sxs-lookup"><span data-stu-id="b15bb-106">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance implemented by the host, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b15bb-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b15bb-107">Return Value</span></span>  
  
|<span data-ttu-id="b15bb-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b15bb-108">HRESULT</span></span>|<span data-ttu-id="b15bb-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="b15bb-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b15bb-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b15bb-110">S_OK</span></span>|<span data-ttu-id="b15bb-111">`CreateAutoEvent`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b15bb-111">`CreateAutoEvent` returned successfully.</span></span>|  
|<span data-ttu-id="b15bb-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b15bb-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b15bb-113">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="b15bb-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b15bb-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b15bb-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b15bb-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="b15bb-115">The call timed out.</span></span>|  
|<span data-ttu-id="b15bb-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b15bb-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b15bb-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="b15bb-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b15bb-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b15bb-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b15bb-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="b15bb-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b15bb-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b15bb-120">E_FAIL</span></span>|<span data-ttu-id="b15bb-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="b15bb-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b15bb-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="b15bb-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b15bb-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b15bb-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b15bb-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="b15bb-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="b15bb-125">No había memoria suficiente disponible para crear el objeto de evento solicitado.</span><span class="sxs-lookup"><span data-stu-id="b15bb-125">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b15bb-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b15bb-126">Remarks</span></span>  
 <span data-ttu-id="b15bb-127">`CreateAutoEvent`crea un objeto de evento automático cuyo estado se cambia automáticamente a no señalado después de que se ha liberado el subproceso en espera.</span><span class="sxs-lookup"><span data-stu-id="b15bb-127">`CreateAutoEvent` creates an auto-event object whose state is automatically changed to non-signaled after the waiting thread has been released.</span></span> <span data-ttu-id="b15bb-128">Este método refleja el Win32 `CreateEvent` función con un valor de `false` especificado para el `bManualReset` parámetro</span><span class="sxs-lookup"><span data-stu-id="b15bb-128">This method mirrors the Win32 `CreateEvent` function with a value of `false` specified for the `bManualReset` parameter</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b15bb-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b15bb-129">Requirements</span></span>  
 <span data-ttu-id="b15bb-130">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b15bb-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b15bb-131">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b15bb-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b15bb-132">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b15bb-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b15bb-133">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b15bb-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b15bb-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="b15bb-134">See Also</span></span>  
 [<span data-ttu-id="b15bb-135">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b15bb-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="b15bb-136">IHostAutoEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b15bb-136">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="b15bb-137">IHostControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b15bb-137">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 [<span data-ttu-id="b15bb-138">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b15bb-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
