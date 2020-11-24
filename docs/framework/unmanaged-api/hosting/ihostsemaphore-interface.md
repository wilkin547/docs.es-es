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
ms.openlocfilehash: cccbf9a28b16ffee14b3fd3ec43c376109d6ccec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683061"
---
# <a name="ihostsemaphore-interface"></a><span data-ttu-id="99178-102">IHostSemaphore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="99178-102">IHostSemaphore Interface</span></span>

<span data-ttu-id="99178-103">Representa la implementación del host de un semáforo para el subprocesamiento.</span><span class="sxs-lookup"><span data-stu-id="99178-103">Represents the host's implementation of a semaphore for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="99178-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="99178-104">Methods</span></span>  
  
|<span data-ttu-id="99178-105">Método</span><span class="sxs-lookup"><span data-stu-id="99178-105">Method</span></span>|<span data-ttu-id="99178-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="99178-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="99178-107">Método ReleaseSemaphore</span><span class="sxs-lookup"><span data-stu-id="99178-107">ReleaseSemaphore Method</span></span>](ihostsemaphore-releasesemaphore-method.md)|<span data-ttu-id="99178-108">Aumenta el recuento de la `IHostSemaphore` instancia actual en la cantidad especificada.</span><span class="sxs-lookup"><span data-stu-id="99178-108">Increases the count of the current `IHostSemaphore` instance by the specified amount.</span></span>|  
|[<span data-ttu-id="99178-109">Wait (Método)</span><span class="sxs-lookup"><span data-stu-id="99178-109">Wait Method</span></span>](ihostsemaphore-wait-method.md)|<span data-ttu-id="99178-110">Hace que la `IHostSemaphore` instancia actual espere hasta que sea propiedad o transcurra la cantidad de tiempo especificada.</span><span class="sxs-lookup"><span data-stu-id="99178-110">Causes the current `IHostSemaphore` instance to wait until it is owned or the specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="99178-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="99178-111">Requirements</span></span>  

 <span data-ttu-id="99178-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99178-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99178-113">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="99178-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="99178-114">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="99178-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="99178-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99178-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99178-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="99178-116">See also</span></span>

- [<span data-ttu-id="99178-117">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="99178-117">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="99178-118">IHostAutoEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="99178-118">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="99178-119">IHostManualEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="99178-119">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="99178-120">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="99178-120">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="99178-121">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="99178-121">Hosting Interfaces</span></span>](hosting-interfaces.md)
