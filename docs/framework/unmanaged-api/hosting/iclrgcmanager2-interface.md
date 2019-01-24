---
title: ICLRGCManager2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRGCManager2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager2
helpviewer_keywords:
- ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 4b5ffd7b-9ad7-41cd-9bba-34030ae3da7e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9897526882a8ae53410a7744f78c558dfa6981e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54708589"
---
# <a name="iclrgcmanager2-interface"></a><span data-ttu-id="ed3d7-102">ICLRGCManager2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ed3d7-102">ICLRGCManager2 Interface</span></span>
<span data-ttu-id="ed3d7-103">Proporciona métodos que permiten a un host interactuar con el sistema de recopilación de elementos no utilizados de common language runtime.</span><span class="sxs-lookup"><span data-stu-id="ed3d7-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ed3d7-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ed3d7-104">Methods</span></span>  
  
|<span data-ttu-id="ed3d7-105">Método</span><span class="sxs-lookup"><span data-stu-id="ed3d7-105">Method</span></span>|<span data-ttu-id="ed3d7-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed3d7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ed3d7-107">SetGCStartupLimitsEx (método)</span><span class="sxs-lookup"><span data-stu-id="ed3d7-107">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)|<span data-ttu-id="ed3d7-108">Establece el tamaño de un segmento de la colección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ed3d7-108">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span> <span data-ttu-id="ed3d7-109">Habilita la generación 0 y el tamaño de segmento mayor que `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="ed3d7-109">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed3d7-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ed3d7-110">Remarks</span></span>  
 <span data-ttu-id="ed3d7-111">Esta interfaz se hereda de la [ICLRGCManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="ed3d7-111">This interface inherits from the [ICLRGCManager Interface](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
 <span data-ttu-id="ed3d7-112">Common language runtime (CLR) implementa su mecanismo de recopilación de elementos no utilizados con los recursos administrados <xref:System.GC> tipo.</span><span class="sxs-lookup"><span data-stu-id="ed3d7-112">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="ed3d7-113">Para obtener más información sobre el sistema de recopilación de elementos no utilizados, vea [recolección](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="ed3d7-113">For more information about the garbage collection system, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed3d7-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ed3d7-114">Requirements</span></span>  
 <span data-ttu-id="ed3d7-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed3d7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed3d7-116">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ed3d7-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ed3d7-117">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ed3d7-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ed3d7-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed3d7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed3d7-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed3d7-119">See also</span></span>
- [<span data-ttu-id="ed3d7-120">Administración automática de la memoria</span><span class="sxs-lookup"><span data-stu-id="ed3d7-120">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="ed3d7-121">COR_GC_STATS (estructura)</span><span class="sxs-lookup"><span data-stu-id="ed3d7-121">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="ed3d7-122">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ed3d7-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="ed3d7-123">Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5</span><span class="sxs-lookup"><span data-stu-id="ed3d7-123">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="ed3d7-124">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="ed3d7-124">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="ed3d7-125">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="ed3d7-125">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
