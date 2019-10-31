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
ms.openlocfilehash: c40febb78c1bc78a5a724f559eb95869e90bdad0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133088"
---
# <a name="ihosttaskmanagerendthreadaffinity-method"></a><span data-ttu-id="2593b-102">IHostTaskManager::EndThreadAffinity (Método)</span><span class="sxs-lookup"><span data-stu-id="2593b-102">IHostTaskManager::EndThreadAffinity Method</span></span>
<span data-ttu-id="2593b-103">Notifica al host que el código administrado está saliendo del período en el que la tarea actual no se debe pasar a otro subproceso del sistema operativo, siguiendo una llamada anterior a [IHostTaskManager:: BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md).</span><span class="sxs-lookup"><span data-stu-id="2593b-103">Notifies the host that managed code is exiting the period in which the current task must not be moved to another operating system thread, following an earlier call to [IHostTaskManager::BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2593b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2593b-104">Syntax</span></span>  
  
```cpp  
HRESULT EndThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="2593b-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2593b-105">Return Value</span></span>  
  
|<span data-ttu-id="2593b-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2593b-106">HRESULT</span></span>|<span data-ttu-id="2593b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="2593b-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2593b-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="2593b-108">S_OK</span></span>|<span data-ttu-id="2593b-109">`EndThreadAffinity` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="2593b-109">`EndThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="2593b-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2593b-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2593b-111">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="2593b-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2593b-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2593b-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2593b-113">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2593b-113">The call timed out.</span></span>|  
|<span data-ttu-id="2593b-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2593b-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2593b-115">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="2593b-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2593b-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2593b-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2593b-117">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="2593b-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2593b-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2593b-118">E_FAIL</span></span>|<span data-ttu-id="2593b-119">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="2593b-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2593b-120">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="2593b-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2593b-121">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2593b-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2593b-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="2593b-122">E_UNEXPECTED</span></span>|<span data-ttu-id="2593b-123">se llamó a `EndThreadAffinity` sin una llamada anterior correspondiente a `BeginThreadAffinity`.</span><span class="sxs-lookup"><span data-stu-id="2593b-123">`EndThreadAffinity` was called without an earlier corresponding call to `BeginThreadAffinity`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2593b-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2593b-124">Remarks</span></span>  
 <span data-ttu-id="2593b-125">CLR realiza una llamada correspondiente a `BeginThreadAffinity` en la tarea actual antes de llamar a `EndThreadAffinity`.</span><span class="sxs-lookup"><span data-stu-id="2593b-125">The CLR makes a corresponding call to `BeginThreadAffinity` on the current task before calling `EndThreadAffinity`.</span></span> <span data-ttu-id="2593b-126">En ausencia de esta llamada correspondiente, la implementación del host de [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) debe devolver E_UNEXPECTED y no realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="2593b-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) should return E_UNEXPECTED, and take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2593b-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2593b-127">Requirements</span></span>  
 <span data-ttu-id="2593b-128">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2593b-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2593b-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2593b-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2593b-130">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2593b-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2593b-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2593b-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2593b-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="2593b-132">See also</span></span>

- <xref:System.Threading>
- [<span data-ttu-id="2593b-133">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2593b-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="2593b-134">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2593b-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="2593b-135">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2593b-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="2593b-136">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2593b-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
