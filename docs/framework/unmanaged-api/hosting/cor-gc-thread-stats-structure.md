---
title: COR_GC_THREAD_STATS (Estructura)
ms.date: 03/30/2017
api_name:
- COR_GC_THREAD_STATS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_THREAD_STATS
helpviewer_keywords:
- COR_GC_THREAD_STATS structure [.NET Framework hosting]
ms.assetid: 01f9a59b-7679-4d42-9ced-4a8981625c3d
topic_type:
- apiref
ms.openlocfilehash: 25a90965dc5466b7cf1a07140705424cf2ba4cd9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699240"
---
# <a name="cor_gc_thread_stats-structure"></a><span data-ttu-id="f9df9-102">COR_GC_THREAD_STATS (Estructura)</span><span class="sxs-lookup"><span data-stu-id="f9df9-102">COR_GC_THREAD_STATS Structure</span></span>

<span data-ttu-id="f9df9-103">Contiene estadísticas por subproceso relativas a la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="f9df9-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9df9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f9df9-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;
    ULONG      Flags;
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="f9df9-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="f9df9-105">Members</span></span>  
  
|<span data-ttu-id="f9df9-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="f9df9-106">Member</span></span>|<span data-ttu-id="f9df9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f9df9-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="f9df9-108">El número de bytes de memoria asignados en el subproceso que está asociado a la `COR_GC_THREAD_STATS` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="f9df9-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="f9df9-109">Este número se borra a cero cada vez que se produce una recolección de elementos no utilizados de generación cero.</span><span class="sxs-lookup"><span data-stu-id="f9df9-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="f9df9-110">Número de bytes promocionados a una generación superior en la recolección de elementos no utilizados más reciente.</span><span class="sxs-lookup"><span data-stu-id="f9df9-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9df9-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f9df9-111">Remarks</span></span>  

 <span data-ttu-id="f9df9-112">[ICLRTask:: getmemstats (](iclrtask-getmemstats-method.md) toma un parámetro de salida de tipo `COR_GC_THREAD_STATS` .</span><span class="sxs-lookup"><span data-stu-id="f9df9-112">[ICLRTask::GetMemStats](iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9df9-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f9df9-113">Requirements</span></span>  

 <span data-ttu-id="f9df9-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9df9-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9df9-115">**Encabezado:** GCHost. idl</span><span class="sxs-lookup"><span data-stu-id="f9df9-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="f9df9-116">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f9df9-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f9df9-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9df9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9df9-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f9df9-118">See also</span></span>

- [<span data-ttu-id="f9df9-119">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="f9df9-119">Hosting Structures</span></span>](hosting-structures.md)
- [<span data-ttu-id="f9df9-120">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f9df9-120">IHostTask Interface</span></span>](ihosttask-interface.md)
