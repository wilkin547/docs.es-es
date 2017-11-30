---
title: "ICLRTask::Reset (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.Reset
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::Reset
helpviewer_keywords:
- ICLRTask::Reset method [.NET Framework hosting]
- Reset method, ICLRTask interface [.NET Framework hosting]
ms.assetid: 1bfb5d3a-0ffd-4bb4-9bf6-aec00cb675b7
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7c50dc4770665e2b049f41a105b58231221b8e9c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskreset-method"></a><span data-ttu-id="d243e-102">ICLRTask::Reset (Método)</span><span class="sxs-lookup"><span data-stu-id="d243e-102">ICLRTask::Reset Method</span></span>
<span data-ttu-id="d243e-103">Informa a common language runtime (CLR) que el host ha finalizado una tarea y permite a CLR reutilizar actual [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instancia para representar otra tarea.</span><span class="sxs-lookup"><span data-stu-id="d243e-103">Informs the common language runtime (CLR) that the host has completed a task, and enables the CLR to reuse the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance to represent another task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d243e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d243e-104">Syntax</span></span>  
  
```  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d243e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d243e-105">Parameters</span></span>  
 `fFull`  
 <span data-ttu-id="d243e-106">[in] `true`, si el tiempo de ejecución debe restablecer todos los valores estáticos relacionados con los subprocesos además de la información de seguridad y la configuración regional actual relacionada con `ICLRTask` instancia; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="d243e-106">[in] `true`, if the runtime should reset all thread-related static values in addition to the security and locale information related to the current `ICLRTask` instance; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="d243e-107">Si el valor es `true`, el tiempo de ejecución restablece los datos que se almacenan con <xref:System.Threading.Thread.AllocateDataSlot%2A> o <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.</span><span class="sxs-lookup"><span data-stu-id="d243e-107">If the value is `true`, the runtime resets data that was stored using <xref:System.Threading.Thread.AllocateDataSlot%2A> or <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d243e-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d243e-108">Return Value</span></span>  
  
|<span data-ttu-id="d243e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d243e-109">HRESULT</span></span>|<span data-ttu-id="d243e-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="d243e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d243e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d243e-111">S_OK</span></span>|<span data-ttu-id="d243e-112">`Reset`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="d243e-112">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="d243e-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d243e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d243e-114">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada.</span><span class="sxs-lookup"><span data-stu-id="d243e-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="d243e-115">correctamente</span><span class="sxs-lookup"><span data-stu-id="d243e-115">successfully</span></span>|  
|<span data-ttu-id="d243e-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d243e-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d243e-117">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="d243e-117">The call timed out.</span></span>|  
|<span data-ttu-id="d243e-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d243e-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d243e-119">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="d243e-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d243e-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d243e-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d243e-121">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="d243e-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d243e-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d243e-122">E_FAIL</span></span>|<span data-ttu-id="d243e-123">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="d243e-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d243e-124">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="d243e-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d243e-125">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d243e-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d243e-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d243e-126">Remarks</span></span>  
 <span data-ttu-id="d243e-127">El CLR se puede reciclar creado anteriormente `ICLRTask` instancias para evitar la sobrecarga que supone crear repetidamente nuevas instancias cada vez que necesita una tarea nueva.</span><span class="sxs-lookup"><span data-stu-id="d243e-127">The CLR can recycle previously created `ICLRTask` instances to avoid the overhead of repeatedly creating new instances every time it needs a fresh task.</span></span> <span data-ttu-id="d243e-128">El host habilita esta característica mediante una llamada a `ICLRTask::Reset` en lugar de [ICLRTask:: ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md) cuándo se ha completado una tarea.</span><span class="sxs-lookup"><span data-stu-id="d243e-128">The host enables this feature by calling `ICLRTask::Reset` instead of [ICLRTask::ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md) when it has completed a task.</span></span> <span data-ttu-id="d243e-129">En la lista siguiente se resume el ciclo de vida normal de una `ICLRTask` instancia:</span><span class="sxs-lookup"><span data-stu-id="d243e-129">The following list summarizes the normal life cycle of an `ICLRTask` instance:</span></span>  
  
1.  <span data-ttu-id="d243e-130">El tiempo de ejecución crea un nuevo `ICLRTask` instancia.</span><span class="sxs-lookup"><span data-stu-id="d243e-130">The runtime creates a new `ICLRTask` instance.</span></span>  
  
2.  <span data-ttu-id="d243e-131">El runtime llama [IHostTaskManager:: GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md) para obtener una referencia a la tarea actual del host.</span><span class="sxs-lookup"><span data-stu-id="d243e-131">The runtime calls [IHostTaskManager::GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md) to get a reference to the current host task.</span></span>  
  
3.  <span data-ttu-id="d243e-132">El runtime llama [IHostTask:: SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md) para asociar la nueva instancia de la tarea del host.</span><span class="sxs-lookup"><span data-stu-id="d243e-132">The runtime calls [IHostTask::SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md) to associate the new instance with the host task.</span></span>  
  
4.  <span data-ttu-id="d243e-133">La tarea se ejecuta y completa.</span><span class="sxs-lookup"><span data-stu-id="d243e-133">The task executes and completes.</span></span>  
  
5.  <span data-ttu-id="d243e-134">El host destruye la tarea mediante una llamada a `ICLRTask::ExitTask`.</span><span class="sxs-lookup"><span data-stu-id="d243e-134">The host destroys the task by calling `ICLRTask::ExitTask`.</span></span>  
  
 <span data-ttu-id="d243e-135">`Reset`modifica este escenario de dos maneras.</span><span class="sxs-lookup"><span data-stu-id="d243e-135">`Reset` alters this scenario in two ways.</span></span> <span data-ttu-id="d243e-136">En el paso 5 anterior, el host llama `Reset` para restablecer la tarea a un estado limpio y, a continuación, se desacopla el `ICLRTask` instancia a partir de su asociado [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instancia.</span><span class="sxs-lookup"><span data-stu-id="d243e-136">In step 5 above, the host calls `Reset` to reset the task to a clean state, and then decouples the `ICLRTask` instance from its associated [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span> <span data-ttu-id="d243e-137">Si lo desea, el host puede almacenar en caché el `IHostTask` instancia para su reutilización.</span><span class="sxs-lookup"><span data-stu-id="d243e-137">If desired, the host can also cache the `IHostTask` instance for reuse.</span></span> <span data-ttu-id="d243e-138">En el paso 1 anterior, el tiempo de ejecución extrae un reciclado `ICLRTask` de la memoria caché en lugar de crear una nueva instancia.</span><span class="sxs-lookup"><span data-stu-id="d243e-138">In step 1 above, the runtime pulls a recycled `ICLRTask` from the cache instead of creating a new instance.</span></span>  
  
 <span data-ttu-id="d243e-139">Este enfoque funciona bien cuando el host también tiene un grupo de tareas de trabajo reutilizables.</span><span class="sxs-lookup"><span data-stu-id="d243e-139">This approach works well when the host also has a pool of reusable worker tasks.</span></span> <span data-ttu-id="d243e-140">Cuando el host destruye una de sus `IHostTask` instancias, se destruirán correspondiente `ICLRTask` mediante una llamada a `ExitTask`.</span><span class="sxs-lookup"><span data-stu-id="d243e-140">When the host destroys one of its `IHostTask` instances, it destroys the corresponding `ICLRTask` by calling `ExitTask`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d243e-141">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d243e-141">Requirements</span></span>  
 <span data-ttu-id="d243e-142">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d243e-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d243e-143">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d243e-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d243e-144">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d243e-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d243e-145">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d243e-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d243e-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="d243e-146">See Also</span></span>  
 [<span data-ttu-id="d243e-147">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d243e-147">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="d243e-148">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d243e-148">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="d243e-149">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d243e-149">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="d243e-150">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d243e-150">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
