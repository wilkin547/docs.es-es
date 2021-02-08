---
description: 'Más información acerca de: IHostSyncManager (interfaz)'
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
ms.openlocfilehash: c3bd2928315567605d320c772de8ff824ad3cd09
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784735"
---
# <a name="ihostsyncmanager-interface"></a><span data-ttu-id="412e1-103">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="412e1-103">IHostSyncManager Interface</span></span>

<span data-ttu-id="412e1-104">Proporciona métodos que permiten al Common Language Runtime (CLR) crear primitivas de sincronización llamando al host en lugar de usar las funciones de sincronización de Win32.</span><span class="sxs-lookup"><span data-stu-id="412e1-104">Provides methods that allow the common language runtime (CLR) to create synchronization primitives by calling the host instead of using the Win32 synchronization functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="412e1-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="412e1-105">Methods</span></span>  
  
|<span data-ttu-id="412e1-106">Método</span><span class="sxs-lookup"><span data-stu-id="412e1-106">Method</span></span>|<span data-ttu-id="412e1-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="412e1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="412e1-108">Método CreateAutoEvent</span><span class="sxs-lookup"><span data-stu-id="412e1-108">CreateAutoEvent Method</span></span>](ihostsyncmanager-createautoevent-method.md)|<span data-ttu-id="412e1-109">Crea un objeto de evento de restablecimiento automático.</span><span class="sxs-lookup"><span data-stu-id="412e1-109">Creates an auto-reset event object.</span></span>|  
|[<span data-ttu-id="412e1-110">Método CreateCrst</span><span class="sxs-lookup"><span data-stu-id="412e1-110">CreateCrst Method</span></span>](ihostsyncmanager-createcrst-method.md)|<span data-ttu-id="412e1-111">Crea un objeto de sección crítica para la sincronización.</span><span class="sxs-lookup"><span data-stu-id="412e1-111">Creates a critical section object for synchronization.</span></span>|  
|[<span data-ttu-id="412e1-112">Método CreateCrstWithSpinCount</span><span class="sxs-lookup"><span data-stu-id="412e1-112">CreateCrstWithSpinCount Method</span></span>](ihostsyncmanager-createcrstwithspincount-method.md)|<span data-ttu-id="412e1-113">Crea un objeto de sección crítica con el recuento de giros para la sincronización.</span><span class="sxs-lookup"><span data-stu-id="412e1-113">Creates a critical section object with spin count for synchronization.</span></span>|  
|[<span data-ttu-id="412e1-114">Método CreateManualEvent</span><span class="sxs-lookup"><span data-stu-id="412e1-114">CreateManualEvent Method</span></span>](ihostsyncmanager-createmanualevent-method.md)|<span data-ttu-id="412e1-115">Crea un objeto de evento de restablecimiento manual.</span><span class="sxs-lookup"><span data-stu-id="412e1-115">Creates a manual-reset event object.</span></span>|  
|[<span data-ttu-id="412e1-116">Método CreateMonitorEvent</span><span class="sxs-lookup"><span data-stu-id="412e1-116">CreateMonitorEvent Method</span></span>](ihostsyncmanager-createmonitorevent-method.md)|<span data-ttu-id="412e1-117">Crea un objeto de evento de restablecimiento automático supervisado.</span><span class="sxs-lookup"><span data-stu-id="412e1-117">Creates a monitored auto-reset event object.</span></span>|  
|[<span data-ttu-id="412e1-118">Método CreateRWLockReaderEvent</span><span class="sxs-lookup"><span data-stu-id="412e1-118">CreateRWLockReaderEvent Method</span></span>](ihostsyncmanager-createrwlockreaderevent-method.md)|<span data-ttu-id="412e1-119">Crea un objeto de evento de restablecimiento manual para la implementación de un bloqueo de lector.</span><span class="sxs-lookup"><span data-stu-id="412e1-119">Creates a manual-reset event object for the implementation of a reader lock.</span></span>|  
|[<span data-ttu-id="412e1-120">Método CreateRWLockWriterEvent</span><span class="sxs-lookup"><span data-stu-id="412e1-120">CreateRWLockWriterEvent Method</span></span>](ihostsyncmanager-createrwlockwriterevent-method.md)|<span data-ttu-id="412e1-121">Crea un objeto de evento de restablecimiento automático para la implementación de un bloqueo de escritor.</span><span class="sxs-lookup"><span data-stu-id="412e1-121">Creates an auto-reset event object for the implementation of a writer lock.</span></span>|  
|[<span data-ttu-id="412e1-122">Método CreateSemaphore</span><span class="sxs-lookup"><span data-stu-id="412e1-122">CreateSemaphore Method</span></span>](ihostsyncmanager-createsemaphore-method.md)|<span data-ttu-id="412e1-123">Crea un objeto [IHostSemaphore](ihostsemaphore-interface.md) para que el CLR lo use como semáforo para los eventos de espera.</span><span class="sxs-lookup"><span data-stu-id="412e1-123">Creates an [IHostSemaphore](ihostsemaphore-interface.md) object for the CLR to use as a semaphore for wait events.</span></span>|  
|[<span data-ttu-id="412e1-124">Método SetCLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="412e1-124">SetCLRSyncManager Method</span></span>](ihostsyncmanager-setclrsyncmanager-method.md)|<span data-ttu-id="412e1-125">Establece la instancia de [ICLRSyncManager](iclrsyncmanager-interface.md) que se va a asociar a la `IHostSyncManager` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="412e1-125">Sets the [ICLRSyncManager](iclrsyncmanager-interface.md) instance to associate with the current `IHostSyncManager` instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="412e1-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="412e1-126">Remarks</span></span>  

 <span data-ttu-id="412e1-127">CLR detecta la implementación del host de llamando al `IHostSyncManager` método [IHostControl:: GetHostManager (](ihostcontrol-gethostmanager-method.md) con una `IID` de IID_IHostSyncManager.</span><span class="sxs-lookup"><span data-stu-id="412e1-127">The CLR discovers the host's implementation of `IHostSyncManager` by calling the [IHostControl::GetHostManager](ihostcontrol-gethostmanager-method.md) method with an `IID` of IID_IHostSyncManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="412e1-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="412e1-128">Requirements</span></span>  

 <span data-ttu-id="412e1-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="412e1-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="412e1-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="412e1-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="412e1-131">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="412e1-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="412e1-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="412e1-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="412e1-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="412e1-133">See also</span></span>

- [<span data-ttu-id="412e1-134">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="412e1-134">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="412e1-135">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="412e1-135">Hosting Interfaces</span></span>](hosting-interfaces.md)
