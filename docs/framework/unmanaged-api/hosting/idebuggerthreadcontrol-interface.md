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
ms.openlocfilehash: 2268fce5d3ca732d852edfdb6f0edf63117df363
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684218"
---
# <a name="idebuggerthreadcontrol-interface"></a><span data-ttu-id="ee1a9-102">IDebuggerThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ee1a9-102">IDebuggerThreadControl Interface</span></span>

<span data-ttu-id="ee1a9-103">Proporciona métodos para notificar al host el bloqueo y desbloqueo de subprocesos por parte de los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="ee1a9-103">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ee1a9-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ee1a9-104">Methods</span></span>  
  
|<span data-ttu-id="ee1a9-105">Método</span><span class="sxs-lookup"><span data-stu-id="ee1a9-105">Method</span></span>|<span data-ttu-id="ee1a9-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ee1a9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ee1a9-107">Método ThreadIsBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="ee1a9-107">ThreadIsBlockingForDebugger Method</span></span>](idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|<span data-ttu-id="ee1a9-108">Notifica al host que el subproceso que está enviando esta devolución de llamada está a punto de bloquearse dentro de los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="ee1a9-108">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>|  
|[<span data-ttu-id="ee1a9-109">Método ReleaseAllRuntimeThreads</span><span class="sxs-lookup"><span data-stu-id="ee1a9-109">ReleaseAllRuntimeThreads Method</span></span>](idebuggerthreadcontrol-releaseallruntimethreads-method.md)|<span data-ttu-id="ee1a9-110">Notifica al host que los servicios de depuración están a punto de liberar todos los subprocesos que están bloqueados.</span><span class="sxs-lookup"><span data-stu-id="ee1a9-110">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>|  
|[<span data-ttu-id="ee1a9-111">Método StartBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="ee1a9-111">StartBlockingForDebugger Method</span></span>](idebuggerthreadcontrol-startblockingfordebugger-method.md)|<span data-ttu-id="ee1a9-112">Notifica al host que los servicios de depuración están a punto de iniciar el bloqueo de todos los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="ee1a9-112">Notifies the host that the debugging services are about to start blocking all threads.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ee1a9-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ee1a9-113">Requirements</span></span>  

 <span data-ttu-id="ee1a9-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee1a9-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee1a9-115">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ee1a9-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ee1a9-116">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ee1a9-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ee1a9-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee1a9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee1a9-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ee1a9-118">See also</span></span>

- [<span data-ttu-id="ee1a9-119">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="ee1a9-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
