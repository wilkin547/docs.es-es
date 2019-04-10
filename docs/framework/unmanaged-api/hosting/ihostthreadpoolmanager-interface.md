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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e7976740a79efda8e5ab569f2efb55444012c5d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220375"
---
# <a name="ihostthreadpoolmanager-interface"></a><span data-ttu-id="d9323-102">IHostThreadPoolManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d9323-102">IHostThreadPoolManager Interface</span></span>
<span data-ttu-id="d9323-103">Proporciona métodos que permiten a common language runtime (CLR) para configurar el grupo de subprocesos y poner en cola los elementos de trabajo al grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="d9323-103">Provides methods that enable the common language runtime (CLR) to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d9323-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="d9323-104">Methods</span></span>  
  
|<span data-ttu-id="d9323-105">Método</span><span class="sxs-lookup"><span data-stu-id="d9323-105">Method</span></span>|<span data-ttu-id="d9323-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9323-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d9323-107">Método GetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="d9323-107">GetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)|<span data-ttu-id="d9323-108">Obtiene el número de subprocesos en el grupo de subprocesos que no se están procesando actualmente elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d9323-108">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>|  
|[<span data-ttu-id="d9323-109">Método GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="d9323-109">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)|<span data-ttu-id="d9323-110">Obtiene el número máximo de subprocesos que el host mantiene simultáneamente en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="d9323-110">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>|  
|[<span data-ttu-id="d9323-111">Método GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="d9323-111">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)|<span data-ttu-id="d9323-112">Obtiene el número mínimo de subprocesos inactivos que mantiene el host en previsión de solicitudes.</span><span class="sxs-lookup"><span data-stu-id="d9323-112">Gets the minimum number of idle threads that the host maintains in anticipation of requests.</span></span>|  
|[<span data-ttu-id="d9323-113">Método QueueUserWorkItem</span><span class="sxs-lookup"><span data-stu-id="d9323-113">QueueUserWorkItem Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)|<span data-ttu-id="d9323-114">Pone en cola una función para su ejecución y proporciona un objeto que contiene los datos que va a usar la función.</span><span class="sxs-lookup"><span data-stu-id="d9323-114">Queues a function for execution, and provides an object containing data to be used by the function.</span></span>|  
|[<span data-ttu-id="d9323-115">Método SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="d9323-115">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)|<span data-ttu-id="d9323-116">Establece el número máximo de subprocesos que el host puede mantener en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="d9323-116">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>|  
|[<span data-ttu-id="d9323-117">Método SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="d9323-117">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)|<span data-ttu-id="d9323-118">Establece el número mínimo de subprocesos inactivos que el host debe mantener en previsión de solicitudes.</span><span class="sxs-lookup"><span data-stu-id="d9323-118">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9323-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d9323-119">Remarks</span></span>  
 <span data-ttu-id="d9323-120">El host no es necesario para configurar el grupo de subprocesos mediante los valores especificados en las llamadas a la `SetMaxThreads` y `SetMinThreads` métodos.</span><span class="sxs-lookup"><span data-stu-id="d9323-120">The host is not required to configure the thread pool by using the values specified in calls to the `SetMaxThreads` and `SetMinThreads` methods.</span></span> <span data-ttu-id="d9323-121">En este caso, el host debe devolver un valor HRESULT de E_NOTIMPL desde estos métodos.</span><span class="sxs-lookup"><span data-stu-id="d9323-121">In this case, the host should return an HRESULT value of E_NOTIMPL from these methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9323-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d9323-122">Requirements</span></span>  
 <span data-ttu-id="d9323-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9323-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9323-124">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d9323-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d9323-125">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d9323-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d9323-126">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d9323-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d9323-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9323-127">See also</span></span>

- <xref:System.Threading>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="d9323-128">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="d9323-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
