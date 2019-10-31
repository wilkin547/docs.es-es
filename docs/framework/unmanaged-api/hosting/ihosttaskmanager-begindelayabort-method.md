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
ms.openlocfilehash: b765d5449cebbdec5f106a8e4743fee2f0ee5521
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133136"
---
# <a name="ihosttaskmanagerbegindelayabort-method"></a><span data-ttu-id="23027-102">IHostTaskManager::BeginDelayAbort (Método)</span><span class="sxs-lookup"><span data-stu-id="23027-102">IHostTaskManager::BeginDelayAbort Method</span></span>
<span data-ttu-id="23027-103">Notifica al host que el código administrado está entrando en un período en el que la tarea actual no se debe anular.</span><span class="sxs-lookup"><span data-stu-id="23027-103">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23027-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="23027-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="23027-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="23027-105">Return Value</span></span>  
  
|<span data-ttu-id="23027-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="23027-106">HRESULT</span></span>|<span data-ttu-id="23027-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="23027-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="23027-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="23027-108">S_OK</span></span>|<span data-ttu-id="23027-109">`BeginDelayAbort` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="23027-109">`BeginDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="23027-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="23027-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="23027-111">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="23027-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="23027-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="23027-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="23027-113">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="23027-113">The call timed out.</span></span>|  
|<span data-ttu-id="23027-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="23027-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="23027-115">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="23027-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="23027-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="23027-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="23027-117">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="23027-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="23027-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="23027-118">E_FAIL</span></span>|<span data-ttu-id="23027-119">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="23027-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="23027-120">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="23027-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="23027-121">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="23027-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="23027-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="23027-122">E_UNEXPECTED</span></span>|<span data-ttu-id="23027-123">ya se ha llamado a `BeginDelayAbort`, pero aún no se ha recibido la llamada correspondiente a [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) .</span><span class="sxs-lookup"><span data-stu-id="23027-123">`BeginDelayAbort` has already been called, but the corresponding call to [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) has not yet been received.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23027-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="23027-124">Remarks</span></span>  
 <span data-ttu-id="23027-125">El host no debe anular la tarea actual hasta que se llame a `EndDelayAbort`.</span><span class="sxs-lookup"><span data-stu-id="23027-125">The host must not abort the current task until `EndDelayAbort` is called.</span></span> <span data-ttu-id="23027-126">Si se realiza otra llamada a `BeginDelayAbort` sin una llamada intermedia a `EndDelayAbort`, el host debe devolver E_UNEXPECTED desde `BeginDelayAbort`y no debe realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="23027-126">If another call to `BeginDelayAbort` is made without an intervening call to `EndDelayAbort`, the host should return E_UNEXPECTED from `BeginDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23027-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="23027-127">Requirements</span></span>  
 <span data-ttu-id="23027-128">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23027-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23027-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="23027-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="23027-130">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="23027-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="23027-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23027-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23027-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="23027-132">See also</span></span>

- [<span data-ttu-id="23027-133">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="23027-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="23027-134">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="23027-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="23027-135">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="23027-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
