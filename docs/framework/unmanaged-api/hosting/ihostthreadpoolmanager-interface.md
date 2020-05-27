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
ms.openlocfilehash: bac29b5950f1547c5c60ac716d40d2ef4b1a2cc2
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842486"
---
# <a name="ihostthreadpoolmanager-interface"></a><span data-ttu-id="e3923-102">IHostThreadPoolManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e3923-102">IHostThreadPoolManager Interface</span></span>
<span data-ttu-id="e3923-103">Proporciona métodos que permiten al Common Language Runtime (CLR) configurar el grupo de subprocesos y poner en cola los elementos de trabajo en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="e3923-103">Provides methods that enable the common language runtime (CLR) to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e3923-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e3923-104">Methods</span></span>  
  
|<span data-ttu-id="e3923-105">Método</span><span class="sxs-lookup"><span data-stu-id="e3923-105">Method</span></span>|<span data-ttu-id="e3923-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3923-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e3923-107">Método GetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="e3923-107">GetAvailableThreads Method</span></span>](ihostthreadpoolmanager-getavailablethreads-method.md)|<span data-ttu-id="e3923-108">Obtiene el número de subprocesos del grupo de subprocesos que no están procesando actualmente los elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e3923-108">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>|  
|[<span data-ttu-id="e3923-109">Método GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="e3923-109">GetMaxThreads Method</span></span>](ihostthreadpoolmanager-getmaxthreads-method.md)|<span data-ttu-id="e3923-110">Obtiene el número máximo de subprocesos que el host mantiene simultáneamente en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="e3923-110">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>|  
|[<span data-ttu-id="e3923-111">Método GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="e3923-111">GetMinThreads Method</span></span>](ihostthreadpoolmanager-getminthreads-method.md)|<span data-ttu-id="e3923-112">Obtiene el número mínimo de subprocesos inactivos que el host mantiene en previsión de solicitudes.</span><span class="sxs-lookup"><span data-stu-id="e3923-112">Gets the minimum number of idle threads that the host maintains in anticipation of requests.</span></span>|  
|[<span data-ttu-id="e3923-113">Método QueueUserWorkItem</span><span class="sxs-lookup"><span data-stu-id="e3923-113">QueueUserWorkItem Method</span></span>](ihostthreadpoolmanager-queueuserworkitem-method.md)|<span data-ttu-id="e3923-114">Pone en cola una función para su ejecución y proporciona un objeto que contiene los datos que va a usar la función.</span><span class="sxs-lookup"><span data-stu-id="e3923-114">Queues a function for execution, and provides an object containing data to be used by the function.</span></span>|  
|[<span data-ttu-id="e3923-115">Método SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="e3923-115">SetMaxThreads Method</span></span>](ihostthreadpoolmanager-setmaxthreads-method.md)|<span data-ttu-id="e3923-116">Establece el número máximo de subprocesos que el host puede mantener en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="e3923-116">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>|  
|[<span data-ttu-id="e3923-117">Método SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="e3923-117">SetMinThreads Method</span></span>](ihostthreadpoolmanager-setminthreads-method.md)|<span data-ttu-id="e3923-118">Establece el número mínimo de subprocesos inactivos que el host debe mantener en previsión de las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="e3923-118">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3923-119">Notas</span><span class="sxs-lookup"><span data-stu-id="e3923-119">Remarks</span></span>  
 <span data-ttu-id="e3923-120">No es necesario que el host configure el grupo de subprocesos utilizando los valores especificados en las llamadas a los `SetMaxThreads` `SetMinThreads` métodos y.</span><span class="sxs-lookup"><span data-stu-id="e3923-120">The host is not required to configure the thread pool by using the values specified in calls to the `SetMaxThreads` and `SetMinThreads` methods.</span></span> <span data-ttu-id="e3923-121">En este caso, el host debe devolver un valor HRESULT de E_NOTIMPL de estos métodos.</span><span class="sxs-lookup"><span data-stu-id="e3923-121">In this case, the host should return an HRESULT value of E_NOTIMPL from these methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3923-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e3923-122">Requirements</span></span>  
 <span data-ttu-id="e3923-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3923-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3923-124">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e3923-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e3923-125">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e3923-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e3923-126">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3923-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3923-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3923-127">See also</span></span>

- <xref:System.Threading>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="e3923-128">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="e3923-128">Hosting Interfaces</span></span>](hosting-interfaces.md)
