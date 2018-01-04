---
title: IHostMalloc (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMAlloc
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMAlloc
helpviewer_keywords: IHostMAlloc interface [.NET Framework hosting]
ms.assetid: e3c6643b-6fc7-4a99-959d-4b7b4e63fdee
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e1690f5fe8f1417e6547ed94db8c71f079ebf5e6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmalloc-interface"></a><span data-ttu-id="b163d-102">IHostMalloc (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b163d-102">IHostMalloc Interface</span></span>
<span data-ttu-id="b163d-103">Proporciona métodos que permiten a common language runtime (CLR) para solicitar asignaciones concretas del montón a través del host.</span><span class="sxs-lookup"><span data-stu-id="b163d-103">Provides methods that allow the common language runtime (CLR) to request fine-grained allocations from the heap through the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b163d-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="b163d-104">Methods</span></span>  
  
|<span data-ttu-id="b163d-105">Método</span><span class="sxs-lookup"><span data-stu-id="b163d-105">Method</span></span>|<span data-ttu-id="b163d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b163d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b163d-107">Alloc (método)</span><span class="sxs-lookup"><span data-stu-id="b163d-107">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|<span data-ttu-id="b163d-108">Solicita que el host asigne la cantidad de memoria solicitada del montón.</span><span class="sxs-lookup"><span data-stu-id="b163d-108">Requests that the host allocate the requested amount of memory from the heap.</span></span>|  
|[<span data-ttu-id="b163d-109">DebugAlloc (método)</span><span class="sxs-lookup"><span data-stu-id="b163d-109">DebugAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|<span data-ttu-id="b163d-110">Solicita que el host de asignar la cantidad de memoria solicitada del montón y además realizar un seguimiento de dónde se ha asignado la memoria.</span><span class="sxs-lookup"><span data-stu-id="b163d-110">Requests that the host allocate the requested amount of memory from the heap, and additionally track where the memory was allocated.</span></span>|  
|[<span data-ttu-id="b163d-111">Free (método)</span><span class="sxs-lookup"><span data-stu-id="b163d-111">Free Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|<span data-ttu-id="b163d-112">Libera la memoria que se asignó utilizando el `Alloc` método.</span><span class="sxs-lookup"><span data-stu-id="b163d-112">Frees memory that was allocated by using the `Alloc` method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b163d-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b163d-113">Remarks</span></span>  
 <span data-ttu-id="b163d-114">CLR Obtiene un puntero de interfaz a una `IHostMalloc` instancia mediante una llamada a la [IHostMemoryManager:: CreateMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="b163d-114">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b163d-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b163d-115">Requirements</span></span>  
 <span data-ttu-id="b163d-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b163d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b163d-117">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b163d-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b163d-118">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b163d-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b163d-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b163d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b163d-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="b163d-120">See Also</span></span>  
 [<span data-ttu-id="b163d-121">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b163d-121">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="b163d-122">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="b163d-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
