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
ms.openlocfilehash: f6e25bfe11880730f6f447ccc0406d716d185624
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501500"
---
# <a name="ihostsecuritycontext-interface"></a><span data-ttu-id="f23e3-102">IHostSecurityContext (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f23e3-102">IHostSecurityContext Interface</span></span>
<span data-ttu-id="f23e3-103">Permite que el Common Language Runtime (CLR) Mantenga la información de contexto de seguridad implementada por el host.</span><span class="sxs-lookup"><span data-stu-id="f23e3-103">Allows the common language runtime (CLR) to maintain security context information implemented by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f23e3-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f23e3-104">Methods</span></span>  
  
|<span data-ttu-id="f23e3-105">Método</span><span class="sxs-lookup"><span data-stu-id="f23e3-105">Method</span></span>|<span data-ttu-id="f23e3-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f23e3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f23e3-107">Método Capture</span><span class="sxs-lookup"><span data-stu-id="f23e3-107">Capture Method</span></span>](ihostsecuritycontext-capture-method.md)|<span data-ttu-id="f23e3-108">Obtiene un clon de la `IHostSecurityContext` instancia de devuelta desde una llamada a [IHostSecurityManager:: GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="f23e3-108">Gets a clone of the `IHostSecurityContext` instance returned from a call to [IHostSecurityManager::GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f23e3-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f23e3-109">Remarks</span></span>  
 <span data-ttu-id="f23e3-110">Un host puede controlar todo el acceso del código a los tokens de subproceso mediante el código de usuario y el CLR.</span><span class="sxs-lookup"><span data-stu-id="f23e3-110">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="f23e3-111">También puede asegurarse de que se pasa información de contexto de seguridad completa a través de operaciones asincrónicas o puntos de código con acceso restringido al código.</span><span class="sxs-lookup"><span data-stu-id="f23e3-111">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="f23e3-112">`IHostSecurityContext`encapsula esta información de contexto de seguridad, que es opaca para el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f23e3-112">`IHostSecurityContext` encapsulates this security context information, which is opaque to the runtime.</span></span> <span data-ttu-id="f23e3-113">El motor en tiempo de ejecución captura esta información mediante `Capture` y la mueve entre la distribución de elementos de trabajo del grupo de subprocesos, la ejecución del finalizador y los constructores de clase y módulo.</span><span class="sxs-lookup"><span data-stu-id="f23e3-113">The runtime captures this information using `Capture`, and moves it across thread pool worker item dispatch, finalizer execution, and module and class constructors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f23e3-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f23e3-114">Requirements</span></span>  
 <span data-ttu-id="f23e3-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f23e3-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f23e3-116">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f23e3-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f23e3-117">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f23e3-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f23e3-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f23e3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f23e3-119">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="f23e3-119">See also</span></span>

- [<span data-ttu-id="f23e3-120">ICLRHostProtectionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f23e3-120">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="f23e3-121">IHostSecurityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f23e3-121">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="f23e3-122">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="f23e3-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
