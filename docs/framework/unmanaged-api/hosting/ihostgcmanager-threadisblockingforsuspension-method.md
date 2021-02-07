---
description: 'Más información sobre: IHostGCManager:: ThreadIsBlockingForSuspension ((método)'
title: IHostGCManager::ThreadIsBlockingForSuspension (Método)
ms.date: 03/30/2017
api_name:
- IHostGCManager.ThreadIsBlockingForSuspension
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension
helpviewer_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: 2657d45d-26d2-4d0a-8473-32b652e3321d
topic_type:
- apiref
ms.openlocfilehash: 9cb07b80fa9aad1ac289bc5a3abb5a4760f2bfc9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708647"
---
# <a name="ihostgcmanagerthreadisblockingforsuspension-method"></a><span data-ttu-id="45a3d-103">IHostGCManager::ThreadIsBlockingForSuspension (Método)</span><span class="sxs-lookup"><span data-stu-id="45a3d-103">IHostGCManager::ThreadIsBlockingForSuspension Method</span></span>

<span data-ttu-id="45a3d-104">Notifica al host que el subproceso del que se realizó la llamada al método está a punto de bloquearse para una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="45a3d-104">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45a3d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45a3d-105">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForSuspension ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="45a3d-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="45a3d-106">Return Value</span></span>  
  
|<span data-ttu-id="45a3d-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="45a3d-107">HRESULT</span></span>|<span data-ttu-id="45a3d-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="45a3d-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="45a3d-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="45a3d-109">S_OK</span></span>|<span data-ttu-id="45a3d-110">`ThreadIsBlockingForSuspension` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="45a3d-110">`ThreadIsBlockingForSuspension` returned successfully.</span></span>|  
|<span data-ttu-id="45a3d-111">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="45a3d-111">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="45a3d-112">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="45a3d-112">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="45a3d-113">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="45a3d-113">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="45a3d-114">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="45a3d-114">The call timed out.</span></span>|  
|<span data-ttu-id="45a3d-115">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="45a3d-115">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="45a3d-116">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="45a3d-116">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="45a3d-117">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="45a3d-117">HOST_E_ABANDONED</span></span>|<span data-ttu-id="45a3d-118">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="45a3d-118">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="45a3d-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="45a3d-119">E_FAIL</span></span>|<span data-ttu-id="45a3d-120">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="45a3d-120">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="45a3d-121">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="45a3d-121">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="45a3d-122">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="45a3d-122">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45a3d-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="45a3d-123">Remarks</span></span>  

 <span data-ttu-id="45a3d-124">El CLR normalmente llama al `ThreadIsBlockForSuspension` método como preparación para una recolección de elementos no utilizados, para dar al host una oportunidad de volver a programar el subproceso para las tareas no administradas.</span><span class="sxs-lookup"><span data-stu-id="45a3d-124">The CLR typically calls the `ThreadIsBlockForSuspension` method in preparation for a garbage collection, to give the host an opportunity to reschedule the thread for unmanaged tasks.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="45a3d-125">El host puede volver a programar las tareas solo después de una llamada a `ThreadIsBlockingForSuspension` .</span><span class="sxs-lookup"><span data-stu-id="45a3d-125">The host can reschedule tasks only after a call to `ThreadIsBlockingForSuspension`.</span></span> <span data-ttu-id="45a3d-126">Una vez que el Runtime llama a [SuspensionStarting (](ihostgcmanager-suspensionstarting-method.md), el host no debe volver a programar una tarea.</span><span class="sxs-lookup"><span data-stu-id="45a3d-126">After the runtime calls [SuspensionStarting](ihostgcmanager-suspensionstarting-method.md), the host must not reschedule a task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45a3d-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="45a3d-127">Requirements</span></span>  

 <span data-ttu-id="45a3d-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45a3d-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45a3d-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="45a3d-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="45a3d-130">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="45a3d-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="45a3d-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45a3d-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45a3d-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="45a3d-132">See also</span></span>

- [<span data-ttu-id="45a3d-133">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="45a3d-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="45a3d-134">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="45a3d-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="45a3d-135">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="45a3d-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="45a3d-136">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="45a3d-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="45a3d-137">IHostGCManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="45a3d-137">IHostGCManager Interface</span></span>](ihostgcmanager-interface.md)
