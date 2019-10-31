---
title: ICLRTask2::EndPreventAsyncAbort (Método)
ms.date: 03/30/2017
api_name:
- ICLRTask2.EndPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::EndPreventAsyncAbort
helpviewer_keywords:
- EndPreventAsyncAbort method [.NET Framework hosting]
- ICLRTask2::EndPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: d8013659-e3df-44b3-814f-a6b534ce62f8
topic_type:
- apiref
ms.openlocfilehash: 8ae66e0bf96138e5bc2f33e4c14ad86e7dabc6b8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124553"
---
# <a name="iclrtask2endpreventasyncabort-method"></a><span data-ttu-id="69af4-102">ICLRTask2::EndPreventAsyncAbort (Método)</span><span class="sxs-lookup"><span data-stu-id="69af4-102">ICLRTask2::EndPreventAsyncAbort Method</span></span>
<span data-ttu-id="69af4-103">Permite que las solicitudes de anulación de subprocesos nuevas o pendientes produzcan anulaciones de subprocesos en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="69af4-103">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69af4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69af4-104">Syntax</span></span>  
  
```cpp  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="69af4-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="69af4-105">Return Value</span></span>  
 <span data-ttu-id="69af4-106">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="69af4-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="69af4-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="69af4-107">HRESULT</span></span>|<span data-ttu-id="69af4-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="69af4-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="69af4-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="69af4-109">S_OK</span></span>|<span data-ttu-id="69af4-110">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="69af4-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="69af4-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="69af4-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="69af4-112">Se llamó al método en un subproceso que no es el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="69af4-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69af4-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="69af4-113">Remarks</span></span>  
 <span data-ttu-id="69af4-114">Al llamar a este método, se reduce el contador Delay-Thread-Abort del subproceso actual en uno.</span><span class="sxs-lookup"><span data-stu-id="69af4-114">Calling this method decrements the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="69af4-115">Las llamadas a [ICLRTask2:: BeginPreventAsyncAbort (](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) y `EndPreventAsyncAbort` se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="69af4-115">Calls to [ICLRTask2::BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="69af4-116">Siempre que el contador sea mayor que cero, se retrasarán las anulaciones de subproceso para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="69af4-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="69af4-117">La funcionalidad que expone esta característica se usa internamente en la máquina virtual (VM).</span><span class="sxs-lookup"><span data-stu-id="69af4-117">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="69af4-118">El uso incorrecto de estos métodos puede provocar un comportamiento no especificado en la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="69af4-118">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="69af4-119">Por ejemplo, la llamada a `EndPreventAsyncAbort` sin llamar primero a `BeginPreventAsyncAbort` podría establecer el contador en cero cuando la máquina virtual lo ha incrementado previamente.</span><span class="sxs-lookup"><span data-stu-id="69af4-119">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="69af4-120">Del mismo modo, no se comprueba el desbordamiento del contador interno.</span><span class="sxs-lookup"><span data-stu-id="69af4-120">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="69af4-121">Si supera su límite entero porque lo incrementa el host y la máquina virtual, el comportamiento resultante no se especifica.</span><span class="sxs-lookup"><span data-stu-id="69af4-121">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69af4-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="69af4-122">Requirements</span></span>  
 <span data-ttu-id="69af4-123">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69af4-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69af4-124">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="69af4-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="69af4-125">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="69af4-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="69af4-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69af4-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69af4-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="69af4-127">See also</span></span>

- [<span data-ttu-id="69af4-128">BeginPreventAsyncAbort (método)</span><span class="sxs-lookup"><span data-stu-id="69af4-128">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)
- [<span data-ttu-id="69af4-129">ICLRTask2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="69af4-129">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
- [<span data-ttu-id="69af4-130">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="69af4-130">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="69af4-131">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="69af4-131">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="69af4-132">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="69af4-132">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="69af4-133">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="69af4-133">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
