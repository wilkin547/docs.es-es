---
description: 'Más información acerca de: enumeración COR_GC_STAT_TYPES'
title: COR_GC_STAT_TYPES (enumeración)
ms.date: 03/30/2017
api_name:
- COR_GC_STAT_TYPES
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_STAT_TYPES
helpviewer_keywords:
- COR_GC_STAT_TYPES enumeration [.NET Framework hosting]
ms.assetid: fc51d6db-f7f8-408b-b93d-c166fc712c99
topic_type:
- apiref
ms.openlocfilehash: c4ea3175c777d49a5d6cffdf506f42e479784971
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799816"
---
# <a name="cor_gc_stat_types-enumeration"></a><span data-ttu-id="56231-103">COR_GC_STAT_TYPES (enumeración)</span><span class="sxs-lookup"><span data-stu-id="56231-103">COR_GC_STAT_TYPES Enumeration</span></span>

<span data-ttu-id="56231-104">Especifica las estadísticas que se van a registrar para una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="56231-104">Specifies the statistics to be recorded for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56231-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="56231-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a><span data-ttu-id="56231-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="56231-106">Remarks</span></span>  

 <span data-ttu-id="56231-107">Esta enumeración especifica qué estadísticas de la estructura de [COR_GC_STATS](cor-gc-stats-structure.md) se van a establecer mediante el método [ICLRGCManager:: getstats (](iclrgcmanager-getstats-method.md) .</span><span class="sxs-lookup"><span data-stu-id="56231-107">This enumeration specifies which statistics in the [COR_GC_STATS](cor-gc-stats-structure.md) structure are to be set by [ICLRGCManager::GetStats](iclrgcmanager-getstats-method.md) method.</span></span>  
  
## <a name="members"></a><span data-ttu-id="56231-108">Members</span><span class="sxs-lookup"><span data-stu-id="56231-108">Members</span></span>  
  
|<span data-ttu-id="56231-109">Miembro</span><span class="sxs-lookup"><span data-stu-id="56231-109">Member</span></span>|<span data-ttu-id="56231-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="56231-110">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_COUNTS`|<span data-ttu-id="56231-111">Registra el número de recolecciones de elementos no utilizados realizadas para cada generación.</span><span class="sxs-lookup"><span data-stu-id="56231-111">Records the number of garbage collections performed for each generation.</span></span>|  
|`COR_GC_MEMORYUSAGE`|<span data-ttu-id="56231-112">Registra las estadísticas de uso de memoria y de tamaño de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="56231-112">Records memory usage and garbage collection size statistics.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="56231-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="56231-113">Requirements</span></span>  

 <span data-ttu-id="56231-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56231-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56231-115">**Encabezado:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="56231-115">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="56231-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56231-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56231-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="56231-117">See also</span></span>

- [<span data-ttu-id="56231-118">COR_GC_STATS (Estructura)</span><span class="sxs-lookup"><span data-stu-id="56231-118">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="56231-119">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="56231-119">Hosting Enumerations</span></span>](hosting-enumerations.md)
