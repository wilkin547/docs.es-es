---
description: 'Más información acerca de: interfaz Iclrgcmanager2 ('
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
ms.openlocfilehash: 455b3a99d10fa43bf325e9f7075d255dd55ae38b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789962"
---
# <a name="iclrgcmanager2-interface"></a><span data-ttu-id="66d2b-103">ICLRGCManager2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="66d2b-103">ICLRGCManager2 Interface</span></span>

<span data-ttu-id="66d2b-104">Proporciona métodos que permiten a un host interactuar con el sistema de recolección de elementos no utilizados del Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="66d2b-104">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="66d2b-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="66d2b-105">Methods</span></span>  
  
|<span data-ttu-id="66d2b-106">Método</span><span class="sxs-lookup"><span data-stu-id="66d2b-106">Method</span></span>|<span data-ttu-id="66d2b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="66d2b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="66d2b-108">SetGCStartupLimitsEx (Método)</span><span class="sxs-lookup"><span data-stu-id="66d2b-108">SetGCStartupLimitsEx Method</span></span>](iclrgcmanager2-setgcstartuplimitsex-method.md)|<span data-ttu-id="66d2b-109">Establece el tamaño de un segmento de recolección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="66d2b-109">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span> <span data-ttu-id="66d2b-110">Habilita la generación 0 y los tamaños de segmento mayores que `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="66d2b-110">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66d2b-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="66d2b-111">Remarks</span></span>  

 <span data-ttu-id="66d2b-112">Esta interfaz hereda de la [interfaz ICLRGCManager](iclrgcmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="66d2b-112">This interface inherits from the [ICLRGCManager Interface](iclrgcmanager-interface.md).</span></span>  
  
 <span data-ttu-id="66d2b-113">El Common Language Runtime (CLR) implementa su mecanismo de recolección de elementos no utilizados con el <xref:System.GC> tipo administrado.</span><span class="sxs-lookup"><span data-stu-id="66d2b-113">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="66d2b-114">Para obtener más información sobre el sistema de recolección de elementos no utilizados, consulte recolección de [elementos no utilizados](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="66d2b-114">For more information about the garbage collection system, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66d2b-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="66d2b-115">Requirements</span></span>  

 <span data-ttu-id="66d2b-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66d2b-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66d2b-117">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="66d2b-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="66d2b-118">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="66d2b-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="66d2b-119">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66d2b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66d2b-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="66d2b-120">See also</span></span>

- [<span data-ttu-id="66d2b-121">Administración automática de la memoria</span><span class="sxs-lookup"><span data-stu-id="66d2b-121">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="66d2b-122">COR_GC_STATS (Estructura)</span><span class="sxs-lookup"><span data-stu-id="66d2b-122">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="66d2b-123">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="66d2b-123">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="66d2b-124">Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5</span><span class="sxs-lookup"><span data-stu-id="66d2b-124">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="66d2b-125">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="66d2b-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="66d2b-126">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="66d2b-126">Hosting</span></span>](index.md)
