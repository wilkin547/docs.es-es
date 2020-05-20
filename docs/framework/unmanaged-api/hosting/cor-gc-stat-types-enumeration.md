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
ms.openlocfilehash: cca393ae34144787ab7800baec7c58209394f30e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616723"
---
# <a name="cor_gc_stat_types-enumeration"></a><span data-ttu-id="0d009-102">COR_GC_STAT_TYPES (enumeración)</span><span class="sxs-lookup"><span data-stu-id="0d009-102">COR_GC_STAT_TYPES Enumeration</span></span>
<span data-ttu-id="0d009-103">Especifica las estadísticas que se van a registrar para una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="0d009-103">Specifies the statistics to be recorded for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d009-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0d009-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a><span data-ttu-id="0d009-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0d009-105">Remarks</span></span>  
 <span data-ttu-id="0d009-106">Esta enumeración especifica qué estadísticas de la estructura de [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) se van a establecer mediante el método [ICLRGCManager:: getstats (](iclrgcmanager-getstats-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0d009-106">This enumeration specifies which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set by [ICLRGCManager::GetStats](iclrgcmanager-getstats-method.md) method.</span></span>  
  
## <a name="members"></a><span data-ttu-id="0d009-107">Miembros</span><span class="sxs-lookup"><span data-stu-id="0d009-107">Members</span></span>  
  
|<span data-ttu-id="0d009-108">Miembro</span><span class="sxs-lookup"><span data-stu-id="0d009-108">Member</span></span>|<span data-ttu-id="0d009-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="0d009-109">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_COUNTS`|<span data-ttu-id="0d009-110">Registra el número de recolecciones de elementos no utilizados realizadas para cada generación.</span><span class="sxs-lookup"><span data-stu-id="0d009-110">Records the number of garbage collections performed for each generation.</span></span>|  
|`COR_GC_MEMORYUSAGE`|<span data-ttu-id="0d009-111">Registra las estadísticas de uso de memoria y de tamaño de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="0d009-111">Records memory usage and garbage collection size statistics.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0d009-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0d009-112">Requirements</span></span>  
 <span data-ttu-id="0d009-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d009-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d009-114">**Encabezado:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="0d009-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="0d009-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d009-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d009-116">Consulta también</span><span class="sxs-lookup"><span data-stu-id="0d009-116">See also</span></span>

- [<span data-ttu-id="0d009-117">COR_GC_STATS (Estructura)</span><span class="sxs-lookup"><span data-stu-id="0d009-117">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="0d009-118">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="0d009-118">Hosting Enumerations</span></span>](hosting-enumerations.md)
