---
description: 'Más información sobre: interfaz IHostSemaphore'
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
ms.openlocfilehash: 682f1f70925310e93f88f1dc314052e801a5e87b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671365"
---
# <a name="ihostsemaphore-interface"></a><span data-ttu-id="0bc68-103">IHostSemaphore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0bc68-103">IHostSemaphore Interface</span></span>

<span data-ttu-id="0bc68-104">Representa la implementación del host de un semáforo para el subprocesamiento.</span><span class="sxs-lookup"><span data-stu-id="0bc68-104">Represents the host's implementation of a semaphore for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0bc68-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="0bc68-105">Methods</span></span>  
  
|<span data-ttu-id="0bc68-106">Método</span><span class="sxs-lookup"><span data-stu-id="0bc68-106">Method</span></span>|<span data-ttu-id="0bc68-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0bc68-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0bc68-108">Método ReleaseSemaphore</span><span class="sxs-lookup"><span data-stu-id="0bc68-108">ReleaseSemaphore Method</span></span>](ihostsemaphore-releasesemaphore-method.md)|<span data-ttu-id="0bc68-109">Aumenta el recuento de la `IHostSemaphore` instancia actual en la cantidad especificada.</span><span class="sxs-lookup"><span data-stu-id="0bc68-109">Increases the count of the current `IHostSemaphore` instance by the specified amount.</span></span>|  
|[<span data-ttu-id="0bc68-110">Wait (Método)</span><span class="sxs-lookup"><span data-stu-id="0bc68-110">Wait Method</span></span>](ihostsemaphore-wait-method.md)|<span data-ttu-id="0bc68-111">Hace que la `IHostSemaphore` instancia actual espere hasta que sea propiedad o transcurra la cantidad de tiempo especificada.</span><span class="sxs-lookup"><span data-stu-id="0bc68-111">Causes the current `IHostSemaphore` instance to wait until it is owned or the specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0bc68-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0bc68-112">Requirements</span></span>  

 <span data-ttu-id="0bc68-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0bc68-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bc68-114">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0bc68-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0bc68-115">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0bc68-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0bc68-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bc68-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bc68-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0bc68-117">See also</span></span>

- [<span data-ttu-id="0bc68-118">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0bc68-118">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="0bc68-119">IHostAutoEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0bc68-119">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="0bc68-120">IHostManualEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0bc68-120">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="0bc68-121">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0bc68-121">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="0bc68-122">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="0bc68-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
