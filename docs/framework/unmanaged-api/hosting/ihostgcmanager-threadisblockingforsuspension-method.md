---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85921156860f52eb2a898e6be356e191c2a4f02d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439275"
---
# <a name="ihostgcmanagerthreadisblockingforsuspension-method"></a><span data-ttu-id="e4a6f-102">IHostGCManager::ThreadIsBlockingForSuspension (Método)</span><span class="sxs-lookup"><span data-stu-id="e4a6f-102">IHostGCManager::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="e4a6f-103">Notifica al host que el subproceso de la que se realizó la llamada al método está a punto de bloquearse para una colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="e4a6f-103">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4a6f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4a6f-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForSuspension ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e4a6f-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e4a6f-105">Return Value</span></span>  
  
|<span data-ttu-id="e4a6f-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e4a6f-106">HRESULT</span></span>|<span data-ttu-id="e4a6f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4a6f-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e4a6f-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="e4a6f-108">S_OK</span></span>|<span data-ttu-id="e4a6f-109">`ThreadIsBlockingForSuspension` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="e4a6f-109">`ThreadIsBlockingForSuspension` returned successfully.</span></span>|  
|<span data-ttu-id="e4a6f-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e4a6f-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e4a6f-111">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="e4a6f-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e4a6f-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e4a6f-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e4a6f-113">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="e4a6f-113">The call timed out.</span></span>|  
|<span data-ttu-id="e4a6f-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e4a6f-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e4a6f-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="e4a6f-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e4a6f-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e4a6f-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e4a6f-117">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="e4a6f-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e4a6f-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e4a6f-118">E_FAIL</span></span>|<span data-ttu-id="e4a6f-119">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="e4a6f-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e4a6f-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="e4a6f-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e4a6f-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e4a6f-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4a6f-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e4a6f-122">Remarks</span></span>  
 <span data-ttu-id="e4a6f-123">CLR llama normalmente el `ThreadIsBlockForSuspension` método como preparación para una recopilación de elementos no utilizados, para dar al host una oportunidad para volver a programar el subproceso para las tareas no administradas.</span><span class="sxs-lookup"><span data-stu-id="e4a6f-123">The CLR typically calls the `ThreadIsBlockForSuspension` method in preparation for a garbage collection, to give the host an opportunity to reschedule the thread for unmanaged tasks.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e4a6f-124">El host puede programar tareas solo después de llamar a `ThreadIsBlockingForSuspension`.</span><span class="sxs-lookup"><span data-stu-id="e4a6f-124">The host can reschedule tasks only after a call to `ThreadIsBlockingForSuspension`.</span></span> <span data-ttu-id="e4a6f-125">Después de las llamadas en tiempo de ejecución [SuspensionStarting](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md), el host no debe volver a programar una tarea.</span><span class="sxs-lookup"><span data-stu-id="e4a6f-125">After the runtime calls [SuspensionStarting](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md), the host must not reschedule a task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4a6f-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e4a6f-126">Requirements</span></span>  
 <span data-ttu-id="e4a6f-127">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4a6f-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4a6f-128">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e4a6f-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e4a6f-129">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e4a6f-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e4a6f-130">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4a6f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4a6f-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4a6f-131">See Also</span></span>  
 [<span data-ttu-id="e4a6f-132">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e4a6f-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="e4a6f-133">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e4a6f-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="e4a6f-134">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e4a6f-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="e4a6f-135">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e4a6f-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="e4a6f-136">IHostGCManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e4a6f-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
