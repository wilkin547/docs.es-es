---
title: IHostGCManager (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager
helpviewer_keywords:
- IHostGCManager interface [.NET Framework hosting]
ms.assetid: 820330a4-244c-4f67-ab5e-f24b0b3c2080
topic_type:
- apiref
ms.openlocfilehash: 6f7158bcac7ad22647104e2041da959285d2be8f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130481"
---
# <a name="ihostgcmanager-interface"></a><span data-ttu-id="c30fe-102">IHostGCManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c30fe-102">IHostGCManager Interface</span></span>
<span data-ttu-id="c30fe-103">Proporciona métodos que notifican al host de eventos en el mecanismo de recolección de elementos no utilizados implementado por el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="c30fe-103">Provides methods that notify the host of events in the garbage collection mechanism implemented by the common language runtime (CLR).</span></span>  
  
## <a name="members"></a><span data-ttu-id="c30fe-104">Miembros</span><span class="sxs-lookup"><span data-stu-id="c30fe-104">Members</span></span>  
  
|<span data-ttu-id="c30fe-105">Miembro</span><span class="sxs-lookup"><span data-stu-id="c30fe-105">Member</span></span>|<span data-ttu-id="c30fe-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c30fe-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c30fe-107">SuspensionEnding (método)</span><span class="sxs-lookup"><span data-stu-id="c30fe-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md)|<span data-ttu-id="c30fe-108">Notifica al host que el CLR está reanudando la ejecución de las tareas en los subprocesos que se han suspendido para una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="c30fe-108">Notifies the host that the CLR is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>|  
|[<span data-ttu-id="c30fe-109">SuspensionStarting (método)</span><span class="sxs-lookup"><span data-stu-id="c30fe-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md)|<span data-ttu-id="c30fe-110">Notifica al host que el CLR está suspendiendo la ejecución de las tareas, para realizar una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="c30fe-110">Notifies the host that the CLR is suspending execution of tasks, to perform a garbage collection.</span></span>|  
|[<span data-ttu-id="c30fe-111">ThreadIsBlockingForSuspension (método)</span><span class="sxs-lookup"><span data-stu-id="c30fe-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md)|<span data-ttu-id="c30fe-112">Notifica al host que el subproceso del que se realizó la llamada al método está a punto de bloquearse para una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="c30fe-112">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c30fe-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c30fe-113">Requirements</span></span>  
 <span data-ttu-id="c30fe-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c30fe-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c30fe-115">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c30fe-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c30fe-116">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c30fe-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c30fe-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c30fe-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c30fe-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c30fe-118">See also</span></span>

- [<span data-ttu-id="c30fe-119">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c30fe-119">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="c30fe-120">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c30fe-120">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="c30fe-121">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c30fe-121">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="c30fe-122">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c30fe-122">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="c30fe-123">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="c30fe-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
