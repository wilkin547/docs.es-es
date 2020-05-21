---
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
ms.openlocfilehash: 15004238ee296e44ae77cd8739b7f62ea2a7a100
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762976"
---
# <a name="iclrtaskreset-method"></a><span data-ttu-id="f2800-102">ICLRTask::Reset (Método)</span><span class="sxs-lookup"><span data-stu-id="f2800-102">ICLRTask::Reset Method</span></span>
<span data-ttu-id="f2800-103">Informa al Common Language Runtime (CLR) de que el host ha completado una tarea y permite al CLR volver a usar la instancia de [ICLRTask](iclrtask-interface.md) actual para representar otra tarea.</span><span class="sxs-lookup"><span data-stu-id="f2800-103">Informs the common language runtime (CLR) that the host has completed a task, and enables the CLR to reuse the current [ICLRTask](iclrtask-interface.md) instance to represent another task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2800-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2800-104">Syntax</span></span>  
  
```cpp  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2800-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f2800-105">Parameters</span></span>  
 `fFull`  
 <span data-ttu-id="f2800-106">[in] `true` , si el tiempo de ejecución debe restablecer todos los valores estáticos relacionados con subprocesos, además de la información de seguridad y configuración regional relacionada con la `ICLRTask` instancia actual; de lo contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="f2800-106">[in] `true`, if the runtime should reset all thread-related static values in addition to the security and locale information related to the current `ICLRTask` instance; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="f2800-107">Si el valor es `true` , el tiempo de ejecución restablece los datos almacenados mediante <xref:System.Threading.Thread.AllocateDataSlot%2A> o <xref:System.Threading.Thread.AllocateNamedDataSlot%2A> .</span><span class="sxs-lookup"><span data-stu-id="f2800-107">If the value is `true`, the runtime resets data that was stored using <xref:System.Threading.Thread.AllocateDataSlot%2A> or <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2800-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f2800-108">Return Value</span></span>  
  
|<span data-ttu-id="f2800-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f2800-109">HRESULT</span></span>|<span data-ttu-id="f2800-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="f2800-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f2800-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f2800-111">S_OK</span></span>|<span data-ttu-id="f2800-112">`Reset`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="f2800-112">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="f2800-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f2800-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f2800-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada.</span><span class="sxs-lookup"><span data-stu-id="f2800-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="f2800-115">successfully</span><span class="sxs-lookup"><span data-stu-id="f2800-115">successfully</span></span>|  
|<span data-ttu-id="f2800-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f2800-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f2800-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f2800-117">The call timed out.</span></span>|  
|<span data-ttu-id="f2800-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f2800-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f2800-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="f2800-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f2800-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f2800-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f2800-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="f2800-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f2800-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f2800-122">E_FAIL</span></span>|<span data-ttu-id="f2800-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="f2800-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f2800-124">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="f2800-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f2800-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f2800-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2800-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f2800-126">Remarks</span></span>  
 <span data-ttu-id="f2800-127">CLR puede reciclar `ICLRTask` las instancias creadas previamente para evitar la sobrecarga que supone crear instancias nuevas de forma repetida cada vez que necesita una nueva tarea.</span><span class="sxs-lookup"><span data-stu-id="f2800-127">The CLR can recycle previously created `ICLRTask` instances to avoid the overhead of repeatedly creating new instances every time it needs a fresh task.</span></span> <span data-ttu-id="f2800-128">El host habilita esta característica llamando a `ICLRTask::Reset` en lugar de a [ICLRTask:: ExitTask](iclrtask-exittask-method.md) cuando ha completado una tarea.</span><span class="sxs-lookup"><span data-stu-id="f2800-128">The host enables this feature by calling `ICLRTask::Reset` instead of [ICLRTask::ExitTask](iclrtask-exittask-method.md) when it has completed a task.</span></span> <span data-ttu-id="f2800-129">En la lista siguiente se resume el ciclo de vida normal de una `ICLRTask` instancia de:</span><span class="sxs-lookup"><span data-stu-id="f2800-129">The following list summarizes the normal life cycle of an `ICLRTask` instance:</span></span>  
  
1. <span data-ttu-id="f2800-130">El tiempo de ejecución crea una nueva `ICLRTask` instancia de.</span><span class="sxs-lookup"><span data-stu-id="f2800-130">The runtime creates a new `ICLRTask` instance.</span></span>  
  
2. <span data-ttu-id="f2800-131">El Runtime llama a [IHostTaskManager:: getcurrenttask (](ihosttaskmanager-getcurrenttask-method.md) para obtener una referencia a la tarea de host actual.</span><span class="sxs-lookup"><span data-stu-id="f2800-131">The runtime calls [IHostTaskManager::GetCurrentTask](ihosttaskmanager-getcurrenttask-method.md) to get a reference to the current host task.</span></span>  
  
3. <span data-ttu-id="f2800-132">El Runtime llama a [IHostTask:: SetCLRTask (](ihosttask-setclrtask-method.md) para asociar la nueva instancia de a la tarea de host.</span><span class="sxs-lookup"><span data-stu-id="f2800-132">The runtime calls [IHostTask::SetCLRTask](ihosttask-setclrtask-method.md) to associate the new instance with the host task.</span></span>  
  
4. <span data-ttu-id="f2800-133">La tarea se ejecuta y completa.</span><span class="sxs-lookup"><span data-stu-id="f2800-133">The task executes and completes.</span></span>  
  
5. <span data-ttu-id="f2800-134">El host destruye la tarea mediante una llamada a `ICLRTask::ExitTask` .</span><span class="sxs-lookup"><span data-stu-id="f2800-134">The host destroys the task by calling `ICLRTask::ExitTask`.</span></span>  
  
 <span data-ttu-id="f2800-135">`Reset`modifica este escenario de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="f2800-135">`Reset` alters this scenario in two ways.</span></span> <span data-ttu-id="f2800-136">En el paso 5 anterior, el host llama `Reset` a para restablecer la tarea a un estado limpio y, a continuación, desacopla la `ICLRTask` instancia de su instancia de [IHostTask](ihosttask-interface.md) asociada.</span><span class="sxs-lookup"><span data-stu-id="f2800-136">In step 5 above, the host calls `Reset` to reset the task to a clean state, and then decouples the `ICLRTask` instance from its associated [IHostTask](ihosttask-interface.md) instance.</span></span> <span data-ttu-id="f2800-137">Si lo desea, el host también puede almacenar en caché la `IHostTask` instancia para su reutilización.</span><span class="sxs-lookup"><span data-stu-id="f2800-137">If desired, the host can also cache the `IHostTask` instance for reuse.</span></span> <span data-ttu-id="f2800-138">En el paso 1 anterior, el tiempo de ejecución extrae un reciclado `ICLRTask` de la memoria caché en lugar de crear una nueva instancia.</span><span class="sxs-lookup"><span data-stu-id="f2800-138">In step 1 above, the runtime pulls a recycled `ICLRTask` from the cache instead of creating a new instance.</span></span>  
  
 <span data-ttu-id="f2800-139">Este enfoque funciona bien cuando el host también tiene un grupo de tareas de trabajo reutilizables.</span><span class="sxs-lookup"><span data-stu-id="f2800-139">This approach works well when the host also has a pool of reusable worker tasks.</span></span> <span data-ttu-id="f2800-140">Cuando el host destruye una de sus `IHostTask` instancias, destruye el correspondiente `ICLRTask` mediante una llamada a `ExitTask` .</span><span class="sxs-lookup"><span data-stu-id="f2800-140">When the host destroys one of its `IHostTask` instances, it destroys the corresponding `ICLRTask` by calling `ExitTask`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2800-141">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f2800-141">Requirements</span></span>  
 <span data-ttu-id="f2800-142">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2800-142">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2800-143">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f2800-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f2800-144">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f2800-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2800-145">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2800-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2800-146">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="f2800-146">See also</span></span>

- [<span data-ttu-id="f2800-147">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f2800-147">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="f2800-148">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f2800-148">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="f2800-149">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f2800-149">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="f2800-150">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f2800-150">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
