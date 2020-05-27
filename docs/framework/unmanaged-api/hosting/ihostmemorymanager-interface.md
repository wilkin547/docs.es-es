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
ms.openlocfilehash: 4e7e76a4a3ab291ee97ad0912e3d6224cdf96fba
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804486"
---
# <a name="ihostmemorymanager-interface"></a><span data-ttu-id="8e9f4-102">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8e9f4-102">IHostMemoryManager Interface</span></span>
<span data-ttu-id="8e9f4-103">Proporciona métodos que permiten que el Common Language Runtime (CLR) realice solicitudes de memoria virtual a través del host, en lugar de usar las funciones estándar de memoria virtual de Win32.</span><span class="sxs-lookup"><span data-stu-id="8e9f4-103">Provides methods that allow the common language runtime (CLR) to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8e9f4-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="8e9f4-104">Methods</span></span>  
  
|<span data-ttu-id="8e9f4-105">Método</span><span class="sxs-lookup"><span data-stu-id="8e9f4-105">Method</span></span>|<span data-ttu-id="8e9f4-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e9f4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8e9f4-107">Método AcquiredVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="8e9f4-107">AcquiredVirtualAddressSpace Method</span></span>](ihostmemorymanager-acquiredvirtualaddressspace-method.md)|<span data-ttu-id="8e9f4-108">Notifica al host que el Common Language Runtime (CLR) ha adquirido la memoria especificada del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="8e9f4-108">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>|  
|[<span data-ttu-id="8e9f4-109">Método CreateMAlloc</span><span class="sxs-lookup"><span data-stu-id="8e9f4-109">CreateMAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|<span data-ttu-id="8e9f4-110">Obtiene un puntero de interfaz a una instancia de [IHostMAlloc](ihostmalloc-interface.md) que se utiliza para solicitar las asignaciones de memoria de un montón creado por el host.</span><span class="sxs-lookup"><span data-stu-id="8e9f4-110">Gets an interface pointer to an [IHostMAlloc](ihostmalloc-interface.md) instance that is used to request memory allocations from a heap created by the host.</span></span>|  
|[<span data-ttu-id="8e9f4-111">Método GetMemoryLoad</span><span class="sxs-lookup"><span data-stu-id="8e9f4-111">GetMemoryLoad Method</span></span>](ihostmemorymanager-getmemoryload-method.md)|<span data-ttu-id="8e9f4-112">Obtiene la cantidad de memoria física que se está usando actualmente, tal y como la ha proporcionado el host.</span><span class="sxs-lookup"><span data-stu-id="8e9f4-112">Gets the amount of physical memory that is currently being used, as reported by the host.</span></span>|  
|[<span data-ttu-id="8e9f4-113">Método NeedsVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="8e9f4-113">NeedsVirtualAddressSpace Method</span></span>](ihostmemorymanager-needsvirtualaddressspace-method.md)|<span data-ttu-id="8e9f4-114">Notifica al host que el CLR va a intentar usar la memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="8e9f4-114">Notifies the host that the CLR is going to attempt to use the specified memory.</span></span>|  
|[<span data-ttu-id="8e9f4-115">Método RegisterMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="8e9f4-115">RegisterMemoryNotificationCallback Method</span></span>](ihostmemorymanager-registermemorynotificationcallback-method.md)|<span data-ttu-id="8e9f4-116">Registra un puntero a una función de devolución de llamada que invoca el host para notificar a CLR la carga de memoria actual en el equipo.</span><span class="sxs-lookup"><span data-stu-id="8e9f4-116">Registers a pointer to a callback function that the host invokes to notify the CLR of the current memory load on the computer.</span></span>|  
|[<span data-ttu-id="8e9f4-117">Método ReleasedVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="8e9f4-117">ReleasedVirtualAddressSpace Method</span></span>](ihostmemorymanager-releasedvirtualaddressspace-method.md)|<span data-ttu-id="8e9f4-118">Notifica al host que el CLR ha terminado de usar la memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="8e9f4-118">Notifies the host that the CLR has finished using the specified memory.</span></span>|  
|[<span data-ttu-id="8e9f4-119">Método VirtualAlloc</span><span class="sxs-lookup"><span data-stu-id="8e9f4-119">VirtualAlloc Method</span></span>](ihostmemorymanager-virtualalloc-method.md)|<span data-ttu-id="8e9f4-120">Actúa como contenedor lógico de la función de Win32 correspondiente, que reserva o confirma una región de páginas en el espacio de direcciones virtuales del proceso de llamada.</span><span class="sxs-lookup"><span data-stu-id="8e9f4-120">Serves as a logical wrapper for the corresponding Win32 function, which reserves or commits a region of pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="8e9f4-121">Método VirtualFree</span><span class="sxs-lookup"><span data-stu-id="8e9f4-121">VirtualFree Method</span></span>](ihostmemorymanager-virtualfree-method.md)|<span data-ttu-id="8e9f4-122">Actúa como un contenedor lógico para la función de Win32 correspondiente, que libera, anula o libera y anula la confirmación de una región de páginas dentro del espacio de direcciones virtuales del proceso de llamada.</span><span class="sxs-lookup"><span data-stu-id="8e9f4-122">Serves as a logical wrapper for the corresponding Win32 function, which releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="8e9f4-123">Método VirtualProtect</span><span class="sxs-lookup"><span data-stu-id="8e9f4-123">VirtualProtect Method</span></span>](ihostmemorymanager-virtualprotect-method.md)|<span data-ttu-id="8e9f4-124">Actúa como contenedor lógico de la función de Win32 correspondiente, que cambia la protección en una región de páginas confirmadas en el espacio de direcciones virtuales del proceso de llamada.</span><span class="sxs-lookup"><span data-stu-id="8e9f4-124">Serves as a logical wrapper for the corresponding Win32 function, which changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="8e9f4-125">Método VirtualQuery</span><span class="sxs-lookup"><span data-stu-id="8e9f4-125">VirtualQuery Method</span></span>](ihostmemorymanager-virtualquery-method.md)|<span data-ttu-id="8e9f4-126">Actúa como contenedor lógico de la función de Win32 correspondiente, que recupera información sobre un intervalo de páginas en el espacio de direcciones virtuales del proceso de llamada.</span><span class="sxs-lookup"><span data-stu-id="8e9f4-126">Serves as a logical wrapper for the corresponding Win32 function, which retrieves information about a range of pages in the virtual address space of the calling process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e9f4-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8e9f4-127">Remarks</span></span>  
 <span data-ttu-id="8e9f4-128">`IHostMemoryManager`también proporciona métodos para que CLR obtenga un puntero a través del cual se van a realizar solicitudes de memoria en el montón y para obtener el nivel de presión de memoria en el proceso, tal y como lo indica el host.</span><span class="sxs-lookup"><span data-stu-id="8e9f4-128">`IHostMemoryManager` also provides methods for the CLR to obtain a pointer through which to make memory requests on the heap and to get the level of memory pressure in the process, as reported by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e9f4-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8e9f4-129">Requirements</span></span>  
 <span data-ttu-id="8e9f4-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e9f4-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e9f4-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8e9f4-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8e9f4-132">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8e9f4-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8e9f4-133">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e9f4-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e9f4-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8e9f4-134">See also</span></span>

- [<span data-ttu-id="8e9f4-135">IHostMalloc (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8e9f4-135">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
- [<span data-ttu-id="8e9f4-136">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="8e9f4-136">Hosting Interfaces</span></span>](hosting-interfaces.md)
