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
ms.openlocfilehash: 52fc21044d345998ad72c045cdf5e80a8a03a38e
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703805"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="537df-102">ICLRMemoryNotificationCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="537df-102">ICLRMemoryNotificationCallback Interface</span></span>
<span data-ttu-id="537df-103">Permite al host notificar las condiciones de presión de memoria mediante un enfoque similar al de la función de Win32 `CreateMemoryResourceNotification` .</span><span class="sxs-lookup"><span data-stu-id="537df-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="537df-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="537df-104">Methods</span></span>  
  
|<span data-ttu-id="537df-105">Método</span><span class="sxs-lookup"><span data-stu-id="537df-105">Method</span></span>|<span data-ttu-id="537df-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="537df-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="537df-107">Método OnMemoryNotification</span><span class="sxs-lookup"><span data-stu-id="537df-107">OnMemoryNotification Method</span></span>](iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="537df-108">Notifica al Common Language Runtime (CLR) la carga de memoria en el equipo.</span><span class="sxs-lookup"><span data-stu-id="537df-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="537df-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="537df-109">Remarks</span></span>  
 <span data-ttu-id="537df-110">El host usa la `ICLRMemoryNotificationCallback` interfaz para solicitar que los recursos de memoria de CLR liberen.</span><span class="sxs-lookup"><span data-stu-id="537df-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="537df-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="537df-111">Requirements</span></span>  
 <span data-ttu-id="537df-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="537df-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="537df-113">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="537df-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="537df-114">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="537df-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="537df-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="537df-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="537df-116">Consulta también</span><span class="sxs-lookup"><span data-stu-id="537df-116">See also</span></span>

- [<span data-ttu-id="537df-117">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="537df-117">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="537df-118">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="537df-118">Hosting Interfaces</span></span>](hosting-interfaces.md)
