---
description: 'Más información acerca de: IHostMalloc (interfaz)'
title: IHostMalloc (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc
helpviewer_keywords:
- IHostMAlloc interface [.NET Framework hosting]
ms.assetid: e3c6643b-6fc7-4a99-959d-4b7b4e63fdee
topic_type:
- apiref
ms.openlocfilehash: cd04a0f71fd429ea10b9edcce02806f4afa57148
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708182"
---
# <a name="ihostmalloc-interface"></a><span data-ttu-id="391e0-103">IHostMalloc (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="391e0-103">IHostMalloc Interface</span></span>

<span data-ttu-id="391e0-104">Proporciona métodos que permiten que el Common Language Runtime (CLR) solicite asignaciones concretas del montón a través del host.</span><span class="sxs-lookup"><span data-stu-id="391e0-104">Provides methods that allow the common language runtime (CLR) to request fine-grained allocations from the heap through the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="391e0-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="391e0-105">Methods</span></span>  
  
|<span data-ttu-id="391e0-106">Método</span><span class="sxs-lookup"><span data-stu-id="391e0-106">Method</span></span>|<span data-ttu-id="391e0-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="391e0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="391e0-108">Alloc (Método)</span><span class="sxs-lookup"><span data-stu-id="391e0-108">Alloc Method</span></span>](ihostmalloc-alloc-method.md)|<span data-ttu-id="391e0-109">Solicita que el host asigne la cantidad de memoria solicitada del montón.</span><span class="sxs-lookup"><span data-stu-id="391e0-109">Requests that the host allocate the requested amount of memory from the heap.</span></span>|  
|[<span data-ttu-id="391e0-110">Método DebugAlloc</span><span class="sxs-lookup"><span data-stu-id="391e0-110">DebugAlloc Method</span></span>](ihostmalloc-debugalloc-method.md)|<span data-ttu-id="391e0-111">Solicita que el host asigne la cantidad de memoria solicitada del montón y, además, realiza un seguimiento del lugar en el que se asignó la memoria.</span><span class="sxs-lookup"><span data-stu-id="391e0-111">Requests that the host allocate the requested amount of memory from the heap, and additionally track where the memory was allocated.</span></span>|  
|[<span data-ttu-id="391e0-112">Método Free</span><span class="sxs-lookup"><span data-stu-id="391e0-112">Free Method</span></span>](ihostmalloc-free-method.md)|<span data-ttu-id="391e0-113">Libera la memoria asignada mediante el `Alloc` método.</span><span class="sxs-lookup"><span data-stu-id="391e0-113">Frees memory that was allocated by using the `Alloc` method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="391e0-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="391e0-114">Remarks</span></span>  

 <span data-ttu-id="391e0-115">CLR obtiene un puntero de interfaz a una `IHostMalloc` instancia llamando al método [IHostMemoryManager:: CreateMAlloc (](ihostmemorymanager-createmalloc-method.md) .</span><span class="sxs-lookup"><span data-stu-id="391e0-115">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="391e0-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="391e0-116">Requirements</span></span>  

 <span data-ttu-id="391e0-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="391e0-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="391e0-118">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="391e0-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="391e0-119">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="391e0-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="391e0-120">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="391e0-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="391e0-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="391e0-121">See also</span></span>

- [<span data-ttu-id="391e0-122">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="391e0-122">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="391e0-123">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="391e0-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
