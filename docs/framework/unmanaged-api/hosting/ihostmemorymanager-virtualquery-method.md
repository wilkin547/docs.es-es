---
title: "IHostMemoryManager::VirtualQuery (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.VirtualQuery
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::VirtualQuery
helpviewer_keywords:
- IHostMemoryManager::VirtualQuery method [.NET Framework hosting]
- VirtualQuery method [.NET Framework hosting]
ms.assetid: 757af1e6-b9e8-49e7-b5db-342be3aa205f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4fd893cd92f7e7621aefe59595cfd9905bc77afd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmemorymanagervirtualquery-method"></a><span data-ttu-id="11b95-102">IHostMemoryManager::VirtualQuery (Método)</span><span class="sxs-lookup"><span data-stu-id="11b95-102">IHostMemoryManager::VirtualQuery Method</span></span>
<span data-ttu-id="11b95-103">Actúa como un contenedor lógico para la función de Win32 correspondiente.</span><span class="sxs-lookup"><span data-stu-id="11b95-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="11b95-104">La implementación de Win32 de `VirtualQuery` recupera información sobre un intervalo de páginas en el espacio de direcciones virtuales del proceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="11b95-104">The Win32 implementation of `VirtualQuery` retrieves information about a range of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11b95-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11b95-105">Syntax</span></span>  
  
```  
HRESULT VirtualQuery (  
    [in]  void*    lpAddress,  
    [out] void*    lpBuffer,  
    [in]  SIZE_T   dwLength,  
    [out] SIZE_T*  pResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="11b95-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="11b95-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="11b95-107">[in] Un puntero a la dirección en la memoria virtual y pueden consultar.</span><span class="sxs-lookup"><span data-stu-id="11b95-107">[in] A pointer to the address in virtual memory to be queried.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="11b95-108">[out] Un puntero a una estructura que contiene información acerca de la región de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="11b95-108">[out] A pointer to a structure that contains information about the specified memory region.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="11b95-109">[in] El tamaño, en bytes, del búfer que `lpBuffer` apunta a.</span><span class="sxs-lookup"><span data-stu-id="11b95-109">[in] The size, in bytes, of the buffer that `lpBuffer` points to.</span></span>  
  
 `pResult`  
 <span data-ttu-id="11b95-110">[out] Un puntero al número de bytes devueltos en el búfer de información.</span><span class="sxs-lookup"><span data-stu-id="11b95-110">[out] A pointer to the number of bytes returned by the information buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11b95-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="11b95-111">Return Value</span></span>  
  
|<span data-ttu-id="11b95-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="11b95-112">HRESULT</span></span>|<span data-ttu-id="11b95-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="11b95-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="11b95-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="11b95-114">S_OK</span></span>|<span data-ttu-id="11b95-115">`VirtualQuery`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="11b95-115">`VirtualQuery` returned successfully.</span></span>|  
|<span data-ttu-id="11b95-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="11b95-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="11b95-117">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="11b95-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="11b95-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="11b95-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="11b95-119">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="11b95-119">The call timed out.</span></span>|  
|<span data-ttu-id="11b95-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="11b95-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="11b95-121">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="11b95-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="11b95-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="11b95-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="11b95-123">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="11b95-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="11b95-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="11b95-124">E_FAIL</span></span>|<span data-ttu-id="11b95-125">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="11b95-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="11b95-126">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="11b95-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="11b95-127">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="11b95-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11b95-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="11b95-128">Remarks</span></span>  
 <span data-ttu-id="11b95-129">`VirtualQuery`Proporciona información sobre un intervalo de páginas en el espacio de direcciones virtuales del proceso que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="11b95-129">`VirtualQuery` provides information about a range of pages in the virtual address space of the calling process.</span></span> <span data-ttu-id="11b95-130">Esta implementación establece el valor de la `pResult` parámetro para el número de bytes devueltos en el búfer de información y devuelve un valor HRESULT.</span><span class="sxs-lookup"><span data-stu-id="11b95-130">This implementation sets the value of the `pResult` parameter to the number of bytes returned in the information buffer, and returns an HRESULT value.</span></span> <span data-ttu-id="11b95-131">En Win32 `VirtualQuery` función, el valor devuelto es el tamaño del búfer.</span><span class="sxs-lookup"><span data-stu-id="11b95-131">In the Win32 `VirtualQuery` function, the return value is the buffer size.</span></span> <span data-ttu-id="11b95-132">Para obtener más información, consulte la documentación de la plataforma de Windows.</span><span class="sxs-lookup"><span data-stu-id="11b95-132">For more information, see the Windows Platform documentation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="11b95-133">Implementación del sistema operativo de `VirtualQuery` no incurre en interbloqueos y puede ejecutarse hasta su finalización con subprocesos aleatorios suspendidos en el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="11b95-133">The operating system's implementation of `VirtualQuery` does not incur deadlock and can run to completion with random threads suspended in user code.</span></span> <span data-ttu-id="11b95-134">Usar mucha precaución al implementar una versión hospedada de este método.</span><span class="sxs-lookup"><span data-stu-id="11b95-134">Use great caution when implementing a hosted version of this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11b95-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="11b95-135">Requirements</span></span>  
 <span data-ttu-id="11b95-136">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11b95-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11b95-137">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="11b95-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="11b95-138">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="11b95-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="11b95-139">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11b95-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11b95-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="11b95-140">See Also</span></span>  
 [<span data-ttu-id="11b95-141">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11b95-141">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
