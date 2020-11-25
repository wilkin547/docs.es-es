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
ms.openlocfilehash: 80b4bb2f6a547250acbc16a89e7396c60cc50d87
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720456"
---
# <a name="ihosttasksetpriority-method"></a><span data-ttu-id="92b46-102">IHostTask::SetPriority (Método)</span><span class="sxs-lookup"><span data-stu-id="92b46-102">IHostTask::SetPriority Method</span></span>

<span data-ttu-id="92b46-103">Solicita que el host ajuste el nivel de prioridad del subproceso para la tarea representada por la instancia de [IHostTask](ihosttask-interface.md) actual.</span><span class="sxs-lookup"><span data-stu-id="92b46-103">Requests that the host adjust the thread priority level for the task represented by the current [IHostTask](ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92b46-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="92b46-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPriority (  
    [in] int newPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92b46-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="92b46-105">Parameters</span></span>  

 `newPriority`  
 <span data-ttu-id="92b46-106">de Entero que representa el valor de prioridad de subproceso solicitado para la tarea representada por la `IHostTask` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="92b46-106">[in] An integer that represents the requested thread priority value for the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="92b46-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="92b46-107">Return Value</span></span>  
  
|<span data-ttu-id="92b46-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="92b46-108">HRESULT</span></span>|<span data-ttu-id="92b46-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="92b46-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="92b46-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="92b46-110">S_OK</span></span>|<span data-ttu-id="92b46-111">`SetPriority` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="92b46-111">`SetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="92b46-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="92b46-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="92b46-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="92b46-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="92b46-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="92b46-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="92b46-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="92b46-115">The call timed out.</span></span>|  
|<span data-ttu-id="92b46-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="92b46-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="92b46-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="92b46-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="92b46-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="92b46-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="92b46-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="92b46-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="92b46-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="92b46-120">E_FAIL</span></span>|<span data-ttu-id="92b46-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="92b46-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="92b46-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="92b46-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="92b46-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="92b46-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92b46-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="92b46-124">Remarks</span></span>  

 <span data-ttu-id="92b46-125">A los subprocesos se les concede el tiempo de procesamiento mediante un sistema Round Robin que se basa parcialmente en el nivel de prioridad de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="92b46-125">Threads are granted processing time using a round-robin system that is partly based on a thread's priority level.</span></span> <span data-ttu-id="92b46-126">`SetPriority` permite que CLR establezca el nivel de prioridad de subproceso para la tarea actual.</span><span class="sxs-lookup"><span data-stu-id="92b46-126">`SetPriority` allows the CLR to set that thread priority level for the current task.</span></span> <span data-ttu-id="92b46-127">`newPriority`Se admiten los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="92b46-127">The following `newPriority` values are supported.</span></span>  
  
- <span data-ttu-id="92b46-128">THREAD_PRIORITY_ABOVE_NORMAL</span><span class="sxs-lookup"><span data-stu-id="92b46-128">THREAD_PRIORITY_ABOVE_NORMAL</span></span>  
  
- <span data-ttu-id="92b46-129">THREAD_PRIORITY_BELOW_NORMAL</span><span class="sxs-lookup"><span data-stu-id="92b46-129">THREAD_PRIORITY_BELOW_NORMAL</span></span>  
  
- <span data-ttu-id="92b46-130">THREAD_PRIORITY_HIGHEST</span><span class="sxs-lookup"><span data-stu-id="92b46-130">THREAD_PRIORITY_HIGHEST</span></span>  
  
- <span data-ttu-id="92b46-131">THREAD_PRIORITY_IDLE</span><span class="sxs-lookup"><span data-stu-id="92b46-131">THREAD_PRIORITY_IDLE</span></span>  
  
- <span data-ttu-id="92b46-132">THREAD_PRIORITY_LOWEST</span><span class="sxs-lookup"><span data-stu-id="92b46-132">THREAD_PRIORITY_LOWEST</span></span>  
  
- <span data-ttu-id="92b46-133">THREAD_PRIORITY_NORMAL</span><span class="sxs-lookup"><span data-stu-id="92b46-133">THREAD_PRIORITY_NORMAL</span></span>  
  
- <span data-ttu-id="92b46-134">THREAD_PRIORITY_TIME_CRITICAL</span><span class="sxs-lookup"><span data-stu-id="92b46-134">THREAD_PRIORITY_TIME_CRITICAL</span></span>  
  
 <span data-ttu-id="92b46-135">CLR llama a `SetPriority` cuando el valor de <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> se modifica mediante código de usuario.</span><span class="sxs-lookup"><span data-stu-id="92b46-135">The CLR calls `SetPriority` when the value of the <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> is modified by user code.</span></span> <span data-ttu-id="92b46-136">Un host puede definir sus propios algoritmos para la asignación de prioridad de subprocesos y es libre de omitir esta solicitud.</span><span class="sxs-lookup"><span data-stu-id="92b46-136">A host can define its own algorithms for thread priority assignment, and is free to ignore this request.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="92b46-137">`SetPriority` no informa de si se cambió el nivel de prioridad del subproceso.</span><span class="sxs-lookup"><span data-stu-id="92b46-137">`SetPriority` does not report whether the thread priority level was changed.</span></span> <span data-ttu-id="92b46-138">Llame a [IHostTask:: GetPriority (](ihosttask-getpriority-method.md) para determinar el valor del nivel de prioridad del subproceso de la tarea.</span><span class="sxs-lookup"><span data-stu-id="92b46-138">Call [IHostTask::GetPriority](ihosttask-getpriority-method.md) to determine the value of the task's thread priority level.</span></span>  
  
 <span data-ttu-id="92b46-139">La función de Win32 define los valores de nivel de prioridad del subproceso `SetThreadPriority` .</span><span class="sxs-lookup"><span data-stu-id="92b46-139">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span> <span data-ttu-id="92b46-140">Para obtener más información sobre la prioridad de los subprocesos, vea la documentación de la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="92b46-140">For more information about thread priority, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92b46-141">Requisitos</span><span class="sxs-lookup"><span data-stu-id="92b46-141">Requirements</span></span>  

 <span data-ttu-id="92b46-142">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92b46-142">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92b46-143">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="92b46-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="92b46-144">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="92b46-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="92b46-145">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92b46-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92b46-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="92b46-146">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="92b46-147">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="92b46-147">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="92b46-148">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="92b46-148">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="92b46-149">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="92b46-149">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="92b46-150">Método GetPriority</span><span class="sxs-lookup"><span data-stu-id="92b46-150">GetPriority Method</span></span>](ihosttask-getpriority-method.md)
- [<span data-ttu-id="92b46-151">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="92b46-151">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
