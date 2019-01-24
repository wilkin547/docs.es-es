---
title: IHostTaskManager::EndThreadAffinity (Método)
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EndThreadAffinity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EndThreadAffinity
helpviewer_keywords:
- EndThreadAffinity method [.NET Framework hosting]
- IHostTaskManager::EndThreadAffinity method [.NET Framework hosting]
ms.assetid: 7738a904-0cd7-4fde-a3eb-2323a5533157
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8de8816f08fa98055bb397d77d060721a0fb30d0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54557921"
---
# <a name="ihosttaskmanagerendthreadaffinity-method"></a><span data-ttu-id="2c401-102">IHostTaskManager::EndThreadAffinity (Método)</span><span class="sxs-lookup"><span data-stu-id="2c401-102">IHostTaskManager::EndThreadAffinity Method</span></span>
<span data-ttu-id="2c401-103">Notifica al host que el código administrado está saliendo del período en el que la tarea actual no se mueve a otro subproceso del sistema operativo, siguiendo una llamada anterior a [IHostTaskManager:: BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md).</span><span class="sxs-lookup"><span data-stu-id="2c401-103">Notifies the host that managed code is exiting the period in which the current task must not be moved to another operating system thread, following an earlier call to [IHostTaskManager::BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c401-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2c401-104">Syntax</span></span>  
  
```  
HRESULT EndThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="2c401-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2c401-105">Return Value</span></span>  
  
|<span data-ttu-id="2c401-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2c401-106">HRESULT</span></span>|<span data-ttu-id="2c401-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="2c401-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2c401-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="2c401-108">S_OK</span></span>|<span data-ttu-id="2c401-109">`EndThreadAffinity` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="2c401-109">`EndThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="2c401-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2c401-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2c401-111">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="2c401-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2c401-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2c401-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2c401-113">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="2c401-113">The call timed out.</span></span>|  
|<span data-ttu-id="2c401-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2c401-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2c401-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="2c401-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2c401-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2c401-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2c401-117">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="2c401-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2c401-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2c401-118">E_FAIL</span></span>|<span data-ttu-id="2c401-119">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="2c401-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2c401-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="2c401-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2c401-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2c401-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2c401-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="2c401-122">E_UNEXPECTED</span></span>|<span data-ttu-id="2c401-123">`EndThreadAffinity` se invocó sin una llamada correspondiente a `BeginThreadAffinity`.</span><span class="sxs-lookup"><span data-stu-id="2c401-123">`EndThreadAffinity` was called without an earlier corresponding call to `BeginThreadAffinity`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c401-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2c401-124">Remarks</span></span>  
 <span data-ttu-id="2c401-125">El CLR realiza la llamada correspondiente a `BeginThreadAffinity` en la tarea actual antes de llamar a `EndThreadAffinity`.</span><span class="sxs-lookup"><span data-stu-id="2c401-125">The CLR makes a corresponding call to `BeginThreadAffinity` on the current task before calling `EndThreadAffinity`.</span></span> <span data-ttu-id="2c401-126">En ausencia de una llamada correspondiente, la implementación del host de [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) debe devolver E_UNEXPECTED y no realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="2c401-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) should return E_UNEXPECTED, and take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c401-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2c401-127">Requirements</span></span>  
 <span data-ttu-id="2c401-128">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c401-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c401-129">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2c401-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2c401-130">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2c401-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2c401-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c401-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c401-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c401-132">See also</span></span>
- <xref:System.Threading>
- [<span data-ttu-id="2c401-133">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2c401-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="2c401-134">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2c401-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="2c401-135">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2c401-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="2c401-136">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2c401-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
