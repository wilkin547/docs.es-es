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
ms.openlocfilehash: 619a28d2382aa9cc3130a3130c07fa1e283119e4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437920"
---
# <a name="idebuggerthreadcontrol-interface"></a><span data-ttu-id="c49ee-102">IDebuggerThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c49ee-102">IDebuggerThreadControl Interface</span></span>
<span data-ttu-id="c49ee-103">Proporciona métodos para notificar al host el bloqueo y desbloqueo de subprocesos por los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="c49ee-103">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c49ee-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c49ee-104">Methods</span></span>  
  
|<span data-ttu-id="c49ee-105">Método</span><span class="sxs-lookup"><span data-stu-id="c49ee-105">Method</span></span>|<span data-ttu-id="c49ee-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c49ee-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c49ee-107">ThreadIsBlockingForDebugger (método)</span><span class="sxs-lookup"><span data-stu-id="c49ee-107">ThreadIsBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|<span data-ttu-id="c49ee-108">Notifica al host que hace referencia el subproceso que está enviando esta devolución de llamada al bloque dentro de los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="c49ee-108">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>|  
|[<span data-ttu-id="c49ee-109">ReleaseAllRuntimeThreads (método)</span><span class="sxs-lookup"><span data-stu-id="c49ee-109">ReleaseAllRuntimeThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-releaseallruntimethreads-method.md)|<span data-ttu-id="c49ee-110">Notifica al host que los servicios de depuración están a punto de liberar todos los subprocesos que están bloqueados.</span><span class="sxs-lookup"><span data-stu-id="c49ee-110">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>|  
|[<span data-ttu-id="c49ee-111">StartBlockingForDebugger (método)</span><span class="sxs-lookup"><span data-stu-id="c49ee-111">StartBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-startblockingfordebugger-method.md)|<span data-ttu-id="c49ee-112">Notifica al host que los servicios de depuración están a punto de iniciarse bloqueando todos los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="c49ee-112">Notifies the host that the debugging services are about to start blocking all threads.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c49ee-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c49ee-113">Requirements</span></span>  
 <span data-ttu-id="c49ee-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c49ee-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c49ee-115">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c49ee-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c49ee-116">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c49ee-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c49ee-117">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c49ee-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c49ee-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c49ee-118">See Also</span></span>  
 [<span data-ttu-id="c49ee-119">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="c49ee-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
