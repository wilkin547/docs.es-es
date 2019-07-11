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
ms.openlocfilehash: 95446996988a22e0d4495f3e0da9f6d2432f5a7c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749717"
---
# <a name="ihosttaskmanagerenddelayabort-method"></a><span data-ttu-id="9a5ca-102">IHostTaskManager::EndDelayAbort (Método)</span><span class="sxs-lookup"><span data-stu-id="9a5ca-102">IHostTaskManager::EndDelayAbort Method</span></span>
<span data-ttu-id="9a5ca-103">Notifica al host que el código administrado está saliendo del período en el que no se debe anular la tarea actual, siguiendo una llamada anterior a [BeginDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md).</span><span class="sxs-lookup"><span data-stu-id="9a5ca-103">Notifies the host that managed code is exiting the period in which the current task must not be aborted, following an earlier call to [IHostTaskManager::BeginDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a5ca-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a5ca-104">Syntax</span></span>  
  
```cpp  
HRESULT EndDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9a5ca-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9a5ca-105">Return Value</span></span>  
  
|<span data-ttu-id="9a5ca-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9a5ca-106">HRESULT</span></span>|<span data-ttu-id="9a5ca-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9a5ca-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9a5ca-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="9a5ca-108">S_OK</span></span>|<span data-ttu-id="9a5ca-109">`EndDelayAbort` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="9a5ca-109">`EndDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="9a5ca-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9a5ca-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9a5ca-111">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="9a5ca-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9a5ca-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9a5ca-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9a5ca-113">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="9a5ca-113">The call timed out.</span></span>|  
|<span data-ttu-id="9a5ca-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9a5ca-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9a5ca-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="9a5ca-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9a5ca-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9a5ca-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9a5ca-117">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="9a5ca-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9a5ca-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9a5ca-118">E_FAIL</span></span>|<span data-ttu-id="9a5ca-119">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="9a5ca-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9a5ca-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="9a5ca-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9a5ca-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9a5ca-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9a5ca-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="9a5ca-122">E_UNEXPECTED</span></span>|<span data-ttu-id="9a5ca-123">`EndDelayAbort` se invocó sin una llamada correspondiente a `BeginDelayAbort`.</span><span class="sxs-lookup"><span data-stu-id="9a5ca-123">`EndDelayAbort` was called without a corresponding call to `BeginDelayAbort`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a5ca-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9a5ca-124">Remarks</span></span>  
 <span data-ttu-id="9a5ca-125">El CLR realiza la llamada correspondiente a `BeginDelayAbort` en la tarea actual antes de llamar a `EndDelayAbort`.</span><span class="sxs-lookup"><span data-stu-id="9a5ca-125">The CLR makes a corresponding call to `BeginDelayAbort` on the current task before calling `EndDelayAbort`.</span></span> <span data-ttu-id="9a5ca-126">En ausencia de una llamada correspondiente, la implementación del host de [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) debe devolver E_UNEXPECTED desde `EndDelayAbort`y debe realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="9a5ca-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) should return E_UNEXPECTED from `EndDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a5ca-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9a5ca-127">Requirements</span></span>  
 <span data-ttu-id="9a5ca-128">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a5ca-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a5ca-129">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9a5ca-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9a5ca-130">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9a5ca-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9a5ca-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a5ca-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a5ca-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a5ca-132">See also</span></span>

- <xref:System.Threading>
- [<span data-ttu-id="9a5ca-133">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9a5ca-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="9a5ca-134">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9a5ca-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="9a5ca-135">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9a5ca-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="9a5ca-136">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9a5ca-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
