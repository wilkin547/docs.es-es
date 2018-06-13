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
ms.openlocfilehash: ed0d2ff3b64bab026087e13d54314eca86181d8c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438813"
---
# <a name="iclrtask2-interface"></a><span data-ttu-id="f1651-102">ICLRTask2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f1651-102">ICLRTask2 Interface</span></span>
<span data-ttu-id="f1651-103">Proporciona toda la funcionalidad de la [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interfaz; además, proporciona métodos que permiten anulaciones de subprocesos para se retrasa en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="f1651-103">Provides all the functionality of the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface; in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f1651-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f1651-104">Methods</span></span>  
  
|<span data-ttu-id="f1651-105">Método</span><span class="sxs-lookup"><span data-stu-id="f1651-105">Method</span></span>|<span data-ttu-id="f1651-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f1651-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f1651-107">BeginPreventAsyncAbort (método)</span><span class="sxs-lookup"><span data-stu-id="f1651-107">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)|<span data-ttu-id="f1651-108">Nuevo subproceso de retrasos anular las solicitudes en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="f1651-108">Delays new thread abort requests on the current thread.</span></span>|  
|[<span data-ttu-id="f1651-109">EndPreventAsyncAbort (método)</span><span class="sxs-lookup"><span data-stu-id="f1651-109">EndPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)|<span data-ttu-id="f1651-110">Permite nuevas o pendiente de solicitudes de anulación de subproceso como resultado en el subproceso que se anula en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="f1651-110">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1651-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f1651-111">Remarks</span></span>  
 <span data-ttu-id="f1651-112">El `ICLRTask2` interfaz hereda el `ICLRTask` de interfaz y agrega métodos que permiten al host retrasar las anulaciones de subprocesos, para proteger una región de código que no debe producir un error.</span><span class="sxs-lookup"><span data-stu-id="f1651-112">The `ICLRTask2` interface inherits the `ICLRTask` interface and adds methods that allow the host to delay thread aborts, to protect a region of code that must not fail.</span></span> <span data-ttu-id="f1651-113">Al llamar a `BeginPreventAsyncAbort` incrementa el contador de anulaciones de subprocesos con retraso para el subproceso actual y llamar al método `EndPreventAsyncAbort` disminuye lo.</span><span class="sxs-lookup"><span data-stu-id="f1651-113">Calling `BeginPreventAsyncAbort` increments the delay-thread-abort counter for the current thread, and calling `EndPreventAsyncAbort` decrements it.</span></span> <span data-ttu-id="f1651-114">Las llamadas a `BeginPreventAsyncAbort` y `EndPreventAsyncAbort` se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="f1651-114">Calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="f1651-115">Siempre que el contador sea mayor que cero, se retrasan las anulaciones de subprocesos para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="f1651-115">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="f1651-116">Si llama a `BeginPreventAsyncAbort` y `EndPreventAsyncAbort` no son emparejados, es posible llegar a un estado en el subproceso no se puede entregar anulaciones para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="f1651-116">If calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` are not paired, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="f1651-117">No se respeta el retraso para un subproceso que se anula a sí mismo.</span><span class="sxs-lookup"><span data-stu-id="f1651-117">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="f1651-118">La funcionalidad que se expone mediante esta característica se utiliza internamente por la máquina virtual (VM).</span><span class="sxs-lookup"><span data-stu-id="f1651-118">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="f1651-119">Uso incorrecto de estos métodos puede provocar un comportamiento no especificado en la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="f1651-119">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="f1651-120">Por ejemplo, al llamar a `EndPreventAsyncAbort` sin antes de llamar a `BeginPreventAsyncAbort` podría establecer el contador a cero cuando la máquina virtual lo ha incrementado previamente.</span><span class="sxs-lookup"><span data-stu-id="f1651-120">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="f1651-121">De forma similar, no se comprueba el contador interno de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="f1651-121">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="f1651-122">Si supera el límite de entero dado que se incrementa por el host y la máquina virtual, el comportamiento resultante no está especificado.</span><span class="sxs-lookup"><span data-stu-id="f1651-122">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
 <span data-ttu-id="f1651-123">Para obtener información acerca de los miembros se hereda de `ICLRTask` y sobre los otros usos de esta interfaz, vea la [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="f1651-123">For information about members inherited from `ICLRTask` and about the other uses of this interface, see the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1651-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f1651-124">Requirements</span></span>  
 <span data-ttu-id="f1651-125">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1651-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1651-126">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f1651-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f1651-127">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f1651-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f1651-128">**Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1651-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1651-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1651-129">See Also</span></span>  
 [<span data-ttu-id="f1651-130">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f1651-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="f1651-131">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f1651-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="f1651-132">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f1651-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="f1651-133">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f1651-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="f1651-134">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="f1651-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
