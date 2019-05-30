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
ms.openlocfilehash: 6e284f94ad0dac9523bd6267e7bc1034a079503d
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/30/2019
ms.locfileid: "66380290"
---
# <a name="iclrgcmanager-interface"></a><span data-ttu-id="b7def-102">ICLRGCManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b7def-102">ICLRGCManager Interface</span></span>
<span data-ttu-id="b7def-103">Proporciona métodos que permiten a un host interactuar con el sistema de recopilación de elementos no utilizados de common language runtime.</span><span class="sxs-lookup"><span data-stu-id="b7def-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7def-104">A partir de .NET Framework 4.5, puede usar el [Iclrgcmanager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) método para establecer el tamaño de un segmento de la colección de elementos no utilizados y el tamaño máximo de la generación del sistema de recopilación de elementos no utilizados 0 a valores mayor que el `DWORD` límite impuesto por el [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="b7def-104">Starting with the .NET Framework 4.5, you can use the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b7def-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="b7def-105">Methods</span></span>  
  
|<span data-ttu-id="b7def-106">Método</span><span class="sxs-lookup"><span data-stu-id="b7def-106">Method</span></span>|<span data-ttu-id="b7def-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7def-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b7def-108">Collect (método)</span><span class="sxs-lookup"><span data-stu-id="b7def-108">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-collect-method.md)|<span data-ttu-id="b7def-109">Fuerza una recolección de elementos no utilizados para la generación especificada.</span><span class="sxs-lookup"><span data-stu-id="b7def-109">Forces a garbage collection for the specified generation.</span></span>|  
|[<span data-ttu-id="b7def-110">GetStats (método)</span><span class="sxs-lookup"><span data-stu-id="b7def-110">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)|<span data-ttu-id="b7def-111">Obtiene un conjunto de estadísticas actuales sobre el sistema de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b7def-111">Gets a set of current statistics about the garbage collection system.</span></span>|  
|[<span data-ttu-id="b7def-112">SetGCStartupLimits (método)</span><span class="sxs-lookup"><span data-stu-id="b7def-112">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)|<span data-ttu-id="b7def-113">Establece el tamaño de un segmento de la colección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b7def-113">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7def-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b7def-114">Remarks</span></span>  
 <span data-ttu-id="b7def-115">Common language runtime (CLR) implementa su mecanismo de recopilación de elementos no utilizados con los recursos administrados <xref:System.GC> tipo.</span><span class="sxs-lookup"><span data-stu-id="b7def-115">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="b7def-116">Para obtener más información sobre el sistema de recopilación de elementos no utilizados, vea [recolección](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="b7def-116">For more information about the garbage collection system, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7def-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7def-117">Requirements</span></span>  
 <span data-ttu-id="b7def-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7def-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7def-119">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b7def-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b7def-120">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b7def-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b7def-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7def-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7def-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7def-122">See also</span></span>

- [<span data-ttu-id="b7def-123">Administración automática de la memoria</span><span class="sxs-lookup"><span data-stu-id="b7def-123">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="b7def-124">COR_GC_STATS (estructura)</span><span class="sxs-lookup"><span data-stu-id="b7def-124">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="b7def-125">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b7def-125">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="b7def-126">Interfaces de hospedaje de CLR</span><span class="sxs-lookup"><span data-stu-id="b7def-126">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="b7def-127">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="b7def-127">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="b7def-128">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="b7def-128">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
