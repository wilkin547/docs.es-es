---
title: ICLRMemoryNotificationCallback (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback
helpviewer_keywords:
- ICLRMemoryNotificationCallback interface [.NET Framework hosting]
ms.assetid: 873639e2-4837-4568-83b3-4493e67e4174
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c98ece9d60571034f3298f15897b10c4d8fb06f4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212159"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="1cede-102">ICLRMemoryNotificationCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1cede-102">ICLRMemoryNotificationCallback Interface</span></span>
<span data-ttu-id="1cede-103">Permite al host a comunicar condiciones de presión de memoria mediante un enfoque similar de Win32 `CreateMemoryResourceNotification` función.</span><span class="sxs-lookup"><span data-stu-id="1cede-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1cede-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="1cede-104">Methods</span></span>  
  
|<span data-ttu-id="1cede-105">Método</span><span class="sxs-lookup"><span data-stu-id="1cede-105">Method</span></span>|<span data-ttu-id="1cede-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="1cede-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1cede-107">Método OnMemoryNotification</span><span class="sxs-lookup"><span data-stu-id="1cede-107">OnMemoryNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="1cede-108">Notifica a common language runtime (CLR) de la carga de memoria en el equipo.</span><span class="sxs-lookup"><span data-stu-id="1cede-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1cede-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1cede-109">Remarks</span></span>  
 <span data-ttu-id="1cede-110">El host usa la `ICLRMemoryNotificationCallback` interfaz para solicitar que CLR libere recursos de memoria.</span><span class="sxs-lookup"><span data-stu-id="1cede-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cede-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1cede-111">Requirements</span></span>  
 <span data-ttu-id="1cede-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1cede-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cede-113">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1cede-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1cede-114">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1cede-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="1cede-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="1cede-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1cede-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1cede-116">See also</span></span>

- [<span data-ttu-id="1cede-117">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1cede-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="1cede-118">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="1cede-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
