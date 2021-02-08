---
description: 'Más información acerca de: IHostTaskManager:: BeginDelayAbort (método)'
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
ms.openlocfilehash: f991690af4f7e634c8d845bdbd09f690b4ea3af7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784618"
---
# <a name="ihosttaskmanagerbegindelayabort-method"></a><span data-ttu-id="1ea6e-103">IHostTaskManager::BeginDelayAbort (Método)</span><span class="sxs-lookup"><span data-stu-id="1ea6e-103">IHostTaskManager::BeginDelayAbort Method</span></span>

<span data-ttu-id="1ea6e-104">Notifica al host que el código administrado está entrando en un período en el que la tarea actual no se debe anular.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-104">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ea6e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ea6e-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="1ea6e-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1ea6e-106">Return Value</span></span>  
  
|<span data-ttu-id="1ea6e-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1ea6e-107">HRESULT</span></span>|<span data-ttu-id="1ea6e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="1ea6e-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1ea6e-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="1ea6e-109">S_OK</span></span>|<span data-ttu-id="1ea6e-110">`BeginDelayAbort` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-110">`BeginDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="1ea6e-111">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1ea6e-111">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1ea6e-112">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-112">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1ea6e-113">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1ea6e-113">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1ea6e-114">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-114">The call timed out.</span></span>|  
|<span data-ttu-id="1ea6e-115">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1ea6e-115">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1ea6e-116">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-116">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1ea6e-117">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1ea6e-117">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1ea6e-118">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-118">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1ea6e-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1ea6e-119">E_FAIL</span></span>|<span data-ttu-id="1ea6e-120">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-120">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1ea6e-121">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-121">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1ea6e-122">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-122">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1ea6e-123">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="1ea6e-123">E_UNEXPECTED</span></span>|<span data-ttu-id="1ea6e-124">`BeginDelayAbort` ya se ha llamado a, pero aún no se ha recibido la llamada correspondiente a [EndDelayAbort](ihosttaskmanager-enddelayabort-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1ea6e-124">`BeginDelayAbort` has already been called, but the corresponding call to [EndDelayAbort](ihosttaskmanager-enddelayabort-method.md) has not yet been received.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ea6e-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1ea6e-125">Remarks</span></span>  

 <span data-ttu-id="1ea6e-126">El host no debe anular la tarea actual hasta que `EndDelayAbort` se llame a.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-126">The host must not abort the current task until `EndDelayAbort` is called.</span></span> <span data-ttu-id="1ea6e-127">Si se realiza otra llamada a `BeginDelayAbort` sin una llamada intermedia a `EndDelayAbort` , el host debe devolver E_UNEXPECTED de `BeginDelayAbort` y no debe realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="1ea6e-127">If another call to `BeginDelayAbort` is made without an intervening call to `EndDelayAbort`, the host should return E_UNEXPECTED from `BeginDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ea6e-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1ea6e-128">Requirements</span></span>  

 <span data-ttu-id="1ea6e-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ea6e-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ea6e-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1ea6e-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1ea6e-131">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1ea6e-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1ea6e-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ea6e-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ea6e-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ea6e-133">See also</span></span>

- [<span data-ttu-id="1ea6e-134">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1ea6e-134">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="1ea6e-135">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1ea6e-135">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="1ea6e-136">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1ea6e-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
