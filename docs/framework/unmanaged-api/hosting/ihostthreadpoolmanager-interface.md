---
description: 'Más información acerca de: IHostThreadPoolManager (interfaz)'
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
ms.openlocfilehash: 0361b7a08f781a8748e43959f65ce0e9f21bbac1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728426"
---
# <a name="ihostthreadpoolmanager-interface"></a><span data-ttu-id="080ab-103">IHostThreadPoolManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="080ab-103">IHostThreadPoolManager Interface</span></span>

<span data-ttu-id="080ab-104">Proporciona métodos que permiten al Common Language Runtime (CLR) configurar el grupo de subprocesos y poner en cola los elementos de trabajo en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="080ab-104">Provides methods that enable the common language runtime (CLR) to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="080ab-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="080ab-105">Methods</span></span>  
  
|<span data-ttu-id="080ab-106">Método</span><span class="sxs-lookup"><span data-stu-id="080ab-106">Method</span></span>|<span data-ttu-id="080ab-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="080ab-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="080ab-108">Método GetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="080ab-108">GetAvailableThreads Method</span></span>](ihostthreadpoolmanager-getavailablethreads-method.md)|<span data-ttu-id="080ab-109">Obtiene el número de subprocesos del grupo de subprocesos que no están procesando actualmente los elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="080ab-109">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>|  
|[<span data-ttu-id="080ab-110">Método GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="080ab-110">GetMaxThreads Method</span></span>](ihostthreadpoolmanager-getmaxthreads-method.md)|<span data-ttu-id="080ab-111">Obtiene el número máximo de subprocesos que el host mantiene simultáneamente en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="080ab-111">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>|  
|[<span data-ttu-id="080ab-112">Método GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="080ab-112">GetMinThreads Method</span></span>](ihostthreadpoolmanager-getminthreads-method.md)|<span data-ttu-id="080ab-113">Obtiene el número mínimo de subprocesos inactivos que el host mantiene en previsión de solicitudes.</span><span class="sxs-lookup"><span data-stu-id="080ab-113">Gets the minimum number of idle threads that the host maintains in anticipation of requests.</span></span>|  
|[<span data-ttu-id="080ab-114">Método QueueUserWorkItem</span><span class="sxs-lookup"><span data-stu-id="080ab-114">QueueUserWorkItem Method</span></span>](ihostthreadpoolmanager-queueuserworkitem-method.md)|<span data-ttu-id="080ab-115">Pone en cola una función para su ejecución y proporciona un objeto que contiene los datos que va a usar la función.</span><span class="sxs-lookup"><span data-stu-id="080ab-115">Queues a function for execution, and provides an object containing data to be used by the function.</span></span>|  
|[<span data-ttu-id="080ab-116">Método SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="080ab-116">SetMaxThreads Method</span></span>](ihostthreadpoolmanager-setmaxthreads-method.md)|<span data-ttu-id="080ab-117">Establece el número máximo de subprocesos que el host puede mantener en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="080ab-117">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>|  
|[<span data-ttu-id="080ab-118">Método SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="080ab-118">SetMinThreads Method</span></span>](ihostthreadpoolmanager-setminthreads-method.md)|<span data-ttu-id="080ab-119">Establece el número mínimo de subprocesos inactivos que el host debe mantener en previsión de las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="080ab-119">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="080ab-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="080ab-120">Remarks</span></span>  

 <span data-ttu-id="080ab-121">No es necesario que el host configure el grupo de subprocesos utilizando los valores especificados en las llamadas a los `SetMaxThreads` `SetMinThreads` métodos y.</span><span class="sxs-lookup"><span data-stu-id="080ab-121">The host is not required to configure the thread pool by using the values specified in calls to the `SetMaxThreads` and `SetMinThreads` methods.</span></span> <span data-ttu-id="080ab-122">En este caso, el host debe devolver un valor HRESULT de E_NOTIMPL de estos métodos.</span><span class="sxs-lookup"><span data-stu-id="080ab-122">In this case, the host should return an HRESULT value of E_NOTIMPL from these methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="080ab-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="080ab-123">Requirements</span></span>  

 <span data-ttu-id="080ab-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="080ab-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="080ab-125">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="080ab-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="080ab-126">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="080ab-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="080ab-127">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="080ab-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="080ab-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="080ab-128">See also</span></span>

- <xref:System.Threading>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="080ab-129">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="080ab-129">Hosting Interfaces</span></span>](hosting-interfaces.md)
