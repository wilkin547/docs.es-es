---
title: COR_GC_STATS (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_GC_STATS
api_location: mscoree.dll
api_type: COM
f1_keywords: COR_GC_STATS
helpviewer_keywords: COR_GC_STATS structure [.NET Framework hosting]
ms.assetid: 8d4ff73e-739b-40f6-9349-359fbc99c2f9
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 02a775be4976760b354a492e7252a67ef04eace9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="corgcstats-structure"></a><span data-ttu-id="5209e-102">COR_GC_STATS (Estructura)</span><span class="sxs-lookup"><span data-stu-id="5209e-102">COR_GC_STATS Structure</span></span>
<span data-ttu-id="5209e-103">Proporciona estadísticas sobre el mecanismo de recopilación de elementos no utilizados de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="5209e-103">Provides statistics about the garbage collection mechanism of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5209e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5209e-104">Syntax</span></span>  
  
```  
typedef struct _COR_GC_STATS {  
    ULONG   Flags;   
    SIZE_T  ExplicitGCCount;  
    SIZE_T  GenCollectionsTaken[3];  
    SIZE_T  CommittedKBytes;   
    SIZE_T  ReservedKBytes;  
    SIZE_T  Gen0HeapSizeKBytes;  
    SIZE_T  Gen1HeapSizeKBytes;  
    SIZE_T  Gen2HeapSizeKBytes;  
    SIZE_T  LargeObjectHeapSizeKBytes;  
    SIZE_T  KBytesPromotedFromGen0;  
    SIZE_T  KBytesPromotedFromGen1;  
} COR_GC_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="5209e-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="5209e-105">Members</span></span>  
  
|<span data-ttu-id="5209e-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="5209e-106">Member</span></span>|<span data-ttu-id="5209e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5209e-107">Description</span></span>|  
|------------|-----------------|  
|`Flags`|<span data-ttu-id="5209e-108">Indica qué valores de campo deben ser calcula y devuelve.</span><span class="sxs-lookup"><span data-stu-id="5209e-108">Indicates which field values should be calculated and returned.</span></span>|  
|`ExplicitGCCount`|<span data-ttu-id="5209e-109">Indica el número de recolecciones de elementos no utilizados forzadas por solicitud externa.</span><span class="sxs-lookup"><span data-stu-id="5209e-109">Indicates the number of garbage collections that were forced by external request.</span></span>|  
|`GenCollectionsTaken`|<span data-ttu-id="5209e-110">Indica el número de recolecciones de elementos no utilizados lleva a cabo para cada generación.</span><span class="sxs-lookup"><span data-stu-id="5209e-110">Indicates the number of garbage collections performed for each generation.</span></span>|  
|`CommittedKBytes`|<span data-ttu-id="5209e-111">El número total de kilobytes confirmados en todos los montones.</span><span class="sxs-lookup"><span data-stu-id="5209e-111">The total number of kilobytes committed in all heaps.</span></span>|  
|`ReservedKBytes`|<span data-ttu-id="5209e-112">El número total de kilobytes reservados en todos los montones.</span><span class="sxs-lookup"><span data-stu-id="5209e-112">The total number of kilobytes reserved in all heaps.</span></span>|  
|`Gen0HeapSizeKBytes`|<span data-ttu-id="5209e-113">El tamaño, en kilobytes, del montón de generación de cero.</span><span class="sxs-lookup"><span data-stu-id="5209e-113">The size, in kilobytes, of the generation-zero heap.</span></span>|  
|`Gen1HeapSizeKBytes`|<span data-ttu-id="5209e-114">El tamaño, en kilobytes, del montón de generación 1.</span><span class="sxs-lookup"><span data-stu-id="5209e-114">The size, in kilobytes, of the generation-one heap.</span></span>|  
|`Gen2HeapSizeKBytes`|<span data-ttu-id="5209e-115">El tamaño, en kilobytes, del montón de generación de dos.</span><span class="sxs-lookup"><span data-stu-id="5209e-115">The size, in kilobytes, of the generation-two heap.</span></span>|  
|`LargeObjectHeapSizeKBytes`|<span data-ttu-id="5209e-116">El tamaño, en kilobytes, del montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="5209e-116">The size, in kilobytes, of the large object heap.</span></span>|  
|`KBytesPromotedFromGen0`|<span data-ttu-id="5209e-117">El tamaño, en kilobytes, de los objetos que se promocionan de la generación 0 a la generación 1.</span><span class="sxs-lookup"><span data-stu-id="5209e-117">The size, in kilobytes, of the objects promoted from generation zero to generation one.</span></span>|  
|`KBytesPromotedFromGen1`|<span data-ttu-id="5209e-118">El tamaño, en kilobytes, de los objetos que se promocionan de la generación 1 a generación 2.</span><span class="sxs-lookup"><span data-stu-id="5209e-118">The size, in kilobytes, of the objects promoted from generation one to generation two.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5209e-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5209e-119">Remarks</span></span>  
 <span data-ttu-id="5209e-120">El [ICLRGCManager:: GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) método requiere el `Flags` campo de la `COR_GC_STATS` estructura se establezca en uno o más valores de la [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeración para especificar qué las estadísticas que se van a establecer.</span><span class="sxs-lookup"><span data-stu-id="5209e-120">The [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method requires the `Flags` field of the `COR_GC_STATS` structure to be set to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics are to be set.</span></span>  
  
 <span data-ttu-id="5209e-121">La tabla siguiente asigna las estadísticas proporcionadas por esta estructura a los dos [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) valores de enumeración, `COR_GC_COUNTS` y `COR_GC_MEMORYUSAGE`.</span><span class="sxs-lookup"><span data-stu-id="5209e-121">The following table maps the statistics provided by this structure to the two [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration values, `COR_GC_COUNTS` and `COR_GC_MEMORYUSAGE`.</span></span>  
  
|<span data-ttu-id="5209e-122">Especifica COR_GC_COUNTS</span><span class="sxs-lookup"><span data-stu-id="5209e-122">Specified by COR_GC_COUNTS</span></span>|<span data-ttu-id="5209e-123">Especifica COR_GC_MEMORYUSAGE</span><span class="sxs-lookup"><span data-stu-id="5209e-123">Specified by COR_GC_MEMORYUSAGE</span></span>|  
|----------------------------------|---------------------------------------|  
|`ExplicitGCCount`<br /><br /> `GenCollectionsTaken`|`CommittedKBytes`<br /><br /> `ReservedKBytes`<br /><br /> `Gen0HeapSizeKBytes`<br /><br /> `Gen1HeapSizeKBytes`<br /><br /> `Gen2HeapSizeKBytes`<br /><br /> `LargeObjectHeapSizeKBytes`<br /><br /> `KBytesPromotedFromGen0`<br /><br /> `KBytesPromotedFromGen1`|  
  
 <span data-ttu-id="5209e-124">Un ejemplo del uso es como sigue:</span><span class="sxs-lookup"><span data-stu-id="5209e-124">An example of the usage is as follows:</span></span>  
  
```  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="5209e-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5209e-125">Requirements</span></span>  
 <span data-ttu-id="5209e-126">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5209e-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5209e-127">**Encabezado:** GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="5209e-127">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="5209e-128">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5209e-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5209e-129">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5209e-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5209e-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="5209e-130">See Also</span></span>  
 [<span data-ttu-id="5209e-131">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="5209e-131">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [<span data-ttu-id="5209e-132">Administración automática de la memoria</span><span class="sxs-lookup"><span data-stu-id="5209e-132">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="5209e-133">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="5209e-133">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
