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
ms.openlocfilehash: 3c3bebe8eabd4d5fd5faec21e0b0efc408353bc2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197274"
---
# <a name="ihostiocompletionmanager-interface"></a><span data-ttu-id="83b59-102">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="83b59-102">IHostIoCompletionManager Interface</span></span>
<span data-ttu-id="83b59-103">Proporciona métodos que permiten a common language runtime (CLR) para interactuar con los puertos de terminación de E/S proporcionados por el host.</span><span class="sxs-lookup"><span data-stu-id="83b59-103">Provides methods that allow the common language runtime (CLR) to interact with I/O completion ports provided by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="83b59-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="83b59-104">Methods</span></span>  
  
|<span data-ttu-id="83b59-105">Método</span><span class="sxs-lookup"><span data-stu-id="83b59-105">Method</span></span>|<span data-ttu-id="83b59-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="83b59-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="83b59-107">Método Bind</span><span class="sxs-lookup"><span data-stu-id="83b59-107">Bind Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)|<span data-ttu-id="83b59-108">Enlaza un identificador a un puerto de terminación de E/S.</span><span class="sxs-lookup"><span data-stu-id="83b59-108">Binds a handle to an I/O completion port.</span></span>|  
|[<span data-ttu-id="83b59-109">Método CloseIoCompletionPort</span><span class="sxs-lookup"><span data-stu-id="83b59-109">CloseIoCompletionPort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-closeiocompletionport-method.md)|<span data-ttu-id="83b59-110">Cierra un puerto que se creó mediante una llamada anterior a `CreateIoCompletionPort`.</span><span class="sxs-lookup"><span data-stu-id="83b59-110">Closes a port that was created through an earlier call to `CreateIoCompletionPort`.</span></span>|  
|[<span data-ttu-id="83b59-111">Método CreateIoCompletionPort</span><span class="sxs-lookup"><span data-stu-id="83b59-111">CreateIoCompletionPort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)|<span data-ttu-id="83b59-112">Solicita que el host cree un nuevo puerto de terminación de E/S.</span><span class="sxs-lookup"><span data-stu-id="83b59-112">Requests that the host create a new I/O completion port.</span></span>|  
|[<span data-ttu-id="83b59-113">Método GetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="83b59-113">GetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getavailablethreads-method.md)|<span data-ttu-id="83b59-114">Obtiene el número de subprocesos de finalización de E/S que no se están procesando actualmente las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="83b59-114">Gets the number of I/O completion threads that are not currently processing requests.</span></span>|  
|[<span data-ttu-id="83b59-115">Método GetHostOverlappedSize</span><span class="sxs-lookup"><span data-stu-id="83b59-115">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)|<span data-ttu-id="83b59-116">Obtiene el tamaño de los datos personalizados que el host pretende anexar a las solicitudes de E/S.</span><span class="sxs-lookup"><span data-stu-id="83b59-116">Gets the size of any custom data the host intends to append to I/O requests.</span></span>|  
|[<span data-ttu-id="83b59-117">Método GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="83b59-117">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getmaxthreads-method.md)|<span data-ttu-id="83b59-118">Obtiene el número máximo de subprocesos que el host puede asignar para atender las solicitudes de E/S.</span><span class="sxs-lookup"><span data-stu-id="83b59-118">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>|  
|[<span data-ttu-id="83b59-119">Método GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="83b59-119">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getminthreads-method.md)|<span data-ttu-id="83b59-120">Obtiene el número mínimo de subprocesos que proporciona el host para atender las solicitudes de E/S.</span><span class="sxs-lookup"><span data-stu-id="83b59-120">Gets the minimum number of threads that the host provides to service I/O requests.</span></span>|  
|[<span data-ttu-id="83b59-121">Método InitializeHostOverlapped</span><span class="sxs-lookup"><span data-stu-id="83b59-121">InitializeHostOverlapped Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md)|<span data-ttu-id="83b59-122">Proporciona una oportunidad para inicializar los datos personalizados sobre una solicitud de E/S al host.</span><span class="sxs-lookup"><span data-stu-id="83b59-122">Provides the host with an opportunity to initialize any custom data about an I/O request.</span></span>|  
|[<span data-ttu-id="83b59-123">Método SetCLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="83b59-123">SetCLRIoCompletionManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setclriocompletionmanager-method.md)|<span data-ttu-id="83b59-124">Proporciona el host con un puntero de interfaz a un [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instancia implementada por CLR.</span><span class="sxs-lookup"><span data-stu-id="83b59-124">Provides the host with an interface pointer to an [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the CLR.</span></span>|  
|[<span data-ttu-id="83b59-125">Método SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="83b59-125">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)|<span data-ttu-id="83b59-126">Establece el número máximo de subprocesos que el host asigna para atender las solicitudes de E/S.</span><span class="sxs-lookup"><span data-stu-id="83b59-126">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>|  
|[<span data-ttu-id="83b59-127">Método SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="83b59-127">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setminthreads-method.md)|<span data-ttu-id="83b59-128">Establece el número mínimo de subprocesos que el host debe asignar a la finalización de E/S.</span><span class="sxs-lookup"><span data-stu-id="83b59-128">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83b59-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="83b59-129">Remarks</span></span>  
 `IHostIoCompletionManager` <span data-ttu-id="83b59-130">corresponde a la `ICLRIoCompletionManager` interfaz implementada por CLR.</span><span class="sxs-lookup"><span data-stu-id="83b59-130">corresponds to the `ICLRIoCompletionManager` interface implemented by the CLR.</span></span> <span data-ttu-id="83b59-131">CLR llama a los métodos de `IHostIoCompletionManager` para enlazar los identificadores a los puertos que proporciona el host y el host llama a los métodos de `ICLRIoCompletionManager` para notificar la finalización de las solicitudes de E/S.</span><span class="sxs-lookup"><span data-stu-id="83b59-131">The CLR calls the methods of `IHostIoCompletionManager` to bind handles to the ports that the host provides, and the host calls the methods of `ICLRIoCompletionManager` to report the completion of I/O requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83b59-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="83b59-132">Requirements</span></span>  
 <span data-ttu-id="83b59-133">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83b59-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83b59-134">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="83b59-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="83b59-135">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="83b59-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="83b59-136">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="83b59-136">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="83b59-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="83b59-137">See also</span></span>

- [<span data-ttu-id="83b59-138">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="83b59-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
