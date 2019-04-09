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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60997717baf70e10366e7f0ba6a06daa1f35f8cd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121672"
---
# <a name="iclrtask2endpreventasyncabort-method"></a><span data-ttu-id="5c3c3-102">ICLRTask2::EndPreventAsyncAbort (Método)</span><span class="sxs-lookup"><span data-stu-id="5c3c3-102">ICLRTask2::EndPreventAsyncAbort Method</span></span>
<span data-ttu-id="5c3c3-103">Permite nuevas o pendiente de solicitudes de anulación de subproceso como resultado en el subproceso se anula en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="5c3c3-103">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c3c3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5c3c3-104">Syntax</span></span>  
  
```  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5c3c3-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5c3c3-105">Return Value</span></span>  
 <span data-ttu-id="5c3c3-106">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="5c3c3-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5c3c3-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5c3c3-107">HRESULT</span></span>|<span data-ttu-id="5c3c3-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c3c3-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5c3c3-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="5c3c3-109">S_OK</span></span>|<span data-ttu-id="5c3c3-110">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="5c3c3-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="5c3c3-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="5c3c3-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="5c3c3-112">Se llamó al método en un subproceso que no es el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="5c3c3-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c3c3-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5c3c3-113">Remarks</span></span>  
 <span data-ttu-id="5c3c3-114">Llamar a este contador disminuye la anulación de subproceso de retraso de método del subproceso actual por uno.</span><span class="sxs-lookup"><span data-stu-id="5c3c3-114">Calling this method decrements the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="5c3c3-115">Las llamadas a [Iclrtask2](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) y `EndPreventAsyncAbort` se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="5c3c3-115">Calls to [ICLRTask2::BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="5c3c3-116">Siempre que el contador es mayor que cero, se retrasan las anulaciones de subproceso del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="5c3c3-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="5c3c3-117">La funcionalidad que se expone mediante esta característica se usa internamente por la máquina virtual (VM).</span><span class="sxs-lookup"><span data-stu-id="5c3c3-117">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="5c3c3-118">Uso inadecuado de estos métodos puede provocar un comportamiento no especificado en la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="5c3c3-118">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="5c3c3-119">Por ejemplo, al llamar a `EndPreventAsyncAbort` sin llamar primero a `BeginPreventAsyncAbort` podría establecer el contador a cero cuando la máquina virtual ha incrementado previamente.</span><span class="sxs-lookup"><span data-stu-id="5c3c3-119">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="5c3c3-120">De forma similar, no se comprueba el contador interno de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="5c3c3-120">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="5c3c3-121">Si supera el límite de entero dado que se incrementa en el host y la máquina virtual, el comportamiento resultante no está especificado.</span><span class="sxs-lookup"><span data-stu-id="5c3c3-121">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c3c3-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5c3c3-122">Requirements</span></span>  
 <span data-ttu-id="5c3c3-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c3c3-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c3c3-124">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5c3c3-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5c3c3-125">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5c3c3-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="5c3c3-126">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5c3c3-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5c3c3-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c3c3-127">See also</span></span>

- [<span data-ttu-id="5c3c3-128">Método BeginPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="5c3c3-128">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)
- [<span data-ttu-id="5c3c3-129">ICLRTask2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5c3c3-129">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
- [<span data-ttu-id="5c3c3-130">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5c3c3-130">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="5c3c3-131">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5c3c3-131">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="5c3c3-132">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5c3c3-132">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="5c3c3-133">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="5c3c3-133">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
