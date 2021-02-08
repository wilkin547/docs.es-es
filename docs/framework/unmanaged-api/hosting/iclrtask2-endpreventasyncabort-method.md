---
description: 'Más información sobre: ICLRTask2:: EndPreventAsyncAbort ((método)'
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
ms.openlocfilehash: 964a68c1ad6d5aa6a95560d2870e135640283590
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799504"
---
# <a name="iclrtask2endpreventasyncabort-method"></a><span data-ttu-id="36de5-103">ICLRTask2::EndPreventAsyncAbort (Método)</span><span class="sxs-lookup"><span data-stu-id="36de5-103">ICLRTask2::EndPreventAsyncAbort Method</span></span>

<span data-ttu-id="36de5-104">Permite que las solicitudes de anulación de subprocesos nuevas o pendientes produzcan anulaciones de subprocesos en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="36de5-104">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36de5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36de5-105">Syntax</span></span>  
  
```cpp  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="36de5-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="36de5-106">Return Value</span></span>  

 <span data-ttu-id="36de5-107">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="36de5-107">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="36de5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="36de5-108">HRESULT</span></span>|<span data-ttu-id="36de5-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="36de5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="36de5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="36de5-110">S_OK</span></span>|<span data-ttu-id="36de5-111">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="36de5-111">The method completed successfully.</span></span>|  
|<span data-ttu-id="36de5-112">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="36de5-112">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="36de5-113">Se llamó al método en un subproceso que no es el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="36de5-113">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36de5-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="36de5-114">Remarks</span></span>  

 <span data-ttu-id="36de5-115">Al llamar a este método, se reduce el contador Delay-Thread-Abort del subproceso actual en uno.</span><span class="sxs-lookup"><span data-stu-id="36de5-115">Calling this method decrements the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="36de5-116">Las llamadas a [ICLRTask2:: BeginPreventAsyncAbort (](iclrtask2-beginpreventasyncabort-method.md) y `EndPreventAsyncAbort` se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="36de5-116">Calls to [ICLRTask2::BeginPreventAsyncAbort](iclrtask2-beginpreventasyncabort-method.md) and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="36de5-117">Siempre que el contador sea mayor que cero, se retrasarán las anulaciones de subproceso para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="36de5-117">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="36de5-118">La funcionalidad que expone esta característica se usa internamente en la máquina virtual (VM).</span><span class="sxs-lookup"><span data-stu-id="36de5-118">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="36de5-119">El uso incorrecto de estos métodos puede provocar un comportamiento no especificado en la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="36de5-119">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="36de5-120">Por ejemplo, llamar a `EndPreventAsyncAbort` sin la primera llamada `BeginPreventAsyncAbort` podría establecer el contador en cero cuando la máquina virtual lo ha incrementado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="36de5-120">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="36de5-121">Del mismo modo, no se comprueba el desbordamiento del contador interno.</span><span class="sxs-lookup"><span data-stu-id="36de5-121">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="36de5-122">Si supera su límite entero porque lo incrementa el host y la máquina virtual, el comportamiento resultante no se especifica.</span><span class="sxs-lookup"><span data-stu-id="36de5-122">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36de5-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="36de5-123">Requirements</span></span>  

 <span data-ttu-id="36de5-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36de5-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36de5-125">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="36de5-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="36de5-126">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="36de5-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="36de5-127">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36de5-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36de5-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="36de5-128">See also</span></span>

- [<span data-ttu-id="36de5-129">Método BeginPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="36de5-129">BeginPreventAsyncAbort Method</span></span>](iclrtask2-beginpreventasyncabort-method.md)
- [<span data-ttu-id="36de5-130">ICLRTask2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="36de5-130">ICLRTask2 Interface</span></span>](iclrtask2-interface.md)
- [<span data-ttu-id="36de5-131">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="36de5-131">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="36de5-132">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="36de5-132">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="36de5-133">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="36de5-133">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="36de5-134">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="36de5-134">Hosting Interfaces</span></span>](hosting-interfaces.md)
