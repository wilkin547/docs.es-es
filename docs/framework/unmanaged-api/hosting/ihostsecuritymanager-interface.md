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
ms.openlocfilehash: 237fe23493460df77a79ba3aed9f0a809cd8aa23
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501474"
---
# <a name="ihostsecuritymanager-interface"></a><span data-ttu-id="7df67-102">IHostSecurityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7df67-102">IHostSecurityManager Interface</span></span>
<span data-ttu-id="7df67-103">Proporciona métodos que permiten el acceso y el control sobre el contexto de seguridad del subproceso que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="7df67-103">Provides methods that allow access to and control over the security context of the currently executing thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7df67-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="7df67-104">Methods</span></span>  
  
|<span data-ttu-id="7df67-105">Método</span><span class="sxs-lookup"><span data-stu-id="7df67-105">Method</span></span>|<span data-ttu-id="7df67-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="7df67-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7df67-107">Método GetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="7df67-107">GetSecurityContext Method</span></span>](ihostsecuritymanager-getsecuritycontext-method.md)|<span data-ttu-id="7df67-108">Obtiene el [IHostSecurityContext](ihostsecuritycontext-interface.md) solicitado del host.</span><span class="sxs-lookup"><span data-stu-id="7df67-108">Gets the requested [IHostSecurityContext](ihostsecuritycontext-interface.md) from the host.</span></span>|  
|[<span data-ttu-id="7df67-109">Método ImpersonateLoggedOnUser</span><span class="sxs-lookup"><span data-stu-id="7df67-109">ImpersonateLoggedOnUser Method</span></span>](ihostsecuritymanager-impersonateloggedonuser-method.md)|<span data-ttu-id="7df67-110">Solicita que el código se ejecute con las credenciales de la identidad del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="7df67-110">Requests that code be executed using the credentials of the current user identity.</span></span>|  
|[<span data-ttu-id="7df67-111">Método OpenThreadToken</span><span class="sxs-lookup"><span data-stu-id="7df67-111">OpenThreadToken Method</span></span>](ihostsecuritymanager-openthreadtoken-method.md)|<span data-ttu-id="7df67-112">Abre el token de acceso discrecional asociado al subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="7df67-112">Opens the discretionary access token associated with the current thread.</span></span>|  
|[<span data-ttu-id="7df67-113">Método RevertToSelf</span><span class="sxs-lookup"><span data-stu-id="7df67-113">RevertToSelf Method</span></span>](ihostsecuritymanager-reverttoself-method.md)|<span data-ttu-id="7df67-114">Finaliza la suplantación de la identidad del usuario actual y devuelve el token del subproceso original.</span><span class="sxs-lookup"><span data-stu-id="7df67-114">Terminates impersonation of the current user identity and returns the original thread token.</span></span>|  
|[<span data-ttu-id="7df67-115">Método SetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="7df67-115">SetSecurityContext Method</span></span>](ihostsecuritymanager-setsecuritycontext-method.md)|<span data-ttu-id="7df67-116">Establece el contexto de seguridad para el subproceso que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="7df67-116">Sets the security context for the currently executing thread.</span></span>|  
|[<span data-ttu-id="7df67-117">Método SetThreadToken</span><span class="sxs-lookup"><span data-stu-id="7df67-117">SetThreadToken Method</span></span>](ihostsecuritymanager-setthreadtoken-method.md)|<span data-ttu-id="7df67-118">Establece un identificador para el subproceso que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="7df67-118">Sets a handle for the currently executing thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7df67-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7df67-119">Remarks</span></span>  
 <span data-ttu-id="7df67-120">Un host puede controlar todo el acceso del código a los tokens de subproceso mediante el Common Language Runtime (CLR) y el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="7df67-120">A host can control all code access to thread tokens by both the common language runtime (CLR) and user code.</span></span> <span data-ttu-id="7df67-121">También puede asegurarse de que se pasa información de contexto de seguridad completa a través de operaciones asincrónicas o puntos de código con acceso restringido al código.</span><span class="sxs-lookup"><span data-stu-id="7df67-121">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="7df67-122">`IHostSecurityContext`encapsula esta información de contexto de seguridad, que es opaca para CLR.</span><span class="sxs-lookup"><span data-stu-id="7df67-122">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span>  
  
 <span data-ttu-id="7df67-123">CLR controla internamente el contexto del subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="7df67-123">The CLR handles managed thread context internally.</span></span> <span data-ttu-id="7df67-124">Consulta el específico del proceso `IHostSecurityManager` en las situaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="7df67-124">It queries the process-specific `IHostSecurityManager` in the following situations:</span></span>  
  
- <span data-ttu-id="7df67-125">En el subproceso finalizador, durante la ejecución del finalizador.</span><span class="sxs-lookup"><span data-stu-id="7df67-125">On the finalizer thread, during finalizer execution.</span></span>  
  
- <span data-ttu-id="7df67-126">Durante la ejecución del constructor de la clase y del módulo.</span><span class="sxs-lookup"><span data-stu-id="7df67-126">During class and module constructor execution.</span></span>  
  
- <span data-ttu-id="7df67-127">En los puntos asincrónicos del subproceso de trabajo, en llamadas al método [IHostThreadPoolManager:: QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7df67-127">At asynchronous points on the worker thread, in calls to the [IHostThreadPoolManager::QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md) method.</span></span>  
  
- <span data-ttu-id="7df67-128">En el servicio de puertos de finalización de e/s.</span><span class="sxs-lookup"><span data-stu-id="7df67-128">In servicing of I/O completion ports.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7df67-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7df67-129">Requirements</span></span>  
 <span data-ttu-id="7df67-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7df67-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7df67-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7df67-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7df67-132">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7df67-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7df67-133">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7df67-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7df67-134">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="7df67-134">See also</span></span>

- [<span data-ttu-id="7df67-135">IHostSecurityContext (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7df67-135">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="7df67-136">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="7df67-136">Hosting Interfaces</span></span>](hosting-interfaces.md)
