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
ms.openlocfilehash: 61aa68aff5c55586b9de227a72746b3c02234043
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727435"
---
# <a name="ihosttaskmanagerbegindelayabort-method"></a><span data-ttu-id="3eb56-102">IHostTaskManager::BeginDelayAbort (Método)</span><span class="sxs-lookup"><span data-stu-id="3eb56-102">IHostTaskManager::BeginDelayAbort Method</span></span>
<span data-ttu-id="3eb56-103">Notifica al host que el código administrado está entrando en un período en el que no se debe anular la tarea actual.</span><span class="sxs-lookup"><span data-stu-id="3eb56-103">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3eb56-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3eb56-104">Syntax</span></span>  
  
```  
HRESULT BeginDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3eb56-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3eb56-105">Return Value</span></span>  
  
|<span data-ttu-id="3eb56-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3eb56-106">HRESULT</span></span>|<span data-ttu-id="3eb56-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3eb56-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3eb56-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="3eb56-108">S_OK</span></span>|<span data-ttu-id="3eb56-109">`BeginDelayAbort` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3eb56-109">`BeginDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="3eb56-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3eb56-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3eb56-111">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="3eb56-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3eb56-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3eb56-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3eb56-113">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="3eb56-113">The call timed out.</span></span>|  
|<span data-ttu-id="3eb56-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3eb56-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3eb56-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="3eb56-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3eb56-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3eb56-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3eb56-117">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="3eb56-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3eb56-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3eb56-118">E_FAIL</span></span>|<span data-ttu-id="3eb56-119">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="3eb56-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3eb56-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="3eb56-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3eb56-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3eb56-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3eb56-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="3eb56-122">E_UNEXPECTED</span></span>|<span data-ttu-id="3eb56-123">`BeginDelayAbort` ya se ha llamado, pero la llamada correspondiente a [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) aún no ha sido recibido.</span><span class="sxs-lookup"><span data-stu-id="3eb56-123">`BeginDelayAbort` has already been called, but the corresponding call to [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) has not yet been received.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3eb56-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3eb56-124">Remarks</span></span>  
 <span data-ttu-id="3eb56-125">El host no debe anular la tarea actual hasta que `EndDelayAbort` se llama.</span><span class="sxs-lookup"><span data-stu-id="3eb56-125">The host must not abort the current task until `EndDelayAbort` is called.</span></span> <span data-ttu-id="3eb56-126">Si otra llamada a `BeginDelayAbort` se realiza sin una llamada intermedia a `EndDelayAbort`, el host debe devolver E_UNEXPECTED desde `BeginDelayAbort`y debe realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="3eb56-126">If another call to `BeginDelayAbort` is made without an intervening call to `EndDelayAbort`, the host should return E_UNEXPECTED from `BeginDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3eb56-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3eb56-127">Requirements</span></span>  
 <span data-ttu-id="3eb56-128">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3eb56-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3eb56-129">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3eb56-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3eb56-130">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3eb56-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3eb56-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3eb56-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eb56-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="3eb56-132">See also</span></span>
- [<span data-ttu-id="3eb56-133">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3eb56-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="3eb56-134">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3eb56-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="3eb56-135">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3eb56-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="3eb56-136">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3eb56-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
