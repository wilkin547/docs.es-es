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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 186f5618cce7a70bc4fab55616a0f8b08025a81f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54542543"
---
# <a name="ihostiocompletionmanager-interface"></a><span data-ttu-id="00106-102">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="00106-102">IHostIoCompletionManager Interface</span></span>
<span data-ttu-id="00106-103">Proporciona métodos que permiten a common language runtime (CLR) para interactuar con los puertos de terminación de E/S proporcionados por el host.</span><span class="sxs-lookup"><span data-stu-id="00106-103">Provides methods that allow the common language runtime (CLR) to interact with I/O completion ports provided by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="00106-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="00106-104">Methods</span></span>  
  
|<span data-ttu-id="00106-105">Método</span><span class="sxs-lookup"><span data-stu-id="00106-105">Method</span></span>|<span data-ttu-id="00106-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="00106-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="00106-107">Bind (método)</span><span class="sxs-lookup"><span data-stu-id="00106-107">Bind Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)|<span data-ttu-id="00106-108">Enlaza un identificador a un puerto de terminación de E/S.</span><span class="sxs-lookup"><span data-stu-id="00106-108">Binds a handle to an I/O completion port.</span></span>|  
|[<span data-ttu-id="00106-109">CloseIoCompletionPort (método)</span><span class="sxs-lookup"><span data-stu-id="00106-109">CloseIoCompletionPort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-closeiocompletionport-method.md)|<span data-ttu-id="00106-110">Cierra un puerto que se creó mediante una llamada anterior a `CreateIoCompletionPort`.</span><span class="sxs-lookup"><span data-stu-id="00106-110">Closes a port that was created through an earlier call to `CreateIoCompletionPort`.</span></span>|  
|[<span data-ttu-id="00106-111">CreateIoCompletionPort (método)</span><span class="sxs-lookup"><span data-stu-id="00106-111">CreateIoCompletionPort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)|<span data-ttu-id="00106-112">Solicita que el host cree un nuevo puerto de terminación de E/S.</span><span class="sxs-lookup"><span data-stu-id="00106-112">Requests that the host create a new I/O completion port.</span></span>|  
|[<span data-ttu-id="00106-113">GetAvailableThreads (método)</span><span class="sxs-lookup"><span data-stu-id="00106-113">GetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getavailablethreads-method.md)|<span data-ttu-id="00106-114">Obtiene el número de subprocesos de finalización de E/S que no se están procesando actualmente las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="00106-114">Gets the number of I/O completion threads that are not currently processing requests.</span></span>|  
|[<span data-ttu-id="00106-115">GetHostOverlappedSize (método)</span><span class="sxs-lookup"><span data-stu-id="00106-115">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)|<span data-ttu-id="00106-116">Obtiene el tamaño de los datos personalizados que el host pretende anexar a las solicitudes de E/S.</span><span class="sxs-lookup"><span data-stu-id="00106-116">Gets the size of any custom data the host intends to append to I/O requests.</span></span>|  
|[<span data-ttu-id="00106-117">GetMaxThreads (método)</span><span class="sxs-lookup"><span data-stu-id="00106-117">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getmaxthreads-method.md)|<span data-ttu-id="00106-118">Obtiene el número máximo de subprocesos que el host puede asignar para atender las solicitudes de E/S.</span><span class="sxs-lookup"><span data-stu-id="00106-118">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>|  
|[<span data-ttu-id="00106-119">GetMinThreads (método)</span><span class="sxs-lookup"><span data-stu-id="00106-119">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getminthreads-method.md)|<span data-ttu-id="00106-120">Obtiene el número mínimo de subprocesos que proporciona el host para atender las solicitudes de E/S.</span><span class="sxs-lookup"><span data-stu-id="00106-120">Gets the minimum number of threads that the host provides to service I/O requests.</span></span>|  
|[<span data-ttu-id="00106-121">InitializeHostOverlapped (método)</span><span class="sxs-lookup"><span data-stu-id="00106-121">InitializeHostOverlapped Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md)|<span data-ttu-id="00106-122">Proporciona una oportunidad para inicializar los datos personalizados sobre una solicitud de E/S al host.</span><span class="sxs-lookup"><span data-stu-id="00106-122">Provides the host with an opportunity to initialize any custom data about an I/O request.</span></span>|  
|[<span data-ttu-id="00106-123">SetCLRIoCompletionManager (método)</span><span class="sxs-lookup"><span data-stu-id="00106-123">SetCLRIoCompletionManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setclriocompletionmanager-method.md)|<span data-ttu-id="00106-124">Proporciona el host con un puntero de interfaz a un [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instancia implementada por CLR.</span><span class="sxs-lookup"><span data-stu-id="00106-124">Provides the host with an interface pointer to an [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the CLR.</span></span>|  
|[<span data-ttu-id="00106-125">SetMaxThreads (método)</span><span class="sxs-lookup"><span data-stu-id="00106-125">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)|<span data-ttu-id="00106-126">Establece el número máximo de subprocesos que el host asigna para atender las solicitudes de E/S.</span><span class="sxs-lookup"><span data-stu-id="00106-126">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>|  
|[<span data-ttu-id="00106-127">SetMinThreads (método)</span><span class="sxs-lookup"><span data-stu-id="00106-127">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setminthreads-method.md)|<span data-ttu-id="00106-128">Establece el número mínimo de subprocesos que el host debe asignar a la finalización de E/S.</span><span class="sxs-lookup"><span data-stu-id="00106-128">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00106-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="00106-129">Remarks</span></span>  
 <span data-ttu-id="00106-130">`IHostIoCompletionManager` corresponde a la `ICLRIoCompletionManager` interfaz implementada por CLR.</span><span class="sxs-lookup"><span data-stu-id="00106-130">`IHostIoCompletionManager` corresponds to the `ICLRIoCompletionManager` interface implemented by the CLR.</span></span> <span data-ttu-id="00106-131">CLR llama a los métodos de `IHostIoCompletionManager` para enlazar los identificadores a los puertos que proporciona el host y el host llama a los métodos de `ICLRIoCompletionManager` para notificar la finalización de las solicitudes de E/S.</span><span class="sxs-lookup"><span data-stu-id="00106-131">The CLR calls the methods of `IHostIoCompletionManager` to bind handles to the ports that the host provides, and the host calls the methods of `ICLRIoCompletionManager` to report the completion of I/O requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00106-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="00106-132">Requirements</span></span>  
 <span data-ttu-id="00106-133">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00106-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00106-134">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="00106-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="00106-135">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="00106-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="00106-136">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00106-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00106-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="00106-137">See also</span></span>
- [<span data-ttu-id="00106-138">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="00106-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
