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
ms.openlocfilehash: 8345d85502087568cb05dd262cccf181e3ca07ac
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803700"
---
# <a name="ihostsemaphore-interface"></a><span data-ttu-id="2499f-102">IHostSemaphore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2499f-102">IHostSemaphore Interface</span></span>
<span data-ttu-id="2499f-103">Representa la implementación del host de un semáforo para el subprocesamiento.</span><span class="sxs-lookup"><span data-stu-id="2499f-103">Represents the host's implementation of a semaphore for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2499f-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="2499f-104">Methods</span></span>  
  
|<span data-ttu-id="2499f-105">Método</span><span class="sxs-lookup"><span data-stu-id="2499f-105">Method</span></span>|<span data-ttu-id="2499f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="2499f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2499f-107">Método ReleaseSemaphore</span><span class="sxs-lookup"><span data-stu-id="2499f-107">ReleaseSemaphore Method</span></span>](ihostsemaphore-releasesemaphore-method.md)|<span data-ttu-id="2499f-108">Aumenta el recuento de la `IHostSemaphore` instancia actual en la cantidad especificada.</span><span class="sxs-lookup"><span data-stu-id="2499f-108">Increases the count of the current `IHostSemaphore` instance by the specified amount.</span></span>|  
|[<span data-ttu-id="2499f-109">Wait (Método)</span><span class="sxs-lookup"><span data-stu-id="2499f-109">Wait Method</span></span>](ihostsemaphore-wait-method.md)|<span data-ttu-id="2499f-110">Hace que la `IHostSemaphore` instancia actual espere hasta que sea propiedad o transcurra la cantidad de tiempo especificada.</span><span class="sxs-lookup"><span data-stu-id="2499f-110">Causes the current `IHostSemaphore` instance to wait until it is owned or the specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2499f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2499f-111">Requirements</span></span>  
 <span data-ttu-id="2499f-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2499f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2499f-113">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2499f-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2499f-114">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2499f-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2499f-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2499f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2499f-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2499f-116">See also</span></span>

- [<span data-ttu-id="2499f-117">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2499f-117">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="2499f-118">IHostAutoEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2499f-118">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="2499f-119">IHostManualEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2499f-119">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="2499f-120">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2499f-120">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="2499f-121">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="2499f-121">Hosting Interfaces</span></span>](hosting-interfaces.md)
