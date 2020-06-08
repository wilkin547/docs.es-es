---
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
ms.openlocfilehash: d7e78dfc4beba67cc376b221d0cd49f7200f5d23
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501708"
---
# <a name="cor_gc_stat_types-enumeration"></a><span data-ttu-id="fac99-102">COR_GC_STAT_TYPES (enumeración)</span><span class="sxs-lookup"><span data-stu-id="fac99-102">COR_GC_STAT_TYPES Enumeration</span></span>
<span data-ttu-id="fac99-103">Especifica las estadísticas que se van a registrar para una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="fac99-103">Specifies the statistics to be recorded for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fac99-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fac99-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a><span data-ttu-id="fac99-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fac99-105">Remarks</span></span>  
 <span data-ttu-id="fac99-106">Esta enumeración especifica qué estadísticas de la estructura de [COR_GC_STATS](cor-gc-stats-structure.md) se van a establecer mediante el método [ICLRGCManager:: getstats (](iclrgcmanager-getstats-method.md) .</span><span class="sxs-lookup"><span data-stu-id="fac99-106">This enumeration specifies which statistics in the [COR_GC_STATS](cor-gc-stats-structure.md) structure are to be set by [ICLRGCManager::GetStats](iclrgcmanager-getstats-method.md) method.</span></span>  
  
## <a name="members"></a><span data-ttu-id="fac99-107">Miembros</span><span class="sxs-lookup"><span data-stu-id="fac99-107">Members</span></span>  
  
|<span data-ttu-id="fac99-108">Miembro</span><span class="sxs-lookup"><span data-stu-id="fac99-108">Member</span></span>|<span data-ttu-id="fac99-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="fac99-109">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_COUNTS`|<span data-ttu-id="fac99-110">Registra el número de recolecciones de elementos no utilizados realizadas para cada generación.</span><span class="sxs-lookup"><span data-stu-id="fac99-110">Records the number of garbage collections performed for each generation.</span></span>|  
|`COR_GC_MEMORYUSAGE`|<span data-ttu-id="fac99-111">Registra las estadísticas de uso de memoria y de tamaño de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="fac99-111">Records memory usage and garbage collection size statistics.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fac99-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fac99-112">Requirements</span></span>  
 <span data-ttu-id="fac99-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fac99-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fac99-114">**Encabezado:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="fac99-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="fac99-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fac99-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fac99-116">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="fac99-116">See also</span></span>

- [<span data-ttu-id="fac99-117">COR_GC_STATS (Estructura)</span><span class="sxs-lookup"><span data-stu-id="fac99-117">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="fac99-118">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="fac99-118">Hosting Enumerations</span></span>](hosting-enumerations.md)
