---
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
ms.openlocfilehash: 2530c7fcd63f81b566d6623a533bd8e2af084047
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702165"
---
# <a name="ihostmalloc-interface"></a><span data-ttu-id="1afb1-102">IHostMalloc (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1afb1-102">IHostMalloc Interface</span></span>

<span data-ttu-id="1afb1-103">Proporciona métodos que permiten que el Common Language Runtime (CLR) solicite asignaciones concretas del montón a través del host.</span><span class="sxs-lookup"><span data-stu-id="1afb1-103">Provides methods that allow the common language runtime (CLR) to request fine-grained allocations from the heap through the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1afb1-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="1afb1-104">Methods</span></span>  
  
|<span data-ttu-id="1afb1-105">Método</span><span class="sxs-lookup"><span data-stu-id="1afb1-105">Method</span></span>|<span data-ttu-id="1afb1-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="1afb1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1afb1-107">Alloc (Método)</span><span class="sxs-lookup"><span data-stu-id="1afb1-107">Alloc Method</span></span>](ihostmalloc-alloc-method.md)|<span data-ttu-id="1afb1-108">Solicita que el host asigne la cantidad de memoria solicitada del montón.</span><span class="sxs-lookup"><span data-stu-id="1afb1-108">Requests that the host allocate the requested amount of memory from the heap.</span></span>|  
|[<span data-ttu-id="1afb1-109">Método DebugAlloc</span><span class="sxs-lookup"><span data-stu-id="1afb1-109">DebugAlloc Method</span></span>](ihostmalloc-debugalloc-method.md)|<span data-ttu-id="1afb1-110">Solicita que el host asigne la cantidad de memoria solicitada del montón y, además, realiza un seguimiento del lugar en el que se asignó la memoria.</span><span class="sxs-lookup"><span data-stu-id="1afb1-110">Requests that the host allocate the requested amount of memory from the heap, and additionally track where the memory was allocated.</span></span>|  
|[<span data-ttu-id="1afb1-111">Método Free</span><span class="sxs-lookup"><span data-stu-id="1afb1-111">Free Method</span></span>](ihostmalloc-free-method.md)|<span data-ttu-id="1afb1-112">Libera la memoria asignada mediante el `Alloc` método.</span><span class="sxs-lookup"><span data-stu-id="1afb1-112">Frees memory that was allocated by using the `Alloc` method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1afb1-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1afb1-113">Remarks</span></span>  

 <span data-ttu-id="1afb1-114">CLR obtiene un puntero de interfaz a una `IHostMalloc` instancia llamando al método [IHostMemoryManager:: CreateMAlloc (](ihostmemorymanager-createmalloc-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1afb1-114">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1afb1-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1afb1-115">Requirements</span></span>  

 <span data-ttu-id="1afb1-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1afb1-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1afb1-117">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1afb1-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1afb1-118">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1afb1-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1afb1-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1afb1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1afb1-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1afb1-120">See also</span></span>

- [<span data-ttu-id="1afb1-121">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1afb1-121">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="1afb1-122">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="1afb1-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
