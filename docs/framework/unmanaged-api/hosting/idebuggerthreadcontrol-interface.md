---
title: IDebuggerThreadControl (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IDebuggerThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IDebuggerThreadControl
helpviewer_keywords:
- IDebuggerThreadControl interface [.NET Framework hosting]
ms.assetid: 0a270c42-a7d1-45f1-a64d-fa3e84d14532
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 297a66f9466b00dec4d32f7d8a6e2bd13b6e5655
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="idebuggerthreadcontrol-interface"></a><span data-ttu-id="a8624-102">IDebuggerThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8624-102">IDebuggerThreadControl Interface</span></span>
<span data-ttu-id="a8624-103">Proporciona métodos para notificar al host el bloqueo y desbloqueo de subprocesos por los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="a8624-103">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a8624-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a8624-104">Methods</span></span>  
  
|<span data-ttu-id="a8624-105">Método</span><span class="sxs-lookup"><span data-stu-id="a8624-105">Method</span></span>|<span data-ttu-id="a8624-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8624-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a8624-107">ThreadIsBlockingForDebugger (método)</span><span class="sxs-lookup"><span data-stu-id="a8624-107">ThreadIsBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|<span data-ttu-id="a8624-108">Notifica al host que hace referencia el subproceso que está enviando esta devolución de llamada al bloque dentro de los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="a8624-108">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>|  
|[<span data-ttu-id="a8624-109">ReleaseAllRuntimeThreads (método)</span><span class="sxs-lookup"><span data-stu-id="a8624-109">ReleaseAllRuntimeThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-releaseallruntimethreads-method.md)|<span data-ttu-id="a8624-110">Notifica al host que los servicios de depuración están a punto de liberar todos los subprocesos que están bloqueados.</span><span class="sxs-lookup"><span data-stu-id="a8624-110">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>|  
|[<span data-ttu-id="a8624-111">StartBlockingForDebugger (método)</span><span class="sxs-lookup"><span data-stu-id="a8624-111">StartBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-startblockingfordebugger-method.md)|<span data-ttu-id="a8624-112">Notifica al host que los servicios de depuración están a punto de iniciarse bloqueando todos los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="a8624-112">Notifies the host that the debugging services are about to start blocking all threads.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a8624-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a8624-113">Requirements</span></span>  
 <span data-ttu-id="a8624-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8624-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8624-115">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a8624-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a8624-116">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a8624-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a8624-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8624-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8624-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8624-118">See Also</span></span>  
 [<span data-ttu-id="a8624-119">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="a8624-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
