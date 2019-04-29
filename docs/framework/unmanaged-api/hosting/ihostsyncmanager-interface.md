---
title: IHostSyncManager (Interfaz)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 200da8b87b52a29c2b075d1e06929031d3f588b7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769634"
---
# <a name="ihostsyncmanager-interface"></a><span data-ttu-id="c2da8-102">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c2da8-102">IHostSyncManager Interface</span></span>
<span data-ttu-id="c2da8-103">Proporciona métodos que permiten a common language runtime (CLR) para crear a las primitivas de sincronización llamando al host en lugar de usar las funciones de sincronización de Win32.</span><span class="sxs-lookup"><span data-stu-id="c2da8-103">Provides methods that allow the common language runtime (CLR) to create synchronization primitives by calling the host instead of using the Win32 synchronization functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c2da8-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c2da8-104">Methods</span></span>  
  
|<span data-ttu-id="c2da8-105">Método</span><span class="sxs-lookup"><span data-stu-id="c2da8-105">Method</span></span>|<span data-ttu-id="c2da8-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2da8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c2da8-107">CreateAutoEvent (método)</span><span class="sxs-lookup"><span data-stu-id="c2da8-107">CreateAutoEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createautoevent-method.md)|<span data-ttu-id="c2da8-108">Crea un objeto de evento de restablecimiento automático.</span><span class="sxs-lookup"><span data-stu-id="c2da8-108">Creates an auto-reset event object.</span></span>|  
|[<span data-ttu-id="c2da8-109">CreateCrst (método)</span><span class="sxs-lookup"><span data-stu-id="c2da8-109">CreateCrst Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrst-method.md)|<span data-ttu-id="c2da8-110">Crea un objeto de sección crítica para la sincronización.</span><span class="sxs-lookup"><span data-stu-id="c2da8-110">Creates a critical section object for synchronization.</span></span>|  
|[<span data-ttu-id="c2da8-111">CreateCrstWithSpinCount (método)</span><span class="sxs-lookup"><span data-stu-id="c2da8-111">CreateCrstWithSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrstwithspincount-method.md)|<span data-ttu-id="c2da8-112">Crea un objeto de sección crítica con recuento de rotación para la sincronización.</span><span class="sxs-lookup"><span data-stu-id="c2da8-112">Creates a critical section object with spin count for synchronization.</span></span>|  
|[<span data-ttu-id="c2da8-113">CreateManualEvent (método)</span><span class="sxs-lookup"><span data-stu-id="c2da8-113">CreateManualEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmanualevent-method.md)|<span data-ttu-id="c2da8-114">Crea un objeto de evento de restablecimiento manual.</span><span class="sxs-lookup"><span data-stu-id="c2da8-114">Creates a manual-reset event object.</span></span>|  
|[<span data-ttu-id="c2da8-115">CreateMonitorEvent (método)</span><span class="sxs-lookup"><span data-stu-id="c2da8-115">CreateMonitorEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)|<span data-ttu-id="c2da8-116">Crea un objeto de evento de restablecimiento automático supervisado.</span><span class="sxs-lookup"><span data-stu-id="c2da8-116">Creates a monitored auto-reset event object.</span></span>|  
|[<span data-ttu-id="c2da8-117">CreateRWLockReaderEvent (método)</span><span class="sxs-lookup"><span data-stu-id="c2da8-117">CreateRWLockReaderEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockreaderevent-method.md)|<span data-ttu-id="c2da8-118">Crea un objeto de evento de restablecimiento manual para la implementación de un bloqueo de lector.</span><span class="sxs-lookup"><span data-stu-id="c2da8-118">Creates a manual-reset event object for the implementation of a reader lock.</span></span>|  
|[<span data-ttu-id="c2da8-119">CreateRWLockWriterEvent (método)</span><span class="sxs-lookup"><span data-stu-id="c2da8-119">CreateRWLockWriterEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockwriterevent-method.md)|<span data-ttu-id="c2da8-120">Crea un objeto de evento de restablecimiento automático para la implementación de un bloqueo de escritor.</span><span class="sxs-lookup"><span data-stu-id="c2da8-120">Creates an auto-reset event object for the implementation of a writer lock.</span></span>|  
|[<span data-ttu-id="c2da8-121">CreateSemaphore (método)</span><span class="sxs-lookup"><span data-stu-id="c2da8-121">CreateSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|<span data-ttu-id="c2da8-122">Crea un [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) objeto CLR que se usará como un semáforo para los eventos de espera.</span><span class="sxs-lookup"><span data-stu-id="c2da8-122">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the CLR to use as a semaphore for wait events.</span></span>|  
|[<span data-ttu-id="c2da8-123">SetCLRSyncManager (método)</span><span class="sxs-lookup"><span data-stu-id="c2da8-123">SetCLRSyncManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|<span data-ttu-id="c2da8-124">Establece el [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instancia asociada con el actual `IHostSyncManager` instancia.</span><span class="sxs-lookup"><span data-stu-id="c2da8-124">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current `IHostSyncManager` instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2da8-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c2da8-125">Remarks</span></span>  
 <span data-ttu-id="c2da8-126">El CLR detecta la implementación del host de `IHostSyncManager` mediante una llamada a la [IHostControl](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) método con un `IID` de IID_IHostSyncManager.</span><span class="sxs-lookup"><span data-stu-id="c2da8-126">The CLR discovers the host's implementation of `IHostSyncManager` by calling the [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) method with an `IID` of IID_IHostSyncManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2da8-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c2da8-127">Requirements</span></span>  
 <span data-ttu-id="c2da8-128">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2da8-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2da8-129">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c2da8-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c2da8-130">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c2da8-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2da8-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2da8-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2da8-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2da8-132">See also</span></span>

- [<span data-ttu-id="c2da8-133">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c2da8-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="c2da8-134">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="c2da8-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
