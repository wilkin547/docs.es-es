---
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
ms.openlocfilehash: daf211fcc496f63ef71575abf6a28655004db264
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720248"
---
# <a name="iclrtask2beginpreventasyncabort-method"></a><span data-ttu-id="e141d-102">ICLRTask2::BeginPreventAsyncAbort (Método)</span><span class="sxs-lookup"><span data-stu-id="e141d-102">ICLRTask2::BeginPreventAsyncAbort Method</span></span>

<span data-ttu-id="e141d-103">Retrasa las nuevas solicitudes de anulación de subprocesos para que resulten anulaciones de subprocesos en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="e141d-103">Delays new thread abort requests from resulting in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e141d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e141d-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e141d-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e141d-105">Return Value</span></span>  

 <span data-ttu-id="e141d-106">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="e141d-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e141d-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e141d-107">HRESULT</span></span>|<span data-ttu-id="e141d-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="e141d-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e141d-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="e141d-109">S_OK</span></span>|<span data-ttu-id="e141d-110">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="e141d-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="e141d-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="e141d-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="e141d-112">Se llamó al método en un subproceso que no es el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="e141d-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e141d-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e141d-113">Remarks</span></span>  

 <span data-ttu-id="e141d-114">Al llamar a este método, se incrementa el contador Delay-Thread-Abort del subproceso actual en uno.</span><span class="sxs-lookup"><span data-stu-id="e141d-114">Calling this method increments the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="e141d-115">Las llamadas a `BeginPreventAsyncAbort` y [ICLRTask2:: EndPreventAsyncAbort (](iclrtask2-endpreventasyncabort-method.md) se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="e141d-115">Calls to `BeginPreventAsyncAbort` and [ICLRTask2::EndPreventAsyncAbort](iclrtask2-endpreventasyncabort-method.md) can be nested.</span></span> <span data-ttu-id="e141d-116">Siempre que el contador sea mayor que cero, se retrasarán las anulaciones de subproceso para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="e141d-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span> <span data-ttu-id="e141d-117">Si esta llamada no se empareja con una llamada al `EndPreventAsyncAbort` método, es posible llegar a un estado en el que no se puedan entregar las anulaciones de subprocesos al subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="e141d-117">If this call is not paired with a call to the `EndPreventAsyncAbort` method, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="e141d-118">No se respeta el retraso de un subproceso que se anule.</span><span class="sxs-lookup"><span data-stu-id="e141d-118">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="e141d-119">La funcionalidad que expone esta característica se usa internamente en la máquina virtual (VM).</span><span class="sxs-lookup"><span data-stu-id="e141d-119">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="e141d-120">El uso incorrecto de estos métodos puede provocar un comportamiento no especificado en la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="e141d-120">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="e141d-121">Por ejemplo, llamar a `EndPreventAsyncAbort` sin la primera llamada `BeginPreventAsyncAbort` podría establecer el contador en cero cuando la máquina virtual lo ha incrementado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e141d-121">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="e141d-122">Del mismo modo, no se comprueba el desbordamiento del contador interno.</span><span class="sxs-lookup"><span data-stu-id="e141d-122">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="e141d-123">Si supera su límite entero porque lo incrementa el host y la máquina virtual, el comportamiento resultante no se especifica.</span><span class="sxs-lookup"><span data-stu-id="e141d-123">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e141d-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e141d-124">Requirements</span></span>  

 <span data-ttu-id="e141d-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e141d-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e141d-126">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e141d-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e141d-127">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e141d-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e141d-128">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e141d-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e141d-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e141d-129">See also</span></span>

- [<span data-ttu-id="e141d-130">Método EndPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="e141d-130">EndPreventAsyncAbort Method</span></span>](iclrtask2-endpreventasyncabort-method.md)
- [<span data-ttu-id="e141d-131">ICLRTask2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e141d-131">ICLRTask2 Interface</span></span>](iclrtask2-interface.md)
- [<span data-ttu-id="e141d-132">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e141d-132">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="e141d-133">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e141d-133">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="e141d-134">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e141d-134">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="e141d-135">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="e141d-135">Hosting Interfaces</span></span>](hosting-interfaces.md)
