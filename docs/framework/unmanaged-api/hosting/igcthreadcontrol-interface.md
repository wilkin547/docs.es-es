---
description: 'Más información acerca de: interfaz IGCThreadControl'
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
ms.openlocfilehash: 07c76848668b1525f4ff45ba5de746beefe0e004
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709290"
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="10ef8-103">IGCThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="10ef8-103">IGCThreadControl Interface</span></span>

<span data-ttu-id="10ef8-104">Proporciona métodos para participar en la programación de subprocesos que de otro modo se bloquearían para una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="10ef8-104">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="10ef8-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="10ef8-105">Methods</span></span>  
  
|<span data-ttu-id="10ef8-106">Método</span><span class="sxs-lookup"><span data-stu-id="10ef8-106">Method</span></span>|<span data-ttu-id="10ef8-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="10ef8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="10ef8-108">Método SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="10ef8-108">SuspensionEnding Method</span></span>](igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="10ef8-109">Notifica al host que el Runtime está reanudando los subprocesos después de una recolección de elementos no utilizados u otra suspensión.</span><span class="sxs-lookup"><span data-stu-id="10ef8-109">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="10ef8-110">Método SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="10ef8-110">SuspensionStarting Method</span></span>](igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="10ef8-111">Notifica al host que el motor en tiempo de ejecución está iniciando una suspensión de subprocesos para una recolección de elementos no utilizados u otra suspensión.</span><span class="sxs-lookup"><span data-stu-id="10ef8-111">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="10ef8-112">Método ThreadIsBlockingForSuspension</span><span class="sxs-lookup"><span data-stu-id="10ef8-112">ThreadIsBlockingForSuspension Method</span></span>](igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="10ef8-113">Notifica al host que el subproceso que realiza la llamada está a punto de bloquearse, quizás para una recolección de elementos no utilizados u otra suspensión.</span><span class="sxs-lookup"><span data-stu-id="10ef8-113">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="10ef8-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="10ef8-114">Requirements</span></span>  

 <span data-ttu-id="10ef8-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10ef8-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10ef8-116">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="10ef8-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="10ef8-117">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="10ef8-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="10ef8-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10ef8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10ef8-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="10ef8-119">See also</span></span>

- [<span data-ttu-id="10ef8-120">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="10ef8-120">Hosting Interfaces</span></span>](hosting-interfaces.md)
