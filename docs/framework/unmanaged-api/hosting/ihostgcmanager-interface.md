---
description: 'Más información acerca de: interfaz IHostGCManager'
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
ms.openlocfilehash: da229c04eb5f5a27c34c133b5c88183d00f47c40
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708663"
---
# <a name="ihostgcmanager-interface"></a><span data-ttu-id="0d4cf-103">IHostGCManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0d4cf-103">IHostGCManager Interface</span></span>

<span data-ttu-id="0d4cf-104">Proporciona métodos que notifican al host de eventos en el mecanismo de recolección de elementos no utilizados implementado por el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="0d4cf-104">Provides methods that notify the host of events in the garbage collection mechanism implemented by the common language runtime (CLR).</span></span>  
  
## <a name="members"></a><span data-ttu-id="0d4cf-105">Members</span><span class="sxs-lookup"><span data-stu-id="0d4cf-105">Members</span></span>  
  
|<span data-ttu-id="0d4cf-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="0d4cf-106">Member</span></span>|<span data-ttu-id="0d4cf-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0d4cf-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0d4cf-108">Método SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="0d4cf-108">SuspensionEnding Method</span></span>](ihostgcmanager-suspensionending-method.md)|<span data-ttu-id="0d4cf-109">Notifica al host que el CLR está reanudando la ejecución de las tareas en los subprocesos que se han suspendido para una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="0d4cf-109">Notifies the host that the CLR is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>|  
|[<span data-ttu-id="0d4cf-110">Método SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="0d4cf-110">SuspensionStarting Method</span></span>](ihostgcmanager-suspensionstarting-method.md)|<span data-ttu-id="0d4cf-111">Notifica al host que el CLR está suspendiendo la ejecución de las tareas, para realizar una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="0d4cf-111">Notifies the host that the CLR is suspending execution of tasks, to perform a garbage collection.</span></span>|  
|[<span data-ttu-id="0d4cf-112">Método ThreadIsBlockingForSuspension</span><span class="sxs-lookup"><span data-stu-id="0d4cf-112">ThreadIsBlockingForSuspension Method</span></span>](ihostgcmanager-threadisblockingforsuspension-method.md)|<span data-ttu-id="0d4cf-113">Notifica al host que el subproceso del que se realizó la llamada al método está a punto de bloquearse para una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="0d4cf-113">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0d4cf-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0d4cf-114">Requirements</span></span>  

 <span data-ttu-id="0d4cf-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d4cf-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d4cf-116">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0d4cf-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0d4cf-117">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0d4cf-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0d4cf-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d4cf-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d4cf-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d4cf-119">See also</span></span>

- [<span data-ttu-id="0d4cf-120">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0d4cf-120">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="0d4cf-121">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0d4cf-121">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="0d4cf-122">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0d4cf-122">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="0d4cf-123">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0d4cf-123">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="0d4cf-124">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="0d4cf-124">Hosting Interfaces</span></span>](hosting-interfaces.md)
