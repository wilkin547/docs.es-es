---
description: 'Más información sobre: IHostGCManager:: SuspensionStarting ((método)'
title: IHostGCManager::SuspensionStarting (Método)
ms.date: 03/30/2017
api_name:
- IHostGCManager.SuspensionStarting
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::SuspensionStarting
helpviewer_keywords:
- SuspensionStarting method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionStarting method [.NET Framework hosting]
ms.assetid: c381f524-94cf-4fa2-9298-50f847a03431
topic_type:
- apiref
ms.openlocfilehash: 3a57d47fea735ab004fd0db293bed1ba4d3314e6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708650"
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="87e08-103">IHostGCManager::SuspensionStarting (Método)</span><span class="sxs-lookup"><span data-stu-id="87e08-103">IHostGCManager::SuspensionStarting Method</span></span>

<span data-ttu-id="87e08-104">Notifica al host que el Common Language Runtime (CLR) está suspendiendo la ejecución de las tareas, para realizar una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="87e08-104">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87e08-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="87e08-105">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="87e08-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="87e08-106">Return Value</span></span>  
  
|<span data-ttu-id="87e08-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="87e08-107">HRESULT</span></span>|<span data-ttu-id="87e08-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="87e08-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="87e08-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="87e08-109">S_OK</span></span>|<span data-ttu-id="87e08-110">`SuspensionStarting` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="87e08-110">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="87e08-111">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="87e08-111">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="87e08-112">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="87e08-112">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="87e08-113">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="87e08-113">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="87e08-114">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="87e08-114">The call timed out.</span></span>|  
|<span data-ttu-id="87e08-115">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="87e08-115">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="87e08-116">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="87e08-116">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="87e08-117">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="87e08-117">HOST_E_ABANDONED</span></span>|<span data-ttu-id="87e08-118">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="87e08-118">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="87e08-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="87e08-119">E_FAIL</span></span>|<span data-ttu-id="87e08-120">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="87e08-120">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="87e08-121">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="87e08-121">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="87e08-122">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="87e08-122">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87e08-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="87e08-123">Remarks</span></span>  

 <span data-ttu-id="87e08-124">Las llamadas CLR `SuspensionStarting` para informar al host de que se está produciendo la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="87e08-124">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="87e08-125">No vuelva a programar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="87e08-125">Do not reschedule this task.</span></span> <span data-ttu-id="87e08-126">El host debe volver a programar una tarea cuando se llama a [ThreadIsBlockingForSuspension (](ihostgcmanager-threadisblockingforsuspension-method.md) .</span><span class="sxs-lookup"><span data-stu-id="87e08-126">The host must reschedule a task when [ThreadIsBlockingForSuspension](ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87e08-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="87e08-127">Requirements</span></span>  

 <span data-ttu-id="87e08-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87e08-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87e08-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="87e08-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="87e08-130">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="87e08-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87e08-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87e08-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87e08-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="87e08-132">See also</span></span>

- [<span data-ttu-id="87e08-133">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="87e08-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="87e08-134">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="87e08-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="87e08-135">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="87e08-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="87e08-136">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="87e08-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="87e08-137">IHostGCManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="87e08-137">IHostGCManager Interface</span></span>](ihostgcmanager-interface.md)
