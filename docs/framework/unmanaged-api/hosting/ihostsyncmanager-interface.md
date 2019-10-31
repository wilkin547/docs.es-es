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
ms.openlocfilehash: 02a59b8ef63f7e866e419db4e3232da7eec19558
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132629"
---
# <a name="ihostsyncmanager-interface"></a><span data-ttu-id="8d50f-102">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d50f-102">IHostSyncManager Interface</span></span>
<span data-ttu-id="8d50f-103">Proporciona métodos que permiten al Common Language Runtime (CLR) crear primitivas de sincronización llamando al host en lugar de usar las funciones de sincronización de Win32.</span><span class="sxs-lookup"><span data-stu-id="8d50f-103">Provides methods that allow the common language runtime (CLR) to create synchronization primitives by calling the host instead of using the Win32 synchronization functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8d50f-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="8d50f-104">Methods</span></span>  
  
|<span data-ttu-id="8d50f-105">Método</span><span class="sxs-lookup"><span data-stu-id="8d50f-105">Method</span></span>|<span data-ttu-id="8d50f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d50f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8d50f-107">CreateAutoEvent (método)</span><span class="sxs-lookup"><span data-stu-id="8d50f-107">CreateAutoEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createautoevent-method.md)|<span data-ttu-id="8d50f-108">Crea un objeto de evento de restablecimiento automático.</span><span class="sxs-lookup"><span data-stu-id="8d50f-108">Creates an auto-reset event object.</span></span>|  
|[<span data-ttu-id="8d50f-109">CreateCrst (método)</span><span class="sxs-lookup"><span data-stu-id="8d50f-109">CreateCrst Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrst-method.md)|<span data-ttu-id="8d50f-110">Crea un objeto de sección crítica para la sincronización.</span><span class="sxs-lookup"><span data-stu-id="8d50f-110">Creates a critical section object for synchronization.</span></span>|  
|[<span data-ttu-id="8d50f-111">CreateCrstWithSpinCount (método)</span><span class="sxs-lookup"><span data-stu-id="8d50f-111">CreateCrstWithSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrstwithspincount-method.md)|<span data-ttu-id="8d50f-112">Crea un objeto de sección crítica con el recuento de giros para la sincronización.</span><span class="sxs-lookup"><span data-stu-id="8d50f-112">Creates a critical section object with spin count for synchronization.</span></span>|  
|[<span data-ttu-id="8d50f-113">CreateManualEvent (método)</span><span class="sxs-lookup"><span data-stu-id="8d50f-113">CreateManualEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmanualevent-method.md)|<span data-ttu-id="8d50f-114">Crea un objeto de evento de restablecimiento manual.</span><span class="sxs-lookup"><span data-stu-id="8d50f-114">Creates a manual-reset event object.</span></span>|  
|[<span data-ttu-id="8d50f-115">CreateMonitorEvent (método)</span><span class="sxs-lookup"><span data-stu-id="8d50f-115">CreateMonitorEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)|<span data-ttu-id="8d50f-116">Crea un objeto de evento de restablecimiento automático supervisado.</span><span class="sxs-lookup"><span data-stu-id="8d50f-116">Creates a monitored auto-reset event object.</span></span>|  
|[<span data-ttu-id="8d50f-117">CreateRWLockReaderEvent (método)</span><span class="sxs-lookup"><span data-stu-id="8d50f-117">CreateRWLockReaderEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockreaderevent-method.md)|<span data-ttu-id="8d50f-118">Crea un objeto de evento de restablecimiento manual para la implementación de un bloqueo de lector.</span><span class="sxs-lookup"><span data-stu-id="8d50f-118">Creates a manual-reset event object for the implementation of a reader lock.</span></span>|  
|[<span data-ttu-id="8d50f-119">CreateRWLockWriterEvent (método)</span><span class="sxs-lookup"><span data-stu-id="8d50f-119">CreateRWLockWriterEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockwriterevent-method.md)|<span data-ttu-id="8d50f-120">Crea un objeto de evento de restablecimiento automático para la implementación de un bloqueo de escritor.</span><span class="sxs-lookup"><span data-stu-id="8d50f-120">Creates an auto-reset event object for the implementation of a writer lock.</span></span>|  
|[<span data-ttu-id="8d50f-121">CreateSemaphore (método)</span><span class="sxs-lookup"><span data-stu-id="8d50f-121">CreateSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|<span data-ttu-id="8d50f-122">Crea un objeto [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) para que el CLR lo use como semáforo para los eventos de espera.</span><span class="sxs-lookup"><span data-stu-id="8d50f-122">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the CLR to use as a semaphore for wait events.</span></span>|  
|[<span data-ttu-id="8d50f-123">SetCLRSyncManager (método)</span><span class="sxs-lookup"><span data-stu-id="8d50f-123">SetCLRSyncManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|<span data-ttu-id="8d50f-124">Establece la instancia de [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) que se va a asociar a la instancia de `IHostSyncManager` actual.</span><span class="sxs-lookup"><span data-stu-id="8d50f-124">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current `IHostSyncManager` instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d50f-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8d50f-125">Remarks</span></span>  
 <span data-ttu-id="8d50f-126">CLR detecta la implementación del host de `IHostSyncManager` llamando al método [IHostControl:: GetHostManager (](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) con una `IID` de IID_IHostSyncManager.</span><span class="sxs-lookup"><span data-stu-id="8d50f-126">The CLR discovers the host's implementation of `IHostSyncManager` by calling the [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) method with an `IID` of IID_IHostSyncManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d50f-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8d50f-127">Requirements</span></span>  
 <span data-ttu-id="8d50f-128">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d50f-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d50f-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8d50f-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8d50f-130">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8d50f-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8d50f-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d50f-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d50f-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d50f-132">See also</span></span>

- [<span data-ttu-id="8d50f-133">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d50f-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="8d50f-134">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="8d50f-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
