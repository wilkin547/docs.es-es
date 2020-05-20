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
ms.openlocfilehash: 2206499cad9be2a29f485ee66d468accbe00b5f5
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616689"
---
# <a name="cor_gc_thread_stats_types-enumeration"></a><span data-ttu-id="985f6-102">COR_GC_THREAD_STATS_TYPES (enumeración)</span><span class="sxs-lookup"><span data-stu-id="985f6-102">COR_GC_THREAD_STATS_TYPES Enumeration</span></span>
<span data-ttu-id="985f6-103">Indica las estadísticas de recolección de elementos no utilizados de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="985f6-103">Indicates the garbage collection statistics for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="985f6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="985f6-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_GC_THREAD_HAS_PROMOTED_BYTES  = 0x00000001  
} COR_GC_THREAD_STATS_TYPES;  
```  
  
## <a name="members"></a><span data-ttu-id="985f6-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="985f6-105">Members</span></span>  
  
|<span data-ttu-id="985f6-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="985f6-106">Member</span></span>|<span data-ttu-id="985f6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="985f6-107">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_THREAD_HAS_PROMOTED_BYTES`|<span data-ttu-id="985f6-108">El subproceso tiene bytes que se promovieron en la recolección de elementos no utilizados más reciente.</span><span class="sxs-lookup"><span data-stu-id="985f6-108">The thread has bytes that were promoted in the most recent garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="985f6-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="985f6-109">Requirements</span></span>  
 <span data-ttu-id="985f6-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="985f6-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="985f6-111">**Encabezado:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="985f6-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="985f6-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="985f6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="985f6-113">Consulta también</span><span class="sxs-lookup"><span data-stu-id="985f6-113">See also</span></span>

- [<span data-ttu-id="985f6-114">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="985f6-114">Hosting Enumerations</span></span>](hosting-enumerations.md)
