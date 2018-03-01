---
title: ICLRTask2 (Interfaz)
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8701cff3400e46660fac90486cf5648d29aa9972
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtask2-interface"></a><span data-ttu-id="2816b-102">ICLRTask2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2816b-102">ICLRTask2 Interface</span></span>
<span data-ttu-id="2816b-103">Proporciona toda la funcionalidad de la [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interfaz; además, proporciona métodos que permiten anulaciones de subprocesos para se retrasa en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="2816b-103">Provides all the functionality of the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface; in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2816b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="2816b-104">Methods</span></span>  
  
|<span data-ttu-id="2816b-105">Método</span><span class="sxs-lookup"><span data-stu-id="2816b-105">Method</span></span>|<span data-ttu-id="2816b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="2816b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2816b-107">BeginPreventAsyncAbort (método)</span><span class="sxs-lookup"><span data-stu-id="2816b-107">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)|<span data-ttu-id="2816b-108">Nuevo subproceso de retrasos anular las solicitudes en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="2816b-108">Delays new thread abort requests on the current thread.</span></span>|  
|[<span data-ttu-id="2816b-109">EndPreventAsyncAbort (método)</span><span class="sxs-lookup"><span data-stu-id="2816b-109">EndPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)|<span data-ttu-id="2816b-110">Permite nuevas o pendiente de solicitudes de anulación de subproceso como resultado en el subproceso que se anula en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="2816b-110">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2816b-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2816b-111">Remarks</span></span>  
 <span data-ttu-id="2816b-112">El `ICLRTask2` interfaz hereda el `ICLRTask` de interfaz y agrega métodos que permiten al host retrasar las anulaciones de subprocesos, para proteger una región de código que no debe producir un error.</span><span class="sxs-lookup"><span data-stu-id="2816b-112">The `ICLRTask2` interface inherits the `ICLRTask` interface and adds methods that allow the host to delay thread aborts, to protect a region of code that must not fail.</span></span> <span data-ttu-id="2816b-113">Al llamar a `BeginPreventAsyncAbort` incrementa el contador de anulaciones de subprocesos con retraso para el subproceso actual y llamar al método `EndPreventAsyncAbort` disminuye lo.</span><span class="sxs-lookup"><span data-stu-id="2816b-113">Calling `BeginPreventAsyncAbort` increments the delay-thread-abort counter for the current thread, and calling `EndPreventAsyncAbort` decrements it.</span></span> <span data-ttu-id="2816b-114">Las llamadas a `BeginPreventAsyncAbort` y `EndPreventAsyncAbort` se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="2816b-114">Calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="2816b-115">Siempre que el contador sea mayor que cero, se retrasan las anulaciones de subprocesos para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="2816b-115">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="2816b-116">Si llama a `BeginPreventAsyncAbort` y `EndPreventAsyncAbort` no son emparejados, es posible llegar a un estado en el subproceso no se puede entregar anulaciones para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="2816b-116">If calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` are not paired, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="2816b-117">No se respeta el retraso para un subproceso que se anula a sí mismo.</span><span class="sxs-lookup"><span data-stu-id="2816b-117">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="2816b-118">La funcionalidad que se expone mediante esta característica se utiliza internamente por la máquina virtual (VM).</span><span class="sxs-lookup"><span data-stu-id="2816b-118">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="2816b-119">Uso incorrecto de estos métodos puede provocar un comportamiento no especificado en la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="2816b-119">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="2816b-120">Por ejemplo, al llamar a `EndPreventAsyncAbort` sin antes de llamar a `BeginPreventAsyncAbort` podría establecer el contador a cero cuando la máquina virtual lo ha incrementado previamente.</span><span class="sxs-lookup"><span data-stu-id="2816b-120">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="2816b-121">De forma similar, no se comprueba el contador interno de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="2816b-121">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="2816b-122">Si supera el límite de entero dado que se incrementa por el host y la máquina virtual, el comportamiento resultante no está especificado.</span><span class="sxs-lookup"><span data-stu-id="2816b-122">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
 <span data-ttu-id="2816b-123">Para obtener información acerca de los miembros se hereda de `ICLRTask` y sobre los otros usos de esta interfaz, vea la [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="2816b-123">For information about members inherited from `ICLRTask` and about the other uses of this interface, see the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2816b-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2816b-124">Requirements</span></span>  
 <span data-ttu-id="2816b-125">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2816b-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2816b-126">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2816b-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2816b-127">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2816b-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2816b-128">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2816b-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2816b-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="2816b-129">See Also</span></span>  
 [<span data-ttu-id="2816b-130">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2816b-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="2816b-131">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2816b-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="2816b-132">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2816b-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="2816b-133">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2816b-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="2816b-134">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="2816b-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
