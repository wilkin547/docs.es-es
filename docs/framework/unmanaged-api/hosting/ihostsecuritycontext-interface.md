---
title: IHostSecurityContext (Interfaz)
ms.date: 03/30/2017
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
ms.openlocfilehash: 993d16818b25dfefe1f53c7afd06bc9857d9eb24
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121522"
---
# <a name="ihostsecuritycontext-interface"></a><span data-ttu-id="f22f6-102">IHostSecurityContext (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f22f6-102">IHostSecurityContext Interface</span></span>
<span data-ttu-id="f22f6-103">Permite que el Common Language Runtime (CLR) Mantenga la información de contexto de seguridad implementada por el host.</span><span class="sxs-lookup"><span data-stu-id="f22f6-103">Allows the common language runtime (CLR) to maintain security context information implemented by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f22f6-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f22f6-104">Methods</span></span>  
  
|<span data-ttu-id="f22f6-105">Método</span><span class="sxs-lookup"><span data-stu-id="f22f6-105">Method</span></span>|<span data-ttu-id="f22f6-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f22f6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f22f6-107">Capture (método)</span><span class="sxs-lookup"><span data-stu-id="f22f6-107">Capture Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-capture-method.md)|<span data-ttu-id="f22f6-108">Obtiene un clon de la instancia de `IHostSecurityContext` devuelta desde una llamada a [IHostSecurityManager:: GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="f22f6-108">Gets a clone of the `IHostSecurityContext` instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f22f6-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f22f6-109">Remarks</span></span>  
 <span data-ttu-id="f22f6-110">Un host puede controlar todo el acceso del código a los tokens de subproceso mediante el código de usuario y el CLR.</span><span class="sxs-lookup"><span data-stu-id="f22f6-110">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="f22f6-111">También puede asegurarse de que se pasa información de contexto de seguridad completa a través de operaciones asincrónicas o puntos de código con acceso restringido al código.</span><span class="sxs-lookup"><span data-stu-id="f22f6-111">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="f22f6-112">`IHostSecurityContext` encapsula esta información de contexto de seguridad, que es opaca para el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f22f6-112">`IHostSecurityContext` encapsulates this security context information, which is opaque to the runtime.</span></span> <span data-ttu-id="f22f6-113">El motor en tiempo de ejecución captura esta información mediante `Capture`y la mueve entre el envío de elementos de trabajo del grupo de subprocesos, la ejecución del finalizador y los constructores de clase y módulo.</span><span class="sxs-lookup"><span data-stu-id="f22f6-113">The runtime captures this information using `Capture`, and moves it across thread pool worker item dispatch, finalizer execution, and module and class constructors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f22f6-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f22f6-114">Requirements</span></span>  
 <span data-ttu-id="f22f6-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f22f6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f22f6-116">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f22f6-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f22f6-117">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f22f6-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f22f6-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f22f6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f22f6-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="f22f6-119">See also</span></span>

- [<span data-ttu-id="f22f6-120">ICLRHostProtectionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f22f6-120">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="f22f6-121">IHostSecurityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f22f6-121">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="f22f6-122">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="f22f6-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
