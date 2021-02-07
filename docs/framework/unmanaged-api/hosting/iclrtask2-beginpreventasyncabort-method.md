---
description: 'Más información sobre: ICLRTask2:: BeginPreventAsyncAbort ((método)'
title: ICLRTask2::BeginPreventAsyncAbort (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: 1e25cb0e6157d77efc6a04016dc49d9d5d0bf116
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728655"
---
# <a name="iclrtask2beginpreventasyncabort-method"></a><span data-ttu-id="1aed4-103">ICLRTask2::BeginPreventAsyncAbort (Método)</span><span class="sxs-lookup"><span data-stu-id="1aed4-103">ICLRTask2::BeginPreventAsyncAbort Method</span></span>

<span data-ttu-id="1aed4-104">Retrasa las nuevas solicitudes de anulación de subprocesos para que resulten anulaciones de subprocesos en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="1aed4-104">Delays new thread abort requests from resulting in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1aed4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1aed4-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="1aed4-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1aed4-106">Return Value</span></span>  

 <span data-ttu-id="1aed4-107">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="1aed4-107">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="1aed4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1aed4-108">HRESULT</span></span>|<span data-ttu-id="1aed4-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="1aed4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1aed4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1aed4-110">S_OK</span></span>|<span data-ttu-id="1aed4-111">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="1aed4-111">The method completed successfully.</span></span>|  
|<span data-ttu-id="1aed4-112">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="1aed4-112">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="1aed4-113">Se llamó al método en un subproceso que no es el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="1aed4-113">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1aed4-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1aed4-114">Remarks</span></span>  

 <span data-ttu-id="1aed4-115">Al llamar a este método, se incrementa el contador Delay-Thread-Abort del subproceso actual en uno.</span><span class="sxs-lookup"><span data-stu-id="1aed4-115">Calling this method increments the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="1aed4-116">Las llamadas a `BeginPreventAsyncAbort` y [ICLRTask2:: EndPreventAsyncAbort (](iclrtask2-endpreventasyncabort-method.md) se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="1aed4-116">Calls to `BeginPreventAsyncAbort` and [ICLRTask2::EndPreventAsyncAbort](iclrtask2-endpreventasyncabort-method.md) can be nested.</span></span> <span data-ttu-id="1aed4-117">Siempre que el contador sea mayor que cero, se retrasarán las anulaciones de subproceso para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="1aed4-117">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span> <span data-ttu-id="1aed4-118">Si esta llamada no se empareja con una llamada al `EndPreventAsyncAbort` método, es posible llegar a un estado en el que no se puedan entregar las anulaciones de subprocesos al subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="1aed4-118">If this call is not paired with a call to the `EndPreventAsyncAbort` method, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="1aed4-119">No se respeta el retraso de un subproceso que se anule.</span><span class="sxs-lookup"><span data-stu-id="1aed4-119">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="1aed4-120">La funcionalidad que expone esta característica se usa internamente en la máquina virtual (VM).</span><span class="sxs-lookup"><span data-stu-id="1aed4-120">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="1aed4-121">El uso incorrecto de estos métodos puede provocar un comportamiento no especificado en la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="1aed4-121">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="1aed4-122">Por ejemplo, llamar a `EndPreventAsyncAbort` sin la primera llamada `BeginPreventAsyncAbort` podría establecer el contador en cero cuando la máquina virtual lo ha incrementado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="1aed4-122">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="1aed4-123">Del mismo modo, no se comprueba el desbordamiento del contador interno.</span><span class="sxs-lookup"><span data-stu-id="1aed4-123">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="1aed4-124">Si supera su límite entero porque lo incrementa el host y la máquina virtual, el comportamiento resultante no se especifica.</span><span class="sxs-lookup"><span data-stu-id="1aed4-124">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1aed4-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1aed4-125">Requirements</span></span>  

 <span data-ttu-id="1aed4-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1aed4-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1aed4-127">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1aed4-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1aed4-128">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1aed4-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1aed4-129">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1aed4-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aed4-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="1aed4-130">See also</span></span>

- [<span data-ttu-id="1aed4-131">Método EndPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="1aed4-131">EndPreventAsyncAbort Method</span></span>](iclrtask2-endpreventasyncabort-method.md)
- [<span data-ttu-id="1aed4-132">ICLRTask2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1aed4-132">ICLRTask2 Interface</span></span>](iclrtask2-interface.md)
- [<span data-ttu-id="1aed4-133">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1aed4-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="1aed4-134">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1aed4-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="1aed4-135">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1aed4-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="1aed4-136">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="1aed4-136">Hosting Interfaces</span></span>](hosting-interfaces.md)
