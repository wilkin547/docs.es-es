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
ms.openlocfilehash: 9e228cfbdade420c4d5248ffd417c6131083ee74
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59110422"
---
# <a name="corgcstattypes-enumeration"></a><span data-ttu-id="7b2e5-102">COR_GC_STAT_TYPES (enumeración)</span><span class="sxs-lookup"><span data-stu-id="7b2e5-102">COR_GC_STAT_TYPES Enumeration</span></span>
<span data-ttu-id="7b2e5-103">Especifica las estadísticas que se registren para la recolección.</span><span class="sxs-lookup"><span data-stu-id="7b2e5-103">Specifies the statistics to be recorded for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b2e5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b2e5-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a><span data-ttu-id="7b2e5-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7b2e5-105">Remarks</span></span>  
 <span data-ttu-id="7b2e5-106">Esta enumeración especifica las estadísticas que en el [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) estructura que se va a establecer [ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="7b2e5-106">This enumeration specifies which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set by [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method.</span></span>  
  
## <a name="members"></a><span data-ttu-id="7b2e5-107">Miembros</span><span class="sxs-lookup"><span data-stu-id="7b2e5-107">Members</span></span>  
  
|<span data-ttu-id="7b2e5-108">Miembro</span><span class="sxs-lookup"><span data-stu-id="7b2e5-108">Member</span></span>|<span data-ttu-id="7b2e5-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="7b2e5-109">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_COUNTS`|<span data-ttu-id="7b2e5-110">Registra el número de recolecciones de elementos no utilizados realizadas para cada generación.</span><span class="sxs-lookup"><span data-stu-id="7b2e5-110">Records the number of garbage collections performed for each generation.</span></span>|  
|`COR_GC_MEMORYUSAGE`|<span data-ttu-id="7b2e5-111">Registros memoria elementos no utilizados y el uso de las estadísticas de tamaño.</span><span class="sxs-lookup"><span data-stu-id="7b2e5-111">Records memory usage and garbage collection size statistics.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7b2e5-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b2e5-112">Requirements</span></span>  
 <span data-ttu-id="7b2e5-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b2e5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b2e5-114">**Encabezado**: GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="7b2e5-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 **<span data-ttu-id="7b2e5-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="7b2e5-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7b2e5-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b2e5-116">See also</span></span>

- [<span data-ttu-id="7b2e5-117">COR_GC_STATS (Estructura)</span><span class="sxs-lookup"><span data-stu-id="7b2e5-117">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="7b2e5-118">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="7b2e5-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
