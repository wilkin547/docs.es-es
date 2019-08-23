---
title: IHostTask::SetPriority (Método)
ms.date: 03/30/2017
api_name:
- IHostTask.SetPriority
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetPriority
helpviewer_keywords:
- IHostTask::SetPriority method [.NET Framework hosting]
- SetPriority method [.NET Framework hosting]
ms.assetid: cd8c379b-c7a0-434f-8e23-899bd26be75d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 533e3d715b46b4ef6d473795a010fa3ad297ded2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913749"
---
# <a name="ihosttasksetpriority-method"></a><span data-ttu-id="55d3f-102">IHostTask::SetPriority (Método)</span><span class="sxs-lookup"><span data-stu-id="55d3f-102">IHostTask::SetPriority Method</span></span>
<span data-ttu-id="55d3f-103">Solicita que el host ajuste el nivel de prioridad del subproceso para la tarea representada por la instancia de [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) actual.</span><span class="sxs-lookup"><span data-stu-id="55d3f-103">Requests that the host adjust the thread priority level for the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55d3f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="55d3f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPriority (  
    [in] int newPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55d3f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="55d3f-105">Parameters</span></span>  
 `newPriority`  
 <span data-ttu-id="55d3f-106">de Entero que representa el valor de prioridad de subproceso solicitado para la tarea representada `IHostTask` por la instancia actual.</span><span class="sxs-lookup"><span data-stu-id="55d3f-106">[in] An integer that represents the requested thread priority value for the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="55d3f-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="55d3f-107">Return Value</span></span>  
  
|<span data-ttu-id="55d3f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="55d3f-108">HRESULT</span></span>|<span data-ttu-id="55d3f-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="55d3f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="55d3f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="55d3f-110">S_OK</span></span>|<span data-ttu-id="55d3f-111">`SetPriority`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="55d3f-111">`SetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="55d3f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="55d3f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="55d3f-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="55d3f-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="55d3f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="55d3f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="55d3f-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="55d3f-115">The call timed out.</span></span>|  
|<span data-ttu-id="55d3f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="55d3f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="55d3f-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="55d3f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="55d3f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="55d3f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="55d3f-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="55d3f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="55d3f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="55d3f-120">E_FAIL</span></span>|<span data-ttu-id="55d3f-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="55d3f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="55d3f-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="55d3f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="55d3f-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="55d3f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55d3f-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="55d3f-124">Remarks</span></span>  
 <span data-ttu-id="55d3f-125">A los subprocesos se les concede el tiempo de procesamiento mediante un sistema Round Robin que se basa parcialmente en el nivel de prioridad de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="55d3f-125">Threads are granted processing time using a round-robin system that is partly based on a thread's priority level.</span></span> <span data-ttu-id="55d3f-126">`SetPriority`permite que CLR establezca el nivel de prioridad de subproceso para la tarea actual.</span><span class="sxs-lookup"><span data-stu-id="55d3f-126">`SetPriority` allows the CLR to set that thread priority level for the current task.</span></span> <span data-ttu-id="55d3f-127">Se admiten los valores siguientes `newPriority` .</span><span class="sxs-lookup"><span data-stu-id="55d3f-127">The following `newPriority` values are supported.</span></span>  
  
- <span data-ttu-id="55d3f-128">THREAD_PRIORITY_ABOVE_NORMAL</span><span class="sxs-lookup"><span data-stu-id="55d3f-128">THREAD_PRIORITY_ABOVE_NORMAL</span></span>  
  
- <span data-ttu-id="55d3f-129">THREAD_PRIORITY_BELOW_NORMAL</span><span class="sxs-lookup"><span data-stu-id="55d3f-129">THREAD_PRIORITY_BELOW_NORMAL</span></span>  
  
- <span data-ttu-id="55d3f-130">THREAD_PRIORITY_HIGHEST</span><span class="sxs-lookup"><span data-stu-id="55d3f-130">THREAD_PRIORITY_HIGHEST</span></span>  
  
- <span data-ttu-id="55d3f-131">THREAD_PRIORITY_IDLE</span><span class="sxs-lookup"><span data-stu-id="55d3f-131">THREAD_PRIORITY_IDLE</span></span>  
  
- <span data-ttu-id="55d3f-132">THREAD_PRIORITY_LOWEST</span><span class="sxs-lookup"><span data-stu-id="55d3f-132">THREAD_PRIORITY_LOWEST</span></span>  
  
- <span data-ttu-id="55d3f-133">THREAD_PRIORITY_NORMAL</span><span class="sxs-lookup"><span data-stu-id="55d3f-133">THREAD_PRIORITY_NORMAL</span></span>  
  
- <span data-ttu-id="55d3f-134">THREAD_PRIORITY_TIME_CRITICAL</span><span class="sxs-lookup"><span data-stu-id="55d3f-134">THREAD_PRIORITY_TIME_CRITICAL</span></span>  
  
 <span data-ttu-id="55d3f-135">CLR llama a `SetPriority` cuando el valor <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> de se modifica mediante código de usuario.</span><span class="sxs-lookup"><span data-stu-id="55d3f-135">The CLR calls `SetPriority` when the value of the <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> is modified by user code.</span></span> <span data-ttu-id="55d3f-136">Un host puede definir sus propios algoritmos para la asignación de prioridad de subprocesos y es libre de omitir esta solicitud.</span><span class="sxs-lookup"><span data-stu-id="55d3f-136">A host can define its own algorithms for thread priority assignment, and is free to ignore this request.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="55d3f-137">`SetPriority`no informa de si se cambió el nivel de prioridad del subproceso.</span><span class="sxs-lookup"><span data-stu-id="55d3f-137">`SetPriority` does not report whether the thread priority level was changed.</span></span> <span data-ttu-id="55d3f-138">Llame a [IHostTask:: GetPriority (](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md) para determinar el valor del nivel de prioridad del subproceso de la tarea.</span><span class="sxs-lookup"><span data-stu-id="55d3f-138">Call [IHostTask::GetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md) to determine the value of the task's thread priority level.</span></span>  
  
 <span data-ttu-id="55d3f-139">La función de Win32 `SetThreadPriority` define los valores de nivel de prioridad del subproceso.</span><span class="sxs-lookup"><span data-stu-id="55d3f-139">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span> <span data-ttu-id="55d3f-140">Para obtener más información sobre la prioridad de los subprocesos, vea la documentación de la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="55d3f-140">For more information about thread priority, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55d3f-141">Requisitos</span><span class="sxs-lookup"><span data-stu-id="55d3f-141">Requirements</span></span>  
 <span data-ttu-id="55d3f-142">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55d3f-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55d3f-143">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="55d3f-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="55d3f-144">**Biblioteca** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="55d3f-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="55d3f-145">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55d3f-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55d3f-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="55d3f-146">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="55d3f-147">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="55d3f-147">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="55d3f-148">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="55d3f-148">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="55d3f-149">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="55d3f-149">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="55d3f-150">GetPriority (método)</span><span class="sxs-lookup"><span data-stu-id="55d3f-150">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)
- [<span data-ttu-id="55d3f-151">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="55d3f-151">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
