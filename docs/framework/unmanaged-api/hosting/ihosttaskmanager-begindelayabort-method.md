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
ms.openlocfilehash: f72cc15904d098e159dd7f75f673d43ae987998d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727333"
---
# <a name="ihosttaskmanagerbegindelayabort-method"></a><span data-ttu-id="afc6d-102">IHostTaskManager::BeginDelayAbort (Método)</span><span class="sxs-lookup"><span data-stu-id="afc6d-102">IHostTaskManager::BeginDelayAbort Method</span></span>

<span data-ttu-id="afc6d-103">Notifica al host que el código administrado está entrando en un período en el que la tarea actual no se debe anular.</span><span class="sxs-lookup"><span data-stu-id="afc6d-103">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afc6d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="afc6d-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="afc6d-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="afc6d-105">Return Value</span></span>  
  
|<span data-ttu-id="afc6d-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="afc6d-106">HRESULT</span></span>|<span data-ttu-id="afc6d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="afc6d-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="afc6d-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="afc6d-108">S_OK</span></span>|<span data-ttu-id="afc6d-109">`BeginDelayAbort` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="afc6d-109">`BeginDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="afc6d-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="afc6d-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="afc6d-111">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="afc6d-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="afc6d-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="afc6d-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="afc6d-113">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="afc6d-113">The call timed out.</span></span>|  
|<span data-ttu-id="afc6d-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="afc6d-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="afc6d-115">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="afc6d-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="afc6d-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="afc6d-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="afc6d-117">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="afc6d-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="afc6d-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="afc6d-118">E_FAIL</span></span>|<span data-ttu-id="afc6d-119">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="afc6d-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="afc6d-120">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="afc6d-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="afc6d-121">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="afc6d-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="afc6d-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="afc6d-122">E_UNEXPECTED</span></span>|<span data-ttu-id="afc6d-123">`BeginDelayAbort` ya se ha llamado a, pero aún no se ha recibido la llamada correspondiente a [EndDelayAbort](ihosttaskmanager-enddelayabort-method.md) .</span><span class="sxs-lookup"><span data-stu-id="afc6d-123">`BeginDelayAbort` has already been called, but the corresponding call to [EndDelayAbort](ihosttaskmanager-enddelayabort-method.md) has not yet been received.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="afc6d-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="afc6d-124">Remarks</span></span>  

 <span data-ttu-id="afc6d-125">El host no debe anular la tarea actual hasta que `EndDelayAbort` se llame a.</span><span class="sxs-lookup"><span data-stu-id="afc6d-125">The host must not abort the current task until `EndDelayAbort` is called.</span></span> <span data-ttu-id="afc6d-126">Si se realiza otra llamada a `BeginDelayAbort` sin una llamada intermedia a `EndDelayAbort` , el host debe devolver E_UNEXPECTED de `BeginDelayAbort` y no debe realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="afc6d-126">If another call to `BeginDelayAbort` is made without an intervening call to `EndDelayAbort`, the host should return E_UNEXPECTED from `BeginDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afc6d-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="afc6d-127">Requirements</span></span>  

 <span data-ttu-id="afc6d-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="afc6d-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afc6d-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="afc6d-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="afc6d-130">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="afc6d-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="afc6d-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afc6d-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afc6d-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="afc6d-132">See also</span></span>

- [<span data-ttu-id="afc6d-133">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="afc6d-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="afc6d-134">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="afc6d-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="afc6d-135">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="afc6d-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
