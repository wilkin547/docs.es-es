---
title: ICLRTask2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRTask2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2
helpviewer_keywords:
- ICLRTask2 interface [.NET Framework hosting]
ms.assetid: b5a22ebc-0582-49de-91f9-97a3d9789290
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cbd627eff9318fce38ec238e5fa686cc9d759b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627192"
---
# <a name="iclrtask2-interface"></a><span data-ttu-id="448ec-102">ICLRTask2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="448ec-102">ICLRTask2 Interface</span></span>
<span data-ttu-id="448ec-103">Proporciona toda la funcionalidad de la [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interfaz; además, proporciona métodos que permiten las anulaciones de subprocesos para que se retrasa en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="448ec-103">Provides all the functionality of the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface; in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="448ec-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="448ec-104">Methods</span></span>  
  
|<span data-ttu-id="448ec-105">Método</span><span class="sxs-lookup"><span data-stu-id="448ec-105">Method</span></span>|<span data-ttu-id="448ec-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="448ec-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="448ec-107">BeginPreventAsyncAbort (método)</span><span class="sxs-lookup"><span data-stu-id="448ec-107">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)|<span data-ttu-id="448ec-108">Subproceso nuevo retrasos anular las solicitudes en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="448ec-108">Delays new thread abort requests on the current thread.</span></span>|  
|[<span data-ttu-id="448ec-109">EndPreventAsyncAbort (método)</span><span class="sxs-lookup"><span data-stu-id="448ec-109">EndPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)|<span data-ttu-id="448ec-110">Permite nuevas o pendiente de solicitudes de anulación de subproceso como resultado en el subproceso se anula en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="448ec-110">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="448ec-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="448ec-111">Remarks</span></span>  
 <span data-ttu-id="448ec-112">El `ICLRTask2` interfaz hereda el `ICLRTask` interfaz y agrega los métodos que permiten al host retrasar las anulaciones de subproceso, para proteger una región de código que no debe sufrir un error.</span><span class="sxs-lookup"><span data-stu-id="448ec-112">The `ICLRTask2` interface inherits the `ICLRTask` interface and adds methods that allow the host to delay thread aborts, to protect a region of code that must not fail.</span></span> <span data-ttu-id="448ec-113">Una llamada a `BeginPreventAsyncAbort` incrementa el contador de anulaciones de subprocesos con retraso para el subproceso actual y llamar al método `EndPreventAsyncAbort` disminuye lo.</span><span class="sxs-lookup"><span data-stu-id="448ec-113">Calling `BeginPreventAsyncAbort` increments the delay-thread-abort counter for the current thread, and calling `EndPreventAsyncAbort` decrements it.</span></span> <span data-ttu-id="448ec-114">Las llamadas a `BeginPreventAsyncAbort` y `EndPreventAsyncAbort` se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="448ec-114">Calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="448ec-115">Siempre que el contador es mayor que cero, se retrasan las anulaciones de subproceso del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="448ec-115">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="448ec-116">Si las llamadas a `BeginPreventAsyncAbort` y `EndPreventAsyncAbort` están emparejados no, es posible obtener acceso a un estado en que el subproceso no se puede entregar anulaciones al subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="448ec-116">If calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` are not paired, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="448ec-117">No se respeta el retraso de un subproceso que se anula a sí mismo.</span><span class="sxs-lookup"><span data-stu-id="448ec-117">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="448ec-118">La funcionalidad que se expone mediante esta característica se usa internamente por la máquina virtual (VM).</span><span class="sxs-lookup"><span data-stu-id="448ec-118">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="448ec-119">Uso inadecuado de estos métodos puede provocar un comportamiento no especificado en la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="448ec-119">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="448ec-120">Por ejemplo, al llamar a `EndPreventAsyncAbort` sin llamar primero a `BeginPreventAsyncAbort` podría establecer el contador a cero cuando la máquina virtual ha incrementado previamente.</span><span class="sxs-lookup"><span data-stu-id="448ec-120">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="448ec-121">De forma similar, no se comprueba el contador interno de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="448ec-121">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="448ec-122">Si supera el límite de entero dado que se incrementa en el host y la máquina virtual, el comportamiento resultante no está especificado.</span><span class="sxs-lookup"><span data-stu-id="448ec-122">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
 <span data-ttu-id="448ec-123">Para obtener información acerca de los miembros que hereda de `ICLRTask` y sobre otros usos de esta interfaz, vea el [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="448ec-123">For information about members inherited from `ICLRTask` and about the other uses of this interface, see the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="448ec-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="448ec-124">Requirements</span></span>  
 <span data-ttu-id="448ec-125">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="448ec-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="448ec-126">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="448ec-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="448ec-127">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="448ec-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="448ec-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="448ec-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="448ec-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="448ec-129">See also</span></span>
- [<span data-ttu-id="448ec-130">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="448ec-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="448ec-131">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="448ec-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="448ec-132">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="448ec-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="448ec-133">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="448ec-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="448ec-134">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="448ec-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
