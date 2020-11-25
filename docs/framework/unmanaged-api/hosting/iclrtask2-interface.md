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
ms.openlocfilehash: 9332b3462ba389783a113d173e32850d40427ce2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720235"
---
# <a name="iclrtask2-interface"></a><span data-ttu-id="e6af6-102">ICLRTask2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6af6-102">ICLRTask2 Interface</span></span>

<span data-ttu-id="e6af6-103">Proporciona toda la funcionalidad de la interfaz [ICLRTask](iclrtask-interface.md) ; Además, proporciona métodos que permiten que las anulaciones de subprocesos se retrasen en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="e6af6-103">Provides all the functionality of the [ICLRTask](iclrtask-interface.md) interface; in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e6af6-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e6af6-104">Methods</span></span>  
  
|<span data-ttu-id="e6af6-105">Método</span><span class="sxs-lookup"><span data-stu-id="e6af6-105">Method</span></span>|<span data-ttu-id="e6af6-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6af6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e6af6-107">Método BeginPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="e6af6-107">BeginPreventAsyncAbort Method</span></span>](iclrtask2-beginpreventasyncabort-method.md)|<span data-ttu-id="e6af6-108">Retrasa nuevas solicitudes de anulación de subprocesos en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="e6af6-108">Delays new thread abort requests on the current thread.</span></span>|  
|[<span data-ttu-id="e6af6-109">Método EndPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="e6af6-109">EndPreventAsyncAbort Method</span></span>](iclrtask2-endpreventasyncabort-method.md)|<span data-ttu-id="e6af6-110">Permite que las solicitudes de anulación de subprocesos nuevas o pendientes produzcan anulaciones de subprocesos en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="e6af6-110">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6af6-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e6af6-111">Remarks</span></span>  

 <span data-ttu-id="e6af6-112">La `ICLRTask2` interfaz hereda la `ICLRTask` interfaz y agrega métodos que permiten al host retrasar las anulaciones de subprocesos, para proteger una región de código que no se debe producir un error.</span><span class="sxs-lookup"><span data-stu-id="e6af6-112">The `ICLRTask2` interface inherits the `ICLRTask` interface and adds methods that allow the host to delay thread aborts, to protect a region of code that must not fail.</span></span> <span data-ttu-id="e6af6-113">La llamada a `BeginPreventAsyncAbort` incrementa el contador Delay-Thread-Abort para el subproceso actual y la llamada a `EndPreventAsyncAbort` lo reduce.</span><span class="sxs-lookup"><span data-stu-id="e6af6-113">Calling `BeginPreventAsyncAbort` increments the delay-thread-abort counter for the current thread, and calling `EndPreventAsyncAbort` decrements it.</span></span> <span data-ttu-id="e6af6-114">Las llamadas a `BeginPreventAsyncAbort` y `EndPreventAsyncAbort` se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="e6af6-114">Calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="e6af6-115">Siempre que el contador sea mayor que cero, se retrasarán las anulaciones de subproceso para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="e6af6-115">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="e6af6-116">Si las llamadas a `BeginPreventAsyncAbort` y `EndPreventAsyncAbort` no están emparejadas, es posible llegar a un estado en el que las anulaciones de subprocesos no se puedan entregar al subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="e6af6-116">If calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` are not paired, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="e6af6-117">No se respeta el retraso de un subproceso que se anule.</span><span class="sxs-lookup"><span data-stu-id="e6af6-117">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="e6af6-118">La funcionalidad que expone esta característica se usa internamente en la máquina virtual (VM).</span><span class="sxs-lookup"><span data-stu-id="e6af6-118">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="e6af6-119">El uso incorrecto de estos métodos puede provocar un comportamiento no especificado en la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="e6af6-119">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="e6af6-120">Por ejemplo, llamar a `EndPreventAsyncAbort` sin la primera llamada `BeginPreventAsyncAbort` podría establecer el contador en cero cuando la máquina virtual lo ha incrementado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e6af6-120">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="e6af6-121">Del mismo modo, no se comprueba el desbordamiento del contador interno.</span><span class="sxs-lookup"><span data-stu-id="e6af6-121">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="e6af6-122">Si supera su límite entero porque lo incrementa el host y la máquina virtual, el comportamiento resultante no se especifica.</span><span class="sxs-lookup"><span data-stu-id="e6af6-122">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
 <span data-ttu-id="e6af6-123">Para obtener información sobre los miembros heredados de `ICLRTask` y sobre los otros usos de esta interfaz, vea la interfaz [ICLRTask](iclrtask-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e6af6-123">For information about members inherited from `ICLRTask` and about the other uses of this interface, see the [ICLRTask](iclrtask-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6af6-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e6af6-124">Requirements</span></span>  

 <span data-ttu-id="e6af6-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6af6-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6af6-126">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e6af6-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e6af6-127">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e6af6-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6af6-128">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6af6-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6af6-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e6af6-129">See also</span></span>

- [<span data-ttu-id="e6af6-130">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6af6-130">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="e6af6-131">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6af6-131">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="e6af6-132">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6af6-132">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="e6af6-133">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6af6-133">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="e6af6-134">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="e6af6-134">Hosting Interfaces</span></span>](hosting-interfaces.md)
