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
ms.openlocfilehash: bbf889aaa6a78e67d0f08758adc0bf31cd932e88
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441353"
---
# <a name="ihostmalloc-interface"></a><span data-ttu-id="deab8-102">IHostMalloc (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="deab8-102">IHostMalloc Interface</span></span>
<span data-ttu-id="deab8-103">Proporciona métodos que permiten a common language runtime (CLR) para solicitar asignaciones concretas del montón a través del host.</span><span class="sxs-lookup"><span data-stu-id="deab8-103">Provides methods that allow the common language runtime (CLR) to request fine-grained allocations from the heap through the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="deab8-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="deab8-104">Methods</span></span>  
  
|<span data-ttu-id="deab8-105">Método</span><span class="sxs-lookup"><span data-stu-id="deab8-105">Method</span></span>|<span data-ttu-id="deab8-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="deab8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="deab8-107">Alloc (método)</span><span class="sxs-lookup"><span data-stu-id="deab8-107">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|<span data-ttu-id="deab8-108">Solicita que el host asigne la cantidad de memoria solicitada del montón.</span><span class="sxs-lookup"><span data-stu-id="deab8-108">Requests that the host allocate the requested amount of memory from the heap.</span></span>|  
|[<span data-ttu-id="deab8-109">DebugAlloc (método)</span><span class="sxs-lookup"><span data-stu-id="deab8-109">DebugAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|<span data-ttu-id="deab8-110">Solicita que el host de asignar la cantidad de memoria solicitada del montón y además realizar un seguimiento de dónde se ha asignado la memoria.</span><span class="sxs-lookup"><span data-stu-id="deab8-110">Requests that the host allocate the requested amount of memory from the heap, and additionally track where the memory was allocated.</span></span>|  
|[<span data-ttu-id="deab8-111">Free (método)</span><span class="sxs-lookup"><span data-stu-id="deab8-111">Free Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|<span data-ttu-id="deab8-112">Libera la memoria que se asignó utilizando el `Alloc` método.</span><span class="sxs-lookup"><span data-stu-id="deab8-112">Frees memory that was allocated by using the `Alloc` method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="deab8-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="deab8-113">Remarks</span></span>  
 <span data-ttu-id="deab8-114">CLR Obtiene un puntero de interfaz a una `IHostMalloc` instancia mediante una llamada a la [IHostMemoryManager:: CreateMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="deab8-114">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="deab8-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="deab8-115">Requirements</span></span>  
 <span data-ttu-id="deab8-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="deab8-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="deab8-117">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="deab8-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="deab8-118">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="deab8-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="deab8-119">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="deab8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="deab8-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="deab8-120">See Also</span></span>  
 [<span data-ttu-id="deab8-121">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="deab8-121">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="deab8-122">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="deab8-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
