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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7864bb81c3b457bf8ec07cd194d24b29a42bd441
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59156070"
---
# <a name="iclriocompletionmanager-interface"></a><span data-ttu-id="d9ee1-102">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d9ee1-102">ICLRIoCompletionManager Interface</span></span>
<span data-ttu-id="d9ee1-103">Implementa un método de devolución de llamada que permite al host informar a common language runtime (CLR) del estado de E/S especificado solicitudes.</span><span class="sxs-lookup"><span data-stu-id="d9ee1-103">Implements a callback method that allows the host to notify the common language runtime (CLR) of the status of specified I/O requests.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d9ee1-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="d9ee1-104">Methods</span></span>  
  
|<span data-ttu-id="d9ee1-105">Método</span><span class="sxs-lookup"><span data-stu-id="d9ee1-105">Method</span></span>|<span data-ttu-id="d9ee1-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9ee1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d9ee1-107">Método OnComplete</span><span class="sxs-lookup"><span data-stu-id="d9ee1-107">OnComplete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|<span data-ttu-id="d9ee1-108">Notifica a CLR del estado de una solicitud de E/S que se hace mediante una llamada a la [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="d9ee1-108">Notifies the CLR of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9ee1-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d9ee1-109">Remarks</span></span>  
 <span data-ttu-id="d9ee1-110">El host implementa la abstracción de finalización de E/S mediante el uso de la [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="d9ee1-110">The host implements the I/O completion abstraction by using the [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) interface.</span></span> <span data-ttu-id="d9ee1-111">El CLR realiza las solicitudes de E/S a través de esta interfaz, y el host informa el tiempo de ejecución del resultado de dichas solicitudes mediante el uso de la `ICLRIoCompletionManager` interfaz.</span><span class="sxs-lookup"><span data-stu-id="d9ee1-111">The CLR makes I/O requests through this interface, and the host notifies the runtime of the outcome of such requests by using the `ICLRIoCompletionManager` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9ee1-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d9ee1-112">Requirements</span></span>  
 <span data-ttu-id="d9ee1-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9ee1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9ee1-114">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d9ee1-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d9ee1-115">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d9ee1-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d9ee1-116">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d9ee1-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d9ee1-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9ee1-117">See also</span></span>

- [<span data-ttu-id="d9ee1-118">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d9ee1-118">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="d9ee1-119">IHostThreadPoolManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d9ee1-119">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
- [<span data-ttu-id="d9ee1-120">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="d9ee1-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
