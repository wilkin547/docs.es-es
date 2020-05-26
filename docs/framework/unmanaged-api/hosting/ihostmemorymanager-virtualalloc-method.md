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
ms.openlocfilehash: de41b5e0aaf835ee2d4e4f32696fe104d5830b57
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804451"
---
# <a name="ihostmemorymanagervirtualalloc-method"></a><span data-ttu-id="03190-102">IHostMemoryManager::VirtualAlloc (Método)</span><span class="sxs-lookup"><span data-stu-id="03190-102">IHostMemoryManager::VirtualAlloc Method</span></span>
<span data-ttu-id="03190-103">Actúa como un contenedor lógico para la función de Win32 correspondiente.</span><span class="sxs-lookup"><span data-stu-id="03190-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="03190-104">La implementación de Win32 de `VirtualAlloc` reserva o confirma una región de páginas en el espacio de direcciones virtuales del proceso de llamada.</span><span class="sxs-lookup"><span data-stu-id="03190-104">The Win32 implementation of `VirtualAlloc` reserves or commits a region of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03190-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03190-105">Syntax</span></span>  
  
```cpp  
HRESULT VirtualAlloc (  
    [in]  void*   pAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flAllocationType,  
    [in]  DWORD   flProtect,  
    [in]  EMemoryCriticalLevel dwCriticalLevel,  
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03190-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="03190-106">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="03190-107">de Puntero a la dirección inicial de la región que se va a asignar.</span><span class="sxs-lookup"><span data-stu-id="03190-107">[in] A pointer to the starting address of the region to allocate.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="03190-108">de Tamaño, en bytes, de la región.</span><span class="sxs-lookup"><span data-stu-id="03190-108">[in] The size, in bytes, of the region.</span></span>  
  
 `flAllocationType`  
 <span data-ttu-id="03190-109">de Tipo de asignación de memoria.</span><span class="sxs-lookup"><span data-stu-id="03190-109">[in] The type of memory allocation.</span></span>  
  
 `flProtect`  
 <span data-ttu-id="03190-110">de Protección de memoria para la región de páginas que se va a asignar.</span><span class="sxs-lookup"><span data-stu-id="03190-110">[in] Memory protection for the region of pages to be allocated.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="03190-111">de Un valor [ememorycriticallevel (](ememorycriticallevel-enumeration.md) que indica el impacto de un error de asignación.</span><span class="sxs-lookup"><span data-stu-id="03190-111">[in] An [EMemoryCriticalLevel](ememorycriticallevel-enumeration.md) value that indicates the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="03190-112">enuncia Puntero a la dirección inicial de la memoria asignada, o null si no se puede satisfacer la solicitud.</span><span class="sxs-lookup"><span data-stu-id="03190-112">[out] Pointer to the starting address of the allocated memory, or null if the request could not be satisfied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="03190-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="03190-113">Return Value</span></span>  
  
|<span data-ttu-id="03190-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="03190-114">HRESULT</span></span>|<span data-ttu-id="03190-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="03190-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="03190-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="03190-116">S_OK</span></span>|<span data-ttu-id="03190-117">`VirtualAlloc`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="03190-117">`VirtualAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="03190-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="03190-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="03190-119">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="03190-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="03190-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="03190-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="03190-121">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="03190-121">The call timed out.</span></span>|  
|<span data-ttu-id="03190-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="03190-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="03190-123">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="03190-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="03190-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="03190-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="03190-125">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="03190-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="03190-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="03190-126">E_FAIL</span></span>|<span data-ttu-id="03190-127">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="03190-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="03190-128">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="03190-128">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="03190-129">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="03190-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="03190-130">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="03190-130">E_OUTOFMEMORY</span></span>|<span data-ttu-id="03190-131">No hay suficiente memoria disponible para completar la solicitud de asignación</span><span class="sxs-lookup"><span data-stu-id="03190-131">Not enough memory was available to complete the allocation request</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03190-132">Observaciones</span><span class="sxs-lookup"><span data-stu-id="03190-132">Remarks</span></span>  
 <span data-ttu-id="03190-133">Reserva una región en el espacio de direcciones del proceso mediante una llamada a `VirtualAlloc` .</span><span class="sxs-lookup"><span data-stu-id="03190-133">You reserve a region in the address space of your process by calling `VirtualAlloc`.</span></span> <span data-ttu-id="03190-134">El `pAddress` parámetro contiene la dirección inicial del bloque de memoria que desee.</span><span class="sxs-lookup"><span data-stu-id="03190-134">The `pAddress` parameter contains the beginning address of the memory block you want.</span></span> <span data-ttu-id="03190-135">Normalmente, este parámetro se establece en NULL.</span><span class="sxs-lookup"><span data-stu-id="03190-135">This parameter is typically set to null.</span></span> <span data-ttu-id="03190-136">El sistema operativo mantiene un registro de los intervalos de direcciones libres disponibles para el proceso.</span><span class="sxs-lookup"><span data-stu-id="03190-136">The operating system keeps a record of free address ranges available to your process.</span></span> <span data-ttu-id="03190-137">Un `pAddress` valor null indica al sistema que Reserve la región donde sea adecuado.</span><span class="sxs-lookup"><span data-stu-id="03190-137">A `pAddress` value of null instructs the system to reserve the region wherever it sees fit.</span></span> <span data-ttu-id="03190-138">Como alternativa, puede proporcionar una dirección de inicio específica para el bloque de memoria.</span><span class="sxs-lookup"><span data-stu-id="03190-138">Alternatively, you can provide a specific starting address for the memory block.</span></span> <span data-ttu-id="03190-139">En ambos casos, el parámetro de salida `ppMem` se devuelve como un puntero a la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="03190-139">In both cases, the output parameter `ppMem` is returned as a pointer to the allocated memory.</span></span> <span data-ttu-id="03190-140">La propia función devuelve un valor HRESULT.</span><span class="sxs-lookup"><span data-stu-id="03190-140">The function itself returns an HRESULT value.</span></span>  
  
 <span data-ttu-id="03190-141">La función de Win32 `VirtualAlloc` no tiene un `ppMem` parámetro y devuelve el puntero a la memoria asignada en su lugar.</span><span class="sxs-lookup"><span data-stu-id="03190-141">The Win32 `VirtualAlloc` function does not have a `ppMem` parameter, and returns the pointer to the allocated memory instead.</span></span> <span data-ttu-id="03190-142">Para obtener más información, vea la documentación de la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="03190-142">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03190-143">Requisitos</span><span class="sxs-lookup"><span data-stu-id="03190-143">Requirements</span></span>  
 <span data-ttu-id="03190-144">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03190-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03190-145">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="03190-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="03190-146">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="03190-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="03190-147">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03190-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03190-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="03190-148">See also</span></span>

- [<span data-ttu-id="03190-149">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="03190-149">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
