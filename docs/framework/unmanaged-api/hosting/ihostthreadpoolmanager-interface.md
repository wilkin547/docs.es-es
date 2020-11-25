---
title: IHostThreadPoolManager (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager
helpviewer_keywords:
- IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: c3a2cd90-7c4e-4374-bb87-b41befb8344f
topic_type:
- apiref
ms.openlocfilehash: b6625b0ef4dc3de4067514a0b39849c7a958d5c4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730766"
---
# <a name="ihostthreadpoolmanager-interface"></a><span data-ttu-id="bf615-102">IHostThreadPoolManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf615-102">IHostThreadPoolManager Interface</span></span>

<span data-ttu-id="bf615-103">Proporciona métodos que permiten al Common Language Runtime (CLR) configurar el grupo de subprocesos y poner en cola los elementos de trabajo en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="bf615-103">Provides methods that enable the common language runtime (CLR) to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bf615-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="bf615-104">Methods</span></span>  
  
|<span data-ttu-id="bf615-105">Método</span><span class="sxs-lookup"><span data-stu-id="bf615-105">Method</span></span>|<span data-ttu-id="bf615-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf615-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bf615-107">Método GetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="bf615-107">GetAvailableThreads Method</span></span>](ihostthreadpoolmanager-getavailablethreads-method.md)|<span data-ttu-id="bf615-108">Obtiene el número de subprocesos del grupo de subprocesos que no están procesando actualmente los elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bf615-108">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>|  
|[<span data-ttu-id="bf615-109">Método GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="bf615-109">GetMaxThreads Method</span></span>](ihostthreadpoolmanager-getmaxthreads-method.md)|<span data-ttu-id="bf615-110">Obtiene el número máximo de subprocesos que el host mantiene simultáneamente en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="bf615-110">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>|  
|[<span data-ttu-id="bf615-111">Método GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="bf615-111">GetMinThreads Method</span></span>](ihostthreadpoolmanager-getminthreads-method.md)|<span data-ttu-id="bf615-112">Obtiene el número mínimo de subprocesos inactivos que el host mantiene en previsión de solicitudes.</span><span class="sxs-lookup"><span data-stu-id="bf615-112">Gets the minimum number of idle threads that the host maintains in anticipation of requests.</span></span>|  
|[<span data-ttu-id="bf615-113">Método QueueUserWorkItem</span><span class="sxs-lookup"><span data-stu-id="bf615-113">QueueUserWorkItem Method</span></span>](ihostthreadpoolmanager-queueuserworkitem-method.md)|<span data-ttu-id="bf615-114">Pone en cola una función para su ejecución y proporciona un objeto que contiene los datos que va a usar la función.</span><span class="sxs-lookup"><span data-stu-id="bf615-114">Queues a function for execution, and provides an object containing data to be used by the function.</span></span>|  
|[<span data-ttu-id="bf615-115">Método SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="bf615-115">SetMaxThreads Method</span></span>](ihostthreadpoolmanager-setmaxthreads-method.md)|<span data-ttu-id="bf615-116">Establece el número máximo de subprocesos que el host puede mantener en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="bf615-116">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>|  
|[<span data-ttu-id="bf615-117">Método SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="bf615-117">SetMinThreads Method</span></span>](ihostthreadpoolmanager-setminthreads-method.md)|<span data-ttu-id="bf615-118">Establece el número mínimo de subprocesos inactivos que el host debe mantener en previsión de las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="bf615-118">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf615-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bf615-119">Remarks</span></span>  

 <span data-ttu-id="bf615-120">No es necesario que el host configure el grupo de subprocesos utilizando los valores especificados en las llamadas a los `SetMaxThreads` `SetMinThreads` métodos y.</span><span class="sxs-lookup"><span data-stu-id="bf615-120">The host is not required to configure the thread pool by using the values specified in calls to the `SetMaxThreads` and `SetMinThreads` methods.</span></span> <span data-ttu-id="bf615-121">En este caso, el host debe devolver un valor HRESULT de E_NOTIMPL de estos métodos.</span><span class="sxs-lookup"><span data-stu-id="bf615-121">In this case, the host should return an HRESULT value of E_NOTIMPL from these methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf615-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf615-122">Requirements</span></span>  

 <span data-ttu-id="bf615-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf615-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf615-124">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="bf615-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bf615-125">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bf615-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bf615-126">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf615-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf615-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bf615-127">See also</span></span>

- <xref:System.Threading>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="bf615-128">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="bf615-128">Hosting Interfaces</span></span>](hosting-interfaces.md)
