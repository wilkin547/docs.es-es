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
ms.openlocfilehash: 5bfab21a36becf943b1813f266cf70c4b5e5b1d2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690998"
---
# <a name="iclrsyncmanager-interface"></a><span data-ttu-id="b35eb-102">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b35eb-102">ICLRSyncManager Interface</span></span>

<span data-ttu-id="b35eb-103">Define métodos que permiten al host obtener información sobre las tareas solicitadas y detectar interbloqueos en su implementación de sincronización.</span><span class="sxs-lookup"><span data-stu-id="b35eb-103">Defines methods that allow the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b35eb-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="b35eb-104">Methods</span></span>  
  
|<span data-ttu-id="b35eb-105">Método</span><span class="sxs-lookup"><span data-stu-id="b35eb-105">Method</span></span>|<span data-ttu-id="b35eb-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b35eb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b35eb-107">Método CreateRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="b35eb-107">CreateRWLockOwnerIterator Method</span></span>](iclrsyncmanager-createrwlockowneriterator-method.md)|<span data-ttu-id="b35eb-108">Solicita que el Common Language Runtime (CLR) cree un iterador para que lo use el host con el fin de determinar el conjunto de tareas que esperan en un bloqueo de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="b35eb-108">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>|  
|[<span data-ttu-id="b35eb-109">Método DeleteRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="b35eb-109">DeleteRWLockOwnerIterator Method</span></span>](iclrsyncmanager-deleterwlockowneriterator-method.md)|<span data-ttu-id="b35eb-110">Solicita que CLR destruya un iterador creado por una llamada a `CreateRWLockOwnerIterator` .</span><span class="sxs-lookup"><span data-stu-id="b35eb-110">Requests that the CLR destroy an iterator that was created by a call to `CreateRWLockOwnerIterator`.</span></span>|  
|[<span data-ttu-id="b35eb-111">Método GetMonitorOwner</span><span class="sxs-lookup"><span data-stu-id="b35eb-111">GetMonitorOwner Method</span></span>](iclrsyncmanager-getmonitorowner-method.md)|<span data-ttu-id="b35eb-112">Obtiene la tarea que posee el monitor especificado.</span><span class="sxs-lookup"><span data-stu-id="b35eb-112">Gets the task that owns the specified monitor.</span></span>|  
|[<span data-ttu-id="b35eb-113">Método GetRWLockOwnerNext</span><span class="sxs-lookup"><span data-stu-id="b35eb-113">GetRWLockOwnerNext Method</span></span>](iclrsyncmanager-getrwlockownernext-method.md)|<span data-ttu-id="b35eb-114">Obtiene la siguiente tarea que está esperando en el bloqueo de lector-Writer actual.</span><span class="sxs-lookup"><span data-stu-id="b35eb-114">Gets the next task that is waiting on the current reader-writer lock.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b35eb-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b35eb-115">Requirements</span></span>  

 <span data-ttu-id="b35eb-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b35eb-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b35eb-117">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b35eb-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b35eb-118">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b35eb-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b35eb-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b35eb-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b35eb-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b35eb-120">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="b35eb-121">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b35eb-121">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- <span data-ttu-id="b35eb-122">[Subprocesamiento administrado y no administrado](/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b35eb-122">[Managed and Unmanaged Threading](/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span></span>
- [<span data-ttu-id="b35eb-123">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="b35eb-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
