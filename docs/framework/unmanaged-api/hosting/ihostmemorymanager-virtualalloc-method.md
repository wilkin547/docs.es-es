---
title: "IHostMemoryManager::VirtualAlloc (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.VirtualAlloc
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::VirtualAlloc
helpviewer_keywords:
- VirtualAlloc method [.NET Framework hosting]
- IHostMemoryManager::VirtualAlloc method [.NET Framework hosting]
ms.assetid: 4dff3646-a050-4bd9-ac31-fe307e8637ec
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 761958c44ad374d522a52826929e320e65957ffa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmemorymanagervirtualalloc-method"></a><span data-ttu-id="2fed6-102">IHostMemoryManager::VirtualAlloc (Método)</span><span class="sxs-lookup"><span data-stu-id="2fed6-102">IHostMemoryManager::VirtualAlloc Method</span></span>
<span data-ttu-id="2fed6-103">Actúa como un contenedor lógico para la función de Win32 correspondiente.</span><span class="sxs-lookup"><span data-stu-id="2fed6-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="2fed6-104">La implementación de Win32 de `VirtualAlloc` reserva o confirma una región de páginas en el espacio de direcciones virtuales del proceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="2fed6-104">The Win32 implementation of `VirtualAlloc` reserves or commits a region of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fed6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2fed6-105">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="2fed6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2fed6-106">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="2fed6-107">[in] Un puntero a la dirección inicial de la región para asignar.</span><span class="sxs-lookup"><span data-stu-id="2fed6-107">[in] A pointer to the starting address of the region to allocate.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="2fed6-108">[in] El tamaño, en bytes, de la región.</span><span class="sxs-lookup"><span data-stu-id="2fed6-108">[in] The size, in bytes, of the region.</span></span>  
  
 `flAllocationType`  
 <span data-ttu-id="2fed6-109">[in] El tipo de asignación de memoria.</span><span class="sxs-lookup"><span data-stu-id="2fed6-109">[in] The type of memory allocation.</span></span>  
  
 `flProtect`  
 <span data-ttu-id="2fed6-110">[in] Protección de la memoria para la región de páginas que se va a asignar.</span><span class="sxs-lookup"><span data-stu-id="2fed6-110">[in] Memory protection for the region of pages to be allocated.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="2fed6-111">[in] Un [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) valor que indica el impacto de un error de asignación.</span><span class="sxs-lookup"><span data-stu-id="2fed6-111">[in] An [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) value that indicates the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="2fed6-112">[out] Puntero a la dirección inicial de la memoria asignada, o null si no se pudo satisfacer la solicitud.</span><span class="sxs-lookup"><span data-stu-id="2fed6-112">[out] Pointer to the starting address of the allocated memory, or null if the request could not be satisfied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2fed6-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2fed6-113">Return Value</span></span>  
  
|<span data-ttu-id="2fed6-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2fed6-114">HRESULT</span></span>|<span data-ttu-id="2fed6-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="2fed6-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2fed6-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="2fed6-116">S_OK</span></span>|<span data-ttu-id="2fed6-117">`VirtualAlloc`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="2fed6-117">`VirtualAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="2fed6-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2fed6-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2fed6-119">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="2fed6-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2fed6-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2fed6-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2fed6-121">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="2fed6-121">The call timed out.</span></span>|  
|<span data-ttu-id="2fed6-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2fed6-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2fed6-123">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="2fed6-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2fed6-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2fed6-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2fed6-125">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="2fed6-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2fed6-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2fed6-126">E_FAIL</span></span>|<span data-ttu-id="2fed6-127">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="2fed6-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2fed6-128">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="2fed6-128">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2fed6-129">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2fed6-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2fed6-130">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="2fed6-130">E_OUTOFMEMORY</span></span>|<span data-ttu-id="2fed6-131">No había suficiente memoria disponible para completar la solicitud de asignación</span><span class="sxs-lookup"><span data-stu-id="2fed6-131">Not enough memory was available to complete the allocation request</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2fed6-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2fed6-132">Remarks</span></span>  
 <span data-ttu-id="2fed6-133">Para reservar una región en el espacio de direcciones del proceso mediante una llamada a `VirtualAlloc`.</span><span class="sxs-lookup"><span data-stu-id="2fed6-133">You reserve a region in the address space of your process by calling `VirtualAlloc`.</span></span> <span data-ttu-id="2fed6-134">El `pAddress` parámetro contiene la dirección del principio del bloque de memoria que desee.</span><span class="sxs-lookup"><span data-stu-id="2fed6-134">The `pAddress` parameter contains the beginning address of the memory block you want.</span></span> <span data-ttu-id="2fed6-135">Este parámetro se establece normalmente en null.</span><span class="sxs-lookup"><span data-stu-id="2fed6-135">This parameter is typically set to null.</span></span> <span data-ttu-id="2fed6-136">El sistema operativo mantiene un registro de intervalos de direcciones libres disponibles para el proceso.</span><span class="sxs-lookup"><span data-stu-id="2fed6-136">The operating system keeps a record of free address ranges available to your process.</span></span> <span data-ttu-id="2fed6-137">Un `pAddress` valor null indica al sistema que reserve la región dondequiera que considere apropiada.</span><span class="sxs-lookup"><span data-stu-id="2fed6-137">A `pAddress` value of null instructs the system to reserve the region wherever it sees fit.</span></span> <span data-ttu-id="2fed6-138">Como alternativa, puede proporcionar una dirección inicial concreta para el bloque de memoria.</span><span class="sxs-lookup"><span data-stu-id="2fed6-138">Alternatively, you can provide a specific starting address for the memory block.</span></span> <span data-ttu-id="2fed6-139">En ambos casos, el parámetro de salida `ppMem` se devuelve como un puntero a la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="2fed6-139">In both cases, the output parameter `ppMem` is returned as a pointer to the allocated memory.</span></span> <span data-ttu-id="2fed6-140">La propia función devuelve un valor HRESULT.</span><span class="sxs-lookup"><span data-stu-id="2fed6-140">The function itself returns an HRESULT value.</span></span>  
  
 <span data-ttu-id="2fed6-141">Win32 `VirtualAlloc` la función no tiene un `ppMem` parámetro y devuelve el puntero a la memoria asignada en su lugar.</span><span class="sxs-lookup"><span data-stu-id="2fed6-141">The Win32 `VirtualAlloc` function does not have a `ppMem` parameter, and returns the pointer to the allocated memory instead.</span></span> <span data-ttu-id="2fed6-142">Para obtener más información, consulte la documentación de la plataforma de Windows.</span><span class="sxs-lookup"><span data-stu-id="2fed6-142">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fed6-143">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2fed6-143">Requirements</span></span>  
 <span data-ttu-id="2fed6-144">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fed6-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fed6-145">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2fed6-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2fed6-146">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2fed6-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2fed6-147">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fed6-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fed6-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="2fed6-148">See Also</span></span>  
 [<span data-ttu-id="2fed6-149">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2fed6-149">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
