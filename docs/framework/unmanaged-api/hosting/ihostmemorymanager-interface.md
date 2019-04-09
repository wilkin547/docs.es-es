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
ms.openlocfilehash: 57f34ed1796f6fa411d31fca83baeff693f85d70
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137363"
---
# <a name="ihostmemorymanager-interface"></a><span data-ttu-id="80658-102">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="80658-102">IHostMemoryManager Interface</span></span>
<span data-ttu-id="80658-103">Proporciona métodos que permiten a common language runtime (CLR) para realizar solicitudes de memoria virtual a través del host, en lugar de usar las funciones de memoria virtual estándar de Win32.</span><span class="sxs-lookup"><span data-stu-id="80658-103">Provides methods that allow the common language runtime (CLR) to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="80658-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="80658-104">Methods</span></span>  
  
|<span data-ttu-id="80658-105">Método</span><span class="sxs-lookup"><span data-stu-id="80658-105">Method</span></span>|<span data-ttu-id="80658-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="80658-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="80658-107">Método AcquiredVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="80658-107">AcquiredVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-acquiredvirtualaddressspace-method.md)|<span data-ttu-id="80658-108">Notifica al host que common language runtime (CLR) ha adquirido la memoria especificada desde el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="80658-108">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>|  
|[<span data-ttu-id="80658-109">Método CreateMAlloc</span><span class="sxs-lookup"><span data-stu-id="80658-109">CreateMAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|<span data-ttu-id="80658-110">Obtiene un puntero de interfaz a un [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instancia que se usa para solicitar las asignaciones de memoria de un montón creado por el host.</span><span class="sxs-lookup"><span data-stu-id="80658-110">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to request memory allocations from a heap created by the host.</span></span>|  
|[<span data-ttu-id="80658-111">Método GetMemoryLoad</span><span class="sxs-lookup"><span data-stu-id="80658-111">GetMemoryLoad Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-getmemoryload-method.md)|<span data-ttu-id="80658-112">Obtiene la cantidad de memoria física que se está usando actualmente, devuelto por el host.</span><span class="sxs-lookup"><span data-stu-id="80658-112">Gets the amount of physical memory that is currently being used, as reported by the host.</span></span>|  
|[<span data-ttu-id="80658-113">Método NeedsVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="80658-113">NeedsVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-needsvirtualaddressspace-method.md)|<span data-ttu-id="80658-114">Notifica al host que el CLR se va a intentar usar la memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="80658-114">Notifies the host that the CLR is going to attempt to use the specified memory.</span></span>|  
|[<span data-ttu-id="80658-115">Método RegisterMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="80658-115">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)|<span data-ttu-id="80658-116">Registra un puntero a una función de devolución de llamada que el host invoca para notificar al CLR de la carga de memoria actual en el equipo.</span><span class="sxs-lookup"><span data-stu-id="80658-116">Registers a pointer to a callback function that the host invokes to notify the CLR of the current memory load on the computer.</span></span>|  
|[<span data-ttu-id="80658-117">Método ReleasedVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="80658-117">ReleasedVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-releasedvirtualaddressspace-method.md)|<span data-ttu-id="80658-118">Notifica al host que CLR ha terminado de utilizar la memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="80658-118">Notifies the host that the CLR has finished using the specified memory.</span></span>|  
|[<span data-ttu-id="80658-119">Método VirtualAlloc</span><span class="sxs-lookup"><span data-stu-id="80658-119">VirtualAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md)|<span data-ttu-id="80658-120">Actúa como un contenedor lógico para la función de Win32 correspondiente, que se reserva o confirma una región de páginas en el espacio de direcciones virtuales del proceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="80658-120">Serves as a logical wrapper for the corresponding Win32 function, which reserves or commits a region of pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="80658-121">Método VirtualFree</span><span class="sxs-lookup"><span data-stu-id="80658-121">VirtualFree Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualfree-method.md)|<span data-ttu-id="80658-122">Actúa como un contenedor lógico para la función de Win32 correspondiente, que libera, anula el registro, o si libera y anula una región de páginas dentro del espacio de direcciones virtuales del proceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="80658-122">Serves as a logical wrapper for the corresponding Win32 function, which releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="80658-123">Método VirtualProtect</span><span class="sxs-lookup"><span data-stu-id="80658-123">VirtualProtect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualprotect-method.md)|<span data-ttu-id="80658-124">Actúa como un contenedor lógico para la función de Win32 correspondiente, que cambia la protección en una región de páginas confirmadas en el espacio de direcciones virtuales del proceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="80658-124">Serves as a logical wrapper for the corresponding Win32 function, which changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="80658-125">Método VirtualQuery</span><span class="sxs-lookup"><span data-stu-id="80658-125">VirtualQuery Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualquery-method.md)|<span data-ttu-id="80658-126">Actúa como un contenedor lógico para la función de Win32 correspondiente, que recupera información sobre un intervalo de páginas en el espacio de direcciones virtuales del proceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="80658-126">Serves as a logical wrapper for the corresponding Win32 function, which retrieves information about a range of pages in the virtual address space of the calling process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80658-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="80658-127">Remarks</span></span>  
 `IHostMemoryManager` <span data-ttu-id="80658-128">También proporciona métodos de CLR para obtener un puntero a través de la que se deben realizar solicitudes de memoria en el montón y obtener el nivel de presión de memoria en el proceso, notificado por el host.</span><span class="sxs-lookup"><span data-stu-id="80658-128">also provides methods for the CLR to obtain a pointer through which to make memory requests on the heap and to get the level of memory pressure in the process, as reported by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80658-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="80658-129">Requirements</span></span>  
 <span data-ttu-id="80658-130">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80658-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80658-131">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="80658-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="80658-132">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="80658-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="80658-133">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="80658-133">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="80658-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="80658-134">See also</span></span>

- [<span data-ttu-id="80658-135">IHostMalloc (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="80658-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
- [<span data-ttu-id="80658-136">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="80658-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
