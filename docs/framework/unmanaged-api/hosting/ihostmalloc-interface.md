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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f2a7a29ef1dc85c2ad554995286e5137fcb104be
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136419"
---
# <a name="ihostmalloc-interface"></a><span data-ttu-id="93005-102">IHostMalloc (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="93005-102">IHostMalloc Interface</span></span>
<span data-ttu-id="93005-103">Proporciona métodos que permiten a common language runtime (CLR) para solicitar asignaciones concretas del montón a través del host.</span><span class="sxs-lookup"><span data-stu-id="93005-103">Provides methods that allow the common language runtime (CLR) to request fine-grained allocations from the heap through the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="93005-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="93005-104">Methods</span></span>  
  
|<span data-ttu-id="93005-105">Método</span><span class="sxs-lookup"><span data-stu-id="93005-105">Method</span></span>|<span data-ttu-id="93005-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="93005-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="93005-107">Método Alloc</span><span class="sxs-lookup"><span data-stu-id="93005-107">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|<span data-ttu-id="93005-108">Solicita que el host de asignar la cantidad de memoria del montón.</span><span class="sxs-lookup"><span data-stu-id="93005-108">Requests that the host allocate the requested amount of memory from the heap.</span></span>|  
|[<span data-ttu-id="93005-109">Método DebugAlloc</span><span class="sxs-lookup"><span data-stu-id="93005-109">DebugAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|<span data-ttu-id="93005-110">Solicita que el host de asignar la cantidad de memoria del montón y además realizar un seguimiento de dónde se ha asignado la memoria.</span><span class="sxs-lookup"><span data-stu-id="93005-110">Requests that the host allocate the requested amount of memory from the heap, and additionally track where the memory was allocated.</span></span>|  
|[<span data-ttu-id="93005-111">Método Free</span><span class="sxs-lookup"><span data-stu-id="93005-111">Free Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|<span data-ttu-id="93005-112">Libera la memoria que se asignó utilizando el `Alloc` método.</span><span class="sxs-lookup"><span data-stu-id="93005-112">Frees memory that was allocated by using the `Alloc` method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93005-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="93005-113">Remarks</span></span>  
 <span data-ttu-id="93005-114">CLR Obtiene un puntero de interfaz a un `IHostMalloc` instancia mediante una llamada a la [IHostMemoryManager:: CreateMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="93005-114">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93005-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="93005-115">Requirements</span></span>  
 <span data-ttu-id="93005-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93005-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93005-117">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="93005-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="93005-118">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="93005-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="93005-119">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="93005-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="93005-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="93005-120">See also</span></span>

- [<span data-ttu-id="93005-121">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="93005-121">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="93005-122">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="93005-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
