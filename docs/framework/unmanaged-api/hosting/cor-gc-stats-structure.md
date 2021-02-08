---
description: 'Más información acerca de: estructura de COR_GC_STATS'
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
ms.openlocfilehash: 9b1002f462fb9b447e521cd1b3e5c78297eefc04
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799814"
---
# <a name="cor_gc_stats-structure"></a><span data-ttu-id="536d2-103">COR_GC_STATS (Estructura)</span><span class="sxs-lookup"><span data-stu-id="536d2-103">COR_GC_STATS Structure</span></span>

<span data-ttu-id="536d2-104">Proporciona estadísticas sobre el mecanismo de recolección de elementos no utilizados del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="536d2-104">Provides statistics about the garbage collection mechanism of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="536d2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="536d2-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="536d2-106">Members</span><span class="sxs-lookup"><span data-stu-id="536d2-106">Members</span></span>  
  
|<span data-ttu-id="536d2-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="536d2-107">Member</span></span>|<span data-ttu-id="536d2-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="536d2-108">Description</span></span>|  
|------------|-----------------|  
|`Flags`|<span data-ttu-id="536d2-109">Indica qué valores de campo deben calcularse y devolverse.</span><span class="sxs-lookup"><span data-stu-id="536d2-109">Indicates which field values should be calculated and returned.</span></span>|  
|`ExplicitGCCount`|<span data-ttu-id="536d2-110">Indica el número de recolecciones de elementos no utilizados forzadas por la solicitud externa.</span><span class="sxs-lookup"><span data-stu-id="536d2-110">Indicates the number of garbage collections that were forced by external request.</span></span>|  
|`GenCollectionsTaken`|<span data-ttu-id="536d2-111">Indica el número de recolecciones de elementos no utilizados realizadas para cada generación.</span><span class="sxs-lookup"><span data-stu-id="536d2-111">Indicates the number of garbage collections performed for each generation.</span></span>|  
|`CommittedKBytes`|<span data-ttu-id="536d2-112">Número total de kilobytes confirmados en todos los montones.</span><span class="sxs-lookup"><span data-stu-id="536d2-112">The total number of kilobytes committed in all heaps.</span></span>|  
|`ReservedKBytes`|<span data-ttu-id="536d2-113">Número total de kilobytes reservados en todos los montones.</span><span class="sxs-lookup"><span data-stu-id="536d2-113">The total number of kilobytes reserved in all heaps.</span></span>|  
|`Gen0HeapSizeKBytes`|<span data-ttu-id="536d2-114">Tamaño, en kilobytes, del montón de generación cero.</span><span class="sxs-lookup"><span data-stu-id="536d2-114">The size, in kilobytes, of the generation-zero heap.</span></span>|  
|`Gen1HeapSizeKBytes`|<span data-ttu-id="536d2-115">Tamaño, en kilobytes, del montón de generación uno.</span><span class="sxs-lookup"><span data-stu-id="536d2-115">The size, in kilobytes, of the generation-one heap.</span></span>|  
|`Gen2HeapSizeKBytes`|<span data-ttu-id="536d2-116">Tamaño, en kilobytes, del montón de generación 2.</span><span class="sxs-lookup"><span data-stu-id="536d2-116">The size, in kilobytes, of the generation-two heap.</span></span>|  
|`LargeObjectHeapSizeKBytes`|<span data-ttu-id="536d2-117">Tamaño, en kilobytes, del montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="536d2-117">The size, in kilobytes, of the large object heap.</span></span>|  
|`KBytesPromotedFromGen0`|<span data-ttu-id="536d2-118">Tamaño, en kilobytes, de los objetos promovidos de la generación cero a la generación uno.</span><span class="sxs-lookup"><span data-stu-id="536d2-118">The size, in kilobytes, of the objects promoted from generation zero to generation one.</span></span>|  
|`KBytesPromotedFromGen1`|<span data-ttu-id="536d2-119">Tamaño, en kilobytes, de los objetos promovidos de la generación de uno a la generación dos.</span><span class="sxs-lookup"><span data-stu-id="536d2-119">The size, in kilobytes, of the objects promoted from generation one to generation two.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="536d2-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="536d2-120">Remarks</span></span>  

 <span data-ttu-id="536d2-121">El método [ICLRGCManager:: getstats (](iclrgcmanager-getstats-method.md) requiere que el `Flags` campo de la `COR_GC_STATS` estructura se establezca en uno o más valores de la enumeración [COR_GC_STAT_TYPES](cor-gc-stat-types-enumeration.md) para especificar qué estadísticas se van a establecer.</span><span class="sxs-lookup"><span data-stu-id="536d2-121">The [ICLRGCManager::GetStats](iclrgcmanager-getstats-method.md) method requires the `Flags` field of the `COR_GC_STATS` structure to be set to one or more values of the [COR_GC_STAT_TYPES](cor-gc-stat-types-enumeration.md) enumeration to specify which statistics are to be set.</span></span>  
  
 <span data-ttu-id="536d2-122">En la tabla siguiente se asignan las estadísticas proporcionadas por esta estructura a los dos valores de enumeración [COR_GC_STAT_TYPES](cor-gc-stat-types-enumeration.md) , `COR_GC_COUNTS` y `COR_GC_MEMORYUSAGE` .</span><span class="sxs-lookup"><span data-stu-id="536d2-122">The following table maps the statistics provided by this structure to the two [COR_GC_STAT_TYPES](cor-gc-stat-types-enumeration.md) enumeration values, `COR_GC_COUNTS` and `COR_GC_MEMORYUSAGE`.</span></span>  
  
|<span data-ttu-id="536d2-123">Especificado por COR_GC_COUNTS</span><span class="sxs-lookup"><span data-stu-id="536d2-123">Specified by COR_GC_COUNTS</span></span>|<span data-ttu-id="536d2-124">Especificado por COR_GC_MEMORYUSAGE</span><span class="sxs-lookup"><span data-stu-id="536d2-124">Specified by COR_GC_MEMORYUSAGE</span></span>|  
|----------------------------------|---------------------------------------|  
|`ExplicitGCCount`<br /><br /> `GenCollectionsTaken`|`CommittedKBytes`<br /><br /> `ReservedKBytes`<br /><br /> `Gen0HeapSizeKBytes`<br /><br /> `Gen1HeapSizeKBytes`<br /><br /> `Gen2HeapSizeKBytes`<br /><br /> `LargeObjectHeapSizeKBytes`<br /><br /> `KBytesPromotedFromGen0`<br /><br /> `KBytesPromotedFromGen1`|  
  
 <span data-ttu-id="536d2-125">A continuación se muestra un ejemplo de uso:</span><span class="sxs-lookup"><span data-stu-id="536d2-125">An example of the usage is as follows:</span></span>  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="536d2-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="536d2-126">Requirements</span></span>  

 <span data-ttu-id="536d2-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="536d2-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="536d2-128">**Encabezado:** GCHost. idl</span><span class="sxs-lookup"><span data-stu-id="536d2-128">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="536d2-129">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="536d2-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="536d2-130">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="536d2-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="536d2-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="536d2-131">See also</span></span>

- [<span data-ttu-id="536d2-132">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="536d2-132">Hosting Structures</span></span>](hosting-structures.md)
- [<span data-ttu-id="536d2-133">Administración automática de la memoria</span><span class="sxs-lookup"><span data-stu-id="536d2-133">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="536d2-134">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="536d2-134">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
