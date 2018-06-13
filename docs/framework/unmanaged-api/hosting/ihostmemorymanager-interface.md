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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3edae4cb112f46643734c5f1612d9df36ad47e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441337"
---
# <a name="ihostmemorymanager-interface"></a><span data-ttu-id="7b981-102">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b981-102">IHostMemoryManager Interface</span></span>
<span data-ttu-id="7b981-103">Proporciona métodos que permiten a common language runtime (CLR) para realizar solicitudes de memoria virtual a través del host, en lugar de utilizar las funciones estándar de memoria virtual de Win32.</span><span class="sxs-lookup"><span data-stu-id="7b981-103">Provides methods that allow the common language runtime (CLR) to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7b981-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="7b981-104">Methods</span></span>  
  
|<span data-ttu-id="7b981-105">Método</span><span class="sxs-lookup"><span data-stu-id="7b981-105">Method</span></span>|<span data-ttu-id="7b981-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="7b981-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7b981-107">AcquiredVirtualAddressSpace (método)</span><span class="sxs-lookup"><span data-stu-id="7b981-107">AcquiredVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-acquiredvirtualaddressspace-method.md)|<span data-ttu-id="7b981-108">Notifica al host que common language runtime (CLR) ha adquirido la memoria especificada del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7b981-108">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>|  
|[<span data-ttu-id="7b981-109">CreateMAlloc (método)</span><span class="sxs-lookup"><span data-stu-id="7b981-109">CreateMAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|<span data-ttu-id="7b981-110">Obtiene un puntero de interfaz a una [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instancia que se usa para solicitar las asignaciones de memoria de un montón creado por el host.</span><span class="sxs-lookup"><span data-stu-id="7b981-110">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to request memory allocations from a heap created by the host.</span></span>|  
|[<span data-ttu-id="7b981-111">GetMemoryLoad (método)</span><span class="sxs-lookup"><span data-stu-id="7b981-111">GetMemoryLoad Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-getmemoryload-method.md)|<span data-ttu-id="7b981-112">Obtiene la cantidad de memoria física que se está usando actualmente, devuelto por el host.</span><span class="sxs-lookup"><span data-stu-id="7b981-112">Gets the amount of physical memory that is currently being used, as reported by the host.</span></span>|  
|[<span data-ttu-id="7b981-113">NeedsVirtualAddressSpace (método)</span><span class="sxs-lookup"><span data-stu-id="7b981-113">NeedsVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-needsvirtualaddressspace-method.md)|<span data-ttu-id="7b981-114">Notifica al host que el CLR se va a intentar utilizar la memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="7b981-114">Notifies the host that the CLR is going to attempt to use the specified memory.</span></span>|  
|[<span data-ttu-id="7b981-115">RegisterMemoryNotificationCallback (método)</span><span class="sxs-lookup"><span data-stu-id="7b981-115">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)|<span data-ttu-id="7b981-116">Registra un puntero a una función de devolución de llamada que el host invoca para notificar a CLR de la carga de memoria actual en el equipo.</span><span class="sxs-lookup"><span data-stu-id="7b981-116">Registers a pointer to a callback function that the host invokes to notify the CLR of the current memory load on the computer.</span></span>|  
|[<span data-ttu-id="7b981-117">ReleasedVirtualAddressSpace (método)</span><span class="sxs-lookup"><span data-stu-id="7b981-117">ReleasedVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-releasedvirtualaddressspace-method.md)|<span data-ttu-id="7b981-118">Notifica al host que CLR ha terminado de utilizar la memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="7b981-118">Notifies the host that the CLR has finished using the specified memory.</span></span>|  
|[<span data-ttu-id="7b981-119">VirtualAlloc (método)</span><span class="sxs-lookup"><span data-stu-id="7b981-119">VirtualAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md)|<span data-ttu-id="7b981-120">Actúa como un contenedor lógico para la función de Win32 correspondiente, que se reserva o confirma una región de páginas en el espacio de direcciones virtuales del proceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="7b981-120">Serves as a logical wrapper for the corresponding Win32 function, which reserves or commits a region of pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="7b981-121">VirtualFree (método)</span><span class="sxs-lookup"><span data-stu-id="7b981-121">VirtualFree Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualfree-method.md)|<span data-ttu-id="7b981-122">Actúa como un contenedor lógico para la función de Win32 correspondiente, que libera, anula el registro, o si libera y anula el registro de una región de páginas en el espacio de direcciones virtuales del proceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="7b981-122">Serves as a logical wrapper for the corresponding Win32 function, which releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="7b981-123">VirtualProtect (método)</span><span class="sxs-lookup"><span data-stu-id="7b981-123">VirtualProtect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualprotect-method.md)|<span data-ttu-id="7b981-124">Actúa como un contenedor lógico para la función de Win32 correspondiente, que cambia la protección en una región de páginas confirmadas en el espacio de direcciones virtuales del proceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="7b981-124">Serves as a logical wrapper for the corresponding Win32 function, which changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="7b981-125">VirtualQuery (método)</span><span class="sxs-lookup"><span data-stu-id="7b981-125">VirtualQuery Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualquery-method.md)|<span data-ttu-id="7b981-126">Actúa como un contenedor lógico para la función de Win32 correspondiente, que recupera información sobre un intervalo de páginas en el espacio de direcciones virtuales del proceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="7b981-126">Serves as a logical wrapper for the corresponding Win32 function, which retrieves information about a range of pages in the virtual address space of the calling process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b981-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7b981-127">Remarks</span></span>  
 <span data-ttu-id="7b981-128">`IHostMemoryManager` También proporciona métodos para el CLR obtener un puntero a través del cual para realizar solicitudes de memoria en el montón y obtener el nivel de presión de memoria en el proceso, tal y como informa el host.</span><span class="sxs-lookup"><span data-stu-id="7b981-128">`IHostMemoryManager` also provides methods for the CLR to obtain a pointer through which to make memory requests on the heap and to get the level of memory pressure in the process, as reported by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b981-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b981-129">Requirements</span></span>  
 <span data-ttu-id="7b981-130">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b981-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b981-131">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7b981-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7b981-132">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7b981-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7b981-133">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b981-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b981-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b981-134">See Also</span></span>  
 [<span data-ttu-id="7b981-135">IHostMalloc (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b981-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 [<span data-ttu-id="7b981-136">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="7b981-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
