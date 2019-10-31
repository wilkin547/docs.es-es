---
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
ms.openlocfilehash: 63275aaa7ed1f63c4f100845d2cbe9e93fcd0bcd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131253"
---
# <a name="cor_gc_thread_stats_types-enumeration"></a><span data-ttu-id="9855c-102">COR_GC_THREAD_STATS_TYPES (enumeración)</span><span class="sxs-lookup"><span data-stu-id="9855c-102">COR_GC_THREAD_STATS_TYPES Enumeration</span></span>
<span data-ttu-id="9855c-103">Indica las estadísticas de recolección de elementos no utilizados de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="9855c-103">Indicates the garbage collection statistics for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9855c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9855c-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_GC_THREAD_HAS_PROMOTED_BYTES  = 0x00000001  
} COR_GC_THREAD_STATS_TYPES;  
```  
  
## <a name="members"></a><span data-ttu-id="9855c-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="9855c-105">Members</span></span>  
  
|<span data-ttu-id="9855c-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="9855c-106">Member</span></span>|<span data-ttu-id="9855c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9855c-107">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_THREAD_HAS_PROMOTED_BYTES`|<span data-ttu-id="9855c-108">El subproceso tiene bytes que se promovieron en la recolección de elementos no utilizados más reciente.</span><span class="sxs-lookup"><span data-stu-id="9855c-108">The thread has bytes that were promoted in the most recent garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9855c-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9855c-109">Requirements</span></span>  
 <span data-ttu-id="9855c-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9855c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9855c-111">**Encabezado:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="9855c-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="9855c-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9855c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9855c-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="9855c-113">See also</span></span>

- [<span data-ttu-id="9855c-114">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="9855c-114">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
