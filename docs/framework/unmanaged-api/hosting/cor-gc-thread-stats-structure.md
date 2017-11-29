---
title: COR_GC_THREAD_STATS (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_GC_THREAD_STATS
api_location: mscoree.dll
api_type: COM
f1_keywords: COR_GC_THREAD_STATS
helpviewer_keywords: COR_GC_THREAD_STATS structure [.NET Framework hosting]
ms.assetid: 01f9a59b-7679-4d42-9ced-4a8981625c3d
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 10366d183ed7fd7386609e4c5726df0cea4e29a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="corgcthreadstats-structure"></a><span data-ttu-id="76117-102">COR_GC_THREAD_STATS (Estructura)</span><span class="sxs-lookup"><span data-stu-id="76117-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="76117-103">Contiene estadísticas por subproceso que pertenecen a la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="76117-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76117-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76117-104">Syntax</span></span>  
  
```  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;   
    ULONG      Flags;   
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="76117-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="76117-105">Members</span></span>  
  
|<span data-ttu-id="76117-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="76117-106">Member</span></span>|<span data-ttu-id="76117-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="76117-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="76117-108">El número de bytes de memoria asignada en el subproceso que está asociado con el actual `COR_GC_THREAD_STATS` instancia.</span><span class="sxs-lookup"><span data-stu-id="76117-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="76117-109">Este número se pone a cero cada vez que se produce una recolección de generación de cero.</span><span class="sxs-lookup"><span data-stu-id="76117-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="76117-110">El número de bytes había promocionado a una generación superior recolección las más recientes.</span><span class="sxs-lookup"><span data-stu-id="76117-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76117-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="76117-111">Remarks</span></span>  
 <span data-ttu-id="76117-112">[ICLRTask:: GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) toma un parámetro de salida de tipo `COR_GC_THREAD_STATS`.</span><span class="sxs-lookup"><span data-stu-id="76117-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76117-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="76117-113">Requirements</span></span>  
 <span data-ttu-id="76117-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76117-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76117-115">**Encabezado:** GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="76117-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="76117-116">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="76117-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="76117-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76117-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76117-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="76117-118">See Also</span></span>  
 [<span data-ttu-id="76117-119">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="76117-119">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [<span data-ttu-id="76117-120">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="76117-120">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
