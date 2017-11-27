---
title: "IHostMAlloc::Alloc (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMAlloc.Alloc
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMAlloc::Alloc
helpviewer_keywords:
- Alloc method, IHostMAlloc interface [.NET Framework hosting]
- IHostMAlloc::Alloc method [.NET Framework hosting]
ms.assetid: a3007f5e-d75d-4b37-842b-704e9edced5e
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9cc4447424d1594f6fa86e07be659a6ba97f0427
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmallocalloc-method"></a><span data-ttu-id="2349f-102">IHostMAlloc::Alloc (Método)</span><span class="sxs-lookup"><span data-stu-id="2349f-102">IHostMAlloc::Alloc Method</span></span>
<span data-ttu-id="2349f-103">Solicita que el host de asignar la cantidad especificada de memoria del montón.</span><span class="sxs-lookup"><span data-stu-id="2349f-103">Requests that the host allocate the specified amount of memory from the heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2349f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2349f-104">Syntax</span></span>  
  
```  
HRESULT Alloc (  
    [in] SIZE_T  cbSize,   
    [in] EMemoryCriticalLevel dwCriticalLevel,   
    [out] void** ppMem  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2349f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2349f-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="2349f-106">[in] El tamaño, en bytes, de la solicitud de asignación de memoria actual.</span><span class="sxs-lookup"><span data-stu-id="2349f-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="2349f-107">[in] Uno de los [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) valores, que indican el impacto de un error de asignación.</span><span class="sxs-lookup"><span data-stu-id="2349f-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="2349f-108">[out] Un puntero a la memoria asignada, o null si no se pudo completar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="2349f-108">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2349f-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2349f-109">Return Value</span></span>  
  
|<span data-ttu-id="2349f-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2349f-110">HRESULT</span></span>|<span data-ttu-id="2349f-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="2349f-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2349f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="2349f-112">S_OK</span></span>|<span data-ttu-id="2349f-113">`Alloc`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="2349f-113">`Alloc` returned successfully.</span></span>|  
|<span data-ttu-id="2349f-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2349f-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2349f-115">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="2349f-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2349f-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2349f-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2349f-117">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="2349f-117">The call timed out.</span></span>|  
|<span data-ttu-id="2349f-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2349f-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2349f-119">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="2349f-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2349f-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2349f-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2349f-121">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="2349f-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2349f-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2349f-122">E_FAIL</span></span>|<span data-ttu-id="2349f-123">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="2349f-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2349f-124">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="2349f-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2349f-125">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2349f-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2349f-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="2349f-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="2349f-127">No había suficiente memoria disponible para completar la solicitud de asignación.</span><span class="sxs-lookup"><span data-stu-id="2349f-127">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2349f-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2349f-128">Remarks</span></span>  
 <span data-ttu-id="2349f-129">CLR Obtiene un puntero de interfaz a una `IHostMalloc` instancia mediante una llamada a la [IHostMemoryManager:: CreateMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="2349f-129">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2349f-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2349f-130">Requirements</span></span>  
 <span data-ttu-id="2349f-131">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2349f-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2349f-132">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2349f-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2349f-133">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2349f-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2349f-134">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2349f-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2349f-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="2349f-135">See Also</span></span>  
 [<span data-ttu-id="2349f-136">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2349f-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="2349f-137">IHostMalloc (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2349f-137">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
