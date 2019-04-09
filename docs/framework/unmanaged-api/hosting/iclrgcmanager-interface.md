---
title: ICLRGCManager (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager
helpviewer_keywords:
- ICLRGCManager interface [.NET Framework hosting]
ms.assetid: fb511c9b-3fe4-41b0-822a-6ba4a079d1f5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b9519f7c2df5cf078bac6be038275527d7741edb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59152170"
---
# <a name="iclrgcmanager-interface"></a><span data-ttu-id="ea8ed-102">ICLRGCManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ea8ed-102">ICLRGCManager Interface</span></span>
<span data-ttu-id="ea8ed-103">Proporciona métodos que permiten a un host interactuar con el sistema de recopilación de elementos no utilizados de common language runtime.</span><span class="sxs-lookup"><span data-stu-id="ea8ed-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea8ed-104">A partir de la [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], puede usar el [Iclrgcmanager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) método para establecer el tamaño de un segmento de la colección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recopilación de elementos no utilizados en los valores mayor que el `DWORD` límite impuesto por el [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="ea8ed-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can use the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ea8ed-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="ea8ed-105">Methods</span></span>  
  
|<span data-ttu-id="ea8ed-106">Método</span><span class="sxs-lookup"><span data-stu-id="ea8ed-106">Method</span></span>|<span data-ttu-id="ea8ed-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ea8ed-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ea8ed-108">Método Collect</span><span class="sxs-lookup"><span data-stu-id="ea8ed-108">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-collect-method.md)|<span data-ttu-id="ea8ed-109">Fuerza una recolección de elementos no utilizados para la generación especificada.</span><span class="sxs-lookup"><span data-stu-id="ea8ed-109">Forces a garbage collection for the specified generation.</span></span>|  
|[<span data-ttu-id="ea8ed-110">Método GetStats</span><span class="sxs-lookup"><span data-stu-id="ea8ed-110">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)|<span data-ttu-id="ea8ed-111">Obtiene un conjunto de estadísticas actuales sobre el sistema de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ea8ed-111">Gets a set of current statistics about the garbage collection system.</span></span>|  
|[<span data-ttu-id="ea8ed-112">Método SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="ea8ed-112">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)|<span data-ttu-id="ea8ed-113">Establece el tamaño de un segmento de la colección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ea8ed-113">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea8ed-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ea8ed-114">Remarks</span></span>  
 <span data-ttu-id="ea8ed-115">Common language runtime (CLR) implementa su mecanismo de recopilación de elementos no utilizados con los recursos administrados <xref:System.GC> tipo.</span><span class="sxs-lookup"><span data-stu-id="ea8ed-115">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="ea8ed-116">Para obtener más información sobre el sistema de recopilación de elementos no utilizados, vea [recolección](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="ea8ed-116">For more information about the garbage collection system, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea8ed-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ea8ed-117">Requirements</span></span>  
 <span data-ttu-id="ea8ed-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea8ed-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea8ed-119">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ea8ed-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ea8ed-120">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ea8ed-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="ea8ed-121">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ea8ed-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ea8ed-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea8ed-122">See also</span></span>

- [<span data-ttu-id="ea8ed-123">Automatic Memory Management</span><span class="sxs-lookup"><span data-stu-id="ea8ed-123">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="ea8ed-124">COR_GC_STATS (Estructura)</span><span class="sxs-lookup"><span data-stu-id="ea8ed-124">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="ea8ed-125">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ea8ed-125">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="ea8ed-126">Interfaces de hospedaje de CLR</span><span class="sxs-lookup"><span data-stu-id="ea8ed-126">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="ea8ed-127">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="ea8ed-127">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="ea8ed-128">Hospedaje</span><span class="sxs-lookup"><span data-stu-id="ea8ed-128">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
