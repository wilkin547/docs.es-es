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
ms.openlocfilehash: 47c6dd9045636bcfbe07c909fec3fda515d28ee8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124527"
---
# <a name="iclrtask2-interface"></a><span data-ttu-id="f4d33-102">ICLRTask2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f4d33-102">ICLRTask2 Interface</span></span>
<span data-ttu-id="f4d33-103">Proporciona toda la funcionalidad de la interfaz [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) ; Además, proporciona métodos que permiten que las anulaciones de subprocesos se retrasen en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="f4d33-103">Provides all the functionality of the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface; in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f4d33-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f4d33-104">Methods</span></span>  
  
|<span data-ttu-id="f4d33-105">Método</span><span class="sxs-lookup"><span data-stu-id="f4d33-105">Method</span></span>|<span data-ttu-id="f4d33-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f4d33-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f4d33-107">BeginPreventAsyncAbort (método)</span><span class="sxs-lookup"><span data-stu-id="f4d33-107">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)|<span data-ttu-id="f4d33-108">Retrasa nuevas solicitudes de anulación de subprocesos en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="f4d33-108">Delays new thread abort requests on the current thread.</span></span>|  
|[<span data-ttu-id="f4d33-109">EndPreventAsyncAbort (método)</span><span class="sxs-lookup"><span data-stu-id="f4d33-109">EndPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)|<span data-ttu-id="f4d33-110">Permite que las solicitudes de anulación de subprocesos nuevas o pendientes produzcan anulaciones de subprocesos en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="f4d33-110">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4d33-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f4d33-111">Remarks</span></span>  
 <span data-ttu-id="f4d33-112">La interfaz de `ICLRTask2` hereda la interfaz de `ICLRTask` y agrega métodos que permiten al host retrasar las anulaciones de subprocesos, para proteger una región de código que no se debe producir un error.</span><span class="sxs-lookup"><span data-stu-id="f4d33-112">The `ICLRTask2` interface inherits the `ICLRTask` interface and adds methods that allow the host to delay thread aborts, to protect a region of code that must not fail.</span></span> <span data-ttu-id="f4d33-113">La llamada a `BeginPreventAsyncAbort` incrementa el contador Delay-Thread-Abort para el subproceso actual y la llamada a `EndPreventAsyncAbort` lo reduce.</span><span class="sxs-lookup"><span data-stu-id="f4d33-113">Calling `BeginPreventAsyncAbort` increments the delay-thread-abort counter for the current thread, and calling `EndPreventAsyncAbort` decrements it.</span></span> <span data-ttu-id="f4d33-114">Las llamadas a `BeginPreventAsyncAbort` y `EndPreventAsyncAbort` se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="f4d33-114">Calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="f4d33-115">Siempre que el contador sea mayor que cero, se retrasarán las anulaciones de subproceso para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="f4d33-115">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="f4d33-116">Si las llamadas a `BeginPreventAsyncAbort` y `EndPreventAsyncAbort` no están emparejadas, es posible llegar a un estado en el que no se puedan entregar las anulaciones de subprocesos al subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="f4d33-116">If calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` are not paired, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="f4d33-117">No se respeta el retraso de un subproceso que se anule.</span><span class="sxs-lookup"><span data-stu-id="f4d33-117">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="f4d33-118">La funcionalidad que expone esta característica se usa internamente en la máquina virtual (VM).</span><span class="sxs-lookup"><span data-stu-id="f4d33-118">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="f4d33-119">El uso incorrecto de estos métodos puede provocar un comportamiento no especificado en la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="f4d33-119">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="f4d33-120">Por ejemplo, la llamada a `EndPreventAsyncAbort` sin llamar primero a `BeginPreventAsyncAbort` podría establecer el contador en cero cuando la máquina virtual lo ha incrementado previamente.</span><span class="sxs-lookup"><span data-stu-id="f4d33-120">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="f4d33-121">Del mismo modo, no se comprueba el desbordamiento del contador interno.</span><span class="sxs-lookup"><span data-stu-id="f4d33-121">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="f4d33-122">Si supera su límite entero porque lo incrementa el host y la máquina virtual, el comportamiento resultante no se especifica.</span><span class="sxs-lookup"><span data-stu-id="f4d33-122">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
 <span data-ttu-id="f4d33-123">Para obtener información sobre los miembros heredados de `ICLRTask` y sobre los otros usos de esta interfaz, vea la interfaz [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="f4d33-123">For information about members inherited from `ICLRTask` and about the other uses of this interface, see the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4d33-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f4d33-124">Requirements</span></span>  
 <span data-ttu-id="f4d33-125">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4d33-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4d33-126">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f4d33-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f4d33-127">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f4d33-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f4d33-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4d33-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4d33-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4d33-129">See also</span></span>

- [<span data-ttu-id="f4d33-130">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f4d33-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="f4d33-131">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f4d33-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="f4d33-132">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f4d33-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="f4d33-133">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f4d33-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="f4d33-134">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="f4d33-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
