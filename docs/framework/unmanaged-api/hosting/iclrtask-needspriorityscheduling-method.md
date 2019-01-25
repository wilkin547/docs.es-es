---
title: ICLRTask::NeedsPriorityScheduling (Método)
ms.date: 03/30/2017
api_name:
- ICLRTask.NeedsPriorityScheduling
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::NeedsPriorityScheduling
helpviewer_keywords:
- ICLRTask::NeedsPriorityScheduling method [.NET Framework hosting]
- NeedsPriorityScheduling method [.NET Framework hosting]
ms.assetid: 9c9db3f3-26bf-4317-88de-5eb926a22a1d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a2a26e32040f705fd46f9d9d8909fd47e963baa8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54510786"
---
# <a name="iclrtaskneedspriorityscheduling-method"></a><span data-ttu-id="a84d2-102">ICLRTask::NeedsPriorityScheduling (Método)</span><span class="sxs-lookup"><span data-stu-id="a84d2-102">ICLRTask::NeedsPriorityScheduling Method</span></span>
<span data-ttu-id="a84d2-103">Obtiene un valor que indica si la tarea actual, que se está saliendo, debe marcarse como de alta prioridad para volver a programar.</span><span class="sxs-lookup"><span data-stu-id="a84d2-103">Gets a value that indicates whether the current task, which is being switched out, needs to be marked as a high priority for rescheduling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a84d2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a84d2-104">Syntax</span></span>  
  
```  
HRESULT NeedsPriorityScheduling (  
    [out] BOOL *pbNeedsPriorityScheduling  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a84d2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a84d2-105">Parameters</span></span>  
 `pbNeedsPriorityRescheduling`  
 <span data-ttu-id="a84d2-106">[out] `true`, si el host debe intentar volver a programar la instancia actual de la tarea tan pronto como sea posible; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="a84d2-106">[out] `true`, if the host should attempt to reschedule the current task instance as soon as possible; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a84d2-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a84d2-107">Return Value</span></span>  
  
|<span data-ttu-id="a84d2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a84d2-108">HRESULT</span></span>|<span data-ttu-id="a84d2-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="a84d2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a84d2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a84d2-110">S_OK</span></span>|<span data-ttu-id="a84d2-111">`NeedsPriorityRescheduling` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a84d2-111">`NeedsPriorityRescheduling` returned successfully.</span></span>|  
|<span data-ttu-id="a84d2-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a84d2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a84d2-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="a84d2-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a84d2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a84d2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a84d2-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="a84d2-115">The call timed out.</span></span>|  
|<span data-ttu-id="a84d2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a84d2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a84d2-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a84d2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a84d2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a84d2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a84d2-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="a84d2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a84d2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a84d2-120">E_FAIL</span></span>|<span data-ttu-id="a84d2-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="a84d2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a84d2-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="a84d2-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a84d2-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a84d2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a84d2-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a84d2-124">Remarks</span></span>  
 <span data-ttu-id="a84d2-125">En situaciones donde la tarea está cerca de la que se recopilan por el recolector de elementos no utilizados, el CLR establece el valor de `pbNeedsPriorityScheduling` a `true`, que indica la reprogramación de prioridad alta.</span><span class="sxs-lookup"><span data-stu-id="a84d2-125">In situations where the task is close to being collected by the garbage collector, the CLR sets the value of `pbNeedsPriorityScheduling` to `true`, indicating high-priority rescheduling.</span></span> <span data-ttu-id="a84d2-126">Esto permite al host a programar la tarea rápidamente, con lo que se minimiza la posibilidad de retrasos en la recolección de elementos y habilitar el host y el tiempo de ejecución para cooperar en la conservación de los recursos de memoria.</span><span class="sxs-lookup"><span data-stu-id="a84d2-126">This allows the host to reschedule the task quickly, thereby minimizing the potential for delays in garbage collection, and enabling the host and the runtime to cooperate in conserving memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a84d2-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a84d2-127">Requirements</span></span>  
 <span data-ttu-id="a84d2-128">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a84d2-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a84d2-129">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a84d2-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a84d2-130">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a84d2-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a84d2-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a84d2-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a84d2-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="a84d2-132">See also</span></span>
- [<span data-ttu-id="a84d2-133">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a84d2-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="a84d2-134">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a84d2-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="a84d2-135">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a84d2-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="a84d2-136">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a84d2-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
