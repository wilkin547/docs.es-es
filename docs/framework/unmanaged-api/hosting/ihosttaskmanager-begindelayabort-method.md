---
title: IHostTaskManager::BeginDelayAbort (Método)
ms.date: 03/30/2017
api_name:
- IHostTaskManager.BeginDelayAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::BeginDelayAbort
helpviewer_keywords:
- BeginDelayAbort method [.NET Framework hosting]
- IHostTaskManager::BeginDelayAbort method [.NET Framework hosting]
ms.assetid: 75f42a8b-ed68-4718-a030-a179cfba7d72
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 328462343669b3ea6bed2d86514ea348f6ae2b1e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197976"
---
# <a name="ihosttaskmanagerbegindelayabort-method"></a><span data-ttu-id="64120-102">IHostTaskManager::BeginDelayAbort (Método)</span><span class="sxs-lookup"><span data-stu-id="64120-102">IHostTaskManager::BeginDelayAbort Method</span></span>
<span data-ttu-id="64120-103">Notifica al host que el código administrado está entrando en un período en el que no se debe anular la tarea actual.</span><span class="sxs-lookup"><span data-stu-id="64120-103">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64120-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="64120-104">Syntax</span></span>  
  
```  
HRESULT BeginDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="64120-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="64120-105">Return Value</span></span>  
  
|<span data-ttu-id="64120-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="64120-106">HRESULT</span></span>|<span data-ttu-id="64120-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="64120-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="64120-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="64120-108">S_OK</span></span>|<span data-ttu-id="64120-109">`BeginDelayAbort` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="64120-109">`BeginDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="64120-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="64120-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="64120-111">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="64120-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="64120-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="64120-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="64120-113">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="64120-113">The call timed out.</span></span>|  
|<span data-ttu-id="64120-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="64120-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="64120-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="64120-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="64120-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="64120-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="64120-117">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="64120-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="64120-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="64120-118">E_FAIL</span></span>|<span data-ttu-id="64120-119">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="64120-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="64120-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="64120-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="64120-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="64120-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="64120-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="64120-122">E_UNEXPECTED</span></span>|<span data-ttu-id="64120-123">`BeginDelayAbort` ya se ha llamado, pero la llamada correspondiente a [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) aún no ha sido recibido.</span><span class="sxs-lookup"><span data-stu-id="64120-123">`BeginDelayAbort` has already been called, but the corresponding call to [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) has not yet been received.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64120-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="64120-124">Remarks</span></span>  
 <span data-ttu-id="64120-125">El host no debe anular la tarea actual hasta que `EndDelayAbort` se llama.</span><span class="sxs-lookup"><span data-stu-id="64120-125">The host must not abort the current task until `EndDelayAbort` is called.</span></span> <span data-ttu-id="64120-126">Si otra llamada a `BeginDelayAbort` se realiza sin una llamada intermedia a `EndDelayAbort`, el host debe devolver E_UNEXPECTED desde `BeginDelayAbort`y debe realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="64120-126">If another call to `BeginDelayAbort` is made without an intervening call to `EndDelayAbort`, the host should return E_UNEXPECTED from `BeginDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64120-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="64120-127">Requirements</span></span>  
 <span data-ttu-id="64120-128">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64120-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64120-129">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="64120-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="64120-130">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="64120-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="64120-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64120-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64120-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="64120-132">See also</span></span>

- [<span data-ttu-id="64120-133">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="64120-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="64120-134">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="64120-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="64120-135">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="64120-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
