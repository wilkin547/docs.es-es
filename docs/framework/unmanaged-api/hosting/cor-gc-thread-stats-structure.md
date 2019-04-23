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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f60a4b56270318a05d0e5a480fdb56eb45593d5e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177741"
---
# <a name="corgcthreadstats-structure"></a><span data-ttu-id="7bd34-102">COR_GC_THREAD_STATS (Estructura)</span><span class="sxs-lookup"><span data-stu-id="7bd34-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="7bd34-103">Contiene estadísticas por subproceso que pertenecen a la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="7bd34-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bd34-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7bd34-104">Syntax</span></span>  
  
```  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;   
    ULONG      Flags;   
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="7bd34-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="7bd34-105">Members</span></span>  
  
|<span data-ttu-id="7bd34-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="7bd34-106">Member</span></span>|<span data-ttu-id="7bd34-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="7bd34-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="7bd34-108">El número de bytes de memoria asignada en el subproceso que está asociado con el actual `COR_GC_THREAD_STATS` instancia.</span><span class="sxs-lookup"><span data-stu-id="7bd34-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="7bd34-109">Este número se pone a cero cada vez que se produce una recolección de generación de cero.</span><span class="sxs-lookup"><span data-stu-id="7bd34-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="7bd34-110">El número de bytes promueve a una generación superior recolección las más recientes.</span><span class="sxs-lookup"><span data-stu-id="7bd34-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7bd34-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7bd34-111">Remarks</span></span>  
 <span data-ttu-id="7bd34-112">[ICLRTask:: GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) toma un parámetro de salida de tipo `COR_GC_THREAD_STATS`.</span><span class="sxs-lookup"><span data-stu-id="7bd34-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bd34-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7bd34-113">Requirements</span></span>  
 <span data-ttu-id="7bd34-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7bd34-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bd34-115">**Encabezado**: GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="7bd34-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="7bd34-116">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7bd34-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7bd34-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bd34-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bd34-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="7bd34-118">See also</span></span>

- [<span data-ttu-id="7bd34-119">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="7bd34-119">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="7bd34-120">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7bd34-120">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
