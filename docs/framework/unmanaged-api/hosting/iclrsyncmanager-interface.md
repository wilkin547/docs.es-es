---
description: 'Más información acerca de: ICLRSyncManager (interfaz)'
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
ms.openlocfilehash: 188d1c913d75666aea09b17244012401d377fa10
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785021"
---
# <a name="iclrsyncmanager-interface"></a><span data-ttu-id="64075-103">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="64075-103">ICLRSyncManager Interface</span></span>

<span data-ttu-id="64075-104">Define métodos que permiten al host obtener información sobre las tareas solicitadas y detectar interbloqueos en su implementación de sincronización.</span><span class="sxs-lookup"><span data-stu-id="64075-104">Defines methods that allow the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="64075-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="64075-105">Methods</span></span>  
  
|<span data-ttu-id="64075-106">Método</span><span class="sxs-lookup"><span data-stu-id="64075-106">Method</span></span>|<span data-ttu-id="64075-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="64075-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="64075-108">Método CreateRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="64075-108">CreateRWLockOwnerIterator Method</span></span>](iclrsyncmanager-createrwlockowneriterator-method.md)|<span data-ttu-id="64075-109">Solicita que el Common Language Runtime (CLR) cree un iterador para que lo use el host con el fin de determinar el conjunto de tareas que esperan en un bloqueo de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="64075-109">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>|  
|[<span data-ttu-id="64075-110">Método DeleteRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="64075-110">DeleteRWLockOwnerIterator Method</span></span>](iclrsyncmanager-deleterwlockowneriterator-method.md)|<span data-ttu-id="64075-111">Solicita que CLR destruya un iterador creado por una llamada a `CreateRWLockOwnerIterator` .</span><span class="sxs-lookup"><span data-stu-id="64075-111">Requests that the CLR destroy an iterator that was created by a call to `CreateRWLockOwnerIterator`.</span></span>|  
|[<span data-ttu-id="64075-112">Método GetMonitorOwner</span><span class="sxs-lookup"><span data-stu-id="64075-112">GetMonitorOwner Method</span></span>](iclrsyncmanager-getmonitorowner-method.md)|<span data-ttu-id="64075-113">Obtiene la tarea que posee el monitor especificado.</span><span class="sxs-lookup"><span data-stu-id="64075-113">Gets the task that owns the specified monitor.</span></span>|  
|[<span data-ttu-id="64075-114">Método GetRWLockOwnerNext</span><span class="sxs-lookup"><span data-stu-id="64075-114">GetRWLockOwnerNext Method</span></span>](iclrsyncmanager-getrwlockownernext-method.md)|<span data-ttu-id="64075-115">Obtiene la siguiente tarea que está esperando en el bloqueo de lector-Writer actual.</span><span class="sxs-lookup"><span data-stu-id="64075-115">Gets the next task that is waiting on the current reader-writer lock.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="64075-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="64075-116">Requirements</span></span>  

 <span data-ttu-id="64075-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64075-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64075-118">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="64075-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="64075-119">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="64075-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="64075-120">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64075-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64075-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="64075-121">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="64075-122">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="64075-122">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- <span data-ttu-id="64075-123">[Subprocesamiento administrado y no administrado](/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="64075-123">[Managed and Unmanaged Threading](/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span></span>
- [<span data-ttu-id="64075-124">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="64075-124">Hosting Interfaces</span></span>](hosting-interfaces.md)
