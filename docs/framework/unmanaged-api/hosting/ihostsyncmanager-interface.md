---
title: IHostSyncManager (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager
helpviewer_keywords:
- IHostSyncManager interface [.NET Framework hosting]
ms.assetid: 2e081a37-6a28-4c93-b7ab-1c96a464637c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b51e1dd9219c30eb4918bf1e331c96585f7c03ac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsyncmanager-interface"></a><span data-ttu-id="fbcfc-102">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fbcfc-102">IHostSyncManager Interface</span></span>
<span data-ttu-id="fbcfc-103">Proporciona métodos que permiten a common language runtime (CLR) para crear a las primitivas de sincronización llamando al host en lugar de utilizar las funciones de sincronización de Win32.</span><span class="sxs-lookup"><span data-stu-id="fbcfc-103">Provides methods that allow the common language runtime (CLR) to create synchronization primitives by calling the host instead of using the Win32 synchronization functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fbcfc-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="fbcfc-104">Methods</span></span>  
  
|<span data-ttu-id="fbcfc-105">Método</span><span class="sxs-lookup"><span data-stu-id="fbcfc-105">Method</span></span>|<span data-ttu-id="fbcfc-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="fbcfc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fbcfc-107">CreateAutoEvent (método)</span><span class="sxs-lookup"><span data-stu-id="fbcfc-107">CreateAutoEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createautoevent-method.md)|<span data-ttu-id="fbcfc-108">Crea un objeto de evento de restablecimiento automático.</span><span class="sxs-lookup"><span data-stu-id="fbcfc-108">Creates an auto-reset event object.</span></span>|  
|[<span data-ttu-id="fbcfc-109">CreateCrst (método)</span><span class="sxs-lookup"><span data-stu-id="fbcfc-109">CreateCrst Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrst-method.md)|<span data-ttu-id="fbcfc-110">Crea un objeto de sección crítica para la sincronización.</span><span class="sxs-lookup"><span data-stu-id="fbcfc-110">Creates a critical section object for synchronization.</span></span>|  
|[<span data-ttu-id="fbcfc-111">CreateCrstWithSpinCount (método)</span><span class="sxs-lookup"><span data-stu-id="fbcfc-111">CreateCrstWithSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrstwithspincount-method.md)|<span data-ttu-id="fbcfc-112">Crea un objeto de sección crítica con recuento circular para la sincronización.</span><span class="sxs-lookup"><span data-stu-id="fbcfc-112">Creates a critical section object with spin count for synchronization.</span></span>|  
|[<span data-ttu-id="fbcfc-113">CreateManualEvent (método)</span><span class="sxs-lookup"><span data-stu-id="fbcfc-113">CreateManualEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmanualevent-method.md)|<span data-ttu-id="fbcfc-114">Crea un objeto de evento de restablecimiento manual.</span><span class="sxs-lookup"><span data-stu-id="fbcfc-114">Creates a manual-reset event object.</span></span>|  
|[<span data-ttu-id="fbcfc-115">CreateMonitorEvent (método)</span><span class="sxs-lookup"><span data-stu-id="fbcfc-115">CreateMonitorEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)|<span data-ttu-id="fbcfc-116">Crea un objeto de evento de restablecimiento automático supervisado.</span><span class="sxs-lookup"><span data-stu-id="fbcfc-116">Creates a monitored auto-reset event object.</span></span>|  
|[<span data-ttu-id="fbcfc-117">CreateRWLockReaderEvent (método)</span><span class="sxs-lookup"><span data-stu-id="fbcfc-117">CreateRWLockReaderEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockreaderevent-method.md)|<span data-ttu-id="fbcfc-118">Crea un objeto de evento de restablecimiento manual para la implementación de un bloqueo de lector.</span><span class="sxs-lookup"><span data-stu-id="fbcfc-118">Creates a manual-reset event object for the implementation of a reader lock.</span></span>|  
|[<span data-ttu-id="fbcfc-119">CreateRWLockWriterEvent (método)</span><span class="sxs-lookup"><span data-stu-id="fbcfc-119">CreateRWLockWriterEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockwriterevent-method.md)|<span data-ttu-id="fbcfc-120">Crea un objeto de evento de restablecimiento automático para la implementación de un bloqueo de escritor.</span><span class="sxs-lookup"><span data-stu-id="fbcfc-120">Creates an auto-reset event object for the implementation of a writer lock.</span></span>|  
|[<span data-ttu-id="fbcfc-121">CreateSemaphore (método)</span><span class="sxs-lookup"><span data-stu-id="fbcfc-121">CreateSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|<span data-ttu-id="fbcfc-122">Crea un [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) objeto para el CLR que se usará como un semáforo para los eventos de espera.</span><span class="sxs-lookup"><span data-stu-id="fbcfc-122">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the CLR to use as a semaphore for wait events.</span></span>|  
|[<span data-ttu-id="fbcfc-123">SetCLRSyncManager (método)</span><span class="sxs-lookup"><span data-stu-id="fbcfc-123">SetCLRSyncManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|<span data-ttu-id="fbcfc-124">Establece el [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instancia asociada con el actual `IHostSyncManager` instancia.</span><span class="sxs-lookup"><span data-stu-id="fbcfc-124">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current `IHostSyncManager` instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fbcfc-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fbcfc-125">Remarks</span></span>  
 <span data-ttu-id="fbcfc-126">El CLR detecta la implementación del host de `IHostSyncManager` mediante una llamada a la [IHostControl:: GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) método con un `IID` de IID_IHostSyncManager.</span><span class="sxs-lookup"><span data-stu-id="fbcfc-126">The CLR discovers the host's implementation of `IHostSyncManager` by calling the [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) method with an `IID` of IID_IHostSyncManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbcfc-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fbcfc-127">Requirements</span></span>  
 <span data-ttu-id="fbcfc-128">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbcfc-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbcfc-129">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fbcfc-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fbcfc-130">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fbcfc-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fbcfc-131">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbcfc-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbcfc-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="fbcfc-132">See Also</span></span>  
 [<span data-ttu-id="fbcfc-133">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fbcfc-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="fbcfc-134">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="fbcfc-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
