---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a2c71f32dfd190e188bb28aad5d51c72160eb4bc
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64603223"
---
# <a name="ihostsecuritymanager-interface"></a><span data-ttu-id="4829b-102">IHostSecurityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4829b-102">IHostSecurityManager Interface</span></span>
<span data-ttu-id="4829b-103">Proporciona métodos que permiten el acceso y control sobre el contexto de seguridad del subproceso en ejecución actualmente.</span><span class="sxs-lookup"><span data-stu-id="4829b-103">Provides methods that allow access to and control over the security context of the currently executing thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4829b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="4829b-104">Methods</span></span>  
  
|<span data-ttu-id="4829b-105">Método</span><span class="sxs-lookup"><span data-stu-id="4829b-105">Method</span></span>|<span data-ttu-id="4829b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="4829b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4829b-107">GetSecurityContext (método)</span><span class="sxs-lookup"><span data-stu-id="4829b-107">GetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)|<span data-ttu-id="4829b-108">Obtiene el solicitado [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) desde el host.</span><span class="sxs-lookup"><span data-stu-id="4829b-108">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>|  
|[<span data-ttu-id="4829b-109">ImpersonateLoggedOnUser (método)</span><span class="sxs-lookup"><span data-stu-id="4829b-109">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)|<span data-ttu-id="4829b-110">Las solicitudes que se ejecuta código mediante las credenciales de la identidad del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="4829b-110">Requests that code be executed using the credentials of the current user identity.</span></span>|  
|[<span data-ttu-id="4829b-111">OpenThreadToken (método)</span><span class="sxs-lookup"><span data-stu-id="4829b-111">OpenThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-openthreadtoken-method.md)|<span data-ttu-id="4829b-112">Se abre el token de acceso discrecional asociado al subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="4829b-112">Opens the discretionary access token associated with the current thread.</span></span>|  
|[<span data-ttu-id="4829b-113">RevertToSelf (método)</span><span class="sxs-lookup"><span data-stu-id="4829b-113">RevertToSelf Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)|<span data-ttu-id="4829b-114">Termina la suplantación de identidad del usuario actual y devuelve el token de subproceso original.</span><span class="sxs-lookup"><span data-stu-id="4829b-114">Terminates impersonation of the current user identity and returns the original thread token.</span></span>|  
|[<span data-ttu-id="4829b-115">SetSecurityContext (método)</span><span class="sxs-lookup"><span data-stu-id="4829b-115">SetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)|<span data-ttu-id="4829b-116">Establece el contexto de seguridad para el subproceso actualmente en ejecución.</span><span class="sxs-lookup"><span data-stu-id="4829b-116">Sets the security context for the currently executing thread.</span></span>|  
|[<span data-ttu-id="4829b-117">SetThreadToken (método)</span><span class="sxs-lookup"><span data-stu-id="4829b-117">SetThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setthreadtoken-method.md)|<span data-ttu-id="4829b-118">Establece un identificador para el subproceso actualmente en ejecución.</span><span class="sxs-lookup"><span data-stu-id="4829b-118">Sets a handle for the currently executing thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4829b-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4829b-119">Remarks</span></span>  
 <span data-ttu-id="4829b-120">Un host puede controlar todo el acceso de código a los tokens de subprocesos por el common language runtime (CLR) y el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="4829b-120">A host can control all code access to thread tokens by both the common language runtime (CLR) and user code.</span></span> <span data-ttu-id="4829b-121">También puede garantizar que la seguridad completa información de contexto se pasa a través de operaciones asincrónicas o puntos de código con acceso restringido al código.</span><span class="sxs-lookup"><span data-stu-id="4829b-121">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="4829b-122">`IHostSecurityContext` encapsula esta información de contexto de seguridad, que es opaca para el CLR.</span><span class="sxs-lookup"><span data-stu-id="4829b-122">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span>  
  
 <span data-ttu-id="4829b-123">CLR controla internamente el contexto de subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="4829b-123">The CLR handles managed thread context internally.</span></span> <span data-ttu-id="4829b-124">Consulta específico del proceso `IHostSecurityManager` en las situaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="4829b-124">It queries the process-specific `IHostSecurityManager` in the following situations:</span></span>  
  
- <span data-ttu-id="4829b-125">En el subproceso de finalizador, durante la ejecución del finalizador.</span><span class="sxs-lookup"><span data-stu-id="4829b-125">On the finalizer thread, during finalizer execution.</span></span>  
  
- <span data-ttu-id="4829b-126">Durante la ejecución del constructor de clase y el módulo.</span><span class="sxs-lookup"><span data-stu-id="4829b-126">During class and module constructor execution.</span></span>  
  
- <span data-ttu-id="4829b-127">En los puntos asincrónicos en el subproceso de trabajo, en las llamadas a la [IHostThreadPoolManager](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="4829b-127">At asynchronous points on the worker thread, in calls to the [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) method.</span></span>  
  
- <span data-ttu-id="4829b-128">En el mantenimiento de los puertos de finalización de E/S.</span><span class="sxs-lookup"><span data-stu-id="4829b-128">In servicing of I/O completion ports.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4829b-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4829b-129">Requirements</span></span>  
 <span data-ttu-id="4829b-130">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4829b-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4829b-131">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4829b-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4829b-132">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4829b-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4829b-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4829b-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4829b-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="4829b-134">See also</span></span>

- [<span data-ttu-id="4829b-135">IHostSecurityContext (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4829b-135">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="4829b-136">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="4829b-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
