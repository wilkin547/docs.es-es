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
ms.openlocfilehash: 76d1071ddde1509f16fd786afa4c05c05224d051
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966212"
---
# <a name="iclrgcmanager-interface"></a><span data-ttu-id="cf7d6-102">ICLRGCManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cf7d6-102">ICLRGCManager Interface</span></span>
<span data-ttu-id="cf7d6-103">Proporciona métodos que permiten a un host interactuar con el sistema de recolección de elementos no utilizados del Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="cf7d6-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cf7d6-104">A partir del .NET Framework 4,5, puede usar el método [iclrgcmanager2 (:: setgcstartuplimitsex (](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) para establecer el tamaño de un segmento de recolección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recolección de elementos no utilizados en valores mayores que el `DWORD`límite impuesto por el método [setgcstartuplimits (](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) .</span><span class="sxs-lookup"><span data-stu-id="cf7d6-104">Starting with the .NET Framework 4.5, you can use the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cf7d6-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="cf7d6-105">Methods</span></span>  
  
|<span data-ttu-id="cf7d6-106">Método</span><span class="sxs-lookup"><span data-stu-id="cf7d6-106">Method</span></span>|<span data-ttu-id="cf7d6-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="cf7d6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cf7d6-108">Collect (método)</span><span class="sxs-lookup"><span data-stu-id="cf7d6-108">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-collect-method.md)|<span data-ttu-id="cf7d6-109">Fuerza una recolección de elementos no utilizados para la generación especificada.</span><span class="sxs-lookup"><span data-stu-id="cf7d6-109">Forces a garbage collection for the specified generation.</span></span>|  
|[<span data-ttu-id="cf7d6-110">GetStats (método)</span><span class="sxs-lookup"><span data-stu-id="cf7d6-110">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)|<span data-ttu-id="cf7d6-111">Obtiene un conjunto de estadísticas actuales sobre el sistema de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="cf7d6-111">Gets a set of current statistics about the garbage collection system.</span></span>|  
|[<span data-ttu-id="cf7d6-112">SetGCStartupLimits (método)</span><span class="sxs-lookup"><span data-stu-id="cf7d6-112">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)|<span data-ttu-id="cf7d6-113">Establece el tamaño de un segmento de recolección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="cf7d6-113">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf7d6-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cf7d6-114">Remarks</span></span>  
 <span data-ttu-id="cf7d6-115">El Common Language Runtime (CLR) implementa su mecanismo de recolección de elementos no utilizados <xref:System.GC> con el tipo administrado.</span><span class="sxs-lookup"><span data-stu-id="cf7d6-115">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="cf7d6-116">Para obtener más información sobre el sistema de recolección de elementos no utilizados, consulte recolección de [elementos no utilizados](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="cf7d6-116">For more information about the garbage collection system, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf7d6-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cf7d6-117">Requirements</span></span>  
 <span data-ttu-id="cf7d6-118">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf7d6-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf7d6-119">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cf7d6-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cf7d6-120">**Biblioteca** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cf7d6-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cf7d6-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf7d6-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf7d6-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf7d6-122">See also</span></span>

- [<span data-ttu-id="cf7d6-123">Administración automática de la memoria</span><span class="sxs-lookup"><span data-stu-id="cf7d6-123">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="cf7d6-124">COR_GC_STATS (estructura)</span><span class="sxs-lookup"><span data-stu-id="cf7d6-124">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="cf7d6-125">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cf7d6-125">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="cf7d6-126">Interfaces de hospedaje de CLR</span><span class="sxs-lookup"><span data-stu-id="cf7d6-126">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="cf7d6-127">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="cf7d6-127">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="cf7d6-128">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="cf7d6-128">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
