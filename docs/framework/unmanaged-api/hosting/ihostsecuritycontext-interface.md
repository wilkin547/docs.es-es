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
ms.openlocfilehash: aafaa1d648396ddaa76193fa15cf7f74394777a9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724811"
---
# <a name="ihostsecuritycontext-interface"></a><span data-ttu-id="031f9-102">IHostSecurityContext (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="031f9-102">IHostSecurityContext Interface</span></span>

<span data-ttu-id="031f9-103">Permite que el Common Language Runtime (CLR) Mantenga la información de contexto de seguridad implementada por el host.</span><span class="sxs-lookup"><span data-stu-id="031f9-103">Allows the common language runtime (CLR) to maintain security context information implemented by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="031f9-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="031f9-104">Methods</span></span>  
  
|<span data-ttu-id="031f9-105">Método</span><span class="sxs-lookup"><span data-stu-id="031f9-105">Method</span></span>|<span data-ttu-id="031f9-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="031f9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="031f9-107">Método Capture</span><span class="sxs-lookup"><span data-stu-id="031f9-107">Capture Method</span></span>](ihostsecuritycontext-capture-method.md)|<span data-ttu-id="031f9-108">Obtiene un clon de la `IHostSecurityContext` instancia de devuelta desde una llamada a [IHostSecurityManager:: GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="031f9-108">Gets a clone of the `IHostSecurityContext` instance returned from a call to [IHostSecurityManager::GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="031f9-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="031f9-109">Remarks</span></span>  

 <span data-ttu-id="031f9-110">Un host puede controlar todo el acceso del código a los tokens de subproceso mediante el código de usuario y el CLR.</span><span class="sxs-lookup"><span data-stu-id="031f9-110">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="031f9-111">También puede asegurarse de que se pasa información de contexto de seguridad completa a través de operaciones asincrónicas o puntos de código con acceso restringido al código.</span><span class="sxs-lookup"><span data-stu-id="031f9-111">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="031f9-112">`IHostSecurityContext` encapsula esta información de contexto de seguridad, que es opaca para el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="031f9-112">`IHostSecurityContext` encapsulates this security context information, which is opaque to the runtime.</span></span> <span data-ttu-id="031f9-113">El motor en tiempo de ejecución captura esta información mediante `Capture` y la mueve entre la distribución de elementos de trabajo del grupo de subprocesos, la ejecución del finalizador y los constructores de clase y módulo.</span><span class="sxs-lookup"><span data-stu-id="031f9-113">The runtime captures this information using `Capture`, and moves it across thread pool worker item dispatch, finalizer execution, and module and class constructors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="031f9-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="031f9-114">Requirements</span></span>  

 <span data-ttu-id="031f9-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="031f9-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="031f9-116">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="031f9-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="031f9-117">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="031f9-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="031f9-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="031f9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="031f9-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="031f9-119">See also</span></span>

- [<span data-ttu-id="031f9-120">ICLRHostProtectionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="031f9-120">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="031f9-121">IHostSecurityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="031f9-121">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="031f9-122">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="031f9-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
