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
ms.openlocfilehash: 8eba189d6dfca3781c28631a72a9af3c037efeda
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136792"
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="27a34-102">IHostManualEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="27a34-102">IHostManualEvent Interface</span></span>
<span data-ttu-id="27a34-103">Proporciona la implementación del host de una representación de un evento de restablecimiento manual.</span><span class="sxs-lookup"><span data-stu-id="27a34-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="27a34-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="27a34-104">Methods</span></span>  
  
|<span data-ttu-id="27a34-105">Método</span><span class="sxs-lookup"><span data-stu-id="27a34-105">Method</span></span>|<span data-ttu-id="27a34-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="27a34-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="27a34-107">Reset (método)</span><span class="sxs-lookup"><span data-stu-id="27a34-107">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)|<span data-ttu-id="27a34-108">Restablece la instancia de `IHostManualEvent` actual a un estado no señalado.</span><span class="sxs-lookup"><span data-stu-id="27a34-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="27a34-109">Set (método)</span><span class="sxs-lookup"><span data-stu-id="27a34-109">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-set-method.md)|<span data-ttu-id="27a34-110">Establece la instancia de `IHostManualEvent` actual en un estado señalado.</span><span class="sxs-lookup"><span data-stu-id="27a34-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="27a34-111">Wait (método)</span><span class="sxs-lookup"><span data-stu-id="27a34-111">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-wait-method.md)|<span data-ttu-id="27a34-112">Hace que la instancia de `IHostManualEvent` actual espere hasta que sea propiedad o transcurra un período de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="27a34-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="27a34-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="27a34-113">Requirements</span></span>  
 <span data-ttu-id="27a34-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27a34-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27a34-115">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="27a34-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="27a34-116">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="27a34-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="27a34-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27a34-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27a34-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="27a34-118">See also</span></span>

- [<span data-ttu-id="27a34-119">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="27a34-119">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="27a34-120">IHostAutoEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="27a34-120">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="27a34-121">IHostSemaphore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="27a34-121">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="27a34-122">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="27a34-122">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="27a34-123">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="27a34-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
