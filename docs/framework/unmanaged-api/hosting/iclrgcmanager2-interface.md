---
title: ICLRGCManager2 (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager2
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager2
helpviewer_keywords: ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 4b5ffd7b-9ad7-41cd-9bba-34030ae3da7e
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4a8b51cf4297c1ccadbef8730c06148263d310e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrgcmanager2-interface"></a><span data-ttu-id="c1ed0-102">ICLRGCManager2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c1ed0-102">ICLRGCManager2 Interface</span></span>
<span data-ttu-id="c1ed0-103">Proporciona métodos que permiten a un host interactuar con el sistema de recopilación de elementos no utilizados de common language runtime.</span><span class="sxs-lookup"><span data-stu-id="c1ed0-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c1ed0-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c1ed0-104">Methods</span></span>  
  
|<span data-ttu-id="c1ed0-105">Método</span><span class="sxs-lookup"><span data-stu-id="c1ed0-105">Method</span></span>|<span data-ttu-id="c1ed0-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1ed0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c1ed0-107">SetGCStartupLimitsEx (método)</span><span class="sxs-lookup"><span data-stu-id="c1ed0-107">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)|<span data-ttu-id="c1ed0-108">Establece el tamaño de un segmento de la colección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="c1ed0-108">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span> <span data-ttu-id="c1ed0-109">Permite la generación 0 y tamaño de segmento mayor que `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="c1ed0-109">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1ed0-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c1ed0-110">Remarks</span></span>  
 <span data-ttu-id="c1ed0-111">Esta interfaz se hereda de la [ICLRGCManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="c1ed0-111">This interface inherits from the [ICLRGCManager Interface](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
 <span data-ttu-id="c1ed0-112">Common language runtime (CLR) implementa su mecanismo de recopilación de elementos no utilizados con los recursos administrados <xref:System.GC> tipo.</span><span class="sxs-lookup"><span data-stu-id="c1ed0-112">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="c1ed0-113">Para obtener más información sobre el sistema de recopilación de elementos no utilizados, vea [recolección](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="c1ed0-113">For more information about the garbage collection system, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1ed0-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c1ed0-114">Requirements</span></span>  
 <span data-ttu-id="c1ed0-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1ed0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1ed0-116">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c1ed0-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c1ed0-117">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c1ed0-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c1ed0-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1ed0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1ed0-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1ed0-119">See Also</span></span>  
 [<span data-ttu-id="c1ed0-120">Administración automática de la memoria</span><span class="sxs-lookup"><span data-stu-id="c1ed0-120">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="c1ed0-121">COR_GC_STATS (estructura)</span><span class="sxs-lookup"><span data-stu-id="c1ed0-121">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [<span data-ttu-id="c1ed0-122">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c1ed0-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="c1ed0-123">Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5</span><span class="sxs-lookup"><span data-stu-id="c1ed0-123">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 [<span data-ttu-id="c1ed0-124">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="c1ed0-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="c1ed0-125">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="c1ed0-125">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
