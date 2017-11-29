---
title: IHostSecurityManager (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager
helpviewer_keywords: IHostSecurityManager interface [.NET Framework hosting]
ms.assetid: c3be2cbd-2d93-438b-9888-9a0251b63c03
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2b3d67328dbf68491d319e55e63a9c3540cd1ee4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritymanager-interface"></a><span data-ttu-id="74211-102">IHostSecurityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="74211-102">IHostSecurityManager Interface</span></span>
<span data-ttu-id="74211-103">Proporciona métodos que permiten el acceso y control sobre el contexto de seguridad del subproceso actualmente en ejecución.</span><span class="sxs-lookup"><span data-stu-id="74211-103">Provides methods that allow access to and control over the security context of the currently executing thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="74211-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="74211-104">Methods</span></span>  
  
|<span data-ttu-id="74211-105">Método</span><span class="sxs-lookup"><span data-stu-id="74211-105">Method</span></span>|<span data-ttu-id="74211-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="74211-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="74211-107">GetSecurityContext (método)</span><span class="sxs-lookup"><span data-stu-id="74211-107">GetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)|<span data-ttu-id="74211-108">Obtiene el solicitado [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) desde el host.</span><span class="sxs-lookup"><span data-stu-id="74211-108">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>|  
|[<span data-ttu-id="74211-109">ImpersonateLoggedOnUser (método)</span><span class="sxs-lookup"><span data-stu-id="74211-109">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)|<span data-ttu-id="74211-110">Las solicitudes que se ejecuta código con las credenciales de identidad del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="74211-110">Requests that code be executed using the credentials of the current user identity.</span></span>|  
|[<span data-ttu-id="74211-111">OpenThreadToken (método)</span><span class="sxs-lookup"><span data-stu-id="74211-111">OpenThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-openthreadtoken-method.md)|<span data-ttu-id="74211-112">Se abre el símbolo (token) de acceso discrecional asociado al subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="74211-112">Opens the discretionary access token associated with the current thread.</span></span>|  
|[<span data-ttu-id="74211-113">RevertToSelf (método)</span><span class="sxs-lookup"><span data-stu-id="74211-113">RevertToSelf Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)|<span data-ttu-id="74211-114">Termina la suplantación de identidad del usuario actual y devuelve el token de subproceso original.</span><span class="sxs-lookup"><span data-stu-id="74211-114">Terminates impersonation of the current user identity and returns the original thread token.</span></span>|  
|[<span data-ttu-id="74211-115">SetSecurityContext (método)</span><span class="sxs-lookup"><span data-stu-id="74211-115">SetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)|<span data-ttu-id="74211-116">Establece el contexto de seguridad para el subproceso actualmente en ejecución.</span><span class="sxs-lookup"><span data-stu-id="74211-116">Sets the security context for the currently executing thread.</span></span>|  
|[<span data-ttu-id="74211-117">SetThreadToken (método)</span><span class="sxs-lookup"><span data-stu-id="74211-117">SetThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setthreadtoken-method.md)|<span data-ttu-id="74211-118">Establece un identificador para el subproceso actualmente en ejecución.</span><span class="sxs-lookup"><span data-stu-id="74211-118">Sets a handle for the currently executing thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74211-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="74211-119">Remarks</span></span>  
 <span data-ttu-id="74211-120">Un host puede controlar todo el acceso de código a los tokens de subprocesos por el common language runtime (CLR) y el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="74211-120">A host can control all code access to thread tokens by both the common language runtime (CLR) and user code.</span></span> <span data-ttu-id="74211-121">También puede asegurar que la seguridad completa información de contexto se pasa a través de operaciones asincrónicas o puntos de código con acceso restringido al código.</span><span class="sxs-lookup"><span data-stu-id="74211-121">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="74211-122">`IHostSecurityContext`encapsula esta información de contexto de seguridad, que es opaca para CLR.</span><span class="sxs-lookup"><span data-stu-id="74211-122">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span>  
  
 <span data-ttu-id="74211-123">El CLR controla internamente el contexto de subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="74211-123">The CLR handles managed thread context internally.</span></span> <span data-ttu-id="74211-124">Consulta específico del proceso `IHostSecurityManager` en las situaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="74211-124">It queries the process-specific `IHostSecurityManager` in the following situations:</span></span>  
  
-   <span data-ttu-id="74211-125">En el subproceso finalizador, durante la ejecución del finalizador.</span><span class="sxs-lookup"><span data-stu-id="74211-125">On the finalizer thread, during finalizer execution.</span></span>  
  
-   <span data-ttu-id="74211-126">Durante la ejecución del constructor de clase y módulo.</span><span class="sxs-lookup"><span data-stu-id="74211-126">During class and module constructor execution.</span></span>  
  
-   <span data-ttu-id="74211-127">En los puntos asincrónicos en el subproceso de trabajo, en las llamadas a la [IHostThreadPoolManager:: QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="74211-127">At asynchronous points on the worker thread, in calls to the [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) method.</span></span>  
  
-   <span data-ttu-id="74211-128">En servicio de los puertos de terminación de E/S.</span><span class="sxs-lookup"><span data-stu-id="74211-128">In servicing of I/O completion ports.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74211-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74211-129">Requirements</span></span>  
 <span data-ttu-id="74211-130">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74211-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74211-131">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="74211-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="74211-132">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="74211-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="74211-133">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74211-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74211-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="74211-134">See Also</span></span>  
 [<span data-ttu-id="74211-135">IHostSecurityContext (interfaz)</span><span class="sxs-lookup"><span data-stu-id="74211-135">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="74211-136">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="74211-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
