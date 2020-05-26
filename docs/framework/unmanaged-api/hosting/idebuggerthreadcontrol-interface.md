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
ms.openlocfilehash: 82c6113f4df3334500128df22f7e9ce8d4bf151f
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805286"
---
# <a name="idebuggerthreadcontrol-interface"></a><span data-ttu-id="e7418-102">IDebuggerThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e7418-102">IDebuggerThreadControl Interface</span></span>
<span data-ttu-id="e7418-103">Proporciona métodos para notificar al host el bloqueo y desbloqueo de subprocesos por parte de los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="e7418-103">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e7418-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e7418-104">Methods</span></span>  
  
|<span data-ttu-id="e7418-105">Método</span><span class="sxs-lookup"><span data-stu-id="e7418-105">Method</span></span>|<span data-ttu-id="e7418-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7418-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e7418-107">Método ThreadIsBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="e7418-107">ThreadIsBlockingForDebugger Method</span></span>](idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|<span data-ttu-id="e7418-108">Notifica al host que el subproceso que está enviando esta devolución de llamada está a punto de bloquearse dentro de los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="e7418-108">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>|  
|[<span data-ttu-id="e7418-109">Método ReleaseAllRuntimeThreads</span><span class="sxs-lookup"><span data-stu-id="e7418-109">ReleaseAllRuntimeThreads Method</span></span>](idebuggerthreadcontrol-releaseallruntimethreads-method.md)|<span data-ttu-id="e7418-110">Notifica al host que los servicios de depuración están a punto de liberar todos los subprocesos que están bloqueados.</span><span class="sxs-lookup"><span data-stu-id="e7418-110">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>|  
|[<span data-ttu-id="e7418-111">Método StartBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="e7418-111">StartBlockingForDebugger Method</span></span>](idebuggerthreadcontrol-startblockingfordebugger-method.md)|<span data-ttu-id="e7418-112">Notifica al host que los servicios de depuración están a punto de iniciar el bloqueo de todos los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="e7418-112">Notifies the host that the debugging services are about to start blocking all threads.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e7418-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e7418-113">Requirements</span></span>  
 <span data-ttu-id="e7418-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7418-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7418-115">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e7418-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e7418-116">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e7418-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e7418-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7418-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7418-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e7418-118">See also</span></span>

- [<span data-ttu-id="e7418-119">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="e7418-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
