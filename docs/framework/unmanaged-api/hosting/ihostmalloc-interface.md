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
ms.openlocfilehash: abc6cca185b318be016f92ac8c97d21f7af5940a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136777"
---
# <a name="ihostmalloc-interface"></a><span data-ttu-id="b321e-102">IHostMalloc (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b321e-102">IHostMalloc Interface</span></span>
<span data-ttu-id="b321e-103">Proporciona métodos que permiten que el Common Language Runtime (CLR) solicite asignaciones concretas del montón a través del host.</span><span class="sxs-lookup"><span data-stu-id="b321e-103">Provides methods that allow the common language runtime (CLR) to request fine-grained allocations from the heap through the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b321e-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="b321e-104">Methods</span></span>  
  
|<span data-ttu-id="b321e-105">Método</span><span class="sxs-lookup"><span data-stu-id="b321e-105">Method</span></span>|<span data-ttu-id="b321e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b321e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b321e-107">Alloc (método)</span><span class="sxs-lookup"><span data-stu-id="b321e-107">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|<span data-ttu-id="b321e-108">Solicita que el host asigne la cantidad de memoria solicitada del montón.</span><span class="sxs-lookup"><span data-stu-id="b321e-108">Requests that the host allocate the requested amount of memory from the heap.</span></span>|  
|[<span data-ttu-id="b321e-109">DebugAlloc (método)</span><span class="sxs-lookup"><span data-stu-id="b321e-109">DebugAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|<span data-ttu-id="b321e-110">Solicita que el host asigne la cantidad de memoria solicitada del montón y, además, realiza un seguimiento del lugar en el que se asignó la memoria.</span><span class="sxs-lookup"><span data-stu-id="b321e-110">Requests that the host allocate the requested amount of memory from the heap, and additionally track where the memory was allocated.</span></span>|  
|[<span data-ttu-id="b321e-111">Free (método)</span><span class="sxs-lookup"><span data-stu-id="b321e-111">Free Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|<span data-ttu-id="b321e-112">Libera la memoria asignada mediante el método `Alloc`.</span><span class="sxs-lookup"><span data-stu-id="b321e-112">Frees memory that was allocated by using the `Alloc` method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b321e-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b321e-113">Remarks</span></span>  
 <span data-ttu-id="b321e-114">CLR obtiene un puntero de interfaz a una instancia de `IHostMalloc` llamando al método [IHostMemoryManager:: CreateMAlloc (](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b321e-114">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b321e-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b321e-115">Requirements</span></span>  
 <span data-ttu-id="b321e-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b321e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b321e-117">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b321e-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b321e-118">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b321e-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b321e-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b321e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b321e-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="b321e-120">See also</span></span>

- [<span data-ttu-id="b321e-121">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b321e-121">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="b321e-122">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="b321e-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
