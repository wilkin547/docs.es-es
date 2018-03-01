---
title: ICLRIoCompletionManager (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 99dc183674abaff33047f070c14794150a8615f0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclriocompletionmanager-interface"></a><span data-ttu-id="9a139-102">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9a139-102">ICLRIoCompletionManager Interface</span></span>
<span data-ttu-id="9a139-103">Implementa un método de devolución de llamada que permite al host informar a common language runtime (CLR) del estado de E/S especificado solicitudes.</span><span class="sxs-lookup"><span data-stu-id="9a139-103">Implements a callback method that allows the host to notify the common language runtime (CLR) of the status of specified I/O requests.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9a139-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="9a139-104">Methods</span></span>  
  
|<span data-ttu-id="9a139-105">Método</span><span class="sxs-lookup"><span data-stu-id="9a139-105">Method</span></span>|<span data-ttu-id="9a139-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="9a139-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9a139-107">OnComplete (método)</span><span class="sxs-lookup"><span data-stu-id="9a139-107">OnComplete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|<span data-ttu-id="9a139-108">Notifica a CLR del estado de una solicitud de E/S que se realiza mediante una llamada a la [IHostIoCompletionManager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="9a139-108">Notifies the CLR of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a139-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9a139-109">Remarks</span></span>  
 <span data-ttu-id="9a139-110">El host implementa la abstracción de finalización de E/S mediante la [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="9a139-110">The host implements the I/O completion abstraction by using the [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) interface.</span></span> <span data-ttu-id="9a139-111">El CLR realiza las solicitudes de E/S a través de esta interfaz, y el host notifica el tiempo de ejecución del resultado de dichas solicitudes mediante el uso de la `ICLRIoCompletionManager` interfaz.</span><span class="sxs-lookup"><span data-stu-id="9a139-111">The CLR makes I/O requests through this interface, and the host notifies the runtime of the outcome of such requests by using the `ICLRIoCompletionManager` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a139-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9a139-112">Requirements</span></span>  
 <span data-ttu-id="9a139-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a139-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a139-114">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9a139-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9a139-115">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9a139-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9a139-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a139-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a139-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a139-117">See Also</span></span>  
 [<span data-ttu-id="9a139-118">IHostIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9a139-118">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 [<span data-ttu-id="9a139-119">IHostThreadPoolManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9a139-119">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
 [<span data-ttu-id="9a139-120">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="9a139-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
