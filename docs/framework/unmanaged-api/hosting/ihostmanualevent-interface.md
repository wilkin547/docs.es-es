---
description: 'Más información sobre: IHostManualEvent (interfaz)'
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
ms.openlocfilehash: 1c70935568b9ff4080fd5bcdc372c02d354aa06f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708169"
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="ba6b7-103">IHostManualEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba6b7-103">IHostManualEvent Interface</span></span>

<span data-ttu-id="ba6b7-104">Proporciona la implementación del host de una representación de un evento de restablecimiento manual.</span><span class="sxs-lookup"><span data-stu-id="ba6b7-104">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ba6b7-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="ba6b7-105">Methods</span></span>  
  
|<span data-ttu-id="ba6b7-106">Método</span><span class="sxs-lookup"><span data-stu-id="ba6b7-106">Method</span></span>|<span data-ttu-id="ba6b7-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba6b7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ba6b7-108">Reset (Método)</span><span class="sxs-lookup"><span data-stu-id="ba6b7-108">Reset Method</span></span>](ihostmanualevent-reset-method.md)|<span data-ttu-id="ba6b7-109">Restablece la instancia actual `IHostManualEvent` a un estado no señalado.</span><span class="sxs-lookup"><span data-stu-id="ba6b7-109">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="ba6b7-110">Método Set</span><span class="sxs-lookup"><span data-stu-id="ba6b7-110">Set Method</span></span>](ihostmanualevent-set-method.md)|<span data-ttu-id="ba6b7-111">Establece la `IHostManualEvent` instancia actual en un estado señalado.</span><span class="sxs-lookup"><span data-stu-id="ba6b7-111">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="ba6b7-112">Wait (Método)</span><span class="sxs-lookup"><span data-stu-id="ba6b7-112">Wait Method</span></span>](ihostmanualevent-wait-method.md)|<span data-ttu-id="ba6b7-113">Hace que la `IHostManualEvent` instancia actual espere hasta que sea propiedad o transcurra un período de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="ba6b7-113">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ba6b7-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ba6b7-114">Requirements</span></span>  

 <span data-ttu-id="ba6b7-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba6b7-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba6b7-116">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ba6b7-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ba6b7-117">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ba6b7-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ba6b7-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba6b7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba6b7-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba6b7-119">See also</span></span>

- [<span data-ttu-id="ba6b7-120">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba6b7-120">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="ba6b7-121">IHostAutoEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba6b7-121">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="ba6b7-122">IHostSemaphore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba6b7-122">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="ba6b7-123">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba6b7-123">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="ba6b7-124">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="ba6b7-124">Hosting Interfaces</span></span>](hosting-interfaces.md)
