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
ms.openlocfilehash: c14e27b67fc600e2684f8c967af30bb9a5cee126
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716749"
---
# <a name="cor_gc_stat_types-enumeration"></a><span data-ttu-id="b0c6a-102">COR_GC_STAT_TYPES (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b0c6a-102">COR_GC_STAT_TYPES Enumeration</span></span>

<span data-ttu-id="b0c6a-103">Especifica las estadísticas que se van a registrar para una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b0c6a-103">Specifies the statistics to be recorded for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0c6a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0c6a-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a><span data-ttu-id="b0c6a-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b0c6a-105">Remarks</span></span>  

 <span data-ttu-id="b0c6a-106">Esta enumeración especifica qué estadísticas de la estructura de [COR_GC_STATS](cor-gc-stats-structure.md) se van a establecer mediante el método [ICLRGCManager:: getstats (](iclrgcmanager-getstats-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b0c6a-106">This enumeration specifies which statistics in the [COR_GC_STATS](cor-gc-stats-structure.md) structure are to be set by [ICLRGCManager::GetStats](iclrgcmanager-getstats-method.md) method.</span></span>  
  
## <a name="members"></a><span data-ttu-id="b0c6a-107">Miembros</span><span class="sxs-lookup"><span data-stu-id="b0c6a-107">Members</span></span>  
  
|<span data-ttu-id="b0c6a-108">Miembro</span><span class="sxs-lookup"><span data-stu-id="b0c6a-108">Member</span></span>|<span data-ttu-id="b0c6a-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0c6a-109">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_COUNTS`|<span data-ttu-id="b0c6a-110">Registra el número de recolecciones de elementos no utilizados realizadas para cada generación.</span><span class="sxs-lookup"><span data-stu-id="b0c6a-110">Records the number of garbage collections performed for each generation.</span></span>|  
|`COR_GC_MEMORYUSAGE`|<span data-ttu-id="b0c6a-111">Registra las estadísticas de uso de memoria y de tamaño de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b0c6a-111">Records memory usage and garbage collection size statistics.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b0c6a-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b0c6a-112">Requirements</span></span>  

 <span data-ttu-id="b0c6a-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0c6a-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0c6a-114">**Encabezado:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="b0c6a-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="b0c6a-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0c6a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0c6a-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b0c6a-116">See also</span></span>

- [<span data-ttu-id="b0c6a-117">COR_GC_STATS (Estructura)</span><span class="sxs-lookup"><span data-stu-id="b0c6a-117">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="b0c6a-118">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="b0c6a-118">Hosting Enumerations</span></span>](hosting-enumerations.md)
