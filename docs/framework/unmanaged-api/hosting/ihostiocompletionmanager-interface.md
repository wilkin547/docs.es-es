---
description: 'Más información sobre: interfaz IHostIoCompletionManager'
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
ms.openlocfilehash: 30cb0ecbfd9645bc0374e3570751832d6fa8eced
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708325"
---
# <a name="ihostiocompletionmanager-interface"></a><span data-ttu-id="d2bc5-103">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d2bc5-103">IHostIoCompletionManager Interface</span></span>

<span data-ttu-id="d2bc5-104">Proporciona métodos que permiten que el Common Language Runtime (CLR) interactúe con los puertos de finalización de e/s proporcionados por el host.</span><span class="sxs-lookup"><span data-stu-id="d2bc5-104">Provides methods that allow the common language runtime (CLR) to interact with I/O completion ports provided by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d2bc5-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="d2bc5-105">Methods</span></span>  
  
|<span data-ttu-id="d2bc5-106">Método</span><span class="sxs-lookup"><span data-stu-id="d2bc5-106">Method</span></span>|<span data-ttu-id="d2bc5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d2bc5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d2bc5-108">Método Bind</span><span class="sxs-lookup"><span data-stu-id="d2bc5-108">Bind Method</span></span>](ihostiocompletionmanager-bind-method.md)|<span data-ttu-id="d2bc5-109">Enlaza un identificador a un puerto de finalización de e/s.</span><span class="sxs-lookup"><span data-stu-id="d2bc5-109">Binds a handle to an I/O completion port.</span></span>|  
|[<span data-ttu-id="d2bc5-110">Método CloseIoCompletionPort</span><span class="sxs-lookup"><span data-stu-id="d2bc5-110">CloseIoCompletionPort Method</span></span>](ihostiocompletionmanager-closeiocompletionport-method.md)|<span data-ttu-id="d2bc5-111">Cierra un puerto que se creó mediante una llamada anterior a `CreateIoCompletionPort` .</span><span class="sxs-lookup"><span data-stu-id="d2bc5-111">Closes a port that was created through an earlier call to `CreateIoCompletionPort`.</span></span>|  
|[<span data-ttu-id="d2bc5-112">Método CreateIoCompletionPort</span><span class="sxs-lookup"><span data-stu-id="d2bc5-112">CreateIoCompletionPort Method</span></span>](ihostiocompletionmanager-createiocompletionport-method.md)|<span data-ttu-id="d2bc5-113">Solicita que el host cree un nuevo puerto de finalización de e/s.</span><span class="sxs-lookup"><span data-stu-id="d2bc5-113">Requests that the host create a new I/O completion port.</span></span>|  
|[<span data-ttu-id="d2bc5-114">Método GetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="d2bc5-114">GetAvailableThreads Method</span></span>](ihostiocompletionmanager-getavailablethreads-method.md)|<span data-ttu-id="d2bc5-115">Obtiene el número de subprocesos de finalización de e/s que no están procesando actualmente solicitudes.</span><span class="sxs-lookup"><span data-stu-id="d2bc5-115">Gets the number of I/O completion threads that are not currently processing requests.</span></span>|  
|[<span data-ttu-id="d2bc5-116">Método GetHostOverlappedSize</span><span class="sxs-lookup"><span data-stu-id="d2bc5-116">GetHostOverlappedSize Method</span></span>](ihostiocompletionmanager-gethostoverlappedsize-method.md)|<span data-ttu-id="d2bc5-117">Obtiene el tamaño de los datos personalizados que el host pretende anexar a las solicitudes de e/s.</span><span class="sxs-lookup"><span data-stu-id="d2bc5-117">Gets the size of any custom data the host intends to append to I/O requests.</span></span>|  
|[<span data-ttu-id="d2bc5-118">Método GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="d2bc5-118">GetMaxThreads Method</span></span>](ihostiocompletionmanager-getmaxthreads-method.md)|<span data-ttu-id="d2bc5-119">Obtiene el número máximo de subprocesos que el host puede asignar a las solicitudes de e/s de servicio.</span><span class="sxs-lookup"><span data-stu-id="d2bc5-119">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>|  
|[<span data-ttu-id="d2bc5-120">Método GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="d2bc5-120">GetMinThreads Method</span></span>](ihostiocompletionmanager-getminthreads-method.md)|<span data-ttu-id="d2bc5-121">Obtiene el número mínimo de subprocesos que proporciona el host para las solicitudes de e/s de servicio.</span><span class="sxs-lookup"><span data-stu-id="d2bc5-121">Gets the minimum number of threads that the host provides to service I/O requests.</span></span>|  
|[<span data-ttu-id="d2bc5-122">Método InitializeHostOverlapped</span><span class="sxs-lookup"><span data-stu-id="d2bc5-122">InitializeHostOverlapped Method</span></span>](ihostiocompletionmanager-initializehostoverlapped-method.md)|<span data-ttu-id="d2bc5-123">Proporciona al host la oportunidad de inicializar los datos personalizados sobre una solicitud de e/s.</span><span class="sxs-lookup"><span data-stu-id="d2bc5-123">Provides the host with an opportunity to initialize any custom data about an I/O request.</span></span>|  
|[<span data-ttu-id="d2bc5-124">Método SetCLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="d2bc5-124">SetCLRIoCompletionManager Method</span></span>](ihostiocompletionmanager-setclriocompletionmanager-method.md)|<span data-ttu-id="d2bc5-125">Proporciona al host un puntero de interfaz a una instancia de [ICLRIoCompletionManager](iclriocompletionmanager-interface.md) implementada por CLR.</span><span class="sxs-lookup"><span data-stu-id="d2bc5-125">Provides the host with an interface pointer to an [ICLRIoCompletionManager](iclriocompletionmanager-interface.md) instance implemented by the CLR.</span></span>|  
|[<span data-ttu-id="d2bc5-126">Método SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="d2bc5-126">SetMaxThreads Method</span></span>](ihostiocompletionmanager-setmaxthreads-method.md)|<span data-ttu-id="d2bc5-127">Establece el número máximo de subprocesos que el host asigna a las solicitudes de e/s de servicio.</span><span class="sxs-lookup"><span data-stu-id="d2bc5-127">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>|  
|[<span data-ttu-id="d2bc5-128">Método SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="d2bc5-128">SetMinThreads Method</span></span>](ihostiocompletionmanager-setminthreads-method.md)|<span data-ttu-id="d2bc5-129">Establece el número mínimo de subprocesos que el host debe asignar a la finalización de e/s.</span><span class="sxs-lookup"><span data-stu-id="d2bc5-129">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2bc5-130">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d2bc5-130">Remarks</span></span>  

 <span data-ttu-id="d2bc5-131">`IHostIoCompletionManager` corresponde a la `ICLRIoCompletionManager` interfaz implementada por CLR.</span><span class="sxs-lookup"><span data-stu-id="d2bc5-131">`IHostIoCompletionManager` corresponds to the `ICLRIoCompletionManager` interface implemented by the CLR.</span></span> <span data-ttu-id="d2bc5-132">CLR llama a los métodos de `IHostIoCompletionManager` para enlazar los identificadores a los puertos proporcionados por el host y el host llama a los métodos de `ICLRIoCompletionManager` para informar de la finalización de las solicitudes de e/s.</span><span class="sxs-lookup"><span data-stu-id="d2bc5-132">The CLR calls the methods of `IHostIoCompletionManager` to bind handles to the ports that the host provides, and the host calls the methods of `ICLRIoCompletionManager` to report the completion of I/O requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2bc5-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d2bc5-133">Requirements</span></span>  

 <span data-ttu-id="d2bc5-134">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2bc5-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2bc5-135">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d2bc5-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d2bc5-136">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d2bc5-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d2bc5-137">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2bc5-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2bc5-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2bc5-138">See also</span></span>

- [<span data-ttu-id="d2bc5-139">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="d2bc5-139">Hosting Interfaces</span></span>](hosting-interfaces.md)
