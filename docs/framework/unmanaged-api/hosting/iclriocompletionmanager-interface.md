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
ms.openlocfilehash: b63d4269a8d48ee49016a4c51d63bf81bdba8da2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141022"
---
# <a name="iclriocompletionmanager-interface"></a><span data-ttu-id="74854-102">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="74854-102">ICLRIoCompletionManager Interface</span></span>
<span data-ttu-id="74854-103">Implementa un método de devolución de llamada que permite al host notificar el Common Language Runtime (CLR) del estado de las solicitudes de e/s especificadas.</span><span class="sxs-lookup"><span data-stu-id="74854-103">Implements a callback method that allows the host to notify the common language runtime (CLR) of the status of specified I/O requests.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="74854-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="74854-104">Methods</span></span>  
  
|<span data-ttu-id="74854-105">Método</span><span class="sxs-lookup"><span data-stu-id="74854-105">Method</span></span>|<span data-ttu-id="74854-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="74854-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="74854-107">OnComplete (método)</span><span class="sxs-lookup"><span data-stu-id="74854-107">OnComplete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|<span data-ttu-id="74854-108">Notifica a CLR el estado de una solicitud de e/s realizada mediante una llamada al método [IHostIoCompletionManager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="74854-108">Notifies the CLR of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74854-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="74854-109">Remarks</span></span>  
 <span data-ttu-id="74854-110">El host implementa la abstracción de finalización de e/s mediante la interfaz [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="74854-110">The host implements the I/O completion abstraction by using the [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) interface.</span></span> <span data-ttu-id="74854-111">El CLR realiza solicitudes de e/s a través de esta interfaz y el host notifica al tiempo de ejecución el resultado de dichas solicitudes mediante el uso de la interfaz de `ICLRIoCompletionManager`.</span><span class="sxs-lookup"><span data-stu-id="74854-111">The CLR makes I/O requests through this interface, and the host notifies the runtime of the outcome of such requests by using the `ICLRIoCompletionManager` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74854-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74854-112">Requirements</span></span>  
 <span data-ttu-id="74854-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74854-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74854-114">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="74854-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="74854-115">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="74854-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="74854-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74854-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74854-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="74854-117">See also</span></span>

- [<span data-ttu-id="74854-118">IHostIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="74854-118">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="74854-119">IHostThreadPoolManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="74854-119">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
- [<span data-ttu-id="74854-120">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="74854-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
