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
ms.openlocfilehash: 2c5cf7e17989f3c083c7c4e52fa8cfc09c00bc7d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431524"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="a8970-102">ICLRMemoryNotificationCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8970-102">ICLRMemoryNotificationCallback Interface</span></span>
<span data-ttu-id="a8970-103">Permite al host situaciones de presión de memoria de informe mediante un enfoque similar de Win32 `CreateMemoryResourceNotification` función.</span><span class="sxs-lookup"><span data-stu-id="a8970-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a8970-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a8970-104">Methods</span></span>  
  
|<span data-ttu-id="a8970-105">Método</span><span class="sxs-lookup"><span data-stu-id="a8970-105">Method</span></span>|<span data-ttu-id="a8970-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8970-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a8970-107">OnMemoryNotification (método)</span><span class="sxs-lookup"><span data-stu-id="a8970-107">OnMemoryNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="a8970-108">Notifica a common language runtime (CLR) de la carga de memoria en el equipo.</span><span class="sxs-lookup"><span data-stu-id="a8970-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8970-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a8970-109">Remarks</span></span>  
 <span data-ttu-id="a8970-110">El host usa la `ICLRMemoryNotificationCallback` interfaz para solicitar a CLR que libere recursos de memoria.</span><span class="sxs-lookup"><span data-stu-id="a8970-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8970-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a8970-111">Requirements</span></span>  
 <span data-ttu-id="a8970-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8970-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8970-113">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a8970-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a8970-114">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a8970-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a8970-115">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8970-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8970-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8970-116">See Also</span></span>  
 [<span data-ttu-id="a8970-117">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8970-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="a8970-118">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="a8970-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
