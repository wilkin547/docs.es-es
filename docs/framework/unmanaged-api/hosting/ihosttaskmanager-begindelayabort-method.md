---
title: "IHostTaskManager::BeginDelayAbort (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.BeginDelayAbort
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::BeginDelayAbort
helpviewer_keywords:
- BeginDelayAbort method [.NET Framework hosting]
- IHostTaskManager::BeginDelayAbort method [.NET Framework hosting]
ms.assetid: 75f42a8b-ed68-4718-a030-a179cfba7d72
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a6b37c87f26013dab95f7607e03463437b9797a0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanagerbegindelayabort-method"></a><span data-ttu-id="7c44f-102">IHostTaskManager::BeginDelayAbort (Método)</span><span class="sxs-lookup"><span data-stu-id="7c44f-102">IHostTaskManager::BeginDelayAbort Method</span></span>
<span data-ttu-id="7c44f-103">Notifica al host que el código administrado está entrando en un período en el que no se debe anular la tarea actual.</span><span class="sxs-lookup"><span data-stu-id="7c44f-103">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c44f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7c44f-104">Syntax</span></span>  
  
```  
HRESULT BeginDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7c44f-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7c44f-105">Return Value</span></span>  
  
|<span data-ttu-id="7c44f-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7c44f-106">HRESULT</span></span>|<span data-ttu-id="7c44f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="7c44f-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7c44f-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="7c44f-108">S_OK</span></span>|<span data-ttu-id="7c44f-109">`BeginDelayAbort`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="7c44f-109">`BeginDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="7c44f-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7c44f-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7c44f-111">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="7c44f-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7c44f-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7c44f-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7c44f-113">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="7c44f-113">The call timed out.</span></span>|  
|<span data-ttu-id="7c44f-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7c44f-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7c44f-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="7c44f-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7c44f-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7c44f-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7c44f-117">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="7c44f-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7c44f-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7c44f-118">E_FAIL</span></span>|<span data-ttu-id="7c44f-119">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="7c44f-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7c44f-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="7c44f-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7c44f-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7c44f-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7c44f-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="7c44f-122">E_UNEXPECTED</span></span>|<span data-ttu-id="7c44f-123">`BeginDelayAbort`ya se ha llamado, pero la llamada correspondiente a [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) aún no se ha recibido.</span><span class="sxs-lookup"><span data-stu-id="7c44f-123">`BeginDelayAbort` has already been called, but the corresponding call to [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) has not yet been received.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c44f-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7c44f-124">Remarks</span></span>  
 <span data-ttu-id="7c44f-125">El host no debe anular la tarea actual hasta que `EndDelayAbort` se llama.</span><span class="sxs-lookup"><span data-stu-id="7c44f-125">The host must not abort the current task until `EndDelayAbort` is called.</span></span> <span data-ttu-id="7c44f-126">Si otra llamada a `BeginDelayAbort` se realiza sin una llamada intermedia a `EndDelayAbort`, el host debe devolver E_UNEXPECTED desde `BeginDelayAbort`y debe realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="7c44f-126">If another call to `BeginDelayAbort` is made without an intervening call to `EndDelayAbort`, the host should return E_UNEXPECTED from `BeginDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c44f-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7c44f-127">Requirements</span></span>  
 <span data-ttu-id="7c44f-128">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c44f-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c44f-129">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7c44f-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7c44f-130">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7c44f-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c44f-131">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c44f-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c44f-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c44f-132">See Also</span></span>  
 [<span data-ttu-id="7c44f-133">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7c44f-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="7c44f-134">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7c44f-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="7c44f-135">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7c44f-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="7c44f-136">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7c44f-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
