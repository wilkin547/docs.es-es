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
ms.openlocfilehash: 91c1ea51969447861ff6d0956c5714baa0054450
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124667"
---
# <a name="iclrtaskneedspriorityscheduling-method"></a><span data-ttu-id="86ea8-102">ICLRTask::NeedsPriorityScheduling (Método)</span><span class="sxs-lookup"><span data-stu-id="86ea8-102">ICLRTask::NeedsPriorityScheduling Method</span></span>
<span data-ttu-id="86ea8-103">Obtiene un valor que indica si la tarea actual, que se va a desactivar, debe marcarse como alta prioridad para la reprogramación.</span><span class="sxs-lookup"><span data-stu-id="86ea8-103">Gets a value that indicates whether the current task, which is being switched out, needs to be marked as a high priority for rescheduling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86ea8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="86ea8-104">Syntax</span></span>  
  
```cpp  
HRESULT NeedsPriorityScheduling (  
    [out] BOOL *pbNeedsPriorityScheduling  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86ea8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="86ea8-105">Parameters</span></span>  
 `pbNeedsPriorityRescheduling`  
 <span data-ttu-id="86ea8-106">[out] `true`, si el host debe intentar volver a programar la instancia actual de la tarea tan pronto como sea posible; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="86ea8-106">[out] `true`, if the host should attempt to reschedule the current task instance as soon as possible; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="86ea8-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="86ea8-107">Return Value</span></span>  
  
|<span data-ttu-id="86ea8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="86ea8-108">HRESULT</span></span>|<span data-ttu-id="86ea8-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="86ea8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="86ea8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="86ea8-110">S_OK</span></span>|<span data-ttu-id="86ea8-111">`NeedsPriorityRescheduling` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="86ea8-111">`NeedsPriorityRescheduling` returned successfully.</span></span>|  
|<span data-ttu-id="86ea8-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="86ea8-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="86ea8-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="86ea8-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="86ea8-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="86ea8-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="86ea8-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="86ea8-115">The call timed out.</span></span>|  
|<span data-ttu-id="86ea8-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="86ea8-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="86ea8-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="86ea8-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="86ea8-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="86ea8-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="86ea8-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="86ea8-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="86ea8-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="86ea8-120">E_FAIL</span></span>|<span data-ttu-id="86ea8-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="86ea8-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="86ea8-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="86ea8-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="86ea8-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="86ea8-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86ea8-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="86ea8-124">Remarks</span></span>  
 <span data-ttu-id="86ea8-125">En situaciones en las que la tarea está próxima a ser recopilada por el recolector de elementos no utilizados, CLR establece el valor de `pbNeedsPriorityScheduling` en `true`, lo que indica una reprogramación de prioridad alta.</span><span class="sxs-lookup"><span data-stu-id="86ea8-125">In situations where the task is close to being collected by the garbage collector, the CLR sets the value of `pbNeedsPriorityScheduling` to `true`, indicating high-priority rescheduling.</span></span> <span data-ttu-id="86ea8-126">Esto permite que el host vuelva a programar la tarea rápidamente, con lo que se reduce la posibilidad de retrasos en la recolección de elementos no utilizados y se habilita el host y el tiempo de ejecución para cooperar en la reserva de recursos de memoria.</span><span class="sxs-lookup"><span data-stu-id="86ea8-126">This allows the host to reschedule the task quickly, thereby minimizing the potential for delays in garbage collection, and enabling the host and the runtime to cooperate in conserving memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86ea8-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="86ea8-127">Requirements</span></span>  
 <span data-ttu-id="86ea8-128">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86ea8-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86ea8-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="86ea8-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="86ea8-130">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="86ea8-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="86ea8-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86ea8-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86ea8-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="86ea8-132">See also</span></span>

- [<span data-ttu-id="86ea8-133">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="86ea8-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="86ea8-134">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="86ea8-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="86ea8-135">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="86ea8-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="86ea8-136">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="86ea8-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
