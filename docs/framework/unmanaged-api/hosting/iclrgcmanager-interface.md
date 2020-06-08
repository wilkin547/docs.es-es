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
ms.openlocfilehash: f878e2f1f86bc42c0ff5abada8d7df4feb9ed228
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504204"
---
# <a name="iclrgcmanager-interface"></a><span data-ttu-id="8a3fe-102">ICLRGCManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8a3fe-102">ICLRGCManager Interface</span></span>
<span data-ttu-id="8a3fe-103">Proporciona métodos que permiten a un host interactuar con el sistema de recolección de elementos no utilizados del Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="8a3fe-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8a3fe-104">A partir del .NET Framework 4,5, puede usar el método [iclrgcmanager2 (:: setgcstartuplimitsex (](iclrgcmanager2-setgcstartuplimitsex-method.md) para establecer el tamaño de un segmento de recolección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recolección de elementos no utilizados en valores mayores que el `DWORD` límite impuesto por el método [setgcstartuplimits (](iclrgcmanager-setgcstartuplimits-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8a3fe-104">Starting with the .NET Framework 4.5, you can use the [ICLRGCManager2::SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](iclrgcmanager-setgcstartuplimits-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8a3fe-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="8a3fe-105">Methods</span></span>  
  
|<span data-ttu-id="8a3fe-106">Método</span><span class="sxs-lookup"><span data-stu-id="8a3fe-106">Method</span></span>|<span data-ttu-id="8a3fe-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a3fe-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8a3fe-108">Método Collect</span><span class="sxs-lookup"><span data-stu-id="8a3fe-108">Collect Method</span></span>](iclrgcmanager-collect-method.md)|<span data-ttu-id="8a3fe-109">Fuerza una recolección de elementos no utilizados para la generación especificada.</span><span class="sxs-lookup"><span data-stu-id="8a3fe-109">Forces a garbage collection for the specified generation.</span></span>|  
|[<span data-ttu-id="8a3fe-110">GetStats (Método)</span><span class="sxs-lookup"><span data-stu-id="8a3fe-110">GetStats Method</span></span>](iclrgcmanager-getstats-method.md)|<span data-ttu-id="8a3fe-111">Obtiene un conjunto de estadísticas actuales sobre el sistema de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="8a3fe-111">Gets a set of current statistics about the garbage collection system.</span></span>|  
|[<span data-ttu-id="8a3fe-112">Método SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="8a3fe-112">SetGCStartupLimits Method</span></span>](iclrgcmanager-setgcstartuplimits-method.md)|<span data-ttu-id="8a3fe-113">Establece el tamaño de un segmento de recolección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="8a3fe-113">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a3fe-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8a3fe-114">Remarks</span></span>  
 <span data-ttu-id="8a3fe-115">El Common Language Runtime (CLR) implementa su mecanismo de recolección de elementos no utilizados con el <xref:System.GC> tipo administrado.</span><span class="sxs-lookup"><span data-stu-id="8a3fe-115">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="8a3fe-116">Para obtener más información sobre el sistema de recolección de elementos no utilizados, consulte recolección de [elementos no utilizados](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="8a3fe-116">For more information about the garbage collection system, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a3fe-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8a3fe-117">Requirements</span></span>  
 <span data-ttu-id="8a3fe-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a3fe-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a3fe-119">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8a3fe-119">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8a3fe-120">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8a3fe-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8a3fe-121">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a3fe-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a3fe-122">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="8a3fe-122">See also</span></span>

- [<span data-ttu-id="8a3fe-123">Administración de memoria automática</span><span class="sxs-lookup"><span data-stu-id="8a3fe-123">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="8a3fe-124">COR_GC_STATS (Estructura)</span><span class="sxs-lookup"><span data-stu-id="8a3fe-124">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="8a3fe-125">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8a3fe-125">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="8a3fe-126">Interfaces de hospedaje de CLR</span><span class="sxs-lookup"><span data-stu-id="8a3fe-126">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="8a3fe-127">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="8a3fe-127">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="8a3fe-128">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="8a3fe-128">Hosting</span></span>](index.md)
