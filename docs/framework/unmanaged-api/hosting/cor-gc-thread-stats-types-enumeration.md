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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c631a0a3abb3cb2a342dfd44fdffb147b742ae3c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698127"
---
# <a name="corgcthreadstatstypes-enumeration"></a><span data-ttu-id="d8519-102">COR_GC_THREAD_STATS_TYPES (enumeración)</span><span class="sxs-lookup"><span data-stu-id="d8519-102">COR_GC_THREAD_STATS_TYPES Enumeration</span></span>
<span data-ttu-id="d8519-103">Indica las estadísticas de la colección de elementos no utilizados para un subproceso.</span><span class="sxs-lookup"><span data-stu-id="d8519-103">Indicates the garbage collection statistics for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8519-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d8519-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_GC_THREAD_HAS_PROMOTED_BYTES  = 0x00000001  
} COR_GC_THREAD_STATS_TYPES;  
```  
  
## <a name="members"></a><span data-ttu-id="d8519-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="d8519-105">Members</span></span>  
  
|<span data-ttu-id="d8519-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="d8519-106">Member</span></span>|<span data-ttu-id="d8519-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d8519-107">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_THREAD_HAS_PROMOTED_BYTES`|<span data-ttu-id="d8519-108">El subproceso tiene bytes que se han promovido en la recolección de elementos más reciente.</span><span class="sxs-lookup"><span data-stu-id="d8519-108">The thread has bytes that were promoted in the most recent garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d8519-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d8519-109">Requirements</span></span>  
 <span data-ttu-id="d8519-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8519-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8519-111">**Encabezado**: GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="d8519-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="d8519-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8519-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8519-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8519-113">See also</span></span>

- [<span data-ttu-id="d8519-114">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="d8519-114">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
