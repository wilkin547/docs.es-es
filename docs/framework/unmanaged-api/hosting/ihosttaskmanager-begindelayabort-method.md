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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197976"
---
# <a name="ihosttaskmanagerbegindelayabort-method"></a><span data-ttu-id="b74e4-102">IHostTaskManager::BeginDelayAbort (Método)</span><span class="sxs-lookup"><span data-stu-id="b74e4-102">IHostTaskManager::BeginDelayAbort Method</span></span>
<span data-ttu-id="b74e4-103">Notifica al host que el código administrado está entrando en un período en el que no se debe anular la tarea actual.</span><span class="sxs-lookup"><span data-stu-id="b74e4-103">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b74e4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b74e4-104">Syntax</span></span>  
  
```  
HRESULT BeginDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b74e4-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b74e4-105">Return Value</span></span>  
  
|<span data-ttu-id="b74e4-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b74e4-106">HRESULT</span></span>|<span data-ttu-id="b74e4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b74e4-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b74e4-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="b74e4-108">S_OK</span></span>|`BeginDelayAbort` <span data-ttu-id="b74e4-109">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b74e4-109">returned successfully.</span></span>|  
|<span data-ttu-id="b74e4-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b74e4-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b74e4-111">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="b74e4-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b74e4-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b74e4-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b74e4-113">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="b74e4-113">The call timed out.</span></span>|  
|<span data-ttu-id="b74e4-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b74e4-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b74e4-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="b74e4-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b74e4-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b74e4-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b74e4-117">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="b74e4-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b74e4-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b74e4-118">E_FAIL</span></span>|<span data-ttu-id="b74e4-119">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="b74e4-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b74e4-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="b74e4-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b74e4-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b74e4-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b74e4-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="b74e4-122">E_UNEXPECTED</span></span>|`BeginDelayAbort` <span data-ttu-id="b74e4-123">ya se ha llamado, pero la llamada correspondiente a [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) aún no ha sido recibido.</span><span class="sxs-lookup"><span data-stu-id="b74e4-123">has already been called, but the corresponding call to [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) has not yet been received.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b74e4-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b74e4-124">Remarks</span></span>  
 <span data-ttu-id="b74e4-125">El host no debe anular la tarea actual hasta que `EndDelayAbort` se llama.</span><span class="sxs-lookup"><span data-stu-id="b74e4-125">The host must not abort the current task until `EndDelayAbort` is called.</span></span> <span data-ttu-id="b74e4-126">Si otra llamada a `BeginDelayAbort` se realiza sin una llamada intermedia a `EndDelayAbort`, el host debe devolver E_UNEXPECTED desde `BeginDelayAbort`y debe realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="b74e4-126">If another call to `BeginDelayAbort` is made without an intervening call to `EndDelayAbort`, the host should return E_UNEXPECTED from `BeginDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b74e4-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b74e4-127">Requirements</span></span>  
 <span data-ttu-id="b74e4-128">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b74e4-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b74e4-129">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b74e4-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b74e4-130">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b74e4-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="b74e4-131">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b74e4-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b74e4-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="b74e4-132">See also</span></span>

- [<span data-ttu-id="b74e4-133">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b74e4-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="b74e4-134">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b74e4-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="b74e4-135">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b74e4-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
