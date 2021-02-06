---
description: 'Más información acerca de: ICLRTask:: RESET (método)'
title: ICLRTask::Reset (Método)
ms.date: 03/30/2017
api_name:
- ICLRTask.Reset
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::Reset
helpviewer_keywords:
- ICLRTask::Reset method [.NET Framework hosting]
- Reset method, ICLRTask interface [.NET Framework hosting]
ms.assetid: 1bfb5d3a-0ffd-4bb4-9bf6-aec00cb675b7
topic_type:
- apiref
ms.openlocfilehash: d30738b98003e0543c1a2a31c7471b15811efe5f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636993"
---
# <a name="iclrtaskreset-method"></a><span data-ttu-id="420b1-103">ICLRTask::Reset (Método)</span><span class="sxs-lookup"><span data-stu-id="420b1-103">ICLRTask::Reset Method</span></span>

<span data-ttu-id="420b1-104">Informa al Common Language Runtime (CLR) de que el host ha completado una tarea y permite al CLR volver a usar la instancia de [ICLRTask](iclrtask-interface.md) actual para representar otra tarea.</span><span class="sxs-lookup"><span data-stu-id="420b1-104">Informs the common language runtime (CLR) that the host has completed a task, and enables the CLR to reuse the current [ICLRTask](iclrtask-interface.md) instance to represent another task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="420b1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="420b1-105">Syntax</span></span>  
  
