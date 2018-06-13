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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4eac8abede82915386abc19c4c8389932451df4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440381"
---
# <a name="ihostgcmanager-interface"></a><span data-ttu-id="726c9-102">IHostGCManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="726c9-102">IHostGCManager Interface</span></span>
<span data-ttu-id="726c9-103">Proporciona métodos que notifican al host de eventos en el mecanismo de recopilación de elementos no utilizados implementado por common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="726c9-103">Provides methods that notify the host of events in the garbage collection mechanism implemented by the common language runtime (CLR).</span></span>  
  
## <a name="members"></a><span data-ttu-id="726c9-104">Miembros</span><span class="sxs-lookup"><span data-stu-id="726c9-104">Members</span></span>  
  
|<span data-ttu-id="726c9-105">Miembro</span><span class="sxs-lookup"><span data-stu-id="726c9-105">Member</span></span>|<span data-ttu-id="726c9-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="726c9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="726c9-107">SuspensionEnding (método)</span><span class="sxs-lookup"><span data-stu-id="726c9-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md)|<span data-ttu-id="726c9-108">Notifica al host que CLR está reanudando la ejecución de tareas en subprocesos que se habían suspendidos para una colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="726c9-108">Notifies the host that the CLR is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>|  
|[<span data-ttu-id="726c9-109">SuspensionStarting (método)</span><span class="sxs-lookup"><span data-stu-id="726c9-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md)|<span data-ttu-id="726c9-110">Notifica al host que CLR está suspendiendo la ejecución de tareas para realizar una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="726c9-110">Notifies the host that the CLR is suspending execution of tasks, to perform a garbage collection.</span></span>|  
|[<span data-ttu-id="726c9-111">ThreadIsBlockingForSuspension (método)</span><span class="sxs-lookup"><span data-stu-id="726c9-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md)|<span data-ttu-id="726c9-112">Notifica al host que el subproceso de la que se realizó la llamada al método está a punto de bloquearse para una colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="726c9-112">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="726c9-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="726c9-113">Requirements</span></span>  
 <span data-ttu-id="726c9-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="726c9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="726c9-115">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="726c9-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="726c9-116">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="726c9-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="726c9-117">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="726c9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="726c9-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="726c9-118">See Also</span></span>  
 [<span data-ttu-id="726c9-119">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="726c9-119">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="726c9-120">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="726c9-120">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="726c9-121">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="726c9-121">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="726c9-122">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="726c9-122">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="726c9-123">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="726c9-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
