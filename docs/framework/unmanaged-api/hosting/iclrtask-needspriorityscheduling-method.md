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
ms.openlocfilehash: df20e98a9e88c10bac748a5acfc91adcb133da79
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762999"
---
# <a name="iclrtaskneedspriorityscheduling-method"></a><span data-ttu-id="10a8e-102">ICLRTask::NeedsPriorityScheduling (Método)</span><span class="sxs-lookup"><span data-stu-id="10a8e-102">ICLRTask::NeedsPriorityScheduling Method</span></span>
<span data-ttu-id="10a8e-103">Obtiene un valor que indica si la tarea actual, que se va a desactivar, debe marcarse como alta prioridad para la reprogramación.</span><span class="sxs-lookup"><span data-stu-id="10a8e-103">Gets a value that indicates whether the current task, which is being switched out, needs to be marked as a high priority for rescheduling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10a8e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="10a8e-104">Syntax</span></span>  
  
```cpp  
HRESULT NeedsPriorityScheduling (  
    [out] BOOL *pbNeedsPriorityScheduling  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10a8e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="10a8e-105">Parameters</span></span>  
 `pbNeedsPriorityRescheduling`  
 <span data-ttu-id="10a8e-106">[out] `true` si el host debe intentar volver a programar la instancia de la tarea actual lo antes posible; de lo contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="10a8e-106">[out] `true`, if the host should attempt to reschedule the current task instance as soon as possible; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10a8e-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="10a8e-107">Return Value</span></span>  
  
|<span data-ttu-id="10a8e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="10a8e-108">HRESULT</span></span>|<span data-ttu-id="10a8e-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="10a8e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="10a8e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="10a8e-110">S_OK</span></span>|<span data-ttu-id="10a8e-111">`NeedsPriorityRescheduling`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="10a8e-111">`NeedsPriorityRescheduling` returned successfully.</span></span>|  
|<span data-ttu-id="10a8e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="10a8e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="10a8e-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="10a8e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="10a8e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="10a8e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="10a8e-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="10a8e-115">The call timed out.</span></span>|  
|<span data-ttu-id="10a8e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="10a8e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="10a8e-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="10a8e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="10a8e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="10a8e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="10a8e-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="10a8e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="10a8e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="10a8e-120">E_FAIL</span></span>|<span data-ttu-id="10a8e-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="10a8e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="10a8e-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="10a8e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="10a8e-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="10a8e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10a8e-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="10a8e-124">Remarks</span></span>  
 <span data-ttu-id="10a8e-125">En situaciones en las que la tarea está próxima a ser recopilada por el recolector de elementos no utilizados, CLR establece el valor de `pbNeedsPriorityScheduling` en `true` , lo que indica una reprogramación de prioridad alta.</span><span class="sxs-lookup"><span data-stu-id="10a8e-125">In situations where the task is close to being collected by the garbage collector, the CLR sets the value of `pbNeedsPriorityScheduling` to `true`, indicating high-priority rescheduling.</span></span> <span data-ttu-id="10a8e-126">Esto permite que el host vuelva a programar la tarea rápidamente, con lo que se reduce la posibilidad de retrasos en la recolección de elementos no utilizados y se habilita el host y el tiempo de ejecución para cooperar en la reserva de recursos de memoria.</span><span class="sxs-lookup"><span data-stu-id="10a8e-126">This allows the host to reschedule the task quickly, thereby minimizing the potential for delays in garbage collection, and enabling the host and the runtime to cooperate in conserving memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10a8e-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="10a8e-127">Requirements</span></span>  
 <span data-ttu-id="10a8e-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10a8e-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10a8e-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="10a8e-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="10a8e-130">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="10a8e-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="10a8e-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10a8e-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10a8e-132">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="10a8e-132">See also</span></span>

- [<span data-ttu-id="10a8e-133">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="10a8e-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="10a8e-134">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="10a8e-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="10a8e-135">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="10a8e-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="10a8e-136">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="10a8e-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
