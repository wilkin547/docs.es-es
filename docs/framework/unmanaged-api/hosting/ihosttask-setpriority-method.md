---
description: 'Más información acerca de: IHostTask:: SetPriority (método)'
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
ms.openlocfilehash: c3e8fee954e5cbea2d084141a4b2d22d2fa5e95b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784644"
---
# <a name="ihosttasksetpriority-method"></a><span data-ttu-id="37aa6-103">IHostTask::SetPriority (Método)</span><span class="sxs-lookup"><span data-stu-id="37aa6-103">IHostTask::SetPriority Method</span></span>

<span data-ttu-id="37aa6-104">Solicita que el host ajuste el nivel de prioridad del subproceso para la tarea representada por la instancia de [IHostTask](ihosttask-interface.md) actual.</span><span class="sxs-lookup"><span data-stu-id="37aa6-104">Requests that the host adjust the thread priority level for the task represented by the current [IHostTask](ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37aa6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37aa6-105">Syntax</span></span>  
  
```cpp  
HRESULT SetPriority (  
    [in] int newPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37aa6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="37aa6-106">Parameters</span></span>  

 `newPriority`  
 <span data-ttu-id="37aa6-107">de Entero que representa el valor de prioridad de subproceso solicitado para la tarea representada por la `IHostTask` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="37aa6-107">[in] An integer that represents the requested thread priority value for the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="37aa6-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="37aa6-108">Return Value</span></span>  
  
|<span data-ttu-id="37aa6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="37aa6-109">HRESULT</span></span>|<span data-ttu-id="37aa6-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="37aa6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="37aa6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="37aa6-111">S_OK</span></span>|<span data-ttu-id="37aa6-112">`SetPriority` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="37aa6-112">`SetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="37aa6-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="37aa6-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="37aa6-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="37aa6-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="37aa6-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="37aa6-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="37aa6-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="37aa6-116">The call timed out.</span></span>|  
|<span data-ttu-id="37aa6-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="37aa6-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="37aa6-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="37aa6-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="37aa6-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="37aa6-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="37aa6-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="37aa6-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="37aa6-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="37aa6-121">E_FAIL</span></span>|<span data-ttu-id="37aa6-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="37aa6-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="37aa6-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="37aa6-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="37aa6-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="37aa6-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37aa6-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="37aa6-125">Remarks</span></span>  

 <span data-ttu-id="37aa6-126">A los subprocesos se les concede el tiempo de procesamiento mediante un sistema Round Robin que se basa parcialmente en el nivel de prioridad de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="37aa6-126">Threads are granted processing time using a round-robin system that is partly based on a thread's priority level.</span></span> <span data-ttu-id="37aa6-127">`SetPriority` permite que CLR establezca el nivel de prioridad de subproceso para la tarea actual.</span><span class="sxs-lookup"><span data-stu-id="37aa6-127">`SetPriority` allows the CLR to set that thread priority level for the current task.</span></span> <span data-ttu-id="37aa6-128">`newPriority`Se admiten los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="37aa6-128">The following `newPriority` values are supported.</span></span>  
  
- <span data-ttu-id="37aa6-129">THREAD_PRIORITY_ABOVE_NORMAL</span><span class="sxs-lookup"><span data-stu-id="37aa6-129">THREAD_PRIORITY_ABOVE_NORMAL</span></span>  
  
- <span data-ttu-id="37aa6-130">THREAD_PRIORITY_BELOW_NORMAL</span><span class="sxs-lookup"><span data-stu-id="37aa6-130">THREAD_PRIORITY_BELOW_NORMAL</span></span>  
  
- <span data-ttu-id="37aa6-131">THREAD_PRIORITY_HIGHEST</span><span class="sxs-lookup"><span data-stu-id="37aa6-131">THREAD_PRIORITY_HIGHEST</span></span>  
  
- <span data-ttu-id="37aa6-132">THREAD_PRIORITY_IDLE</span><span class="sxs-lookup"><span data-stu-id="37aa6-132">THREAD_PRIORITY_IDLE</span></span>  
  
- <span data-ttu-id="37aa6-133">THREAD_PRIORITY_LOWEST</span><span class="sxs-lookup"><span data-stu-id="37aa6-133">THREAD_PRIORITY_LOWEST</span></span>  
  
- <span data-ttu-id="37aa6-134">THREAD_PRIORITY_NORMAL</span><span class="sxs-lookup"><span data-stu-id="37aa6-134">THREAD_PRIORITY_NORMAL</span></span>  
  
- <span data-ttu-id="37aa6-135">THREAD_PRIORITY_TIME_CRITICAL</span><span class="sxs-lookup"><span data-stu-id="37aa6-135">THREAD_PRIORITY_TIME_CRITICAL</span></span>  
  
 <span data-ttu-id="37aa6-136">CLR llama a `SetPriority` cuando el valor de <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> se modifica mediante código de usuario.</span><span class="sxs-lookup"><span data-stu-id="37aa6-136">The CLR calls `SetPriority` when the value of the <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> is modified by user code.</span></span> <span data-ttu-id="37aa6-137">Un host puede definir sus propios algoritmos para la asignación de prioridad de subprocesos y es libre de omitir esta solicitud.</span><span class="sxs-lookup"><span data-stu-id="37aa6-137">A host can define its own algorithms for thread priority assignment, and is free to ignore this request.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="37aa6-138">`SetPriority` no informa de si se cambió el nivel de prioridad del subproceso.</span><span class="sxs-lookup"><span data-stu-id="37aa6-138">`SetPriority` does not report whether the thread priority level was changed.</span></span> <span data-ttu-id="37aa6-139">Llame a [IHostTask:: GetPriority (](ihosttask-getpriority-method.md) para determinar el valor del nivel de prioridad del subproceso de la tarea.</span><span class="sxs-lookup"><span data-stu-id="37aa6-139">Call [IHostTask::GetPriority](ihosttask-getpriority-method.md) to determine the value of the task's thread priority level.</span></span>  
  
 <span data-ttu-id="37aa6-140">La función de Win32 define los valores de nivel de prioridad del subproceso `SetThreadPriority` .</span><span class="sxs-lookup"><span data-stu-id="37aa6-140">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span> <span data-ttu-id="37aa6-141">Para obtener más información sobre la prioridad de los subprocesos, vea la documentación de la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="37aa6-141">For more information about thread priority, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37aa6-142">Requisitos</span><span class="sxs-lookup"><span data-stu-id="37aa6-142">Requirements</span></span>  

 <span data-ttu-id="37aa6-143">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37aa6-143">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37aa6-144">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="37aa6-144">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="37aa6-145">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="37aa6-145">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="37aa6-146">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37aa6-146">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37aa6-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="37aa6-147">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="37aa6-148">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="37aa6-148">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="37aa6-149">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="37aa6-149">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="37aa6-150">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="37aa6-150">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="37aa6-151">Método GetPriority</span><span class="sxs-lookup"><span data-stu-id="37aa6-151">GetPriority Method</span></span>](ihosttask-getpriority-method.md)
- [<span data-ttu-id="37aa6-152">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="37aa6-152">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
