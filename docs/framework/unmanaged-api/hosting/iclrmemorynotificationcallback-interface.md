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
ms.openlocfilehash: e980356ad592e137df7d08dadd77431b0e295380
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141004"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="31700-102">ICLRMemoryNotificationCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="31700-102">ICLRMemoryNotificationCallback Interface</span></span>
<span data-ttu-id="31700-103">Permite al host notificar las condiciones de presión de memoria mediante un enfoque similar al de la función `CreateMemoryResourceNotification` de Win32.</span><span class="sxs-lookup"><span data-stu-id="31700-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="31700-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="31700-104">Methods</span></span>  
  
|<span data-ttu-id="31700-105">Método</span><span class="sxs-lookup"><span data-stu-id="31700-105">Method</span></span>|<span data-ttu-id="31700-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="31700-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="31700-107">OnMemoryNotification (método)</span><span class="sxs-lookup"><span data-stu-id="31700-107">OnMemoryNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="31700-108">Notifica al Common Language Runtime (CLR) la carga de memoria en el equipo.</span><span class="sxs-lookup"><span data-stu-id="31700-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31700-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="31700-109">Remarks</span></span>  
 <span data-ttu-id="31700-110">El host usa la interfaz `ICLRMemoryNotificationCallback` para solicitar que los recursos de memoria de CLR liberen.</span><span class="sxs-lookup"><span data-stu-id="31700-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31700-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="31700-111">Requirements</span></span>  
 <span data-ttu-id="31700-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31700-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31700-113">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="31700-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="31700-114">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="31700-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="31700-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31700-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31700-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="31700-116">See also</span></span>

- [<span data-ttu-id="31700-117">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="31700-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="31700-118">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="31700-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
