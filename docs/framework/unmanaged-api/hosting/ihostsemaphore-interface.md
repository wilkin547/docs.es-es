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
ms.openlocfilehash: 2d7d4a295832a958fb6a8fe2e6c43a09135500d3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696685"
---
# <a name="ihostsemaphore-interface"></a><span data-ttu-id="5bf48-102">IHostSemaphore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5bf48-102">IHostSemaphore Interface</span></span>
<span data-ttu-id="5bf48-103">Representa la implementación del host de un semáforo para el subprocesamiento.</span><span class="sxs-lookup"><span data-stu-id="5bf48-103">Represents the host's implementation of a semaphore for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5bf48-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="5bf48-104">Methods</span></span>  
  
|<span data-ttu-id="5bf48-105">Método</span><span class="sxs-lookup"><span data-stu-id="5bf48-105">Method</span></span>|<span data-ttu-id="5bf48-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="5bf48-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5bf48-107">ReleaseSemaphore (método)</span><span class="sxs-lookup"><span data-stu-id="5bf48-107">ReleaseSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)|<span data-ttu-id="5bf48-108">Aumenta el recuento de actual `IHostSemaphore` instancia en la cantidad especificada.</span><span class="sxs-lookup"><span data-stu-id="5bf48-108">Increases the count of the current `IHostSemaphore` instance by the specified amount.</span></span>|  
|[<span data-ttu-id="5bf48-109">Wait (método)</span><span class="sxs-lookup"><span data-stu-id="5bf48-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md)|<span data-ttu-id="5bf48-110">Hace que el actual `IHostSemaphore` instancia espere hasta que es propietario o la cantidad de tiempo especificada.</span><span class="sxs-lookup"><span data-stu-id="5bf48-110">Causes the current `IHostSemaphore` instance to wait until it is owned or the specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5bf48-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5bf48-111">Requirements</span></span>  
 <span data-ttu-id="5bf48-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5bf48-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bf48-113">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5bf48-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5bf48-114">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5bf48-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5bf48-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bf48-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bf48-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5bf48-116">See also</span></span>

- [<span data-ttu-id="5bf48-117">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5bf48-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="5bf48-118">IHostAutoEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5bf48-118">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="5bf48-119">IHostManualEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5bf48-119">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="5bf48-120">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5bf48-120">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="5bf48-121">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="5bf48-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
