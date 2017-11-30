---
title: "COR_GC_STAT_TYPES (enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_GC_STAT_TYPES
api_location: mscoree.dll
api_type: COM
f1_keywords: COR_GC_STAT_TYPES
helpviewer_keywords: COR_GC_STAT_TYPES enumeration [.NET Framework hosting]
ms.assetid: fc51d6db-f7f8-408b-b93d-c166fc712c99
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4cf66026ecf92d0158a1010e82c078478c280f9b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="corgcstattypes-enumeration"></a><span data-ttu-id="8e8bd-102">COR_GC_STAT_TYPES (enumeración)</span><span class="sxs-lookup"><span data-stu-id="8e8bd-102">COR_GC_STAT_TYPES Enumeration</span></span>
<span data-ttu-id="8e8bd-103">Especifica las estadísticas que se registren para una colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="8e8bd-103">Specifies the statistics to be recorded for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e8bd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8e8bd-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a><span data-ttu-id="8e8bd-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8e8bd-105">Remarks</span></span>  
 <span data-ttu-id="8e8bd-106">Esta enumeración especifica las estadísticas en el [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) estructura que se va a establecer [ICLRGCManager:: GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="8e8bd-106">This enumeration specifies which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set by [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method.</span></span>  
  
## <a name="members"></a><span data-ttu-id="8e8bd-107">Miembros</span><span class="sxs-lookup"><span data-stu-id="8e8bd-107">Members</span></span>  
  
|<span data-ttu-id="8e8bd-108">Miembro</span><span class="sxs-lookup"><span data-stu-id="8e8bd-108">Member</span></span>|<span data-ttu-id="8e8bd-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e8bd-109">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_COUNTS`|<span data-ttu-id="8e8bd-110">Registra el número de recolecciones de elementos no utilizados realizadas para cada generación.</span><span class="sxs-lookup"><span data-stu-id="8e8bd-110">Records the number of garbage collections performed for each generation.</span></span>|  
|`COR_GC_MEMORYUSAGE`|<span data-ttu-id="8e8bd-111">Registros uso y los elementos no utilizados colección tamaño estadísticas de memoria.</span><span class="sxs-lookup"><span data-stu-id="8e8bd-111">Records memory usage and garbage collection size statistics.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8e8bd-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8e8bd-112">Requirements</span></span>  
 <span data-ttu-id="8e8bd-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e8bd-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e8bd-114">**Encabezado:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="8e8bd-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="8e8bd-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e8bd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e8bd-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e8bd-116">See Also</span></span>  
 [<span data-ttu-id="8e8bd-117">COR_GC_STATS (estructura)</span><span class="sxs-lookup"><span data-stu-id="8e8bd-117">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [<span data-ttu-id="8e8bd-118">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="8e8bd-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
