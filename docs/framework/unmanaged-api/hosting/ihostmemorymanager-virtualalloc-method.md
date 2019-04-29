---
title: IHostMemoryManager::VirtualAlloc (Método)
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualAlloc
helpviewer_keywords:
- VirtualAlloc method [.NET Framework hosting]
- IHostMemoryManager::VirtualAlloc method [.NET Framework hosting]
ms.assetid: 4dff3646-a050-4bd9-ac31-fe307e8637ec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5407a9d23833d73b2d6ef0038454f56f01d56867
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760212"
---
# <a name="ihostmemorymanagervirtualalloc-method"></a><span data-ttu-id="c6e1c-102">IHostMemoryManager::VirtualAlloc (Método)</span><span class="sxs-lookup"><span data-stu-id="c6e1c-102">IHostMemoryManager::VirtualAlloc Method</span></span>
<span data-ttu-id="c6e1c-103">Actúa como un contenedor lógico para la función de Win32 correspondiente.</span><span class="sxs-lookup"><span data-stu-id="c6e1c-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="c6e1c-104">La implementación de Win32 de `VirtualAlloc` reserva o confirma una región de páginas en el espacio de direcciones virtuales del proceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="c6e1c-104">The Win32 implementation of `VirtualAlloc` reserves or commits a region of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6e1c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c6e1c-105">Syntax</span></span>  
  
```  
HRESULT VirtualAlloc (  
    [in]  void*   pAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flAllocationType,  
    [in]  DWORD   flProtect,  
    [in]  EMemoryCriticalLevel dwCriticalLevel,  
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6e1c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c6e1c-106">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="c6e1c-107">[in] Un puntero a la dirección inicial de la región para asignar.</span><span class="sxs-lookup"><span data-stu-id="c6e1c-107">[in] A pointer to the starting address of the region to allocate.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="c6e1c-108">[in] El tamaño, en bytes, de la región.</span><span class="sxs-lookup"><span data-stu-id="c6e1c-108">[in] The size, in bytes, of the region.</span></span>  
  
 `flAllocationType`  
 <span data-ttu-id="c6e1c-109">[in] El tipo de asignación de memoria.</span><span class="sxs-lookup"><span data-stu-id="c6e1c-109">[in] The type of memory allocation.</span></span>  
  
 `flProtect`  
 <span data-ttu-id="c6e1c-110">[in] Protección de memoria para la región de páginas asignadas.</span><span class="sxs-lookup"><span data-stu-id="c6e1c-110">[in] Memory protection for the region of pages to be allocated.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="c6e1c-111">[in] Un [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) valor que indica el impacto de un error de asignación.</span><span class="sxs-lookup"><span data-stu-id="c6e1c-111">[in] An [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) value that indicates the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="c6e1c-112">[out] Puntero a la dirección inicial de la memoria asignada, o null si no se pudo satisfacer la solicitud.</span><span class="sxs-lookup"><span data-stu-id="c6e1c-112">[out] Pointer to the starting address of the allocated memory, or null if the request could not be satisfied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6e1c-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c6e1c-113">Return Value</span></span>  
  
|<span data-ttu-id="c6e1c-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c6e1c-114">HRESULT</span></span>|<span data-ttu-id="c6e1c-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="c6e1c-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c6e1c-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="c6e1c-116">S_OK</span></span>|<span data-ttu-id="c6e1c-117">`VirtualAlloc` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="c6e1c-117">`VirtualAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="c6e1c-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c6e1c-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c6e1c-119">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c6e1c-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c6e1c-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c6e1c-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c6e1c-121">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="c6e1c-121">The call timed out.</span></span>|  
|<span data-ttu-id="c6e1c-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c6e1c-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c6e1c-123">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="c6e1c-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c6e1c-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c6e1c-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c6e1c-125">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="c6e1c-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c6e1c-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c6e1c-126">E_FAIL</span></span>|<span data-ttu-id="c6e1c-127">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="c6e1c-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c6e1c-128">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="c6e1c-128">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c6e1c-129">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c6e1c-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c6e1c-130">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c6e1c-130">E_OUTOFMEMORY</span></span>|<span data-ttu-id="c6e1c-131">No había suficiente memoria disponible para completar la solicitud de asignación</span><span class="sxs-lookup"><span data-stu-id="c6e1c-131">Not enough memory was available to complete the allocation request</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6e1c-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c6e1c-132">Remarks</span></span>  
 <span data-ttu-id="c6e1c-133">Reservar una región en el espacio de direcciones del proceso mediante una llamada a `VirtualAlloc`.</span><span class="sxs-lookup"><span data-stu-id="c6e1c-133">You reserve a region in the address space of your process by calling `VirtualAlloc`.</span></span> <span data-ttu-id="c6e1c-134">El `pAddress` parámetro contiene la dirección del principio del bloque de memoria que desee.</span><span class="sxs-lookup"><span data-stu-id="c6e1c-134">The `pAddress` parameter contains the beginning address of the memory block you want.</span></span> <span data-ttu-id="c6e1c-135">Este parámetro normalmente se establece en null.</span><span class="sxs-lookup"><span data-stu-id="c6e1c-135">This parameter is typically set to null.</span></span> <span data-ttu-id="c6e1c-136">El sistema operativo mantiene un registro de los intervalos de direcciones libres disponibles para su proceso.</span><span class="sxs-lookup"><span data-stu-id="c6e1c-136">The operating system keeps a record of free address ranges available to your process.</span></span> <span data-ttu-id="c6e1c-137">Un `pAddress` valor null indica al sistema que reserve la región dondequiera que considere adecuada.</span><span class="sxs-lookup"><span data-stu-id="c6e1c-137">A `pAddress` value of null instructs the system to reserve the region wherever it sees fit.</span></span> <span data-ttu-id="c6e1c-138">Como alternativa, puede proporcionar una dirección de inicio específica para el bloque de memoria.</span><span class="sxs-lookup"><span data-stu-id="c6e1c-138">Alternatively, you can provide a specific starting address for the memory block.</span></span> <span data-ttu-id="c6e1c-139">En ambos casos, el parámetro de salida `ppMem` se devuelve como un puntero a la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="c6e1c-139">In both cases, the output parameter `ppMem` is returned as a pointer to the allocated memory.</span></span> <span data-ttu-id="c6e1c-140">La propia función devuelve un valor HRESULT.</span><span class="sxs-lookup"><span data-stu-id="c6e1c-140">The function itself returns an HRESULT value.</span></span>  
  
 <span data-ttu-id="c6e1c-141">Win32 `VirtualAlloc` función no tiene un `ppMem` parámetro y devuelve el puntero a la memoria asignada en su lugar.</span><span class="sxs-lookup"><span data-stu-id="c6e1c-141">The Win32 `VirtualAlloc` function does not have a `ppMem` parameter, and returns the pointer to the allocated memory instead.</span></span> <span data-ttu-id="c6e1c-142">Para obtener más información, consulte la documentación de la plataforma de Windows.</span><span class="sxs-lookup"><span data-stu-id="c6e1c-142">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6e1c-143">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c6e1c-143">Requirements</span></span>  
 <span data-ttu-id="c6e1c-144">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6e1c-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6e1c-145">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c6e1c-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c6e1c-146">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c6e1c-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c6e1c-147">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6e1c-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6e1c-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6e1c-148">See also</span></span>

- [<span data-ttu-id="c6e1c-149">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c6e1c-149">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