```cpp  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="420b1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="420b1-106">Parameters</span></span>  

 `fFull`  
 <span data-ttu-id="420b1-107">[in] `true` , si el tiempo de ejecución debe restablecer todos los valores estáticos relacionados con subprocesos, además de la información de seguridad y configuración regional relacionada con la `ICLRTask` instancia actual; de lo contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="420b1-107">[in] `true`, if the runtime should reset all thread-related static values in addition to the security and locale information related to the current `ICLRTask` instance; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="420b1-108">Si el valor es `true` , el tiempo de ejecución restablece los datos almacenados mediante <xref:System.Threading.Thread.AllocateDataSlot%2A> o <xref:System.Threading.Thread.AllocateNamedDataSlot%2A> .</span><span class="sxs-lookup"><span data-stu-id="420b1-108">If the value is `true`, the runtime resets data that was stored using <xref:System.Threading.Thread.AllocateDataSlot%2A> or <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="420b1-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="420b1-109">Return Value</span></span>  
  
|<span data-ttu-id="420b1-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="420b1-110">HRESULT</span></span>|<span data-ttu-id="420b1-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="420b1-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="420b1-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="420b1-112">S_OK</span></span>|<span data-ttu-id="420b1-113">`Reset` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="420b1-113">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="420b1-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="420b1-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="420b1-115">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada.</span><span class="sxs-lookup"><span data-stu-id="420b1-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="420b1-116">successfully</span><span class="sxs-lookup"><span data-stu-id="420b1-116">successfully</span></span>|  
|<span data-ttu-id="420b1-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="420b1-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="420b1-118">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="420b1-118">The call timed out.</span></span>|  
|<span data-ttu-id="420b1-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="420b1-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="420b1-120">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="420b1-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="420b1-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="420b1-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="420b1-122">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="420b1-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="420b1-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="420b1-123">E_FAIL</span></span>|<span data-ttu-id="420b1-124">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="420b1-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="420b1-125">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="420b1-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="420b1-126">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="420b1-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="420b1-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="420b1-127">Remarks</span></span>  

 <span data-ttu-id="420b1-128">CLR puede reciclar `ICLRTask` las instancias creadas previamente para evitar la sobrecarga que supone crear instancias nuevas de forma repetida cada vez que necesita una nueva tarea.</span><span class="sxs-lookup"><span data-stu-id="420b1-128">The CLR can recycle previously created `ICLRTask` instances to avoid the overhead of repeatedly creating new instances every time it needs a fresh task.</span></span> <span data-ttu-id="420b1-129">El host habilita esta característica llamando a `ICLRTask::Reset` en lugar de a [ICLRTask:: ExitTask](iclrtask-exittask-method.md) cuando ha completado una tarea.</span><span class="sxs-lookup"><span data-stu-id="420b1-129">The host enables this feature by calling `ICLRTask::Reset` instead of [ICLRTask::ExitTask](iclrtask-exittask-method.md) when it has completed a task.</span></span> <span data-ttu-id="420b1-130">En la lista siguiente se resume el ciclo de vida normal de una `ICLRTask` instancia de:</span><span class="sxs-lookup"><span data-stu-id="420b1-130">The following list summarizes the normal life cycle of an `ICLRTask` instance:</span></span>  
  
1. <span data-ttu-id="420b1-131">El tiempo de ejecución crea una nueva `ICLRTask` instancia de.</span><span class="sxs-lookup"><span data-stu-id="420b1-131">The runtime creates a new `ICLRTask` instance.</span></span>  
  
2. <span data-ttu-id="420b1-132">El Runtime llama a [IHostTaskManager:: getcurrenttask (](ihosttaskmanager-getcurrenttask-method.md) para obtener una referencia a la tarea de host actual.</span><span class="sxs-lookup"><span data-stu-id="420b1-132">The runtime calls [IHostTaskManager::GetCurrentTask](ihosttaskmanager-getcurrenttask-method.md) to get a reference to the current host task.</span></span>  
  
3. <span data-ttu-id="420b1-133">El Runtime llama a [IHostTask:: SetCLRTask (](ihosttask-setclrtask-method.md) para asociar la nueva instancia de a la tarea de host.</span><span class="sxs-lookup"><span data-stu-id="420b1-133">The runtime calls [IHostTask::SetCLRTask](ihosttask-setclrtask-method.md) to associate the new instance with the host task.</span></span>  
  
4. <span data-ttu-id="420b1-134">La tarea se ejecuta y completa.</span><span class="sxs-lookup"><span data-stu-id="420b1-134">The task executes and completes.</span></span>  
  
5. <span data-ttu-id="420b1-135">El host destruye la tarea mediante una llamada a `ICLRTask::ExitTask` .</span><span class="sxs-lookup"><span data-stu-id="420b1-135">The host destroys the task by calling `ICLRTask::ExitTask`.</span></span>  
  
 <span data-ttu-id="420b1-136">`Reset` modifica este escenario de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="420b1-136">`Reset` alters this scenario in two ways.</span></span> <span data-ttu-id="420b1-137">En el paso 5 anterior, el host llama `Reset` a para restablecer la tarea a un estado limpio y, a continuación, desacopla la `ICLRTask` instancia de su instancia de [IHostTask](ihosttask-interface.md) asociada.</span><span class="sxs-lookup"><span data-stu-id="420b1-137">In step 5 above, the host calls `Reset` to reset the task to a clean state, and then decouples the `ICLRTask` instance from its associated [IHostTask](ihosttask-interface.md) instance.</span></span> <span data-ttu-id="420b1-138">Si lo desea, el host también puede almacenar en caché la `IHostTask` instancia para su reutilización.</span><span class="sxs-lookup"><span data-stu-id="420b1-138">If desired, the host can also cache the `IHostTask` instance for reuse.</span></span> <span data-ttu-id="420b1-139">En el paso 1 anterior, el tiempo de ejecución extrae un reciclado `ICLRTask` de la memoria caché en lugar de crear una nueva instancia.</span><span class="sxs-lookup"><span data-stu-id="420b1-139">In step 1 above, the runtime pulls a recycled `ICLRTask` from the cache instead of creating a new instance.</span></span>  
  
 <span data-ttu-id="420b1-140">Este enfoque funciona bien cuando el host también tiene un grupo de tareas de trabajo reutilizables.</span><span class="sxs-lookup"><span data-stu-id="420b1-140">This approach works well when the host also has a pool of reusable worker tasks.</span></span> <span data-ttu-id="420b1-141">Cuando el host destruye una de sus `IHostTask` instancias, destruye el correspondiente `ICLRTask` mediante una llamada a `ExitTask` .</span><span class="sxs-lookup"><span data-stu-id="420b1-141">When the host destroys one of its `IHostTask` instances, it destroys the corresponding `ICLRTask` by calling `ExitTask`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="420b1-142">Requisitos</span><span class="sxs-lookup"><span data-stu-id="420b1-142">Requirements</span></span>  

 <span data-ttu-id="420b1-143">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="420b1-143">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="420b1-144">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="420b1-144">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="420b1-145">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="420b1-145">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="420b1-146">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="420b1-146">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="420b1-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="420b1-147">See also</span></span>

- [<span data-ttu-id="420b1-148">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="420b1-148">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="420b1-149">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="420b1-149">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="420b1-150">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="420b1-150">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="420b1-151">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="420b1-151">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
