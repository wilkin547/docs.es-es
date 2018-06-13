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
ms.openlocfilehash: 9296aedf24979624c3d7357a4d51be835716a16f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438033"
---
# <a name="igcthreadcontrol-interface"></a><span data-ttu-id="23507-102">IGCThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="23507-102">IGCThreadControl Interface</span></span>
<span data-ttu-id="23507-103">Proporciona métodos para participar en la programación de subprocesos que de lo contrario estarían bloqueados para una colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="23507-103">Provides methods for participating in the scheduling of threads that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="23507-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="23507-104">Methods</span></span>  
  
|<span data-ttu-id="23507-105">Método</span><span class="sxs-lookup"><span data-stu-id="23507-105">Method</span></span>|<span data-ttu-id="23507-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="23507-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="23507-107">SuspensionEnding (método)</span><span class="sxs-lookup"><span data-stu-id="23507-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionending-method.md)|<span data-ttu-id="23507-108">Notifica al host que el runtime está reanudando los subprocesos después de una colección de elementos no utilizados u otra suspensión.</span><span class="sxs-lookup"><span data-stu-id="23507-108">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="23507-109">SuspensionStarting (método)</span><span class="sxs-lookup"><span data-stu-id="23507-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-suspensionstarting-method.md)|<span data-ttu-id="23507-110">Notifica al host que el tiempo de ejecución va a comenzar la suspensión de un subproceso para una colección de elementos no utilizados u otra suspensión.</span><span class="sxs-lookup"><span data-stu-id="23507-110">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>|  
|[<span data-ttu-id="23507-111">ThreadIsBlockingForSuspension (método)</span><span class="sxs-lookup"><span data-stu-id="23507-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md)|<span data-ttu-id="23507-112">Notifica al host que el subproceso que realiza la llamada está a punto de bloquearse, quizás para una colección de elementos no utilizados u otra suspensión.</span><span class="sxs-lookup"><span data-stu-id="23507-112">Notifies the host that the thread making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="23507-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="23507-113">Requirements</span></span>  
 <span data-ttu-id="23507-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23507-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23507-115">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="23507-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="23507-116">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="23507-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="23507-117">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23507-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23507-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="23507-118">See Also</span></span>  
 [<span data-ttu-id="23507-119">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="23507-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
