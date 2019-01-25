---
title: IHostTaskManager::BeginThreadAffinity (Método)
ms.date: 03/30/2017
api_name:
- IHostTaskManager.BeginThreadAffinity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::BeginThreadAffinity
helpviewer_keywords:
- IHostTaskManager::BeginThreadAffinity method [.NET Framework hosting]
- BeginThreadAffinity method [.NET Framework hosting]
ms.assetid: fea3ab88-ce41-4c5a-847b-bb78cd748da6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 67a133604e269b8c20dc8640b91e378c498cf038
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745589"
---
# <a name="ihosttaskmanagerbeginthreadaffinity-method"></a><span data-ttu-id="5ce17-102">IHostTaskManager::BeginThreadAffinity (Método)</span><span class="sxs-lookup"><span data-stu-id="5ce17-102">IHostTaskManager::BeginThreadAffinity Method</span></span>
<span data-ttu-id="5ce17-103">Notifica al host que el código administrado está entrando en un período en el que la tarea actual no se mueve a otro subproceso del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5ce17-103">Notifies the host that managed code is entering a period in which the current task must not be moved to another operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ce17-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5ce17-104">Syntax</span></span>  
  
```  
HRESULT BeginThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5ce17-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5ce17-105">Return Value</span></span>  
  
|<span data-ttu-id="5ce17-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5ce17-106">HRESULT</span></span>|<span data-ttu-id="5ce17-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5ce17-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5ce17-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="5ce17-108">S_OK</span></span>|<span data-ttu-id="5ce17-109">`BeginThreadAffinity` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="5ce17-109">`BeginThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="5ce17-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5ce17-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5ce17-111">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="5ce17-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5ce17-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5ce17-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5ce17-113">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="5ce17-113">The call timed out.</span></span>|  
|<span data-ttu-id="5ce17-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5ce17-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5ce17-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="5ce17-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5ce17-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5ce17-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5ce17-117">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="5ce17-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5ce17-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5ce17-118">E_FAIL</span></span>|<span data-ttu-id="5ce17-119">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="5ce17-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5ce17-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="5ce17-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5ce17-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5ce17-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ce17-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5ce17-122">Remarks</span></span>  
 <span data-ttu-id="5ce17-123">CLR llama normalmente `IHostTaskManager::BeginThreadAffinity` en el contexto de una llamada a <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5ce17-123">The CLR typically calls `IHostTaskManager::BeginThreadAffinity` in the context of a call to <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5ce17-124">No se debe programar la tarea actual hasta que se realiza una llamada correspondiente a [IHostTaskManager:: EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md).</span><span class="sxs-lookup"><span data-stu-id="5ce17-124">The current task must not be rescheduled until a corresponding call is made to [IHostTaskManager::EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md).</span></span> <span data-ttu-id="5ce17-125">Pueden salir de las tareas, pero cuando se cambie iniciarla, deben asignarse al mismo subproceso del sistema operativo desde el que estaban. Anidar las llamadas a `BeginThreadAffinity` no tienen ningún efecto, porque la llamada hace referencia a la tarea actual.</span><span class="sxs-lookup"><span data-stu-id="5ce17-125">Tasks can be switched out, but when they are switched back in, they must be assigned to the same operating system thread from which they were switched out. Nested calls to `BeginThreadAffinity` have no effect, because the call refers to the current task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ce17-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5ce17-126">Requirements</span></span>  
 <span data-ttu-id="5ce17-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ce17-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ce17-128">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5ce17-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5ce17-129">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5ce17-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5ce17-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ce17-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ce17-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ce17-131">See also</span></span>
- [<span data-ttu-id="5ce17-132">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5ce17-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="5ce17-133">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5ce17-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="5ce17-134">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5ce17-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="5ce17-135">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5ce17-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
