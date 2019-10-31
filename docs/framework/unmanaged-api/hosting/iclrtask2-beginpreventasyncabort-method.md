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
ms.openlocfilehash: 67841bbcd796e41b3b81f922020fe6c3677730c4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124563"
---
# <a name="iclrtask2beginpreventasyncabort-method"></a><span data-ttu-id="a8385-102">ICLRTask2::BeginPreventAsyncAbort (Método)</span><span class="sxs-lookup"><span data-stu-id="a8385-102">ICLRTask2::BeginPreventAsyncAbort Method</span></span>
<span data-ttu-id="a8385-103">Retrasa las nuevas solicitudes de anulación de subprocesos para que resulten anulaciones de subprocesos en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="a8385-103">Delays new thread abort requests from resulting in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8385-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a8385-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a8385-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a8385-105">Return Value</span></span>  
 <span data-ttu-id="a8385-106">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="a8385-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a8385-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a8385-107">HRESULT</span></span>|<span data-ttu-id="a8385-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8385-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a8385-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="a8385-109">S_OK</span></span>|<span data-ttu-id="a8385-110">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="a8385-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="a8385-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="a8385-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="a8385-112">Se llamó al método en un subproceso que no es el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="a8385-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8385-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a8385-113">Remarks</span></span>  
 <span data-ttu-id="a8385-114">Al llamar a este método, se incrementa el contador Delay-Thread-Abort del subproceso actual en uno.</span><span class="sxs-lookup"><span data-stu-id="a8385-114">Calling this method increments the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="a8385-115">Las llamadas a `BeginPreventAsyncAbort` y [ICLRTask2:: EndPreventAsyncAbort (](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md) se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="a8385-115">Calls to `BeginPreventAsyncAbort` and [ICLRTask2::EndPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md) can be nested.</span></span> <span data-ttu-id="a8385-116">Siempre que el contador sea mayor que cero, se retrasarán las anulaciones de subproceso para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="a8385-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span> <span data-ttu-id="a8385-117">Si esta llamada no se empareja con una llamada al método `EndPreventAsyncAbort`, es posible llegar a un estado en el que las anulaciones de subprocesos no se puedan entregar al subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="a8385-117">If this call is not paired with a call to the `EndPreventAsyncAbort` method, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="a8385-118">No se respeta el retraso de un subproceso que se anule.</span><span class="sxs-lookup"><span data-stu-id="a8385-118">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="a8385-119">La funcionalidad que expone esta característica se usa internamente en la máquina virtual (VM).</span><span class="sxs-lookup"><span data-stu-id="a8385-119">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="a8385-120">El uso incorrecto de estos métodos puede provocar un comportamiento no especificado en la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="a8385-120">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="a8385-121">Por ejemplo, la llamada a `EndPreventAsyncAbort` sin llamar primero a `BeginPreventAsyncAbort` podría establecer el contador en cero cuando la máquina virtual lo ha incrementado previamente.</span><span class="sxs-lookup"><span data-stu-id="a8385-121">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="a8385-122">Del mismo modo, no se comprueba el desbordamiento del contador interno.</span><span class="sxs-lookup"><span data-stu-id="a8385-122">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="a8385-123">Si supera su límite entero porque lo incrementa el host y la máquina virtual, el comportamiento resultante no se especifica.</span><span class="sxs-lookup"><span data-stu-id="a8385-123">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8385-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a8385-124">Requirements</span></span>  
 <span data-ttu-id="a8385-125">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8385-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8385-126">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a8385-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a8385-127">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a8385-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a8385-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8385-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8385-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8385-129">See also</span></span>

- [<span data-ttu-id="a8385-130">EndPreventAsyncAbort (método)</span><span class="sxs-lookup"><span data-stu-id="a8385-130">EndPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)
- [<span data-ttu-id="a8385-131">ICLRTask2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8385-131">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
- [<span data-ttu-id="a8385-132">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8385-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="a8385-133">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8385-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="a8385-134">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8385-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="a8385-135">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="a8385-135">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
