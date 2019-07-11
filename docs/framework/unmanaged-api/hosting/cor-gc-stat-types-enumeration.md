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
ms.openlocfilehash: 6fdfe33c5b488d8f464001a86233124d4e7df0ed
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779071"
---
# <a name="corgcstattypes-enumeration"></a><span data-ttu-id="94b64-102">COR_GC_STAT_TYPES (enumeración)</span><span class="sxs-lookup"><span data-stu-id="94b64-102">COR_GC_STAT_TYPES Enumeration</span></span>
<span data-ttu-id="94b64-103">Especifica las estadísticas que se registren para la recolección.</span><span class="sxs-lookup"><span data-stu-id="94b64-103">Specifies the statistics to be recorded for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94b64-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="94b64-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a><span data-ttu-id="94b64-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="94b64-105">Remarks</span></span>  
 <span data-ttu-id="94b64-106">Esta enumeración especifica las estadísticas que en el [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) estructura que se va a establecer [ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="94b64-106">This enumeration specifies which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set by [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method.</span></span>  
  
## <a name="members"></a><span data-ttu-id="94b64-107">Miembros</span><span class="sxs-lookup"><span data-stu-id="94b64-107">Members</span></span>  
  
|<span data-ttu-id="94b64-108">Member</span><span class="sxs-lookup"><span data-stu-id="94b64-108">Member</span></span>|<span data-ttu-id="94b64-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="94b64-109">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_COUNTS`|<span data-ttu-id="94b64-110">Registra el número de recolecciones de elementos no utilizados realizadas para cada generación.</span><span class="sxs-lookup"><span data-stu-id="94b64-110">Records the number of garbage collections performed for each generation.</span></span>|  
|`COR_GC_MEMORYUSAGE`|<span data-ttu-id="94b64-111">Registros memoria elementos no utilizados y el uso de las estadísticas de tamaño.</span><span class="sxs-lookup"><span data-stu-id="94b64-111">Records memory usage and garbage collection size statistics.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="94b64-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="94b64-112">Requirements</span></span>  
 <span data-ttu-id="94b64-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94b64-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94b64-114">**Encabezado**: GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="94b64-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="94b64-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94b64-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94b64-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="94b64-116">See also</span></span>

- [<span data-ttu-id="94b64-117">COR_GC_STATS (estructura)</span><span class="sxs-lookup"><span data-stu-id="94b64-117">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="94b64-118">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="94b64-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
