---
title: IDebuggerThreadControl (Interfaz)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a551d3cc6ab3dd3887f232018f8201de4036d1b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096841"
---
# <a name="idebuggerthreadcontrol-interface"></a><span data-ttu-id="cbfd6-102">IDebuggerThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cbfd6-102">IDebuggerThreadControl Interface</span></span>
<span data-ttu-id="cbfd6-103">Proporciona métodos para notificar al host el bloqueo y desbloqueo de subprocesos por los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="cbfd6-103">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cbfd6-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="cbfd6-104">Methods</span></span>  
  
|<span data-ttu-id="cbfd6-105">Método</span><span class="sxs-lookup"><span data-stu-id="cbfd6-105">Method</span></span>|<span data-ttu-id="cbfd6-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="cbfd6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cbfd6-107">Método ThreadIsBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="cbfd6-107">ThreadIsBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|<span data-ttu-id="cbfd6-108">Notifica al host que el subproceso que está enviando esta devolución de llamada se acerca al bloque dentro de los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="cbfd6-108">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>|  
|[<span data-ttu-id="cbfd6-109">Método ReleaseAllRuntimeThreads</span><span class="sxs-lookup"><span data-stu-id="cbfd6-109">ReleaseAllRuntimeThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-releaseallruntimethreads-method.md)|<span data-ttu-id="cbfd6-110">Notifica al host que los servicios de depuración están a punto de liberar todos los subprocesos que están bloqueados.</span><span class="sxs-lookup"><span data-stu-id="cbfd6-110">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>|  
|[<span data-ttu-id="cbfd6-111">Método StartBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="cbfd6-111">StartBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-startblockingfordebugger-method.md)|<span data-ttu-id="cbfd6-112">Notifica al host que los servicios de depuración están a punto de comenzar a bloquear todos los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="cbfd6-112">Notifies the host that the debugging services are about to start blocking all threads.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cbfd6-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cbfd6-113">Requirements</span></span>  
 <span data-ttu-id="cbfd6-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbfd6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbfd6-115">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cbfd6-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cbfd6-116">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cbfd6-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="cbfd6-117">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="cbfd6-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cbfd6-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="cbfd6-118">See also</span></span>

- [<span data-ttu-id="cbfd6-119">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="cbfd6-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
