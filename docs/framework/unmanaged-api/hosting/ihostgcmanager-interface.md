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
ms.openlocfilehash: eb7e52b5237d4341c27b8c167249dc2614168679
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729538"
---
# <a name="ihostgcmanager-interface"></a><span data-ttu-id="741f7-102">IHostGCManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="741f7-102">IHostGCManager Interface</span></span>

<span data-ttu-id="741f7-103">Proporciona métodos que notifican al host de eventos en el mecanismo de recolección de elementos no utilizados implementado por el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="741f7-103">Provides methods that notify the host of events in the garbage collection mechanism implemented by the common language runtime (CLR).</span></span>  
  
## <a name="members"></a><span data-ttu-id="741f7-104">Miembros</span><span class="sxs-lookup"><span data-stu-id="741f7-104">Members</span></span>  
  
|<span data-ttu-id="741f7-105">Miembro</span><span class="sxs-lookup"><span data-stu-id="741f7-105">Member</span></span>|<span data-ttu-id="741f7-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="741f7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="741f7-107">Método SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="741f7-107">SuspensionEnding Method</span></span>](ihostgcmanager-suspensionending-method.md)|<span data-ttu-id="741f7-108">Notifica al host que el CLR está reanudando la ejecución de las tareas en los subprocesos que se han suspendido para una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="741f7-108">Notifies the host that the CLR is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>|  
|[<span data-ttu-id="741f7-109">Método SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="741f7-109">SuspensionStarting Method</span></span>](ihostgcmanager-suspensionstarting-method.md)|<span data-ttu-id="741f7-110">Notifica al host que el CLR está suspendiendo la ejecución de las tareas, para realizar una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="741f7-110">Notifies the host that the CLR is suspending execution of tasks, to perform a garbage collection.</span></span>|  
|[<span data-ttu-id="741f7-111">Método ThreadIsBlockingForSuspension</span><span class="sxs-lookup"><span data-stu-id="741f7-111">ThreadIsBlockingForSuspension Method</span></span>](ihostgcmanager-threadisblockingforsuspension-method.md)|<span data-ttu-id="741f7-112">Notifica al host que el subproceso del que se realizó la llamada al método está a punto de bloquearse para una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="741f7-112">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="741f7-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="741f7-113">Requirements</span></span>  

 <span data-ttu-id="741f7-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="741f7-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="741f7-115">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="741f7-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="741f7-116">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="741f7-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="741f7-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="741f7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="741f7-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="741f7-118">See also</span></span>

- [<span data-ttu-id="741f7-119">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="741f7-119">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="741f7-120">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="741f7-120">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="741f7-121">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="741f7-121">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="741f7-122">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="741f7-122">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="741f7-123">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="741f7-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
