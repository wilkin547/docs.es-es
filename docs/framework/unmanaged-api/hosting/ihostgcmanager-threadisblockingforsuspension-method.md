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
ms.openlocfilehash: c0c59d9f5abb200b17d3c46915e73fd3b9e9c8fd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780576"
---
# <a name="ihostgcmanagerthreadisblockingforsuspension-method"></a><span data-ttu-id="73ff3-102">IHostGCManager::ThreadIsBlockingForSuspension (Método)</span><span class="sxs-lookup"><span data-stu-id="73ff3-102">IHostGCManager::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="73ff3-103">Notifica al host que el subproceso desde el que se realizó la llamada al método está a punto de bloquearse para una recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="73ff3-103">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73ff3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73ff3-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForSuspension ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="73ff3-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="73ff3-105">Return Value</span></span>  
  
|<span data-ttu-id="73ff3-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="73ff3-106">HRESULT</span></span>|<span data-ttu-id="73ff3-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="73ff3-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="73ff3-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="73ff3-108">S_OK</span></span>|<span data-ttu-id="73ff3-109">`ThreadIsBlockingForSuspension` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="73ff3-109">`ThreadIsBlockingForSuspension` returned successfully.</span></span>|  
|<span data-ttu-id="73ff3-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="73ff3-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="73ff3-111">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="73ff3-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="73ff3-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="73ff3-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="73ff3-113">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="73ff3-113">The call timed out.</span></span>|  
|<span data-ttu-id="73ff3-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="73ff3-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="73ff3-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="73ff3-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="73ff3-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="73ff3-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="73ff3-117">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="73ff3-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="73ff3-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="73ff3-118">E_FAIL</span></span>|<span data-ttu-id="73ff3-119">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="73ff3-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="73ff3-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="73ff3-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="73ff3-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="73ff3-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73ff3-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="73ff3-122">Remarks</span></span>  
 <span data-ttu-id="73ff3-123">CLR llama normalmente el `ThreadIsBlockForSuspension` método como preparación para una colección de elementos no utilizados, para dar al host una oportunidad para volver a programar el subproceso para las tareas no administradas.</span><span class="sxs-lookup"><span data-stu-id="73ff3-123">The CLR typically calls the `ThreadIsBlockForSuspension` method in preparation for a garbage collection, to give the host an opportunity to reschedule the thread for unmanaged tasks.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="73ff3-124">El host puede programar tareas solo después de llamar a `ThreadIsBlockingForSuspension`.</span><span class="sxs-lookup"><span data-stu-id="73ff3-124">The host can reschedule tasks only after a call to `ThreadIsBlockingForSuspension`.</span></span> <span data-ttu-id="73ff3-125">Después de las llamadas en tiempo de ejecución [SuspensionStarting](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md), el host no debe volver a programar una tarea.</span><span class="sxs-lookup"><span data-stu-id="73ff3-125">After the runtime calls [SuspensionStarting](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md), the host must not reschedule a task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73ff3-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="73ff3-126">Requirements</span></span>  
 <span data-ttu-id="73ff3-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73ff3-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73ff3-128">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="73ff3-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="73ff3-129">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="73ff3-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="73ff3-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73ff3-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73ff3-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="73ff3-131">See also</span></span>

- [<span data-ttu-id="73ff3-132">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="73ff3-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="73ff3-133">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="73ff3-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="73ff3-134">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="73ff3-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="73ff3-135">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="73ff3-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="73ff3-136">IHostGCManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="73ff3-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
