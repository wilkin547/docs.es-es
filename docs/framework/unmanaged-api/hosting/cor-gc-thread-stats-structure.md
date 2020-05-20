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
ms.openlocfilehash: 88e81779fc9c20c506f3b0aa11ac2da3958dfe86
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616702"
---
# <a name="cor_gc_thread_stats-structure"></a><span data-ttu-id="b8533-102">COR_GC_THREAD_STATS (Estructura)</span><span class="sxs-lookup"><span data-stu-id="b8533-102">COR_GC_THREAD_STATS Structure</span></span>
<span data-ttu-id="b8533-103">Contiene estadísticas por subproceso relativas a la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b8533-103">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8533-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b8533-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;
    ULONG      Flags;
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a><span data-ttu-id="b8533-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="b8533-105">Members</span></span>  
  
|<span data-ttu-id="b8533-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="b8533-106">Member</span></span>|<span data-ttu-id="b8533-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8533-107">Description</span></span>|  
|------------|-----------------|  
|`PerThreadAllocation`|<span data-ttu-id="b8533-108">El número de bytes de memoria asignados en el subproceso que está asociado a la `COR_GC_THREAD_STATS` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="b8533-108">The number of bytes of memory allocated on the thread that is associated with the current `COR_GC_THREAD_STATS` instance.</span></span> <span data-ttu-id="b8533-109">Este número se borra a cero cada vez que se produce una recolección de elementos no utilizados de generación cero.</span><span class="sxs-lookup"><span data-stu-id="b8533-109">This number is cleared to zero each time a generation-zero garbage collection occurs.</span></span>|  
|`Flags`|<span data-ttu-id="b8533-110">Número de bytes promocionados a una generación superior en la recolección de elementos no utilizados más reciente.</span><span class="sxs-lookup"><span data-stu-id="b8533-110">The number of bytes promoted to a higher generation at the most recent garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8533-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b8533-111">Remarks</span></span>  
 <span data-ttu-id="b8533-112">[ICLRTask:: getmemstats (](iclrtask-getmemstats-method.md) toma un parámetro de salida de tipo `COR_GC_THREAD_STATS` .</span><span class="sxs-lookup"><span data-stu-id="b8533-112">[ICLRTask::GetMemStats](iclrtask-getmemstats-method.md) takes an output parameter of type `COR_GC_THREAD_STATS`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8533-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b8533-113">Requirements</span></span>  
 <span data-ttu-id="b8533-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8533-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8533-115">**Encabezado:** GCHost. idl</span><span class="sxs-lookup"><span data-stu-id="b8533-115">**Header:** GCHost.idl</span></span>  
  
 <span data-ttu-id="b8533-116">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b8533-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b8533-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8533-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8533-118">Consulta también</span><span class="sxs-lookup"><span data-stu-id="b8533-118">See also</span></span>

- [<span data-ttu-id="b8533-119">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="b8533-119">Hosting Structures</span></span>](hosting-structures.md)
- [<span data-ttu-id="b8533-120">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b8533-120">IHostTask Interface</span></span>](ihosttask-interface.md)
