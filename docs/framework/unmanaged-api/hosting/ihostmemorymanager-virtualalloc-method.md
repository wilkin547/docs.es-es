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
ms.openlocfilehash: fe54aed47d240be37ab9dbc5381235c4e962f1f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440319"
---
# <a name="ihostmemorymanagervirtualalloc-method"></a><span data-ttu-id="eddab-102">IHostMemoryManager::VirtualAlloc (Método)</span><span class="sxs-lookup"><span data-stu-id="eddab-102">IHostMemoryManager::VirtualAlloc Method</span></span>
<span data-ttu-id="eddab-103">Actúa como un contenedor lógico para la función de Win32 correspondiente.</span><span class="sxs-lookup"><span data-stu-id="eddab-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="eddab-104">La implementación de Win32 de `VirtualAlloc` reserva o confirma una región de páginas en el espacio de direcciones virtuales del proceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="eddab-104">The Win32 implementation of `VirtualAlloc` reserves or commits a region of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eddab-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eddab-105">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="eddab-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="eddab-106">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="eddab-107">[in] Un puntero a la dirección inicial de la región para asignar.</span><span class="sxs-lookup"><span data-stu-id="eddab-107">[in] A pointer to the starting address of the region to allocate.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="eddab-108">[in] El tamaño, en bytes, de la región.</span><span class="sxs-lookup"><span data-stu-id="eddab-108">[in] The size, in bytes, of the region.</span></span>  
  
 `flAllocationType`  
 <span data-ttu-id="eddab-109">[in] El tipo de asignación de memoria.</span><span class="sxs-lookup"><span data-stu-id="eddab-109">[in] The type of memory allocation.</span></span>  
  
 `flProtect`  
 <span data-ttu-id="eddab-110">[in] Protección de la memoria para la región de páginas que se va a asignar.</span><span class="sxs-lookup"><span data-stu-id="eddab-110">[in] Memory protection for the region of pages to be allocated.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="eddab-111">[in] Un [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) valor que indica el impacto de un error de asignación.</span><span class="sxs-lookup"><span data-stu-id="eddab-111">[in] An [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) value that indicates the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="eddab-112">[out] Puntero a la dirección inicial de la memoria asignada, o null si no se pudo satisfacer la solicitud.</span><span class="sxs-lookup"><span data-stu-id="eddab-112">[out] Pointer to the starting address of the allocated memory, or null if the request could not be satisfied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eddab-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="eddab-113">Return Value</span></span>  
  
|<span data-ttu-id="eddab-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eddab-114">HRESULT</span></span>|<span data-ttu-id="eddab-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="eddab-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eddab-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="eddab-116">S_OK</span></span>|<span data-ttu-id="eddab-117">`VirtualAlloc` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="eddab-117">`VirtualAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="eddab-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="eddab-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="eddab-119">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="eddab-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="eddab-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="eddab-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="eddab-121">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="eddab-121">The call timed out.</span></span>|  
|<span data-ttu-id="eddab-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="eddab-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="eddab-123">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="eddab-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="eddab-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="eddab-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="eddab-125">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="eddab-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="eddab-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="eddab-126">E_FAIL</span></span>|<span data-ttu-id="eddab-127">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="eddab-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="eddab-128">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="eddab-128">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="eddab-129">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="eddab-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="eddab-130">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="eddab-130">E_OUTOFMEMORY</span></span>|<span data-ttu-id="eddab-131">No había suficiente memoria disponible para completar la solicitud de asignación</span><span class="sxs-lookup"><span data-stu-id="eddab-131">Not enough memory was available to complete the allocation request</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eddab-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="eddab-132">Remarks</span></span>  
 <span data-ttu-id="eddab-133">Para reservar una región en el espacio de direcciones del proceso mediante una llamada a `VirtualAlloc`.</span><span class="sxs-lookup"><span data-stu-id="eddab-133">You reserve a region in the address space of your process by calling `VirtualAlloc`.</span></span> <span data-ttu-id="eddab-134">El `pAddress` parámetro contiene la dirección del principio del bloque de memoria que desee.</span><span class="sxs-lookup"><span data-stu-id="eddab-134">The `pAddress` parameter contains the beginning address of the memory block you want.</span></span> <span data-ttu-id="eddab-135">Este parámetro se establece normalmente en null.</span><span class="sxs-lookup"><span data-stu-id="eddab-135">This parameter is typically set to null.</span></span> <span data-ttu-id="eddab-136">El sistema operativo mantiene un registro de intervalos de direcciones libres disponibles para el proceso.</span><span class="sxs-lookup"><span data-stu-id="eddab-136">The operating system keeps a record of free address ranges available to your process.</span></span> <span data-ttu-id="eddab-137">Un `pAddress` valor null indica al sistema que reserve la región dondequiera que considere apropiada.</span><span class="sxs-lookup"><span data-stu-id="eddab-137">A `pAddress` value of null instructs the system to reserve the region wherever it sees fit.</span></span> <span data-ttu-id="eddab-138">Como alternativa, puede proporcionar una dirección inicial concreta para el bloque de memoria.</span><span class="sxs-lookup"><span data-stu-id="eddab-138">Alternatively, you can provide a specific starting address for the memory block.</span></span> <span data-ttu-id="eddab-139">En ambos casos, el parámetro de salida `ppMem` se devuelve como un puntero a la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="eddab-139">In both cases, the output parameter `ppMem` is returned as a pointer to the allocated memory.</span></span> <span data-ttu-id="eddab-140">La propia función devuelve un valor HRESULT.</span><span class="sxs-lookup"><span data-stu-id="eddab-140">The function itself returns an HRESULT value.</span></span>  
  
 <span data-ttu-id="eddab-141">Win32 `VirtualAlloc` la función no tiene un `ppMem` parámetro y devuelve el puntero a la memoria asignada en su lugar.</span><span class="sxs-lookup"><span data-stu-id="eddab-141">The Win32 `VirtualAlloc` function does not have a `ppMem` parameter, and returns the pointer to the allocated memory instead.</span></span> <span data-ttu-id="eddab-142">Para obtener más información, consulte la documentación de la plataforma de Windows.</span><span class="sxs-lookup"><span data-stu-id="eddab-142">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eddab-143">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eddab-143">Requirements</span></span>  
 <span data-ttu-id="eddab-144">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eddab-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eddab-145">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="eddab-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eddab-146">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="eddab-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eddab-147">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eddab-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eddab-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="eddab-148">See Also</span></span>  
 [<span data-ttu-id="eddab-149">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="eddab-149">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
