---
title: IHostManualEvent (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent
helpviewer_keywords:
- IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 300c2661-b7d1-4c39-b080-9ebdef0fd523
topic_type:
- apiref
ms.openlocfilehash: 7c46f00063cdf9281a5f1080594e8d6dbc6c101e
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804589"
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="692ab-102">IHostManualEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="692ab-102">IHostManualEvent Interface</span></span>
<span data-ttu-id="692ab-103">Proporciona la implementación del host de una representación de un evento de restablecimiento manual.</span><span class="sxs-lookup"><span data-stu-id="692ab-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="692ab-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="692ab-104">Methods</span></span>  
  
|<span data-ttu-id="692ab-105">Método</span><span class="sxs-lookup"><span data-stu-id="692ab-105">Method</span></span>|<span data-ttu-id="692ab-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="692ab-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="692ab-107">Reset (Método)</span><span class="sxs-lookup"><span data-stu-id="692ab-107">Reset Method</span></span>](ihostmanualevent-reset-method.md)|<span data-ttu-id="692ab-108">Restablece la instancia actual `IHostManualEvent` a un estado no señalado.</span><span class="sxs-lookup"><span data-stu-id="692ab-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="692ab-109">Método Set</span><span class="sxs-lookup"><span data-stu-id="692ab-109">Set Method</span></span>](ihostmanualevent-set-method.md)|<span data-ttu-id="692ab-110">Establece la `IHostManualEvent` instancia actual en un estado señalado.</span><span class="sxs-lookup"><span data-stu-id="692ab-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="692ab-111">Wait (Método)</span><span class="sxs-lookup"><span data-stu-id="692ab-111">Wait Method</span></span>](ihostmanualevent-wait-method.md)|<span data-ttu-id="692ab-112">Hace que la `IHostManualEvent` instancia actual espere hasta que sea propiedad o transcurra un período de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="692ab-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="692ab-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="692ab-113">Requirements</span></span>  
 <span data-ttu-id="692ab-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="692ab-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="692ab-115">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="692ab-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="692ab-116">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="692ab-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="692ab-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="692ab-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="692ab-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="692ab-118">See also</span></span>

- [<span data-ttu-id="692ab-119">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="692ab-119">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="692ab-120">IHostAutoEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="692ab-120">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="692ab-121">IHostSemaphore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="692ab-121">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="692ab-122">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="692ab-122">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="692ab-123">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="692ab-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
