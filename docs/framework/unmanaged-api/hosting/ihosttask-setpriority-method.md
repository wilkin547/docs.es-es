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
ms.openlocfilehash: a73982cb4cb7b6e80579714b32cf7aba620272af
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57467109"
---
# <a name="ihosttasksetpriority-method"></a><span data-ttu-id="6f303-102">IHostTask::SetPriority (Método)</span><span class="sxs-lookup"><span data-stu-id="6f303-102">IHostTask::SetPriority Method</span></span>
<span data-ttu-id="6f303-103">Solicita que el host ajuste la prioridad del subproceso de nivel de la tarea representada por el actual [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instancia.</span><span class="sxs-lookup"><span data-stu-id="6f303-103">Requests that the host adjust the thread priority level for the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f303-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6f303-104">Syntax</span></span>  
  
```  
HRESULT SetPriority (  
    [in] int newPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f303-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6f303-105">Parameters</span></span>  
 `newPriority`  
 <span data-ttu-id="6f303-106">[in] Un entero que representa el valor de prioridad de subproceso solicitado para la tarea representada por el actual `IHostTask` instancia.</span><span class="sxs-lookup"><span data-stu-id="6f303-106">[in] An integer that represents the requested thread priority value for the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f303-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6f303-107">Return Value</span></span>  
  
|<span data-ttu-id="6f303-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6f303-108">HRESULT</span></span>|<span data-ttu-id="6f303-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="6f303-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6f303-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6f303-110">S_OK</span></span>|<span data-ttu-id="6f303-111">`SetPriority` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="6f303-111">`SetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="6f303-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6f303-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6f303-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="6f303-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6f303-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6f303-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6f303-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="6f303-115">The call timed out.</span></span>|  
|<span data-ttu-id="6f303-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6f303-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6f303-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="6f303-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6f303-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6f303-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6f303-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="6f303-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6f303-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6f303-120">E_FAIL</span></span>|<span data-ttu-id="6f303-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="6f303-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6f303-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="6f303-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6f303-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6f303-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f303-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6f303-124">Remarks</span></span>  
 <span data-ttu-id="6f303-125">Los subprocesos se usa un sistema de operación por turnos que se basa parcialmente en el nivel de prioridad de un subproceso de tiempo de procesamiento concedido.</span><span class="sxs-lookup"><span data-stu-id="6f303-125">Threads are granted processing time using a round-robin system that is partly based on a thread's priority level.</span></span> <span data-ttu-id="6f303-126">`SetPriority` permite que el CLR establecer ese nivel de prioridad de subproceso de la tarea actual.</span><span class="sxs-lookup"><span data-stu-id="6f303-126">`SetPriority` allows the CLR to set that thread priority level for the current task.</span></span> <span data-ttu-id="6f303-127">La siguiente `newPriority` se admiten los valores.</span><span class="sxs-lookup"><span data-stu-id="6f303-127">The following `newPriority` values are supported.</span></span>  
  
-   <span data-ttu-id="6f303-128">THREAD_PRIORITY_ABOVE_NORMAL</span><span class="sxs-lookup"><span data-stu-id="6f303-128">THREAD_PRIORITY_ABOVE_NORMAL</span></span>  
  
-   <span data-ttu-id="6f303-129">THREAD_PRIORITY_BELOW_NORMAL</span><span class="sxs-lookup"><span data-stu-id="6f303-129">THREAD_PRIORITY_BELOW_NORMAL</span></span>  
  
-   <span data-ttu-id="6f303-130">THREAD_PRIORITY_HIGHEST</span><span class="sxs-lookup"><span data-stu-id="6f303-130">THREAD_PRIORITY_HIGHEST</span></span>  
  
-   <span data-ttu-id="6f303-131">THREAD_PRIORITY_IDLE</span><span class="sxs-lookup"><span data-stu-id="6f303-131">THREAD_PRIORITY_IDLE</span></span>  
  
-   <span data-ttu-id="6f303-132">THREAD_PRIORITY_LOWEST</span><span class="sxs-lookup"><span data-stu-id="6f303-132">THREAD_PRIORITY_LOWEST</span></span>  
  
-   <span data-ttu-id="6f303-133">THREAD_PRIORITY_NORMAL</span><span class="sxs-lookup"><span data-stu-id="6f303-133">THREAD_PRIORITY_NORMAL</span></span>  
  
-   <span data-ttu-id="6f303-134">THREAD_PRIORITY_TIME_CRITICAL</span><span class="sxs-lookup"><span data-stu-id="6f303-134">THREAD_PRIORITY_TIME_CRITICAL</span></span>  
  
 <span data-ttu-id="6f303-135">CLR llama a `SetPriority` cuando el valor de la <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> modificado por código de usuario.</span><span class="sxs-lookup"><span data-stu-id="6f303-135">The CLR calls `SetPriority` when the value of the <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> is modified by user code.</span></span> <span data-ttu-id="6f303-136">Un host puede definir sus propios algoritmos para la asignación de prioridad de subproceso y es libre de omitir esta solicitud.</span><span class="sxs-lookup"><span data-stu-id="6f303-136">A host can define its own algorithms for thread priority assignment, and is free to ignore this request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f303-137">`SetPriority` no informa de si se ha cambiado el nivel de prioridad de subproceso.</span><span class="sxs-lookup"><span data-stu-id="6f303-137">`SetPriority` does not report whether the thread priority level was changed.</span></span> <span data-ttu-id="6f303-138">Llame a [IHostTask:: GetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md) para determinar el valor del nivel de prioridad de subproceso de la tarea.</span><span class="sxs-lookup"><span data-stu-id="6f303-138">Call [IHostTask::GetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md) to determine the value of the task's thread priority level.</span></span>  
  
 <span data-ttu-id="6f303-139">Definen los valores de nivel de prioridad de subproceso Win32 `SetThreadPriority` función.</span><span class="sxs-lookup"><span data-stu-id="6f303-139">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span> <span data-ttu-id="6f303-140">Para obtener más información acerca de la prioridad de subproceso, vea la documentación de la plataforma de Windows.</span><span class="sxs-lookup"><span data-stu-id="6f303-140">For more information about thread priority, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f303-141">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6f303-141">Requirements</span></span>  
 <span data-ttu-id="6f303-142">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f303-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f303-143">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6f303-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6f303-144">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6f303-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6f303-145">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f303-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f303-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f303-146">See also</span></span>
- <xref:System.Threading.Thread>
- [<span data-ttu-id="6f303-147">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6f303-147">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="6f303-148">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6f303-148">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="6f303-149">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6f303-149">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="6f303-150">GetPriority (método)</span><span class="sxs-lookup"><span data-stu-id="6f303-150">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)
- [<span data-ttu-id="6f303-151">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6f303-151">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
