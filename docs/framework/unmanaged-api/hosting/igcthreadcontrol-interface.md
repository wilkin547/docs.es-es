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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c00f401bedc1a2810c4e9b3046a45e53a79f1ea
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992776"
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="6ac5f-102">IGCThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6ac5f-102">IGCThreadControl Interface</span></span>
<span data-ttu-id="6ac5f-103">Proporciona métodos para participar en la programación de subprocesos que de lo contrario, se bloquearía para una colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="6ac5f-103">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6ac5f-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="6ac5f-104">Methods</span></span>  
  
|<span data-ttu-id="6ac5f-105">Método</span><span class="sxs-lookup"><span data-stu-id="6ac5f-105">Method</span></span>|<span data-ttu-id="6ac5f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="6ac5f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6ac5f-107">SuspensionEnding (método)</span><span class="sxs-lookup"><span data-stu-id="6ac5f-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="6ac5f-108">Notifica al host que el tiempo de ejecución es reanudar subprocesos después de una recolección de elementos u otra suspensión.</span><span class="sxs-lookup"><span data-stu-id="6ac5f-108">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="6ac5f-109">SuspensionStarting (método)</span><span class="sxs-lookup"><span data-stu-id="6ac5f-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="6ac5f-110">Notifica al host que el tiempo de ejecución está iniciando la suspensión de un subproceso para una colección de elementos no utilizados u otra suspensión.</span><span class="sxs-lookup"><span data-stu-id="6ac5f-110">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="6ac5f-111">ThreadIsBlockingForSuspension (método)</span><span class="sxs-lookup"><span data-stu-id="6ac5f-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="6ac5f-112">Notifica al host que el subproceso que realiza la llamada está a punto de bloquearse, quizás para una colección de elementos no utilizados u otra suspensión.</span><span class="sxs-lookup"><span data-stu-id="6ac5f-112">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6ac5f-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6ac5f-113">Requirements</span></span>  
 <span data-ttu-id="6ac5f-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ac5f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ac5f-115">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6ac5f-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6ac5f-116">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6ac5f-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6ac5f-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ac5f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ac5f-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ac5f-118">See also</span></span>

- [<span data-ttu-id="6ac5f-119">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="6ac5f-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
