---
title: IHostSecurityContext (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityContext
helpviewer_keywords:
- IHostSecurityContext interface [.NET Framework hosting]
ms.assetid: 88e2eac0-8ccb-404f-abbc-287d55159842
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8ee464e47ad6e333b507c199e1857309f640a37b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsecuritycontext-interface"></a><span data-ttu-id="e6d23-102">IHostSecurityContext (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6d23-102">IHostSecurityContext Interface</span></span>
<span data-ttu-id="e6d23-103">Permite que common language runtime (CLR) para conservar la información de contexto de seguridad implementado por el host.</span><span class="sxs-lookup"><span data-stu-id="e6d23-103">Allows the common language runtime (CLR) to maintain security context information implemented by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e6d23-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e6d23-104">Methods</span></span>  
  
|<span data-ttu-id="e6d23-105">Método</span><span class="sxs-lookup"><span data-stu-id="e6d23-105">Method</span></span>|<span data-ttu-id="e6d23-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6d23-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e6d23-107">Capture (método)</span><span class="sxs-lookup"><span data-stu-id="e6d23-107">Capture Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-capture-method.md)|<span data-ttu-id="e6d23-108">Obtiene un clon de la `IHostSecurityContext` devuelve la instancia de una llamada a [IHostSecurityManager:: GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="e6d23-108">Gets a clone of the `IHostSecurityContext` instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6d23-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e6d23-109">Remarks</span></span>  
 <span data-ttu-id="e6d23-110">Un host puede controlar todo el acceso de código a los tokens de subprocesos por código de usuario y CLR.</span><span class="sxs-lookup"><span data-stu-id="e6d23-110">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="e6d23-111">También puede asegurar que la seguridad completa información de contexto se pasa a través de operaciones asincrónicas o puntos de código con acceso restringido al código.</span><span class="sxs-lookup"><span data-stu-id="e6d23-111">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="e6d23-112">`IHostSecurityContext`encapsula esta información de contexto de seguridad, que es opaca para el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e6d23-112">`IHostSecurityContext` encapsulates this security context information, which is opaque to the runtime.</span></span> <span data-ttu-id="e6d23-113">El tiempo de ejecución captura esta información mediante `Capture`, y se mueve a través del envío de elemento de trabajo de grupo de subprocesos, ejecución del finalizador y los constructores de módulos y de clases.</span><span class="sxs-lookup"><span data-stu-id="e6d23-113">The runtime captures this information using `Capture`, and moves it across thread pool worker item dispatch, finalizer execution, and module and class constructors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6d23-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e6d23-114">Requirements</span></span>  
 <span data-ttu-id="e6d23-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6d23-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6d23-116">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e6d23-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e6d23-117">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e6d23-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6d23-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6d23-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6d23-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6d23-119">See Also</span></span>  
 [<span data-ttu-id="e6d23-120">ICLRHostProtectionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6d23-120">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [<span data-ttu-id="e6d23-121">IHostSecurityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6d23-121">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="e6d23-122">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="e6d23-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
