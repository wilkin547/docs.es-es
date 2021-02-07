---
description: 'Más información sobre: interfaz IHostSecurityManager'
title: IHostSecurityManager (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostSecurityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager
helpviewer_keywords:
- IHostSecurityManager interface [.NET Framework hosting]
ms.assetid: c3be2cbd-2d93-438b-9888-9a0251b63c03
topic_type:
- apiref
ms.openlocfilehash: 76ba26443fa2a4e65459dd073eb6d22031548112
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671548"
---
# <a name="ihostsecuritymanager-interface"></a><span data-ttu-id="4a17d-103">IHostSecurityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4a17d-103">IHostSecurityManager Interface</span></span>

<span data-ttu-id="4a17d-104">Proporciona métodos que permiten el acceso y el control sobre el contexto de seguridad del subproceso que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="4a17d-104">Provides methods that allow access to and control over the security context of the currently executing thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4a17d-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="4a17d-105">Methods</span></span>  
  
|<span data-ttu-id="4a17d-106">Método</span><span class="sxs-lookup"><span data-stu-id="4a17d-106">Method</span></span>|<span data-ttu-id="4a17d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4a17d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4a17d-108">Método GetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="4a17d-108">GetSecurityContext Method</span></span>](ihostsecuritymanager-getsecuritycontext-method.md)|<span data-ttu-id="4a17d-109">Obtiene el [IHostSecurityContext](ihostsecuritycontext-interface.md) solicitado del host.</span><span class="sxs-lookup"><span data-stu-id="4a17d-109">Gets the requested [IHostSecurityContext](ihostsecuritycontext-interface.md) from the host.</span></span>|  
|[<span data-ttu-id="4a17d-110">Método ImpersonateLoggedOnUser</span><span class="sxs-lookup"><span data-stu-id="4a17d-110">ImpersonateLoggedOnUser Method</span></span>](ihostsecuritymanager-impersonateloggedonuser-method.md)|<span data-ttu-id="4a17d-111">Solicita que el código se ejecute con las credenciales de la identidad del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="4a17d-111">Requests that code be executed using the credentials of the current user identity.</span></span>|  
|[<span data-ttu-id="4a17d-112">Método OpenThreadToken</span><span class="sxs-lookup"><span data-stu-id="4a17d-112">OpenThreadToken Method</span></span>](ihostsecuritymanager-openthreadtoken-method.md)|<span data-ttu-id="4a17d-113">Abre el token de acceso discrecional asociado al subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="4a17d-113">Opens the discretionary access token associated with the current thread.</span></span>|  
|[<span data-ttu-id="4a17d-114">Método RevertToSelf</span><span class="sxs-lookup"><span data-stu-id="4a17d-114">RevertToSelf Method</span></span>](ihostsecuritymanager-reverttoself-method.md)|<span data-ttu-id="4a17d-115">Finaliza la suplantación de la identidad del usuario actual y devuelve el token del subproceso original.</span><span class="sxs-lookup"><span data-stu-id="4a17d-115">Terminates impersonation of the current user identity and returns the original thread token.</span></span>|  
|[<span data-ttu-id="4a17d-116">Método SetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="4a17d-116">SetSecurityContext Method</span></span>](ihostsecuritymanager-setsecuritycontext-method.md)|<span data-ttu-id="4a17d-117">Establece el contexto de seguridad para el subproceso que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="4a17d-117">Sets the security context for the currently executing thread.</span></span>|  
|[<span data-ttu-id="4a17d-118">Método SetThreadToken</span><span class="sxs-lookup"><span data-stu-id="4a17d-118">SetThreadToken Method</span></span>](ihostsecuritymanager-setthreadtoken-method.md)|<span data-ttu-id="4a17d-119">Establece un identificador para el subproceso que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="4a17d-119">Sets a handle for the currently executing thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a17d-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4a17d-120">Remarks</span></span>  

 <span data-ttu-id="4a17d-121">Un host puede controlar todo el acceso del código a los tokens de subproceso mediante el Common Language Runtime (CLR) y el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="4a17d-121">A host can control all code access to thread tokens by both the common language runtime (CLR) and user code.</span></span> <span data-ttu-id="4a17d-122">También puede asegurarse de que se pasa información de contexto de seguridad completa a través de operaciones asincrónicas o puntos de código con acceso restringido al código.</span><span class="sxs-lookup"><span data-stu-id="4a17d-122">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="4a17d-123">`IHostSecurityContext` encapsula esta información de contexto de seguridad, que es opaca para CLR.</span><span class="sxs-lookup"><span data-stu-id="4a17d-123">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span>  
  
 <span data-ttu-id="4a17d-124">CLR controla internamente el contexto del subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="4a17d-124">The CLR handles managed thread context internally.</span></span> <span data-ttu-id="4a17d-125">Consulta el específico del proceso `IHostSecurityManager` en las situaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="4a17d-125">It queries the process-specific `IHostSecurityManager` in the following situations:</span></span>  
  
- <span data-ttu-id="4a17d-126">En el subproceso finalizador, durante la ejecución del finalizador.</span><span class="sxs-lookup"><span data-stu-id="4a17d-126">On the finalizer thread, during finalizer execution.</span></span>  
  
- <span data-ttu-id="4a17d-127">Durante la ejecución del constructor de la clase y del módulo.</span><span class="sxs-lookup"><span data-stu-id="4a17d-127">During class and module constructor execution.</span></span>  
  
- <span data-ttu-id="4a17d-128">En los puntos asincrónicos del subproceso de trabajo, en llamadas al método [IHostThreadPoolManager:: QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4a17d-128">At asynchronous points on the worker thread, in calls to the [IHostThreadPoolManager::QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md) method.</span></span>  
  
- <span data-ttu-id="4a17d-129">En el servicio de puertos de finalización de e/s.</span><span class="sxs-lookup"><span data-stu-id="4a17d-129">In servicing of I/O completion ports.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a17d-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4a17d-130">Requirements</span></span>  

 <span data-ttu-id="4a17d-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a17d-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a17d-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4a17d-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4a17d-133">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4a17d-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a17d-134">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a17d-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a17d-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a17d-135">See also</span></span>

- [<span data-ttu-id="4a17d-136">IHostSecurityContext (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4a17d-136">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="4a17d-137">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="4a17d-137">Hosting Interfaces</span></span>](hosting-interfaces.md)
