---
title: IHostTaskManager::EndDelayAbort (Método)
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EndDelayAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EndDelayAbort
helpviewer_keywords:
- EndDelayAbort method [.NET Framework hosting]
- IHostTaskManager::EndDelayAbort method [.NET Framework hosting]
ms.assetid: 6e02facb-2504-4356-9af5-0cee1f8436a7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3e8691461179e4f70a4617fd9487949df62f6cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444384"
---
# <a name="ihosttaskmanagerenddelayabort-method"></a><span data-ttu-id="d4fed-102">IHostTaskManager::EndDelayAbort (Método)</span><span class="sxs-lookup"><span data-stu-id="d4fed-102">IHostTaskManager::EndDelayAbort Method</span></span>
<span data-ttu-id="d4fed-103">Notifica al host que el código administrado está saliendo del período en el que no se debe anular la tarea actual, después de una llamada anterior a [IHostTaskManager:: BeginDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md).</span><span class="sxs-lookup"><span data-stu-id="d4fed-103">Notifies the host that managed code is exiting the period in which the current task must not be aborted, following an earlier call to [IHostTaskManager::BeginDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4fed-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d4fed-104">Syntax</span></span>  
  
```  
HRESULT EndDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d4fed-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d4fed-105">Return Value</span></span>  
  
|<span data-ttu-id="d4fed-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d4fed-106">HRESULT</span></span>|<span data-ttu-id="d4fed-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d4fed-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d4fed-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="d4fed-108">S_OK</span></span>|<span data-ttu-id="d4fed-109">`EndDelayAbort` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="d4fed-109">`EndDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="d4fed-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d4fed-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d4fed-111">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="d4fed-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d4fed-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d4fed-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d4fed-113">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="d4fed-113">The call timed out.</span></span>|  
|<span data-ttu-id="d4fed-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d4fed-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d4fed-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="d4fed-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d4fed-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d4fed-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d4fed-117">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="d4fed-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d4fed-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d4fed-118">E_FAIL</span></span>|<span data-ttu-id="d4fed-119">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="d4fed-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d4fed-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="d4fed-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d4fed-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d4fed-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d4fed-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="d4fed-122">E_UNEXPECTED</span></span>|<span data-ttu-id="d4fed-123">`EndDelayAbort` se llamó sin una llamada correspondiente a `BeginDelayAbort`.</span><span class="sxs-lookup"><span data-stu-id="d4fed-123">`EndDelayAbort` was called without a corresponding call to `BeginDelayAbort`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4fed-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d4fed-124">Remarks</span></span>  
 <span data-ttu-id="d4fed-125">El CLR realiza la llamada correspondiente a `BeginDelayAbort` en la tarea actual antes de llamar a `EndDelayAbort`.</span><span class="sxs-lookup"><span data-stu-id="d4fed-125">The CLR makes a corresponding call to `BeginDelayAbort` on the current task before calling `EndDelayAbort`.</span></span> <span data-ttu-id="d4fed-126">En ausencia de esta llamada correspondiente, la implementación del host de [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) debe devolver E_UNEXPECTED desde `EndDelayAbort`y debe realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="d4fed-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) should return E_UNEXPECTED from `EndDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4fed-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d4fed-127">Requirements</span></span>  
 <span data-ttu-id="d4fed-128">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4fed-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4fed-129">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d4fed-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d4fed-130">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d4fed-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d4fed-131">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4fed-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4fed-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4fed-132">See Also</span></span>  
 <xref:System.Threading>  
 [<span data-ttu-id="d4fed-133">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d4fed-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="d4fed-134">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d4fed-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="d4fed-135">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d4fed-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="d4fed-136">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d4fed-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
