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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948556"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="06188-102">ICLRMemoryNotificationCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="06188-102">ICLRMemoryNotificationCallback Interface</span></span>
<span data-ttu-id="06188-103">Permite al host a comunicar condiciones de presión de memoria mediante un enfoque similar de Win32 `CreateMemoryResourceNotification` función.</span><span class="sxs-lookup"><span data-stu-id="06188-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="06188-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="06188-104">Methods</span></span>  
  
|<span data-ttu-id="06188-105">Método</span><span class="sxs-lookup"><span data-stu-id="06188-105">Method</span></span>|<span data-ttu-id="06188-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="06188-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="06188-107">OnMemoryNotification (método)</span><span class="sxs-lookup"><span data-stu-id="06188-107">OnMemoryNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="06188-108">Notifica a common language runtime (CLR) de la carga de memoria en el equipo.</span><span class="sxs-lookup"><span data-stu-id="06188-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06188-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="06188-109">Remarks</span></span>  
 <span data-ttu-id="06188-110">El host usa la `ICLRMemoryNotificationCallback` interfaz para solicitar que CLR libere recursos de memoria.</span><span class="sxs-lookup"><span data-stu-id="06188-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06188-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="06188-111">Requirements</span></span>  
 <span data-ttu-id="06188-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06188-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06188-113">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="06188-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="06188-114">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="06188-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06188-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06188-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06188-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="06188-116">See also</span></span>

- [<span data-ttu-id="06188-117">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="06188-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="06188-118">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="06188-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
