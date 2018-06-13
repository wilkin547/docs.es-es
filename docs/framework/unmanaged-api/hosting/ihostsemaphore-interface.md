---
title: IHostSemaphore (Interfaz)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 103deb5ec46ba8c1d385c5339bc52a0c220c4c93
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439773"
---
# <a name="ihostsemaphore-interface"></a><span data-ttu-id="82e58-102">IHostSemaphore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="82e58-102">IHostSemaphore Interface</span></span>
<span data-ttu-id="82e58-103">Representa la implementación del host de un semáforo para el subprocesamiento.</span><span class="sxs-lookup"><span data-stu-id="82e58-103">Represents the host's implementation of a semaphore for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="82e58-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="82e58-104">Methods</span></span>  
  
|<span data-ttu-id="82e58-105">Método</span><span class="sxs-lookup"><span data-stu-id="82e58-105">Method</span></span>|<span data-ttu-id="82e58-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="82e58-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="82e58-107">ReleaseSemaphore (método)</span><span class="sxs-lookup"><span data-stu-id="82e58-107">ReleaseSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)|<span data-ttu-id="82e58-108">Aumenta el número del elemento actual `IHostSemaphore` instancia en la cantidad especificada.</span><span class="sxs-lookup"><span data-stu-id="82e58-108">Increases the count of the current `IHostSemaphore` instance by the specified amount.</span></span>|  
|[<span data-ttu-id="82e58-109">Wait (método)</span><span class="sxs-lookup"><span data-stu-id="82e58-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md)|<span data-ttu-id="82e58-110">Hace que el actual `IHostSemaphore` instancia espere hasta que encuentre un propietario o la cantidad especificada de tiempo determinado.</span><span class="sxs-lookup"><span data-stu-id="82e58-110">Causes the current `IHostSemaphore` instance to wait until it is owned or the specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="82e58-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="82e58-111">Requirements</span></span>  
 <span data-ttu-id="82e58-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82e58-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82e58-113">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="82e58-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="82e58-114">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="82e58-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="82e58-115">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82e58-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82e58-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="82e58-116">See Also</span></span>  
 [<span data-ttu-id="82e58-117">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="82e58-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="82e58-118">IHostAutoEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="82e58-118">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="82e58-119">IHostManualEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="82e58-119">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="82e58-120">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="82e58-120">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="82e58-121">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="82e58-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
