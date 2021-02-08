---
description: 'Más información acerca de: estructura de COR_GC_THREAD_STATS'
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
ms.openlocfilehash: 179eb335e9f8c118ee98d4b777c347f3758ee0c6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799790"
---
# <a name="cor_gc_thread_stats-structure"></a><span data-ttu-id="962c5-103">COR_GC_THREAD_STATS (Estructura)</span><span class="sxs-lookup"><span data-stu-id="962c5-103">COR_GC_THREAD_STATS Structure</span></span>

<span data-ttu-id="962c5-104">Contiene estadísticas por subproceso relativas a la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="962c5-104">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="962c5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="962c5-105">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;
    ULONG      Flags;
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="962c5-106">Members</span><span class="sxs-lookup"><span data-stu-id="962c5-106">Members</span></span>  
  
|<span data-ttu-id="962c5-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="962c5-107">Member</span></span>|<span data-ttu-id="962c5-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="962c5-108">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="962c5-109">El número de bytes de memoria asignados en el subproceso que está asociado a la `COR_GC_THREAD_STATS` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="962c5-109">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="962c5-110">Este número se borra a cero cada vez que se produce una recolección de elementos no utilizados de generación cero.</span><span class="sxs-lookup"><span data-stu-id="962c5-110">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="962c5-111">Número de bytes promocionados a una generación superior en la recolección de elementos no utilizados más reciente.</span><span class="sxs-lookup"><span data-stu-id="962c5-111">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="962c5-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="962c5-112">Remarks</span></span>  

 <span data-ttu-id="962c5-113">[ICLRTask:: getmemstats (](iclrtask-getmemstats-method.md) toma un parámetro de salida de tipo `COR_GC_THREAD_STATS` .</span><span class="sxs-lookup"><span data-stu-id="962c5-113">[ICLRTask::GetMemStats](iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="962c5-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="962c5-114">Requirements</span></span>  

 <span data-ttu-id="962c5-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="962c5-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="962c5-116">**Encabezado:** GCHost. idl</span><span class="sxs-lookup"><span data-stu-id="962c5-116">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="962c5-117">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="962c5-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="962c5-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="962c5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="962c5-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="962c5-119">See also</span></span>

- [<span data-ttu-id="962c5-120">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="962c5-120">Hosting Structures</span></span>](hosting-structures.md)
- [<span data-ttu-id="962c5-121">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="962c5-121">IHostTask Interface</span></span>](ihosttask-interface.md)
