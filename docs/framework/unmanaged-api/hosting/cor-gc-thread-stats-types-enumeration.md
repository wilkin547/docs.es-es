---
description: 'Más información acerca de: enumeración COR_GC_THREAD_STATS_TYPES'
title: COR_GC_THREAD_STATS_TYPES (enumeración)
ms.date: 03/30/2017
api_name:
- COR_GC_THREAD_STATS_TYPES
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_THREAD_STATS_TYPES
helpviewer_keywords:
- COR_GC_THREAD_STATS_TYPES enumeration [.NET Framework hosting]
ms.assetid: aa227704-0ab1-4b08-aee2-1f439762162e
topic_type:
- apiref
ms.openlocfilehash: 04bc4e11c527b83cf5f1384b1092cc0d084008a3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799777"
---
# <a name="cor_gc_thread_stats_types-enumeration"></a><span data-ttu-id="98d68-103">COR_GC_THREAD_STATS_TYPES (enumeración)</span><span class="sxs-lookup"><span data-stu-id="98d68-103">COR_GC_THREAD_STATS_TYPES Enumeration</span></span>

<span data-ttu-id="98d68-104">Indica las estadísticas de recolección de elementos no utilizados de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="98d68-104">Indicates the garbage collection statistics for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98d68-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98d68-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_GC_THREAD_HAS_PROMOTED_BYTES  = 0x00000001  
} COR_GC_THREAD_STATS_TYPES;  
```  
  
## <a name="members"></a><span data-ttu-id="98d68-106">Members</span><span class="sxs-lookup"><span data-stu-id="98d68-106">Members</span></span>  
  
|<span data-ttu-id="98d68-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="98d68-107">Member</span></span>|<span data-ttu-id="98d68-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="98d68-108">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_THREAD_HAS_PROMOTED_BYTES`|<span data-ttu-id="98d68-109">El subproceso tiene bytes que se promovieron en la recolección de elementos no utilizados más reciente.</span><span class="sxs-lookup"><span data-stu-id="98d68-109">The thread has bytes that were promoted in the most recent garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="98d68-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="98d68-110">Requirements</span></span>  

 <span data-ttu-id="98d68-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98d68-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98d68-112">**Encabezado:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="98d68-112">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="98d68-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98d68-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98d68-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="98d68-114">See also</span></span>

- [<span data-ttu-id="98d68-115">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="98d68-115">Hosting Enumerations</span></span>](hosting-enumerations.md)
