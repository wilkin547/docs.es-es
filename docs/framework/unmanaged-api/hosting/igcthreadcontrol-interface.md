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
ms.openlocfilehash: 02facbb0ff1c0f8978d4f4f720ab370f70f07fe2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721691"
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="bb496-102">IGCThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bb496-102">IGCThreadControl Interface</span></span>

<span data-ttu-id="bb496-103">Proporciona métodos para participar en la programación de subprocesos que de otro modo se bloquearían para una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="bb496-103">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bb496-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="bb496-104">Methods</span></span>  
  
|<span data-ttu-id="bb496-105">Método</span><span class="sxs-lookup"><span data-stu-id="bb496-105">Method</span></span>|<span data-ttu-id="bb496-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb496-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bb496-107">Método SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="bb496-107">SuspensionEnding Method</span></span>](igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="bb496-108">Notifica al host que el Runtime está reanudando los subprocesos después de una recolección de elementos no utilizados u otra suspensión.</span><span class="sxs-lookup"><span data-stu-id="bb496-108">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="bb496-109">Método SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="bb496-109">SuspensionStarting Method</span></span>](igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="bb496-110">Notifica al host que el motor en tiempo de ejecución está iniciando una suspensión de subprocesos para una recolección de elementos no utilizados u otra suspensión.</span><span class="sxs-lookup"><span data-stu-id="bb496-110">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="bb496-111">Método ThreadIsBlockingForSuspension</span><span class="sxs-lookup"><span data-stu-id="bb496-111">ThreadIsBlockingForSuspension Method</span></span>](igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="bb496-112">Notifica al host que el subproceso que realiza la llamada está a punto de bloquearse, quizás para una recolección de elementos no utilizados u otra suspensión.</span><span class="sxs-lookup"><span data-stu-id="bb496-112">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bb496-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bb496-113">Requirements</span></span>  

 <span data-ttu-id="bb496-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb496-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb496-115">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="bb496-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bb496-116">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bb496-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bb496-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb496-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb496-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bb496-118">See also</span></span>

- [<span data-ttu-id="bb496-119">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="bb496-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
