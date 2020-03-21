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
ms.openlocfilehash: 2ab0c38645a8e5fbd9e71b3c1787e88bfe2c0604
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176531"
---
# <a name="cor_gc_stats-structure"></a><span data-ttu-id="69905-102">COR_GC_STATS (Estructura)</span><span class="sxs-lookup"><span data-stu-id="69905-102">COR_GC_STATS Structure</span></span>
<span data-ttu-id="69905-103">Proporciona estadísticas sobre el mecanismo de recolección de elementos no utilizados de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="69905-103">Provides statistics about the garbage collection mechanism of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69905-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69905-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="69905-105">Members</span><span class="sxs-lookup"><span data-stu-id="69905-105">Members</span></span>  
  
|<span data-ttu-id="69905-106">Member</span><span class="sxs-lookup"><span data-stu-id="69905-106">Member</span></span>|<span data-ttu-id="69905-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="69905-107">Description</span></span>|  
|------------|-----------------|  
|`Flags`|<span data-ttu-id="69905-108">Indica qué valores de campo se deben calcular y devolver.</span><span class="sxs-lookup"><span data-stu-id="69905-108">Indicates which field values should be calculated and returned.</span></span>|  
|`ExplicitGCCount`|<span data-ttu-id="69905-109">Indica el número de recolecciones de elementos no utilizados forzadas por solicitud externa.</span><span class="sxs-lookup"><span data-stu-id="69905-109">Indicates the number of garbage collections that were forced by external request.</span></span>|  
|`GenCollectionsTaken`|<span data-ttu-id="69905-110">Indica el número de recolecciones de elementos no utilizados realizadas para cada generación.</span><span class="sxs-lookup"><span data-stu-id="69905-110">Indicates the number of garbage collections performed for each generation.</span></span>|  
|`CommittedKBytes`|<span data-ttu-id="69905-111">El número total de kilobytes confirmados en todos los montones.</span><span class="sxs-lookup"><span data-stu-id="69905-111">The total number of kilobytes committed in all heaps.</span></span>|  
|`ReservedKBytes`|<span data-ttu-id="69905-112">El número total de kilobytes reservados en todos los montones.</span><span class="sxs-lookup"><span data-stu-id="69905-112">The total number of kilobytes reserved in all heaps.</span></span>|  
|`Gen0HeapSizeKBytes`|<span data-ttu-id="69905-113">El tamaño, en kilobytes, del montón de generación cero.</span><span class="sxs-lookup"><span data-stu-id="69905-113">The size, in kilobytes, of the generation-zero heap.</span></span>|  
|`Gen1HeapSizeKBytes`|<span data-ttu-id="69905-114">El tamaño, en kilobytes, del montón de generación uno.</span><span class="sxs-lookup"><span data-stu-id="69905-114">The size, in kilobytes, of the generation-one heap.</span></span>|  
|`Gen2HeapSizeKBytes`|<span data-ttu-id="69905-115">El tamaño, en kilobytes, del montón de generación dos.</span><span class="sxs-lookup"><span data-stu-id="69905-115">The size, in kilobytes, of the generation-two heap.</span></span>|  
|`LargeObjectHeapSizeKBytes`|<span data-ttu-id="69905-116">El tamaño, en kilobytes, del montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="69905-116">The size, in kilobytes, of the large object heap.</span></span>|  
|`KBytesPromotedFromGen0`|<span data-ttu-id="69905-117">El tamaño, en kilobytes, de los objetos promovidos de generación cero a generación uno.</span><span class="sxs-lookup"><span data-stu-id="69905-117">The size, in kilobytes, of the objects promoted from generation zero to generation one.</span></span>|  
|`KBytesPromotedFromGen1`|<span data-ttu-id="69905-118">El tamaño, en kilobytes, de los objetos promovidos de generación uno a generación dos.</span><span class="sxs-lookup"><span data-stu-id="69905-118">The size, in kilobytes, of the objects promoted from generation one to generation two.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69905-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="69905-119">Remarks</span></span>  
 <span data-ttu-id="69905-120">El método [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) `Flags` requiere que `COR_GC_STATS` el campo de la estructura se establezca en uno o varios valores de la [enumeración COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) para especificar qué estadísticas se deben establecer.</span><span class="sxs-lookup"><span data-stu-id="69905-120">The [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method requires the `Flags` field of the `COR_GC_STATS` structure to be set to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics are to be set.</span></span>  
  
 <span data-ttu-id="69905-121">En la tabla siguiente se asignan las estadísticas proporcionadas `COR_GC_MEMORYUSAGE`por esta estructura a los dos [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) valores de enumeración `COR_GC_COUNTS` y .</span><span class="sxs-lookup"><span data-stu-id="69905-121">The following table maps the statistics provided by this structure to the two [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration values, `COR_GC_COUNTS` and `COR_GC_MEMORYUSAGE`.</span></span>  
  
|<span data-ttu-id="69905-122">Especificado por COR_GC_COUNTS</span><span class="sxs-lookup"><span data-stu-id="69905-122">Specified by COR_GC_COUNTS</span></span>|<span data-ttu-id="69905-123">Especificado por COR_GC_MEMORYUSAGE</span><span class="sxs-lookup"><span data-stu-id="69905-123">Specified by COR_GC_MEMORYUSAGE</span></span>|  
|----------------------------------|---------------------------------------|  
|`ExplicitGCCount`<br /><br /> `GenCollectionsTaken`|`CommittedKBytes`<br /><br /> `ReservedKBytes`<br /><br /> `Gen0HeapSizeKBytes`<br /><br /> `Gen1HeapSizeKBytes`<br /><br /> `Gen2HeapSizeKBytes`<br /><br /> `LargeObjectHeapSizeKBytes`<br /><br /> `KBytesPromotedFromGen0`<br /><br /> `KBytesPromotedFromGen1`|  
  
 <span data-ttu-id="69905-124">Un ejemplo del uso es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="69905-124">An example of the usage is as follows:</span></span>  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="69905-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="69905-125">Requirements</span></span>  
 <span data-ttu-id="69905-126">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69905-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69905-127">**Encabezado:** GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="69905-127">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="69905-128">**Biblioteca:** Incluido como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="69905-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="69905-129">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69905-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69905-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="69905-130">See also</span></span>

- [<span data-ttu-id="69905-131">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="69905-131">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="69905-132">Gestión automática de la memoria</span><span class="sxs-lookup"><span data-stu-id="69905-132">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="69905-133">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="69905-133">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
