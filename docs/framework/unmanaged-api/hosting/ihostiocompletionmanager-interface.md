---
title: IHostIoCompletionManager (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c28d1983-83f7-46e2-990f-dbb9dc07c818
topic_type:
- apiref
ms.openlocfilehash: 51d79c398c94ec355528140325da2c25422cbad9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133847"
---
# <a name="ihostiocompletionmanager-interface"></a><span data-ttu-id="1411c-102">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1411c-102">IHostIoCompletionManager Interface</span></span>
<span data-ttu-id="1411c-103">Proporciona métodos que permiten que el Common Language Runtime (CLR) interactúe con los puertos de finalización de e/s proporcionados por el host.</span><span class="sxs-lookup"><span data-stu-id="1411c-103">Provides methods that allow the common language runtime (CLR) to interact with I/O completion ports provided by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1411c-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="1411c-104">Methods</span></span>  
  
|<span data-ttu-id="1411c-105">Método</span><span class="sxs-lookup"><span data-stu-id="1411c-105">Method</span></span>|<span data-ttu-id="1411c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="1411c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1411c-107">Bind (método)</span><span class="sxs-lookup"><span data-stu-id="1411c-107">Bind Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)|<span data-ttu-id="1411c-108">Enlaza un identificador a un puerto de finalización de e/s.</span><span class="sxs-lookup"><span data-stu-id="1411c-108">Binds a handle to an I/O completion port.</span></span>|  
|[<span data-ttu-id="1411c-109">CloseIoCompletionPort (método)</span><span class="sxs-lookup"><span data-stu-id="1411c-109">CloseIoCompletionPort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-closeiocompletionport-method.md)|<span data-ttu-id="1411c-110">Cierra un puerto que se creó mediante una llamada anterior a `CreateIoCompletionPort`.</span><span class="sxs-lookup"><span data-stu-id="1411c-110">Closes a port that was created through an earlier call to `CreateIoCompletionPort`.</span></span>|  
|[<span data-ttu-id="1411c-111">CreateIoCompletionPort (método)</span><span class="sxs-lookup"><span data-stu-id="1411c-111">CreateIoCompletionPort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)|<span data-ttu-id="1411c-112">Solicita que el host cree un nuevo puerto de finalización de e/s.</span><span class="sxs-lookup"><span data-stu-id="1411c-112">Requests that the host create a new I/O completion port.</span></span>|  
|[<span data-ttu-id="1411c-113">GetAvailableThreads (método)</span><span class="sxs-lookup"><span data-stu-id="1411c-113">GetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getavailablethreads-method.md)|<span data-ttu-id="1411c-114">Obtiene el número de subprocesos de finalización de e/s que no están procesando actualmente solicitudes.</span><span class="sxs-lookup"><span data-stu-id="1411c-114">Gets the number of I/O completion threads that are not currently processing requests.</span></span>|  
|[<span data-ttu-id="1411c-115">GetHostOverlappedSize (método)</span><span class="sxs-lookup"><span data-stu-id="1411c-115">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)|<span data-ttu-id="1411c-116">Obtiene el tamaño de los datos personalizados que el host pretende anexar a las solicitudes de e/s.</span><span class="sxs-lookup"><span data-stu-id="1411c-116">Gets the size of any custom data the host intends to append to I/O requests.</span></span>|  
|[<span data-ttu-id="1411c-117">GetMaxThreads (método)</span><span class="sxs-lookup"><span data-stu-id="1411c-117">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getmaxthreads-method.md)|<span data-ttu-id="1411c-118">Obtiene el número máximo de subprocesos que el host puede asignar a las solicitudes de e/s de servicio.</span><span class="sxs-lookup"><span data-stu-id="1411c-118">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>|  
|[<span data-ttu-id="1411c-119">GetMinThreads (método)</span><span class="sxs-lookup"><span data-stu-id="1411c-119">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getminthreads-method.md)|<span data-ttu-id="1411c-120">Obtiene el número mínimo de subprocesos que proporciona el host para las solicitudes de e/s de servicio.</span><span class="sxs-lookup"><span data-stu-id="1411c-120">Gets the minimum number of threads that the host provides to service I/O requests.</span></span>|  
|[<span data-ttu-id="1411c-121">InitializeHostOverlapped (método)</span><span class="sxs-lookup"><span data-stu-id="1411c-121">InitializeHostOverlapped Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md)|<span data-ttu-id="1411c-122">Proporciona al host la oportunidad de inicializar los datos personalizados sobre una solicitud de e/s.</span><span class="sxs-lookup"><span data-stu-id="1411c-122">Provides the host with an opportunity to initialize any custom data about an I/O request.</span></span>|  
|[<span data-ttu-id="1411c-123">SetCLRIoCompletionManager (método)</span><span class="sxs-lookup"><span data-stu-id="1411c-123">SetCLRIoCompletionManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setclriocompletionmanager-method.md)|<span data-ttu-id="1411c-124">Proporciona al host un puntero de interfaz a una instancia de [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) implementada por CLR.</span><span class="sxs-lookup"><span data-stu-id="1411c-124">Provides the host with an interface pointer to an [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the CLR.</span></span>|  
|[<span data-ttu-id="1411c-125">SetMaxThreads (método)</span><span class="sxs-lookup"><span data-stu-id="1411c-125">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)|<span data-ttu-id="1411c-126">Establece el número máximo de subprocesos que el host asigna a las solicitudes de e/s de servicio.</span><span class="sxs-lookup"><span data-stu-id="1411c-126">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>|  
|[<span data-ttu-id="1411c-127">SetMinThreads (método)</span><span class="sxs-lookup"><span data-stu-id="1411c-127">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setminthreads-method.md)|<span data-ttu-id="1411c-128">Establece el número mínimo de subprocesos que el host debe asignar a la finalización de e/s.</span><span class="sxs-lookup"><span data-stu-id="1411c-128">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1411c-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1411c-129">Remarks</span></span>  
 <span data-ttu-id="1411c-130">`IHostIoCompletionManager` corresponde a la interfaz de `ICLRIoCompletionManager` implementada por CLR.</span><span class="sxs-lookup"><span data-stu-id="1411c-130">`IHostIoCompletionManager` corresponds to the `ICLRIoCompletionManager` interface implemented by the CLR.</span></span> <span data-ttu-id="1411c-131">CLR llama a los métodos de `IHostIoCompletionManager` para enlazar los identificadores a los puertos proporcionados por el host y el host llama a los métodos de `ICLRIoCompletionManager` para notificar la finalización de las solicitudes de e/s.</span><span class="sxs-lookup"><span data-stu-id="1411c-131">The CLR calls the methods of `IHostIoCompletionManager` to bind handles to the ports that the host provides, and the host calls the methods of `ICLRIoCompletionManager` to report the completion of I/O requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1411c-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1411c-132">Requirements</span></span>  
 <span data-ttu-id="1411c-133">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1411c-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1411c-134">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1411c-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1411c-135">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1411c-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1411c-136">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1411c-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1411c-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="1411c-137">See also</span></span>

- [<span data-ttu-id="1411c-138">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="1411c-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
