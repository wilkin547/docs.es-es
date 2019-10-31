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
ms.openlocfilehash: 37da471aaa8e9f802a8430d7b3289b375ff1b40a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136982"
---
# <a name="cor_gc_thread_stats-structure"></a><span data-ttu-id="0ebd1-102">COR_GC_THREAD_STATS (Estructura)</span><span class="sxs-lookup"><span data-stu-id="0ebd1-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="0ebd1-103">Contiene estadísticas por subproceso relativas a la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="0ebd1-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ebd1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0ebd1-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;   
    ULONG      Flags;   
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="0ebd1-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="0ebd1-105">Members</span></span>  
  
|<span data-ttu-id="0ebd1-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="0ebd1-106">Member</span></span>|<span data-ttu-id="0ebd1-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ebd1-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="0ebd1-108">Número de bytes de memoria asignados en el subproceso asociado a la instancia de `COR_GC_THREAD_STATS` actual.</span><span class="sxs-lookup"><span data-stu-id="0ebd1-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="0ebd1-109">Este número se borra a cero cada vez que se produce una recolección de elementos no utilizados de generación cero.</span><span class="sxs-lookup"><span data-stu-id="0ebd1-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="0ebd1-110">Número de bytes promocionados a una generación superior en la recolección de elementos no utilizados más reciente.</span><span class="sxs-lookup"><span data-stu-id="0ebd1-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ebd1-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0ebd1-111">Remarks</span></span>  
 <span data-ttu-id="0ebd1-112">[ICLRTask:: getmemstats (](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) toma un parámetro de salida de tipo `COR_GC_THREAD_STATS`.</span><span class="sxs-lookup"><span data-stu-id="0ebd1-112">[ICLRTask::GetMemStats](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ebd1-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0ebd1-113">Requirements</span></span>  
 <span data-ttu-id="0ebd1-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ebd1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ebd1-115">**Encabezado:** GCHost. idl</span><span class="sxs-lookup"><span data-stu-id="0ebd1-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="0ebd1-116">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0ebd1-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ebd1-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ebd1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ebd1-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ebd1-118">See also</span></span>

- [<span data-ttu-id="0ebd1-119">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="0ebd1-119">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="0ebd1-120">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0ebd1-120">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
