---
title: IHostSecurityContext (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityContext
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityContext
helpviewer_keywords: IHostSecurityContext interface [.NET Framework hosting]
ms.assetid: 88e2eac0-8ccb-404f-abbc-287d55159842
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1d3c616ced761b696f50e9207e6fad312f06c31c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritycontext-interface"></a><span data-ttu-id="ba387-102">IHostSecurityContext (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba387-102">IHostSecurityContext Interface</span></span>
<span data-ttu-id="ba387-103">Permite que common language runtime (CLR) para conservar la información de contexto de seguridad implementado por el host.</span><span class="sxs-lookup"><span data-stu-id="ba387-103">Allows the common language runtime (CLR) to maintain security context information implemented by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ba387-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ba387-104">Methods</span></span>  
  
|<span data-ttu-id="ba387-105">Método</span><span class="sxs-lookup"><span data-stu-id="ba387-105">Method</span></span>|<span data-ttu-id="ba387-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba387-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ba387-107">Capture (método)</span><span class="sxs-lookup"><span data-stu-id="ba387-107">Capture Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-capture-method.md)|<span data-ttu-id="ba387-108">Obtiene un clon de la `IHostSecurityContext` devuelve la instancia de una llamada a [IHostSecurityManager:: GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="ba387-108">Gets a clone of the `IHostSecurityContext` instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba387-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ba387-109">Remarks</span></span>  
 <span data-ttu-id="ba387-110">Un host puede controlar todo el acceso de código a los tokens de subprocesos por código de usuario y CLR.</span><span class="sxs-lookup"><span data-stu-id="ba387-110">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="ba387-111">También puede asegurar que la seguridad completa información de contexto se pasa a través de operaciones asincrónicas o puntos de código con acceso restringido al código.</span><span class="sxs-lookup"><span data-stu-id="ba387-111">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="ba387-112">`IHostSecurityContext`encapsula esta información de contexto de seguridad, que es opaca para el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ba387-112">`IHostSecurityContext` encapsulates this security context information, which is opaque to the runtime.</span></span> <span data-ttu-id="ba387-113">El tiempo de ejecución captura esta información mediante `Capture`, y se mueve a través del envío de elemento de trabajo de grupo de subprocesos, ejecución del finalizador y los constructores de módulos y de clases.</span><span class="sxs-lookup"><span data-stu-id="ba387-113">The runtime captures this information using `Capture`, and moves it across thread pool worker item dispatch, finalizer execution, and module and class constructors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba387-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ba387-114">Requirements</span></span>  
 <span data-ttu-id="ba387-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba387-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba387-116">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ba387-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ba387-117">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ba387-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ba387-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba387-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba387-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba387-119">See Also</span></span>  
 [<span data-ttu-id="ba387-120">ICLRHostProtectionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba387-120">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [<span data-ttu-id="ba387-121">IHostSecurityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba387-121">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="ba387-122">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="ba387-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
