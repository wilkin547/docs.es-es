---
description: 'Más información acerca de: ICLRIoCompletionManager (interfaz)'
title: ICLRIoCompletionManager (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager
helpviewer_keywords:
- ICLRIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c6c3ace6-e5e7-4450-8cc5-a9a48208c493
topic_type:
- apiref
ms.openlocfilehash: b2d18f9c9900d448f0c6517520c303eb4258f8d3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789900"
---
# <a name="iclriocompletionmanager-interface"></a><span data-ttu-id="85ce9-103">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="85ce9-103">ICLRIoCompletionManager Interface</span></span>

<span data-ttu-id="85ce9-104">Implementa un método de devolución de llamada que permite al host notificar el Common Language Runtime (CLR) del estado de las solicitudes de e/s especificadas.</span><span class="sxs-lookup"><span data-stu-id="85ce9-104">Implements a callback method that allows the host to notify the common language runtime (CLR) of the status of specified I/O requests.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="85ce9-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="85ce9-105">Methods</span></span>  
  
|<span data-ttu-id="85ce9-106">Método</span><span class="sxs-lookup"><span data-stu-id="85ce9-106">Method</span></span>|<span data-ttu-id="85ce9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="85ce9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="85ce9-108">Método OnComplete</span><span class="sxs-lookup"><span data-stu-id="85ce9-108">OnComplete Method</span></span>](iclriocompletionmanager-oncomplete-method.md)|<span data-ttu-id="85ce9-109">Notifica a CLR el estado de una solicitud de e/s realizada mediante una llamada al método [IHostIoCompletionManager:: Bind](ihostiocompletionmanager-bind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="85ce9-109">Notifies the CLR of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](ihostiocompletionmanager-bind-method.md) method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85ce9-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="85ce9-110">Remarks</span></span>  

 <span data-ttu-id="85ce9-111">El host implementa la abstracción de finalización de e/s mediante la interfaz [IHostIoCompletionManager](ihostiocompletionmanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="85ce9-111">The host implements the I/O completion abstraction by using the [IHostIoCompletionManager](ihostiocompletionmanager-interface.md) interface.</span></span> <span data-ttu-id="85ce9-112">CLR realiza solicitudes de e/s a través de esta interfaz y el host notifica al tiempo de ejecución el resultado de dichas solicitudes mediante la `ICLRIoCompletionManager` interfaz.</span><span class="sxs-lookup"><span data-stu-id="85ce9-112">The CLR makes I/O requests through this interface, and the host notifies the runtime of the outcome of such requests by using the `ICLRIoCompletionManager` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85ce9-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="85ce9-113">Requirements</span></span>  

 <span data-ttu-id="85ce9-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85ce9-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85ce9-115">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="85ce9-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="85ce9-116">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="85ce9-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="85ce9-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85ce9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85ce9-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="85ce9-118">See also</span></span>

- [<span data-ttu-id="85ce9-119">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="85ce9-119">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="85ce9-120">IHostThreadPoolManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="85ce9-120">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
- [<span data-ttu-id="85ce9-121">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="85ce9-121">Hosting Interfaces</span></span>](hosting-interfaces.md)
