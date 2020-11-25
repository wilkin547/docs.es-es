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
ms.openlocfilehash: 8a5fc42191634a2e5a441baecc4b78212ffad687
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720503"
---
# <a name="ihostsyncmanager-interface"></a><span data-ttu-id="d4499-102">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d4499-102">IHostSyncManager Interface</span></span>

<span data-ttu-id="d4499-103">Proporciona métodos que permiten al Common Language Runtime (CLR) crear primitivas de sincronización llamando al host en lugar de usar las funciones de sincronización de Win32.</span><span class="sxs-lookup"><span data-stu-id="d4499-103">Provides methods that allow the common language runtime (CLR) to create synchronization primitives by calling the host instead of using the Win32 synchronization functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d4499-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="d4499-104">Methods</span></span>  
  
|<span data-ttu-id="d4499-105">Método</span><span class="sxs-lookup"><span data-stu-id="d4499-105">Method</span></span>|<span data-ttu-id="d4499-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="d4499-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d4499-107">Método CreateAutoEvent</span><span class="sxs-lookup"><span data-stu-id="d4499-107">CreateAutoEvent Method</span></span>](ihostsyncmanager-createautoevent-method.md)|<span data-ttu-id="d4499-108">Crea un objeto de evento de restablecimiento automático.</span><span class="sxs-lookup"><span data-stu-id="d4499-108">Creates an auto-reset event object.</span></span>|  
|[<span data-ttu-id="d4499-109">Método CreateCrst</span><span class="sxs-lookup"><span data-stu-id="d4499-109">CreateCrst Method</span></span>](ihostsyncmanager-createcrst-method.md)|<span data-ttu-id="d4499-110">Crea un objeto de sección crítica para la sincronización.</span><span class="sxs-lookup"><span data-stu-id="d4499-110">Creates a critical section object for synchronization.</span></span>|  
|[<span data-ttu-id="d4499-111">Método CreateCrstWithSpinCount</span><span class="sxs-lookup"><span data-stu-id="d4499-111">CreateCrstWithSpinCount Method</span></span>](ihostsyncmanager-createcrstwithspincount-method.md)|<span data-ttu-id="d4499-112">Crea un objeto de sección crítica con el recuento de giros para la sincronización.</span><span class="sxs-lookup"><span data-stu-id="d4499-112">Creates a critical section object with spin count for synchronization.</span></span>|  
|[<span data-ttu-id="d4499-113">Método CreateManualEvent</span><span class="sxs-lookup"><span data-stu-id="d4499-113">CreateManualEvent Method</span></span>](ihostsyncmanager-createmanualevent-method.md)|<span data-ttu-id="d4499-114">Crea un objeto de evento de restablecimiento manual.</span><span class="sxs-lookup"><span data-stu-id="d4499-114">Creates a manual-reset event object.</span></span>|  
|[<span data-ttu-id="d4499-115">Método CreateMonitorEvent</span><span class="sxs-lookup"><span data-stu-id="d4499-115">CreateMonitorEvent Method</span></span>](ihostsyncmanager-createmonitorevent-method.md)|<span data-ttu-id="d4499-116">Crea un objeto de evento de restablecimiento automático supervisado.</span><span class="sxs-lookup"><span data-stu-id="d4499-116">Creates a monitored auto-reset event object.</span></span>|  
|[<span data-ttu-id="d4499-117">Método CreateRWLockReaderEvent</span><span class="sxs-lookup"><span data-stu-id="d4499-117">CreateRWLockReaderEvent Method</span></span>](ihostsyncmanager-createrwlockreaderevent-method.md)|<span data-ttu-id="d4499-118">Crea un objeto de evento de restablecimiento manual para la implementación de un bloqueo de lector.</span><span class="sxs-lookup"><span data-stu-id="d4499-118">Creates a manual-reset event object for the implementation of a reader lock.</span></span>|  
|[<span data-ttu-id="d4499-119">Método CreateRWLockWriterEvent</span><span class="sxs-lookup"><span data-stu-id="d4499-119">CreateRWLockWriterEvent Method</span></span>](ihostsyncmanager-createrwlockwriterevent-method.md)|<span data-ttu-id="d4499-120">Crea un objeto de evento de restablecimiento automático para la implementación de un bloqueo de escritor.</span><span class="sxs-lookup"><span data-stu-id="d4499-120">Creates an auto-reset event object for the implementation of a writer lock.</span></span>|  
|[<span data-ttu-id="d4499-121">Método CreateSemaphore</span><span class="sxs-lookup"><span data-stu-id="d4499-121">CreateSemaphore Method</span></span>](ihostsyncmanager-createsemaphore-method.md)|<span data-ttu-id="d4499-122">Crea un objeto [IHostSemaphore](ihostsemaphore-interface.md) para que el CLR lo use como semáforo para los eventos de espera.</span><span class="sxs-lookup"><span data-stu-id="d4499-122">Creates an [IHostSemaphore](ihostsemaphore-interface.md) object for the CLR to use as a semaphore for wait events.</span></span>|  
|[<span data-ttu-id="d4499-123">Método SetCLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="d4499-123">SetCLRSyncManager Method</span></span>](ihostsyncmanager-setclrsyncmanager-method.md)|<span data-ttu-id="d4499-124">Establece la instancia de [ICLRSyncManager](iclrsyncmanager-interface.md) que se va a asociar a la `IHostSyncManager` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="d4499-124">Sets the [ICLRSyncManager](iclrsyncmanager-interface.md) instance to associate with the current `IHostSyncManager` instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4499-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d4499-125">Remarks</span></span>  

 <span data-ttu-id="d4499-126">CLR detecta la implementación del host de llamando al `IHostSyncManager` método [IHostControl:: GetHostManager (](ihostcontrol-gethostmanager-method.md) con una `IID` de IID_IHostSyncManager.</span><span class="sxs-lookup"><span data-stu-id="d4499-126">The CLR discovers the host's implementation of `IHostSyncManager` by calling the [IHostControl::GetHostManager](ihostcontrol-gethostmanager-method.md) method with an `IID` of IID_IHostSyncManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4499-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d4499-127">Requirements</span></span>  

 <span data-ttu-id="d4499-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4499-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4499-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d4499-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d4499-130">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d4499-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d4499-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4499-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4499-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d4499-132">See also</span></span>

- [<span data-ttu-id="d4499-133">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d4499-133">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="d4499-134">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="d4499-134">Hosting Interfaces</span></span>](hosting-interfaces.md)
