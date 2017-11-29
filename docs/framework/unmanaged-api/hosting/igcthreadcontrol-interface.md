---
title: IGCThreadControl (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCThreadControl
api_location: mscoree.dll
api_type: COM
f1_keywords: IGCThreadControl
helpviewer_keywords: IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 3ff04d75-85ac-4df9-886d-dbaa037c0552
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 66afef7dec0637e98249838ae06ae6f1161df3f3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="ef86a-102">IGCThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef86a-102">IGCThreadControl Interface</span></span>
<span data-ttu-id="ef86a-103">Proporciona métodos para participar en la programación de subprocesos que de lo contrario estarían bloqueados para una colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ef86a-103">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ef86a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ef86a-104">Methods</span></span>  
  
|<span data-ttu-id="ef86a-105">Método</span><span class="sxs-lookup"><span data-stu-id="ef86a-105">Method</span></span>|<span data-ttu-id="ef86a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ef86a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ef86a-107">SuspensionEnding (método)</span><span class="sxs-lookup"><span data-stu-id="ef86a-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="ef86a-108">Notifica al host que el runtime está reanudando los subprocesos después de una colección de elementos no utilizados u otra suspensión.</span><span class="sxs-lookup"><span data-stu-id="ef86a-108">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="ef86a-109">SuspensionStarting (método)</span><span class="sxs-lookup"><span data-stu-id="ef86a-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="ef86a-110">Notifica al host que el tiempo de ejecución va a comenzar la suspensión de un subproceso para una colección de elementos no utilizados u otra suspensión.</span><span class="sxs-lookup"><span data-stu-id="ef86a-110">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="ef86a-111">ThreadIsBlockingForSuspension (método)</span><span class="sxs-lookup"><span data-stu-id="ef86a-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="ef86a-112">Notifica al host que el subproceso que realiza la llamada está a punto de bloquearse, quizás para una colección de elementos no utilizados u otra suspensión.</span><span class="sxs-lookup"><span data-stu-id="ef86a-112">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ef86a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ef86a-113">Requirements</span></span>  
 <span data-ttu-id="ef86a-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef86a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef86a-115">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ef86a-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ef86a-116">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ef86a-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ef86a-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef86a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef86a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef86a-118">See Also</span></span>  
 [<span data-ttu-id="ef86a-119">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="ef86a-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
