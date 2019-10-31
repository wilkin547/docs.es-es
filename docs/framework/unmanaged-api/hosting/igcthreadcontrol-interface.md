---
title: IGCThreadControl (Interfaz)
ms.date: 03/30/2017
api_name:
- IGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCThreadControl
helpviewer_keywords:
- IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 3ff04d75-85ac-4df9-886d-dbaa037c0552
topic_type:
- apiref
ms.openlocfilehash: 3aba31f60af25144b9f01aa9ca8cc633d4c1a438
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134798"
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="db0a9-102">IGCThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="db0a9-102">IGCThreadControl Interface</span></span>
<span data-ttu-id="db0a9-103">Proporciona métodos para participar en la programación de subprocesos que de otro modo se bloquearían para una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="db0a9-103">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="db0a9-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="db0a9-104">Methods</span></span>  
  
|<span data-ttu-id="db0a9-105">Método</span><span class="sxs-lookup"><span data-stu-id="db0a9-105">Method</span></span>|<span data-ttu-id="db0a9-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="db0a9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="db0a9-107">SuspensionEnding (método)</span><span class="sxs-lookup"><span data-stu-id="db0a9-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="db0a9-108">Notifica al host que el Runtime está reanudando los subprocesos después de una recolección de elementos no utilizados u otra suspensión.</span><span class="sxs-lookup"><span data-stu-id="db0a9-108">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="db0a9-109">SuspensionStarting (método)</span><span class="sxs-lookup"><span data-stu-id="db0a9-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="db0a9-110">Notifica al host que el motor en tiempo de ejecución está iniciando una suspensión de subprocesos para una recolección de elementos no utilizados u otra suspensión.</span><span class="sxs-lookup"><span data-stu-id="db0a9-110">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="db0a9-111">ThreadIsBlockingForSuspension (método)</span><span class="sxs-lookup"><span data-stu-id="db0a9-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="db0a9-112">Notifica al host que el subproceso que realiza la llamada está a punto de bloquearse, quizás para una recolección de elementos no utilizados u otra suspensión.</span><span class="sxs-lookup"><span data-stu-id="db0a9-112">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="db0a9-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="db0a9-113">Requirements</span></span>  
 <span data-ttu-id="db0a9-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db0a9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db0a9-115">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="db0a9-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="db0a9-116">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="db0a9-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="db0a9-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db0a9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db0a9-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="db0a9-118">See also</span></span>

- [<span data-ttu-id="db0a9-119">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="db0a9-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
