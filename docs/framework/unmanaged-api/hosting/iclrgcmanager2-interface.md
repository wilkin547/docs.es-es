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
ms.openlocfilehash: 0f3ecc0d497eaee937647df47ba0956335a2fe41
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703949"
---
# <a name="iclrgcmanager2-interface"></a><span data-ttu-id="561bf-102">ICLRGCManager2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="561bf-102">ICLRGCManager2 Interface</span></span>
<span data-ttu-id="561bf-103">Proporciona métodos que permiten a un host interactuar con el sistema de recolección de elementos no utilizados del Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="561bf-103">Provides methods that allow a host to interact with the common language runtime's garbage collection system.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="561bf-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="561bf-104">Methods</span></span>  
  
|<span data-ttu-id="561bf-105">Método</span><span class="sxs-lookup"><span data-stu-id="561bf-105">Method</span></span>|<span data-ttu-id="561bf-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="561bf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="561bf-107">SetGCStartupLimitsEx (Método)</span><span class="sxs-lookup"><span data-stu-id="561bf-107">SetGCStartupLimitsEx Method</span></span>](iclrgcmanager2-setgcstartuplimitsex-method.md)|<span data-ttu-id="561bf-108">Establece el tamaño de un segmento de recolección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="561bf-108">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span> <span data-ttu-id="561bf-109">Habilita la generación 0 y los tamaños de segmento mayores que `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="561bf-109">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="561bf-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="561bf-110">Remarks</span></span>  
 <span data-ttu-id="561bf-111">Esta interfaz hereda de la [interfaz ICLRGCManager](iclrgcmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="561bf-111">This interface inherits from the [ICLRGCManager Interface](iclrgcmanager-interface.md).</span></span>  
  
 <span data-ttu-id="561bf-112">El Common Language Runtime (CLR) implementa su mecanismo de recolección de elementos no utilizados con el <xref:System.GC> tipo administrado.</span><span class="sxs-lookup"><span data-stu-id="561bf-112">The common language runtime (CLR) implements its garbage collection mechanism with the managed <xref:System.GC> type.</span></span> <span data-ttu-id="561bf-113">Para obtener más información sobre el sistema de recolección de elementos no utilizados, consulte recolección de [elementos no utilizados](../../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="561bf-113">For more information about the garbage collection system, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="561bf-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="561bf-114">Requirements</span></span>  
 <span data-ttu-id="561bf-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="561bf-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="561bf-116">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="561bf-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="561bf-117">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="561bf-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="561bf-118">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="561bf-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="561bf-119">Consulta también</span><span class="sxs-lookup"><span data-stu-id="561bf-119">See also</span></span>

- [<span data-ttu-id="561bf-120">Administración de memoria automática</span><span class="sxs-lookup"><span data-stu-id="561bf-120">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="561bf-121">COR_GC_STATS (Estructura)</span><span class="sxs-lookup"><span data-stu-id="561bf-121">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="561bf-122">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="561bf-122">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="561bf-123">Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5</span><span class="sxs-lookup"><span data-stu-id="561bf-123">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="561bf-124">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="561bf-124">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="561bf-125">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="561bf-125">Hosting</span></span>](index.md)
