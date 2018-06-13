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
ms.openlocfilehash: c3abb3e80226da909a0c7eb8e4bf54959557dcbf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436272"
---
# <a name="iclriocompletionmanager-interface"></a><span data-ttu-id="fe57b-102">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fe57b-102">ICLRIoCompletionManager Interface</span></span>
<span data-ttu-id="fe57b-103">Implementa un método de devolución de llamada que permite al host informar a common language runtime (CLR) del estado de E/S especificado solicitudes.</span><span class="sxs-lookup"><span data-stu-id="fe57b-103">Implements a callback method that allows the host to notify the common language runtime (CLR) of the status of specified I/O requests.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fe57b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="fe57b-104">Methods</span></span>  
  
|<span data-ttu-id="fe57b-105">Método</span><span class="sxs-lookup"><span data-stu-id="fe57b-105">Method</span></span>|<span data-ttu-id="fe57b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="fe57b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fe57b-107">OnComplete (método)</span><span class="sxs-lookup"><span data-stu-id="fe57b-107">OnComplete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|<span data-ttu-id="fe57b-108">Notifica a CLR del estado de una solicitud de E/S que se realiza mediante una llamada a la [IHostIoCompletionManager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="fe57b-108">Notifies the CLR of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe57b-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fe57b-109">Remarks</span></span>  
 <span data-ttu-id="fe57b-110">El host implementa la abstracción de finalización de E/S mediante la [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="fe57b-110">The host implements the I/O completion abstraction by using the [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) interface.</span></span> <span data-ttu-id="fe57b-111">El CLR realiza las solicitudes de E/S a través de esta interfaz, y el host notifica el tiempo de ejecución del resultado de dichas solicitudes mediante el uso de la `ICLRIoCompletionManager` interfaz.</span><span class="sxs-lookup"><span data-stu-id="fe57b-111">The CLR makes I/O requests through this interface, and the host notifies the runtime of the outcome of such requests by using the `ICLRIoCompletionManager` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe57b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fe57b-112">Requirements</span></span>  
 <span data-ttu-id="fe57b-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe57b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe57b-114">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fe57b-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fe57b-115">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fe57b-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fe57b-116">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe57b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe57b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe57b-117">See Also</span></span>  
 [<span data-ttu-id="fe57b-118">IHostIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fe57b-118">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 [<span data-ttu-id="fe57b-119">IHostThreadPoolManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fe57b-119">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
 [<span data-ttu-id="fe57b-120">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="fe57b-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
