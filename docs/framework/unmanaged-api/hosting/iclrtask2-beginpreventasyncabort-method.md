---
title: "ICLRTask2::BeginPreventAsyncAbort (Método)"
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
- ICLRTask2.BeginPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::BeginPreventAsyncAbort
helpviewer_keywords:
- ICLRTask2::BeginPreventAsyncAbort method [.NET Framework hosting]
- BeginPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: 75754c2f-38c7-4707-85fe-559db4542729
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7bbbf609963f06e6c0204e8d44db30bb392886e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtask2beginpreventasyncabort-method"></a><span data-ttu-id="ed71b-102">ICLRTask2::BeginPreventAsyncAbort (Método)</span><span class="sxs-lookup"><span data-stu-id="ed71b-102">ICLRTask2::BeginPreventAsyncAbort Method</span></span>
<span data-ttu-id="ed71b-103">Nuevo subproceso de retrasos solicitudes de anulación de resultante en anulaciones de subprocesos en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="ed71b-103">Delays new thread abort requests from resulting in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed71b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ed71b-104">Syntax</span></span>  
  
```  
HRESULT BeginPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ed71b-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ed71b-105">Return Value</span></span>  
 <span data-ttu-id="ed71b-106">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="ed71b-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ed71b-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ed71b-107">HRESULT</span></span>|<span data-ttu-id="ed71b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed71b-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ed71b-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="ed71b-109">S_OK</span></span>|<span data-ttu-id="ed71b-110">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="ed71b-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="ed71b-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="ed71b-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="ed71b-112">Se llamó al método en un subproceso que no es el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="ed71b-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed71b-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ed71b-113">Remarks</span></span>  
 <span data-ttu-id="ed71b-114">Llamar a este método, el contador de anulaciones de subprocesos con retraso para el subproceso actual incrementa en uno.</span><span class="sxs-lookup"><span data-stu-id="ed71b-114">Calling this method increments the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="ed71b-115">Las llamadas a `BeginPreventAsyncAbort` y [ICLRTask2:: EndPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md) se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="ed71b-115">Calls to `BeginPreventAsyncAbort` and [ICLRTask2::EndPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md) can be nested.</span></span> <span data-ttu-id="ed71b-116">Siempre que el contador sea mayor que cero, se retrasan las anulaciones de subprocesos para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="ed71b-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span> <span data-ttu-id="ed71b-117">Si esta llamada no se corresponde con una llamada a la `EndPreventAsyncAbort` método, es posible llegar a un estado en el subproceso no se puede entregar anulaciones para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="ed71b-117">If this call is not paired with a call to the `EndPreventAsyncAbort` method, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="ed71b-118">No se respeta el retraso para un subproceso que se anula a sí mismo.</span><span class="sxs-lookup"><span data-stu-id="ed71b-118">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="ed71b-119">La funcionalidad que se expone mediante esta característica se utiliza internamente por la máquina virtual (VM).</span><span class="sxs-lookup"><span data-stu-id="ed71b-119">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="ed71b-120">Uso incorrecto de estos métodos puede provocar un comportamiento no especificado en la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="ed71b-120">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="ed71b-121">Por ejemplo, al llamar a `EndPreventAsyncAbort` sin antes de llamar a `BeginPreventAsyncAbort` podría establecer el contador a cero cuando la máquina virtual lo ha incrementado previamente.</span><span class="sxs-lookup"><span data-stu-id="ed71b-121">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="ed71b-122">De forma similar, no se comprueba el contador interno de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="ed71b-122">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="ed71b-123">Si supera el límite de entero dado que se incrementa por el host y la máquina virtual, el comportamiento resultante no está especificado.</span><span class="sxs-lookup"><span data-stu-id="ed71b-123">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed71b-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ed71b-124">Requirements</span></span>  
 <span data-ttu-id="ed71b-125">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed71b-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed71b-126">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ed71b-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ed71b-127">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ed71b-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ed71b-128">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed71b-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed71b-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed71b-129">See Also</span></span>  
 [<span data-ttu-id="ed71b-130">EndPreventAsyncAbort (método)</span><span class="sxs-lookup"><span data-stu-id="ed71b-130">EndPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)  
 [<span data-ttu-id="ed71b-131">ICLRTask2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ed71b-131">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 [<span data-ttu-id="ed71b-132">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ed71b-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="ed71b-133">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ed71b-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="ed71b-134">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ed71b-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="ed71b-135">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="ed71b-135">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
