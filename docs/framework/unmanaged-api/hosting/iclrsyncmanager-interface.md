---
title: ICLRSyncManager (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager
helpviewer_keywords:
- ICLRSyncManager interface [.NET Framework hosting]
ms.assetid: a49f9d80-1c76-4ddd-8c49-34f913a5c596
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b87ccc3d6c3e957d0384499048032e35247093a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436486"
---
# <a name="iclrsyncmanager-interface"></a><span data-ttu-id="191e2-102">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="191e2-102">ICLRSyncManager Interface</span></span>
<span data-ttu-id="191e2-103">Define métodos que permiten al host para obtener información sobre las tareas solicitadas y detectar interbloqueos en su implementación de la sincronización.</span><span class="sxs-lookup"><span data-stu-id="191e2-103">Defines methods that allow the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="191e2-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="191e2-104">Methods</span></span>  
  
|<span data-ttu-id="191e2-105">Método</span><span class="sxs-lookup"><span data-stu-id="191e2-105">Method</span></span>|<span data-ttu-id="191e2-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="191e2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="191e2-107">CreateRWLockOwnerIterator (método)</span><span class="sxs-lookup"><span data-stu-id="191e2-107">CreateRWLockOwnerIterator Method</span></span>](iclrsyncmanager-createrwlockowneriterator-method.md)|<span data-ttu-id="191e2-108">Solicita que common language runtime (CLR) cree un iterador para el host se utiliza para determinar el conjunto de tareas que esperan en un bloqueo de lector y escritor.</span><span class="sxs-lookup"><span data-stu-id="191e2-108">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>|  
|[<span data-ttu-id="191e2-109">DeleteRWLockOwnerIterator (método)</span><span class="sxs-lookup"><span data-stu-id="191e2-109">DeleteRWLockOwnerIterator Method</span></span>](iclrsyncmanager-deleterwlockowneriterator-method.md)|<span data-ttu-id="191e2-110">Solicita que CLR destruya un iterador que se creó mediante una llamada a `CreateRWLockOwnerIterator`.</span><span class="sxs-lookup"><span data-stu-id="191e2-110">Requests that the CLR destroy an iterator that was created by a call to `CreateRWLockOwnerIterator`.</span></span>|  
|[<span data-ttu-id="191e2-111">GetMonitorOwner (método)</span><span class="sxs-lookup"><span data-stu-id="191e2-111">GetMonitorOwner Method</span></span>](iclrsyncmanager-getmonitorowner-method.md)|<span data-ttu-id="191e2-112">Obtiene la tarea que posee al monitor especificado.</span><span class="sxs-lookup"><span data-stu-id="191e2-112">Gets the task that owns the specified monitor.</span></span>|  
|[<span data-ttu-id="191e2-113">GetRWLockOwnerNext (método)</span><span class="sxs-lookup"><span data-stu-id="191e2-113">GetRWLockOwnerNext Method</span></span>](iclrsyncmanager-getrwlockownernext-method.md)|<span data-ttu-id="191e2-114">Obtiene la siguiente tarea está esperando el bloqueo de lector y escritor actual.</span><span class="sxs-lookup"><span data-stu-id="191e2-114">Gets the next task that is waiting on the current reader-writer lock.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="191e2-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="191e2-115">Requirements</span></span>  
 <span data-ttu-id="191e2-116">**Plataformas:** vea [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="191e2-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="191e2-117">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="191e2-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="191e2-118">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="191e2-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="191e2-119">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="191e2-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="191e2-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="191e2-120">See Also</span></span>  
 <xref:System.Threading.Thread>  
 [<span data-ttu-id="191e2-121">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="191e2-121">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)  
 <span data-ttu-id="191e2-122">[Subprocesamiento administrado y no administrado](https://msdn.microsoft.com/library/db425c20-4b2f-4433-bf96-76071c7881e5(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="191e2-122">[Managed and Unmanaged Threading](https://msdn.microsoft.com/library/db425c20-4b2f-4433-bf96-76071c7881e5(v=vs.100))</span></span>  
 [<span data-ttu-id="191e2-123">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="191e2-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
