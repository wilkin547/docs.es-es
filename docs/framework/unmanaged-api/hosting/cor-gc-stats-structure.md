---
title: COR_GC_STATS (Estructura)
ms.date: 03/30/2017
api_name:
- COR_GC_STATS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_STATS
helpviewer_keywords:
- COR_GC_STATS structure [.NET Framework hosting]
ms.assetid: 8d4ff73e-739b-40f6-9349-359fbc99c2f9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d335a62545f06a66d4044b59aa9499d3f7ede515
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208480"
---
# <a name="corgcstats-structure"></a><span data-ttu-id="04adf-102">COR_GC_STATS (Estructura)</span><span class="sxs-lookup"><span data-stu-id="04adf-102">COR_GC_STATS Structure</span></span>
<span data-ttu-id="04adf-103">Proporciona estadísticas sobre el mecanismo de recopilación de elementos no utilizados de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="04adf-103">Provides statistics about the garbage collection mechanism of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04adf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04adf-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="04adf-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="04adf-105">Members</span></span>  
  
|<span data-ttu-id="04adf-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="04adf-106">Member</span></span>|<span data-ttu-id="04adf-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="04adf-107">Description</span></span>|  
|------------|-----------------|  
|`Flags`|<span data-ttu-id="04adf-108">Indica qué valores de campo deben ser calcula y devuelve.</span><span class="sxs-lookup"><span data-stu-id="04adf-108">Indicates which field values should be calculated and returned.</span></span>|  
|`ExplicitGCCount`|<span data-ttu-id="04adf-109">Indica el número de recolecciones forzadas por solicitud externa.</span><span class="sxs-lookup"><span data-stu-id="04adf-109">Indicates the number of garbage collections that were forced by external request.</span></span>|  
|`GenCollectionsTaken`|<span data-ttu-id="04adf-110">Indica el número de recolecciones realizadas para cada generación.</span><span class="sxs-lookup"><span data-stu-id="04adf-110">Indicates the number of garbage collections performed for each generation.</span></span>|  
|`CommittedKBytes`|<span data-ttu-id="04adf-111">El número total de kilobytes confirmado en todos los montones.</span><span class="sxs-lookup"><span data-stu-id="04adf-111">The total number of kilobytes committed in all heaps.</span></span>|  
|`ReservedKBytes`|<span data-ttu-id="04adf-112">El número total de kilobytes reservados en todos los montones.</span><span class="sxs-lookup"><span data-stu-id="04adf-112">The total number of kilobytes reserved in all heaps.</span></span>|  
|`Gen0HeapSizeKBytes`|<span data-ttu-id="04adf-113">El tamaño, en kilobytes, del montón de generación de cero.</span><span class="sxs-lookup"><span data-stu-id="04adf-113">The size, in kilobytes, of the generation-zero heap.</span></span>|  
|`Gen1HeapSizeKBytes`|<span data-ttu-id="04adf-114">El tamaño, en kilobytes, del montón de generación 1.</span><span class="sxs-lookup"><span data-stu-id="04adf-114">The size, in kilobytes, of the generation-one heap.</span></span>|  
|`Gen2HeapSizeKBytes`|<span data-ttu-id="04adf-115">El tamaño, en kilobytes, del montón de generación de dos.</span><span class="sxs-lookup"><span data-stu-id="04adf-115">The size, in kilobytes, of the generation-two heap.</span></span>|  
|`LargeObjectHeapSizeKBytes`|<span data-ttu-id="04adf-116">El tamaño, en kilobytes, del montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="04adf-116">The size, in kilobytes, of the large object heap.</span></span>|  
|`KBytesPromotedFromGen0`|<span data-ttu-id="04adf-117">El tamaño, en kilobytes, de los objetos que se promueven de generación 0 a generación uno.</span><span class="sxs-lookup"><span data-stu-id="04adf-117">The size, in kilobytes, of the objects promoted from generation zero to generation one.</span></span>|  
|`KBytesPromotedFromGen1`|<span data-ttu-id="04adf-118">El tamaño, en kilobytes, de los objetos que se promueven de generación 1 a la generación 2.</span><span class="sxs-lookup"><span data-stu-id="04adf-118">The size, in kilobytes, of the objects promoted from generation one to generation two.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04adf-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="04adf-119">Remarks</span></span>  
 <span data-ttu-id="04adf-120">El [ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) método requiere el `Flags` campo de la `COR_GC_STATS` estructura debe establecerse en uno o más valores de la [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeración para especificar qué las estadísticas que se van a establecer.</span><span class="sxs-lookup"><span data-stu-id="04adf-120">The [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method requires the `Flags` field of the `COR_GC_STATS` structure to be set to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics are to be set.</span></span>  
  
 <span data-ttu-id="04adf-121">En la tabla siguiente asigna las estadísticas proporcionadas por esta estructura a los dos [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) valores de enumeración, `COR_GC_COUNTS` y `COR_GC_MEMORYUSAGE`.</span><span class="sxs-lookup"><span data-stu-id="04adf-121">The following table maps the statistics provided by this structure to the two [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration values, `COR_GC_COUNTS` and `COR_GC_MEMORYUSAGE`.</span></span>  
  
|<span data-ttu-id="04adf-122">Especifica COR_GC_COUNTS</span><span class="sxs-lookup"><span data-stu-id="04adf-122">Specified by COR_GC_COUNTS</span></span>|<span data-ttu-id="04adf-123">Especifica COR_GC_MEMORYUSAGE</span><span class="sxs-lookup"><span data-stu-id="04adf-123">Specified by COR_GC_MEMORYUSAGE</span></span>|  
|----------------------------------|---------------------------------------|  
|`ExplicitGCCount`<br /><br /> `GenCollectionsTaken`|`CommittedKBytes`<br /><br /> `ReservedKBytes`<br /><br /> `Gen0HeapSizeKBytes`<br /><br /> `Gen1HeapSizeKBytes`<br /><br /> `Gen2HeapSizeKBytes`<br /><br /> `LargeObjectHeapSizeKBytes`<br /><br /> `KBytesPromotedFromGen0`<br /><br /> `KBytesPromotedFromGen1`|  
  
 <span data-ttu-id="04adf-124">Un ejemplo de uso es como sigue:</span><span class="sxs-lookup"><span data-stu-id="04adf-124">An example of the usage is as follows:</span></span>  
  
```  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="04adf-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="04adf-125">Requirements</span></span>  
 <span data-ttu-id="04adf-126">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04adf-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04adf-127">**Encabezado**: GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="04adf-127">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="04adf-128">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="04adf-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="04adf-129">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="04adf-129">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="04adf-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="04adf-130">See also</span></span>

- [<span data-ttu-id="04adf-131">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="04adf-131">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="04adf-132">Automatic Memory Management</span><span class="sxs-lookup"><span data-stu-id="04adf-132">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="04adf-133">recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="04adf-133">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
