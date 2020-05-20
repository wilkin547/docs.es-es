---
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
ms.openlocfilehash: 822b51531b7afc1c824c74b9580d9208e347e13b
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703551"
---
# <a name="iclriocompletionmanager-interface"></a><span data-ttu-id="dca2a-102">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dca2a-102">ICLRIoCompletionManager Interface</span></span>
<span data-ttu-id="dca2a-103">Implementa un método de devolución de llamada que permite al host notificar el Common Language Runtime (CLR) del estado de las solicitudes de e/s especificadas.</span><span class="sxs-lookup"><span data-stu-id="dca2a-103">Implements a callback method that allows the host to notify the common language runtime (CLR) of the status of specified I/O requests.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dca2a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="dca2a-104">Methods</span></span>  
  
|<span data-ttu-id="dca2a-105">Método</span><span class="sxs-lookup"><span data-stu-id="dca2a-105">Method</span></span>|<span data-ttu-id="dca2a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="dca2a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dca2a-107">Método OnComplete</span><span class="sxs-lookup"><span data-stu-id="dca2a-107">OnComplete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|<span data-ttu-id="dca2a-108">Notifica a CLR el estado de una solicitud de e/s realizada mediante una llamada al método [IHostIoCompletionManager:: Bind](ihostiocompletionmanager-bind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="dca2a-108">Notifies the CLR of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](ihostiocompletionmanager-bind-method.md) method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dca2a-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dca2a-109">Remarks</span></span>  
 <span data-ttu-id="dca2a-110">El host implementa la abstracción de finalización de e/s mediante la interfaz [IHostIoCompletionManager](ihostiocompletionmanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="dca2a-110">The host implements the I/O completion abstraction by using the [IHostIoCompletionManager](ihostiocompletionmanager-interface.md) interface.</span></span> <span data-ttu-id="dca2a-111">CLR realiza solicitudes de e/s a través de esta interfaz y el host notifica al tiempo de ejecución el resultado de dichas solicitudes mediante la `ICLRIoCompletionManager` interfaz.</span><span class="sxs-lookup"><span data-stu-id="dca2a-111">The CLR makes I/O requests through this interface, and the host notifies the runtime of the outcome of such requests by using the `ICLRIoCompletionManager` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dca2a-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dca2a-112">Requirements</span></span>  
 <span data-ttu-id="dca2a-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dca2a-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dca2a-114">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="dca2a-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dca2a-115">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="dca2a-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dca2a-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dca2a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dca2a-117">Consulta también</span><span class="sxs-lookup"><span data-stu-id="dca2a-117">See also</span></span>

- [<span data-ttu-id="dca2a-118">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dca2a-118">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="dca2a-119">IHostThreadPoolManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dca2a-119">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
- [<span data-ttu-id="dca2a-120">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="dca2a-120">Hosting Interfaces</span></span>](hosting-interfaces.md)
