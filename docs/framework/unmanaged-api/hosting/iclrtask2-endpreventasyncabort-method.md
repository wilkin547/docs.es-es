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
ms.openlocfilehash: 3ea36c56ef9ccf5886ba96191627e5283da186f7
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762860"
---
# <a name="iclrtask2endpreventasyncabort-method"></a><span data-ttu-id="a4a7c-102">ICLRTask2::EndPreventAsyncAbort (Método)</span><span class="sxs-lookup"><span data-stu-id="a4a7c-102">ICLRTask2::EndPreventAsyncAbort Method</span></span>
<span data-ttu-id="a4a7c-103">Permite que las solicitudes de anulación de subprocesos nuevas o pendientes produzcan anulaciones de subprocesos en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="a4a7c-103">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4a7c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a4a7c-104">Syntax</span></span>  
  
```cpp  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a4a7c-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a4a7c-105">Return Value</span></span>  
 <span data-ttu-id="a4a7c-106">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="a4a7c-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a4a7c-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a4a7c-107">HRESULT</span></span>|<span data-ttu-id="a4a7c-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a4a7c-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a4a7c-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="a4a7c-109">S_OK</span></span>|<span data-ttu-id="a4a7c-110">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="a4a7c-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="a4a7c-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="a4a7c-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="a4a7c-112">Se llamó al método en un subproceso que no es el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="a4a7c-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4a7c-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a4a7c-113">Remarks</span></span>  
 <span data-ttu-id="a4a7c-114">Al llamar a este método, se reduce el contador Delay-Thread-Abort del subproceso actual en uno.</span><span class="sxs-lookup"><span data-stu-id="a4a7c-114">Calling this method decrements the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="a4a7c-115">Las llamadas a [ICLRTask2:: BeginPreventAsyncAbort (](iclrtask2-beginpreventasyncabort-method.md) y `EndPreventAsyncAbort` se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="a4a7c-115">Calls to [ICLRTask2::BeginPreventAsyncAbort](iclrtask2-beginpreventasyncabort-method.md) and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="a4a7c-116">Siempre que el contador sea mayor que cero, se retrasarán las anulaciones de subproceso para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="a4a7c-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="a4a7c-117">La funcionalidad que expone esta característica se usa internamente en la máquina virtual (VM).</span><span class="sxs-lookup"><span data-stu-id="a4a7c-117">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="a4a7c-118">El uso incorrecto de estos métodos puede provocar un comportamiento no especificado en la máquina virtual.</span><span class="sxs-lookup"><span data-stu-id="a4a7c-118">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="a4a7c-119">Por ejemplo, llamar a `EndPreventAsyncAbort` sin la primera llamada `BeginPreventAsyncAbort` podría establecer el contador en cero cuando la máquina virtual lo ha incrementado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a4a7c-119">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="a4a7c-120">Del mismo modo, no se comprueba el desbordamiento del contador interno.</span><span class="sxs-lookup"><span data-stu-id="a4a7c-120">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="a4a7c-121">Si supera su límite entero porque lo incrementa el host y la máquina virtual, el comportamiento resultante no se especifica.</span><span class="sxs-lookup"><span data-stu-id="a4a7c-121">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4a7c-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a4a7c-122">Requirements</span></span>  
 <span data-ttu-id="a4a7c-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4a7c-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4a7c-124">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a4a7c-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a4a7c-125">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a4a7c-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a4a7c-126">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4a7c-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4a7c-127">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="a4a7c-127">See also</span></span>

- [<span data-ttu-id="a4a7c-128">Método BeginPreventAsyncAbort</span><span class="sxs-lookup"><span data-stu-id="a4a7c-128">BeginPreventAsyncAbort Method</span></span>](iclrtask2-beginpreventasyncabort-method.md)
- [<span data-ttu-id="a4a7c-129">ICLRTask2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a4a7c-129">ICLRTask2 Interface</span></span>](iclrtask2-interface.md)
- [<span data-ttu-id="a4a7c-130">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a4a7c-130">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="a4a7c-131">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a4a7c-131">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="a4a7c-132">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a4a7c-132">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="a4a7c-133">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="a4a7c-133">Hosting Interfaces</span></span>](hosting-interfaces.md)
