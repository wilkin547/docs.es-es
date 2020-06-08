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
ms.openlocfilehash: 7a6553de31d4f9627809af7691218c39dc734c6f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501669"
---
# <a name="cor_gc_stats-structure"></a><span data-ttu-id="dec9d-102">COR_GC_STATS (Estructura)</span><span class="sxs-lookup"><span data-stu-id="dec9d-102">COR_GC_STATS Structure</span></span>
<span data-ttu-id="dec9d-103">Proporciona estadísticas sobre el mecanismo de recolección de elementos no utilizados del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="dec9d-103">Provides statistics about the garbage collection mechanism of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dec9d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dec9d-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="dec9d-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="dec9d-105">Members</span></span>  
  
|<span data-ttu-id="dec9d-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="dec9d-106">Member</span></span>|<span data-ttu-id="dec9d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="dec9d-107">Description</span></span>|  
|------------|-----------------|  
|`Flags`|<span data-ttu-id="dec9d-108">Indica qué valores de campo deben calcularse y devolverse.</span><span class="sxs-lookup"><span data-stu-id="dec9d-108">Indicates which field values should be calculated and returned.</span></span>|  
|`ExplicitGCCount`|<span data-ttu-id="dec9d-109">Indica el número de recolecciones de elementos no utilizados forzadas por la solicitud externa.</span><span class="sxs-lookup"><span data-stu-id="dec9d-109">Indicates the number of garbage collections that were forced by external request.</span></span>|  
|`GenCollectionsTaken`|<span data-ttu-id="dec9d-110">Indica el número de recolecciones de elementos no utilizados realizadas para cada generación.</span><span class="sxs-lookup"><span data-stu-id="dec9d-110">Indicates the number of garbage collections performed for each generation.</span></span>|  
|`CommittedKBytes`|<span data-ttu-id="dec9d-111">Número total de kilobytes confirmados en todos los montones.</span><span class="sxs-lookup"><span data-stu-id="dec9d-111">The total number of kilobytes committed in all heaps.</span></span>|  
|`ReservedKBytes`|<span data-ttu-id="dec9d-112">Número total de kilobytes reservados en todos los montones.</span><span class="sxs-lookup"><span data-stu-id="dec9d-112">The total number of kilobytes reserved in all heaps.</span></span>|  
|`Gen0HeapSizeKBytes`|<span data-ttu-id="dec9d-113">Tamaño, en kilobytes, del montón de generación cero.</span><span class="sxs-lookup"><span data-stu-id="dec9d-113">The size, in kilobytes, of the generation-zero heap.</span></span>|  
|`Gen1HeapSizeKBytes`|<span data-ttu-id="dec9d-114">Tamaño, en kilobytes, del montón de generación uno.</span><span class="sxs-lookup"><span data-stu-id="dec9d-114">The size, in kilobytes, of the generation-one heap.</span></span>|  
|`Gen2HeapSizeKBytes`|<span data-ttu-id="dec9d-115">Tamaño, en kilobytes, del montón de generación 2.</span><span class="sxs-lookup"><span data-stu-id="dec9d-115">The size, in kilobytes, of the generation-two heap.</span></span>|  
|`LargeObjectHeapSizeKBytes`|<span data-ttu-id="dec9d-116">Tamaño, en kilobytes, del montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="dec9d-116">The size, in kilobytes, of the large object heap.</span></span>|  
|`KBytesPromotedFromGen0`|<span data-ttu-id="dec9d-117">Tamaño, en kilobytes, de los objetos promovidos de la generación cero a la generación uno.</span><span class="sxs-lookup"><span data-stu-id="dec9d-117">The size, in kilobytes, of the objects promoted from generation zero to generation one.</span></span>|  
|`KBytesPromotedFromGen1`|<span data-ttu-id="dec9d-118">Tamaño, en kilobytes, de los objetos promovidos de la generación de uno a la generación dos.</span><span class="sxs-lookup"><span data-stu-id="dec9d-118">The size, in kilobytes, of the objects promoted from generation one to generation two.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dec9d-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dec9d-119">Remarks</span></span>  
 <span data-ttu-id="dec9d-120">El método [ICLRGCManager:: getstats (](iclrgcmanager-getstats-method.md) requiere que el `Flags` campo de la `COR_GC_STATS` estructura se establezca en uno o más valores de la enumeración [COR_GC_STAT_TYPES](cor-gc-stat-types-enumeration.md) para especificar qué estadísticas se van a establecer.</span><span class="sxs-lookup"><span data-stu-id="dec9d-120">The [ICLRGCManager::GetStats](iclrgcmanager-getstats-method.md) method requires the `Flags` field of the `COR_GC_STATS` structure to be set to one or more values of the [COR_GC_STAT_TYPES](cor-gc-stat-types-enumeration.md) enumeration to specify which statistics are to be set.</span></span>  
  
 <span data-ttu-id="dec9d-121">En la tabla siguiente se asignan las estadísticas proporcionadas por esta estructura a los dos valores de enumeración [COR_GC_STAT_TYPES](cor-gc-stat-types-enumeration.md) , `COR_GC_COUNTS` y `COR_GC_MEMORYUSAGE` .</span><span class="sxs-lookup"><span data-stu-id="dec9d-121">The following table maps the statistics provided by this structure to the two [COR_GC_STAT_TYPES](cor-gc-stat-types-enumeration.md) enumeration values, `COR_GC_COUNTS` and `COR_GC_MEMORYUSAGE`.</span></span>  
  
|<span data-ttu-id="dec9d-122">Especificado por COR_GC_COUNTS</span><span class="sxs-lookup"><span data-stu-id="dec9d-122">Specified by COR_GC_COUNTS</span></span>|<span data-ttu-id="dec9d-123">Especificado por COR_GC_MEMORYUSAGE</span><span class="sxs-lookup"><span data-stu-id="dec9d-123">Specified by COR_GC_MEMORYUSAGE</span></span>|  
|----------------------------------|---------------------------------------|  
|`ExplicitGCCount`<br /><br /> `GenCollectionsTaken`|`CommittedKBytes`<br /><br /> `ReservedKBytes`<br /><br /> `Gen0HeapSizeKBytes`<br /><br /> `Gen1HeapSizeKBytes`<br /><br /> `Gen2HeapSizeKBytes`<br /><br /> `LargeObjectHeapSizeKBytes`<br /><br /> `KBytesPromotedFromGen0`<br /><br /> `KBytesPromotedFromGen1`|  
  
 <span data-ttu-id="dec9d-124">A continuación se muestra un ejemplo de uso:</span><span class="sxs-lookup"><span data-stu-id="dec9d-124">An example of the usage is as follows:</span></span>  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="dec9d-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dec9d-125">Requirements</span></span>  
 <span data-ttu-id="dec9d-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dec9d-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dec9d-127">**Encabezado:** GCHost. idl</span><span class="sxs-lookup"><span data-stu-id="dec9d-127">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="dec9d-128">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="dec9d-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dec9d-129">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dec9d-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dec9d-130">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="dec9d-130">See also</span></span>

- [<span data-ttu-id="dec9d-131">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="dec9d-131">Hosting Structures</span></span>](hosting-structures.md)
- [<span data-ttu-id="dec9d-132">Administración de memoria automática</span><span class="sxs-lookup"><span data-stu-id="dec9d-132">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="dec9d-133">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="dec9d-133">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
