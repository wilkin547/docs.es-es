---
title: IHostMemoryManager (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostMemoryManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager
helpviewer_keywords:
- IHostMemoryManager interface [.NET Framework hosting]
ms.assetid: a945d439-3b34-4aa4-b575-8413dd7806ce
topic_type:
- apiref
ms.openlocfilehash: bc05d76795f20d28d6d2899d61dc4674ebfdca8c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128649"
---
# <a name="ihostmemorymanager-interface"></a><span data-ttu-id="9efbc-102">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9efbc-102">IHostMemoryManager Interface</span></span>
<span data-ttu-id="9efbc-103">Proporciona métodos que permiten que el Common Language Runtime (CLR) realice solicitudes de memoria virtual a través del host, en lugar de usar las funciones estándar de memoria virtual de Win32.</span><span class="sxs-lookup"><span data-stu-id="9efbc-103">Provides methods that allow the common language runtime (CLR) to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9efbc-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="9efbc-104">Methods</span></span>  
  
|<span data-ttu-id="9efbc-105">Método</span><span class="sxs-lookup"><span data-stu-id="9efbc-105">Method</span></span>|<span data-ttu-id="9efbc-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="9efbc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9efbc-107">AcquiredVirtualAddressSpace (método)</span><span class="sxs-lookup"><span data-stu-id="9efbc-107">AcquiredVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-acquiredvirtualaddressspace-method.md)|<span data-ttu-id="9efbc-108">Notifica al host que el Common Language Runtime (CLR) ha adquirido la memoria especificada del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="9efbc-108">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>|  
|[<span data-ttu-id="9efbc-109">CreateMAlloc (método)</span><span class="sxs-lookup"><span data-stu-id="9efbc-109">CreateMAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|<span data-ttu-id="9efbc-110">Obtiene un puntero de interfaz a una instancia de [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) que se utiliza para solicitar las asignaciones de memoria de un montón creado por el host.</span><span class="sxs-lookup"><span data-stu-id="9efbc-110">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to request memory allocations from a heap created by the host.</span></span>|  
|[<span data-ttu-id="9efbc-111">GetMemoryLoad (método)</span><span class="sxs-lookup"><span data-stu-id="9efbc-111">GetMemoryLoad Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-getmemoryload-method.md)|<span data-ttu-id="9efbc-112">Obtiene la cantidad de memoria física que se está usando actualmente, tal y como la ha proporcionado el host.</span><span class="sxs-lookup"><span data-stu-id="9efbc-112">Gets the amount of physical memory that is currently being used, as reported by the host.</span></span>|  
|[<span data-ttu-id="9efbc-113">NeedsVirtualAddressSpace (método)</span><span class="sxs-lookup"><span data-stu-id="9efbc-113">NeedsVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-needsvirtualaddressspace-method.md)|<span data-ttu-id="9efbc-114">Notifica al host que el CLR va a intentar usar la memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="9efbc-114">Notifies the host that the CLR is going to attempt to use the specified memory.</span></span>|  
|[<span data-ttu-id="9efbc-115">RegisterMemoryNotificationCallback (método)</span><span class="sxs-lookup"><span data-stu-id="9efbc-115">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)|<span data-ttu-id="9efbc-116">Registra un puntero a una función de devolución de llamada que invoca el host para notificar a CLR la carga de memoria actual en el equipo.</span><span class="sxs-lookup"><span data-stu-id="9efbc-116">Registers a pointer to a callback function that the host invokes to notify the CLR of the current memory load on the computer.</span></span>|  
|[<span data-ttu-id="9efbc-117">ReleasedVirtualAddressSpace (método)</span><span class="sxs-lookup"><span data-stu-id="9efbc-117">ReleasedVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-releasedvirtualaddressspace-method.md)|<span data-ttu-id="9efbc-118">Notifica al host que el CLR ha terminado de usar la memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="9efbc-118">Notifies the host that the CLR has finished using the specified memory.</span></span>|  
|[<span data-ttu-id="9efbc-119">VirtualAlloc (método)</span><span class="sxs-lookup"><span data-stu-id="9efbc-119">VirtualAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md)|<span data-ttu-id="9efbc-120">Actúa como contenedor lógico de la función de Win32 correspondiente, que reserva o confirma una región de páginas en el espacio de direcciones virtuales del proceso de llamada.</span><span class="sxs-lookup"><span data-stu-id="9efbc-120">Serves as a logical wrapper for the corresponding Win32 function, which reserves or commits a region of pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="9efbc-121">VirtualFree (método)</span><span class="sxs-lookup"><span data-stu-id="9efbc-121">VirtualFree Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualfree-method.md)|<span data-ttu-id="9efbc-122">Actúa como un contenedor lógico para la función de Win32 correspondiente, que libera, anula o libera y anula la confirmación de una región de páginas dentro del espacio de direcciones virtuales del proceso de llamada.</span><span class="sxs-lookup"><span data-stu-id="9efbc-122">Serves as a logical wrapper for the corresponding Win32 function, which releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="9efbc-123">VirtualProtect (método)</span><span class="sxs-lookup"><span data-stu-id="9efbc-123">VirtualProtect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualprotect-method.md)|<span data-ttu-id="9efbc-124">Actúa como contenedor lógico de la función de Win32 correspondiente, que cambia la protección en una región de páginas confirmadas en el espacio de direcciones virtuales del proceso de llamada.</span><span class="sxs-lookup"><span data-stu-id="9efbc-124">Serves as a logical wrapper for the corresponding Win32 function, which changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="9efbc-125">VirtualQuery (método)</span><span class="sxs-lookup"><span data-stu-id="9efbc-125">VirtualQuery Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualquery-method.md)|<span data-ttu-id="9efbc-126">Actúa como contenedor lógico de la función de Win32 correspondiente, que recupera información sobre un intervalo de páginas en el espacio de direcciones virtuales del proceso de llamada.</span><span class="sxs-lookup"><span data-stu-id="9efbc-126">Serves as a logical wrapper for the corresponding Win32 function, which retrieves information about a range of pages in the virtual address space of the calling process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9efbc-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9efbc-127">Remarks</span></span>  
 <span data-ttu-id="9efbc-128">`IHostMemoryManager` también proporciona métodos para que CLR obtenga un puntero a través del cual se realizan solicitudes de memoria en el montón y para obtener el nivel de presión de memoria en el proceso, tal y como lo indica el host.</span><span class="sxs-lookup"><span data-stu-id="9efbc-128">`IHostMemoryManager` also provides methods for the CLR to obtain a pointer through which to make memory requests on the heap and to get the level of memory pressure in the process, as reported by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9efbc-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9efbc-129">Requirements</span></span>  
 <span data-ttu-id="9efbc-130">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9efbc-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9efbc-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9efbc-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9efbc-132">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9efbc-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9efbc-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9efbc-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9efbc-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="9efbc-134">See also</span></span>

- [<span data-ttu-id="9efbc-135">IHostMalloc (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9efbc-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
- [<span data-ttu-id="9efbc-136">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="9efbc-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
