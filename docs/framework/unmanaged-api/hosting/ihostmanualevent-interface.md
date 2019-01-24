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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb09422872a0d9565be286c25ca1b28d1c45e08f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501703"
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="c125d-102">IHostManualEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c125d-102">IHostManualEvent Interface</span></span>
<span data-ttu-id="c125d-103">Proporciona la implementación del host de una representación de un evento de restablecimiento manual.</span><span class="sxs-lookup"><span data-stu-id="c125d-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c125d-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c125d-104">Methods</span></span>  
  
|<span data-ttu-id="c125d-105">Método</span><span class="sxs-lookup"><span data-stu-id="c125d-105">Method</span></span>|<span data-ttu-id="c125d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c125d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c125d-107">Reset (método)</span><span class="sxs-lookup"><span data-stu-id="c125d-107">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)|<span data-ttu-id="c125d-108">Restablece el actual `IHostManualEvent` instancia a un estado no señalado.</span><span class="sxs-lookup"><span data-stu-id="c125d-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="c125d-109">Set (método)</span><span class="sxs-lookup"><span data-stu-id="c125d-109">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-set-method.md)|<span data-ttu-id="c125d-110">Establece el actual `IHostManualEvent` instancia en un estado señalado.</span><span class="sxs-lookup"><span data-stu-id="c125d-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="c125d-111">Wait (método)</span><span class="sxs-lookup"><span data-stu-id="c125d-111">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-wait-method.md)|<span data-ttu-id="c125d-112">Hace que el actual `IHostManualEvent` instancia espere hasta que sea propiedad o un período de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="c125d-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c125d-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c125d-113">Requirements</span></span>  
 <span data-ttu-id="c125d-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c125d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c125d-115">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c125d-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c125d-116">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c125d-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c125d-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c125d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c125d-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c125d-118">See also</span></span>
- [<span data-ttu-id="c125d-119">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c125d-119">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="c125d-120">IHostAutoEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c125d-120">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="c125d-121">IHostSemaphore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c125d-121">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="c125d-122">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c125d-122">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="c125d-123">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="c125d-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
