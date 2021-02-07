---
description: 'Más información acerca de: ICLRMemoryNotificationCallback (interfaz)'
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
ms.openlocfilehash: 46e53cdf0b7f797b8945237d47fc3b521b08ddb7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689247"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="eb35f-103">ICLRMemoryNotificationCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="eb35f-103">ICLRMemoryNotificationCallback Interface</span></span>

<span data-ttu-id="eb35f-104">Permite al host notificar las condiciones de presión de memoria mediante un enfoque similar al de la función de Win32 `CreateMemoryResourceNotification` .</span><span class="sxs-lookup"><span data-stu-id="eb35f-104">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="eb35f-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="eb35f-105">Methods</span></span>  
  
|<span data-ttu-id="eb35f-106">Método</span><span class="sxs-lookup"><span data-stu-id="eb35f-106">Method</span></span>|<span data-ttu-id="eb35f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="eb35f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eb35f-108">Método OnMemoryNotification</span><span class="sxs-lookup"><span data-stu-id="eb35f-108">OnMemoryNotification Method</span></span>](iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="eb35f-109">Notifica al Common Language Runtime (CLR) la carga de memoria en el equipo.</span><span class="sxs-lookup"><span data-stu-id="eb35f-109">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb35f-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="eb35f-110">Remarks</span></span>  

 <span data-ttu-id="eb35f-111">El host usa la `ICLRMemoryNotificationCallback` interfaz para solicitar que los recursos de memoria de CLR liberen.</span><span class="sxs-lookup"><span data-stu-id="eb35f-111">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb35f-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eb35f-112">Requirements</span></span>  

 <span data-ttu-id="eb35f-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb35f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb35f-114">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="eb35f-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eb35f-115">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="eb35f-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eb35f-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb35f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb35f-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb35f-117">See also</span></span>

- [<span data-ttu-id="eb35f-118">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="eb35f-118">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="eb35f-119">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="eb35f-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
