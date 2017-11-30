---
title: "IHostTaskManager::EndDelayAbort (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.EndDelayAbort
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::EndDelayAbort
helpviewer_keywords:
- EndDelayAbort method [.NET Framework hosting]
- IHostTaskManager::EndDelayAbort method [.NET Framework hosting]
ms.assetid: 6e02facb-2504-4356-9af5-0cee1f8436a7
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 45148c506e2f6073dc175abe4397fad2172b355e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagerenddelayabort-method"></a><span data-ttu-id="c1291-102">IHostTaskManager::EndDelayAbort (Método)</span><span class="sxs-lookup"><span data-stu-id="c1291-102">IHostTaskManager::EndDelayAbort Method</span></span>
<span data-ttu-id="c1291-103">Notifica al host que el código administrado está saliendo del período en el que no se debe anular la tarea actual, después de una llamada anterior a [IHostTaskManager:: BeginDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md).</span><span class="sxs-lookup"><span data-stu-id="c1291-103">Notifies the host that managed code is exiting the period in which the current task must not be aborted, following an earlier call to [IHostTaskManager::BeginDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1291-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1291-104">Syntax</span></span>  
  
```  
HRESULT EndDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="c1291-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c1291-105">Return Value</span></span>  
  
|<span data-ttu-id="c1291-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c1291-106">HRESULT</span></span>|<span data-ttu-id="c1291-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1291-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c1291-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="c1291-108">S_OK</span></span>|<span data-ttu-id="c1291-109">`EndDelayAbort`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="c1291-109">`EndDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="c1291-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c1291-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c1291-111">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c1291-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c1291-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c1291-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c1291-113">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="c1291-113">The call timed out.</span></span>|  
|<span data-ttu-id="c1291-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c1291-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c1291-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="c1291-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c1291-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c1291-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c1291-117">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="c1291-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c1291-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c1291-118">E_FAIL</span></span>|<span data-ttu-id="c1291-119">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="c1291-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c1291-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="c1291-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c1291-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c1291-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c1291-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="c1291-122">E_UNEXPECTED</span></span>|<span data-ttu-id="c1291-123">`EndDelayAbort`se llamó sin una llamada correspondiente a `BeginDelayAbort`.</span><span class="sxs-lookup"><span data-stu-id="c1291-123">`EndDelayAbort` was called without a corresponding call to `BeginDelayAbort`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1291-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c1291-124">Remarks</span></span>  
 <span data-ttu-id="c1291-125">El CLR realiza la llamada correspondiente a `BeginDelayAbort` en la tarea actual antes de llamar a `EndDelayAbort`.</span><span class="sxs-lookup"><span data-stu-id="c1291-125">The CLR makes a corresponding call to `BeginDelayAbort` on the current task before calling `EndDelayAbort`.</span></span> <span data-ttu-id="c1291-126">En ausencia de esta llamada correspondiente, la implementación del host de [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) debe devolver E_UNEXPECTED desde `EndDelayAbort`y debe realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="c1291-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) should return E_UNEXPECTED from `EndDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1291-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c1291-127">Requirements</span></span>  
 <span data-ttu-id="c1291-128">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1291-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1291-129">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c1291-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c1291-130">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c1291-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c1291-131">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1291-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1291-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1291-132">See Also</span></span>  
 <xref:System.Threading>  
 [<span data-ttu-id="c1291-133">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c1291-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="c1291-134">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c1291-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="c1291-135">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c1291-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="c1291-136">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c1291-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
