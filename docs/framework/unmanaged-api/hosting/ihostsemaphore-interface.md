---
title: IHostSemaphore (Interfaz)
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
- IHostSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore
helpviewer_keywords:
- IHostSemaphore interface [.NET Framework hosting]
ms.assetid: c0765321-656c-441e-bab5-58176292be1e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bcc6a9a7847932e9e469cdbffc9792e1d5860570
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsemaphore-interface"></a><span data-ttu-id="5f6ab-102">IHostSemaphore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5f6ab-102">IHostSemaphore Interface</span></span>
<span data-ttu-id="5f6ab-103">Representa la implementación del host de un semáforo para el subprocesamiento.</span><span class="sxs-lookup"><span data-stu-id="5f6ab-103">Represents the host's implementation of a semaphore for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5f6ab-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="5f6ab-104">Methods</span></span>  
  
|<span data-ttu-id="5f6ab-105">Método</span><span class="sxs-lookup"><span data-stu-id="5f6ab-105">Method</span></span>|<span data-ttu-id="5f6ab-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="5f6ab-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5f6ab-107">ReleaseSemaphore (método)</span><span class="sxs-lookup"><span data-stu-id="5f6ab-107">ReleaseSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)|<span data-ttu-id="5f6ab-108">Aumenta el número del elemento actual `IHostSemaphore` instancia en la cantidad especificada.</span><span class="sxs-lookup"><span data-stu-id="5f6ab-108">Increases the count of the current `IHostSemaphore` instance by the specified amount.</span></span>|  
|[<span data-ttu-id="5f6ab-109">Wait (método)</span><span class="sxs-lookup"><span data-stu-id="5f6ab-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md)|<span data-ttu-id="5f6ab-110">Hace que el actual `IHostSemaphore` instancia espere hasta que encuentre un propietario o la cantidad especificada de tiempo determinado.</span><span class="sxs-lookup"><span data-stu-id="5f6ab-110">Causes the current `IHostSemaphore` instance to wait until it is owned or the specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5f6ab-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5f6ab-111">Requirements</span></span>  
 <span data-ttu-id="5f6ab-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f6ab-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f6ab-113">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5f6ab-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5f6ab-114">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5f6ab-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5f6ab-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f6ab-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f6ab-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f6ab-116">See Also</span></span>  
 [<span data-ttu-id="5f6ab-117">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5f6ab-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="5f6ab-118">IHostAutoEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5f6ab-118">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="5f6ab-119">IHostManualEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5f6ab-119">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="5f6ab-120">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5f6ab-120">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="5f6ab-121">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="5f6ab-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
