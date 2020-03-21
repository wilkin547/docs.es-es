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
ms.openlocfilehash: 64e0c466edcd8863244e6ed184c18422b5f66875
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178263"
---
# <a name="cor_gc_thread_stats-structure"></a><span data-ttu-id="0ac19-102">COR_GC_THREAD_STATS (Estructura)</span><span class="sxs-lookup"><span data-stu-id="0ac19-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="0ac19-103">Contiene estadísticas por subproceso pertenecientes a la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="0ac19-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ac19-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0ac19-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;
    ULONG      Flags;
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="0ac19-105">Members</span><span class="sxs-lookup"><span data-stu-id="0ac19-105">Members</span></span>  
  
|<span data-ttu-id="0ac19-106">Member</span><span class="sxs-lookup"><span data-stu-id="0ac19-106">Member</span></span>|<span data-ttu-id="0ac19-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ac19-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="0ac19-108">El número de bytes de memoria asignados en `COR_GC_THREAD_STATS` el subproceso asociado a la instancia actual.</span><span class="sxs-lookup"><span data-stu-id="0ac19-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="0ac19-109">Este número se borra a cero cada vez que se produce una recolección de elementos no utilizados de generación cero.</span><span class="sxs-lookup"><span data-stu-id="0ac19-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="0ac19-110">El número de bytes promovidos a una generación superior en la recolección de elementos no utilizados más reciente.</span><span class="sxs-lookup"><span data-stu-id="0ac19-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ac19-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0ac19-111">Remarks</span></span>  
 <span data-ttu-id="0ac19-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) toma un parámetro `COR_GC_THREAD_STATS`de salida de tipo .</span><span class="sxs-lookup"><span data-stu-id="0ac19-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ac19-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0ac19-113">Requirements</span></span>  
 <span data-ttu-id="0ac19-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ac19-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ac19-115">**Encabezado:** GCHost.idl</span><span class="sxs-lookup"><span data-stu-id="0ac19-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="0ac19-116">**Biblioteca:** Incluido como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0ac19-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ac19-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ac19-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ac19-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0ac19-118">See also</span></span>

- [<span data-ttu-id="0ac19-119">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="0ac19-119">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="0ac19-120">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0ac19-120">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
