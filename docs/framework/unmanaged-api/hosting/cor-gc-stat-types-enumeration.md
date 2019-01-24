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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4bd12feb47352d9bb78aa8ef056072f9bdc6fba3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710331"
---
# <a name="corgcstattypes-enumeration"></a><span data-ttu-id="06182-102">COR_GC_STAT_TYPES (enumeración)</span><span class="sxs-lookup"><span data-stu-id="06182-102">COR_GC_STAT_TYPES Enumeration</span></span>
<span data-ttu-id="06182-103">Especifica las estadísticas que se registren para la recolección.</span><span class="sxs-lookup"><span data-stu-id="06182-103">Specifies the statistics to be recorded for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06182-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06182-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a><span data-ttu-id="06182-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="06182-105">Remarks</span></span>  
 <span data-ttu-id="06182-106">Esta enumeración especifica las estadísticas que en el [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) estructura que se va a establecer [ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="06182-106">This enumeration specifies which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set by [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method.</span></span>  
  
## <a name="members"></a><span data-ttu-id="06182-107">Miembros</span><span class="sxs-lookup"><span data-stu-id="06182-107">Members</span></span>  
  
|<span data-ttu-id="06182-108">Miembro</span><span class="sxs-lookup"><span data-stu-id="06182-108">Member</span></span>|<span data-ttu-id="06182-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="06182-109">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_COUNTS`|<span data-ttu-id="06182-110">Registra el número de recolecciones de elementos no utilizados realizadas para cada generación.</span><span class="sxs-lookup"><span data-stu-id="06182-110">Records the number of garbage collections performed for each generation.</span></span>|  
|`COR_GC_MEMORYUSAGE`|<span data-ttu-id="06182-111">Registros memoria elementos no utilizados y el uso de las estadísticas de tamaño.</span><span class="sxs-lookup"><span data-stu-id="06182-111">Records memory usage and garbage collection size statistics.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="06182-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="06182-112">Requirements</span></span>  
 <span data-ttu-id="06182-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06182-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06182-114">**Encabezado**: GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="06182-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="06182-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06182-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06182-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="06182-116">See also</span></span>
- [<span data-ttu-id="06182-117">COR_GC_STATS (estructura)</span><span class="sxs-lookup"><span data-stu-id="06182-117">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="06182-118">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="06182-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
