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
ms.openlocfilehash: a65f9f0f29a43cf3d26b4b2bc5f6f594f0557009
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133160"
---
# <a name="idebuggerthreadcontrol-interface"></a><span data-ttu-id="9ae2b-102">IDebuggerThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9ae2b-102">IDebuggerThreadControl Interface</span></span>
<span data-ttu-id="9ae2b-103">Proporciona métodos para notificar al host el bloqueo y desbloqueo de subprocesos por parte de los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="9ae2b-103">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9ae2b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="9ae2b-104">Methods</span></span>  
  
|<span data-ttu-id="9ae2b-105">Método</span><span class="sxs-lookup"><span data-stu-id="9ae2b-105">Method</span></span>|<span data-ttu-id="9ae2b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ae2b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9ae2b-107">ThreadIsBlockingForDebugger (método)</span><span class="sxs-lookup"><span data-stu-id="9ae2b-107">ThreadIsBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|<span data-ttu-id="9ae2b-108">Notifica al host que el subproceso que está enviando esta devolución de llamada está a punto de bloquearse dentro de los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="9ae2b-108">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>|  
|[<span data-ttu-id="9ae2b-109">ReleaseAllRuntimeThreads (método)</span><span class="sxs-lookup"><span data-stu-id="9ae2b-109">ReleaseAllRuntimeThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-releaseallruntimethreads-method.md)|<span data-ttu-id="9ae2b-110">Notifica al host que los servicios de depuración están a punto de liberar todos los subprocesos que están bloqueados.</span><span class="sxs-lookup"><span data-stu-id="9ae2b-110">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>|  
|[<span data-ttu-id="9ae2b-111">StartBlockingForDebugger (método)</span><span class="sxs-lookup"><span data-stu-id="9ae2b-111">StartBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-startblockingfordebugger-method.md)|<span data-ttu-id="9ae2b-112">Notifica al host que los servicios de depuración están a punto de iniciar el bloqueo de todos los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="9ae2b-112">Notifies the host that the debugging services are about to start blocking all threads.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9ae2b-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9ae2b-113">Requirements</span></span>  
 <span data-ttu-id="9ae2b-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ae2b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ae2b-115">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9ae2b-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9ae2b-116">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9ae2b-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9ae2b-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ae2b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ae2b-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ae2b-118">See also</span></span>

- [<span data-ttu-id="9ae2b-119">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="9ae2b-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
