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
ms.openlocfilehash: 8cacc96d66d5d4eb46c08c93d9c2793282627539
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438238"
---
# <a name="iclrtask2endpreventasyncabort-method"></a><span data-ttu-id="1e3bf-102">ICLRTask2::EndPreventAsyncAbort (Método)</span><span class="sxs-lookup"><span data-stu-id="1e3bf-102">ICLRTask2::EndPreventAsyncAbort Method</span></span>
<span data-ttu-id="1e3bf-103">Permite nuevas o pendiente de solicitudes de anulación de subproceso como resultado en el subproceso que se anula en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="1e3bf-103">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e3bf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1e3bf-104">Syntax</span></span>  
  
```  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="1e3bf-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1e3bf-105">Return Value</span></span>  
 <span data-ttu-id="1e3bf-106">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="1e3bf-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="1e3bf-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1e3bf-107">HRESULT</span></span>|<span data-ttu-id="1e3bf-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="1e3bf-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1e3bf-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="1e3bf-109">S_OK</span></span>|<span data-ttu-id="1e3bf-110">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="1e3bf-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="1e3bf-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="1e3bf-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="1e3bf-112">Se llamó al método en un subproceso que no es el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="1e3bf-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e3bf-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1e3bf-113">Remarks</span></span>  
 <span data-ttu-id="1e3bf-114">Este contador disminuye la anulación de subproceso de retraso de método de llamada para el subproceso actual en uno.</span><span class="sxs-lookup"><span data-stu-id="1e3bf-114">Calling this method decrements the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="1e3bf-115">Las llamadas a [ICLRTask2:: BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) y `EndPreventAsyncAbort` se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="1e3bf-115">Calls to [ICLRTask2::BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="1e3bf-116">Siempre que el contador sea mayor que cero, se retrasan las anulaciones de subprocesos para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="1e3bf-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="1e3bf-117">La funcionalidad que se expone mediante esta característica se utiliza internamente por la máquina virtual (VM).</span><span class="sxs-lookup"><span data-stu-id="1e3bf-117">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="1e3bf-118">Uso incorrecto de estos métodos puede provocar un comportamiento no especificado en la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="1e3bf-118">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="1e3bf-119">Por ejemplo, al llamar a `EndPreventAsyncAbort` sin antes de llamar a `BeginPreventAsyncAbort` podría establecer el contador a cero cuando la máquina virtual lo ha incrementado previamente.</span><span class="sxs-lookup"><span data-stu-id="1e3bf-119">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="1e3bf-120">De forma similar, no se comprueba el contador interno de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="1e3bf-120">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="1e3bf-121">Si supera el límite de entero dado que se incrementa por el host y la máquina virtual, el comportamiento resultante no está especificado.</span><span class="sxs-lookup"><span data-stu-id="1e3bf-121">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e3bf-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1e3bf-122">Requirements</span></span>  
 <span data-ttu-id="1e3bf-123">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e3bf-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e3bf-124">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1e3bf-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1e3bf-125">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1e3bf-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1e3bf-126">**Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e3bf-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e3bf-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e3bf-127">See Also</span></span>  
 [<span data-ttu-id="1e3bf-128">BeginPreventAsyncAbort (método)</span><span class="sxs-lookup"><span data-stu-id="1e3bf-128">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)  
 [<span data-ttu-id="1e3bf-129">ICLRTask2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1e3bf-129">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 [<span data-ttu-id="1e3bf-130">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1e3bf-130">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="1e3bf-131">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1e3bf-131">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="1e3bf-132">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1e3bf-132">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="1e3bf-133">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="1e3bf-133">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
