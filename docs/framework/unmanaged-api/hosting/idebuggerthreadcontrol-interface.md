---
description: 'Más información acerca de: interfaz IDebuggerThreadControl'
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
ms.openlocfilehash: 293a120d44b9b04d7e367546c477fb273f535310
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709777"
---
# <a name="idebuggerthreadcontrol-interface"></a><span data-ttu-id="7adc2-103">IDebuggerThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7adc2-103">IDebuggerThreadControl Interface</span></span>

<span data-ttu-id="7adc2-104">Proporciona métodos para notificar al host el bloqueo y desbloqueo de subprocesos por parte de los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="7adc2-104">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7adc2-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="7adc2-105">Methods</span></span>  
  
|<span data-ttu-id="7adc2-106">Método</span><span class="sxs-lookup"><span data-stu-id="7adc2-106">Method</span></span>|<span data-ttu-id="7adc2-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="7adc2-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7adc2-108">Método ThreadIsBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="7adc2-108">ThreadIsBlockingForDebugger Method</span></span>](idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|<span data-ttu-id="7adc2-109">Notifica al host que el subproceso que está enviando esta devolución de llamada está a punto de bloquearse dentro de los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="7adc2-109">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>|  
|[<span data-ttu-id="7adc2-110">Método ReleaseAllRuntimeThreads</span><span class="sxs-lookup"><span data-stu-id="7adc2-110">ReleaseAllRuntimeThreads Method</span></span>](idebuggerthreadcontrol-releaseallruntimethreads-method.md)|<span data-ttu-id="7adc2-111">Notifica al host que los servicios de depuración están a punto de liberar todos los subprocesos que están bloqueados.</span><span class="sxs-lookup"><span data-stu-id="7adc2-111">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>|  
|[<span data-ttu-id="7adc2-112">Método StartBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="7adc2-112">StartBlockingForDebugger Method</span></span>](idebuggerthreadcontrol-startblockingfordebugger-method.md)|<span data-ttu-id="7adc2-113">Notifica al host que los servicios de depuración están a punto de iniciar el bloqueo de todos los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="7adc2-113">Notifies the host that the debugging services are about to start blocking all threads.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7adc2-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7adc2-114">Requirements</span></span>  

 <span data-ttu-id="7adc2-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7adc2-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7adc2-116">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7adc2-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7adc2-117">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7adc2-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7adc2-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7adc2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7adc2-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="7adc2-119">See also</span></span>

- [<span data-ttu-id="7adc2-120">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="7adc2-120">Hosting Interfaces</span></span>](hosting-interfaces.md)
