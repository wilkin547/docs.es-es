---
title: "IHostMAlloc::DebugAlloc (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMAlloc.DebugAlloc
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMAlloc::DebugAlloc
helpviewer_keywords:
- DebugAlloc method [.NET Framework hosting]
- IHostMAlloc::DebugAlloc method [.NET Framework hosting]
ms.assetid: 0bfbc527-bea2-43ce-b041-69186f4440dd
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 63249f6ce64071ddaa2bb9dff221ae40d924bbfe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmallocdebugalloc-method"></a><span data-ttu-id="5a4f8-102">IHostMAlloc::DebugAlloc (Método)</span><span class="sxs-lookup"><span data-stu-id="5a4f8-102">IHostMAlloc::DebugAlloc Method</span></span>
<span data-ttu-id="5a4f8-103">Solicita que el host de asignar la cantidad especificada de memoria del montón y además realizar un seguimiento de dónde se ha asignado la memoria.</span><span class="sxs-lookup"><span data-stu-id="5a4f8-103">Requests that the host allocate the specified amount of memory from the heap, and additionally track where the memory was allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a4f8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a4f8-104">Syntax</span></span>  
  
```  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,   
    [in]  EMemoryCriticalLevel dwCriticalLevel,   
    [in]  char*   pszFileName,   
    [in]  int     iLineNo,   
    [out] void**  ppMem  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5a4f8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5a4f8-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="5a4f8-106">[in] El tamaño, en bytes, de la solicitud de asignación de memoria actual.</span><span class="sxs-lookup"><span data-stu-id="5a4f8-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="5a4f8-107">[in] Uno de los [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) valores, que indican el impacto de un error de asignación.</span><span class="sxs-lookup"><span data-stu-id="5a4f8-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="5a4f8-108">[in] El archivo de código del archivo ejecutable que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="5a4f8-108">[in] The code file of the executable being debugged.</span></span>  
  
 `iLineNo`  
 <span data-ttu-id="5a4f8-109">[in] Número de línea del `pszFileName` que se solicitó la asignación.</span><span class="sxs-lookup"><span data-stu-id="5a4f8-109">[in] The line number in `pszFileName` where the allocation was requested.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="5a4f8-110">[out] Un puntero a la memoria asignada, o null si no se pudo completar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="5a4f8-110">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a4f8-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5a4f8-111">Return Value</span></span>  
  
|<span data-ttu-id="5a4f8-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5a4f8-112">HRESULT</span></span>|<span data-ttu-id="5a4f8-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a4f8-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5a4f8-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="5a4f8-114">S_OK</span></span>|<span data-ttu-id="5a4f8-115">`DebugAlloc`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="5a4f8-115">`DebugAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="5a4f8-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5a4f8-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5a4f8-117">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="5a4f8-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5a4f8-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5a4f8-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5a4f8-119">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="5a4f8-119">The call timed out.</span></span>|  
|<span data-ttu-id="5a4f8-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5a4f8-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5a4f8-121">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="5a4f8-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5a4f8-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5a4f8-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5a4f8-123">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="5a4f8-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5a4f8-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5a4f8-124">E_FAIL</span></span>|<span data-ttu-id="5a4f8-125">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="5a4f8-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5a4f8-126">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="5a4f8-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5a4f8-127">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5a4f8-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5a4f8-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="5a4f8-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="5a4f8-129">No había suficiente memoria disponible para completar la solicitud de asignación.</span><span class="sxs-lookup"><span data-stu-id="5a4f8-129">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a4f8-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5a4f8-130">Remarks</span></span>  
 <span data-ttu-id="5a4f8-131">CLR Obtiene un puntero de interfaz a una [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instancia mediante una llamada a la [IHostMemoryManager:: CreateMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="5a4f8-131">The CLR gets an interface pointer to an [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span> <span data-ttu-id="5a4f8-132">`DebugAlloc`permite que el tiempo de ejecución obtener información del archivo de código para su uso durante la depuración.</span><span class="sxs-lookup"><span data-stu-id="5a4f8-132">`DebugAlloc` allows the runtime to get code file information for use during debugging.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a4f8-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a4f8-133">Requirements</span></span>  
 <span data-ttu-id="5a4f8-134">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a4f8-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a4f8-135">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5a4f8-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5a4f8-136">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5a4f8-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5a4f8-137">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a4f8-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a4f8-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a4f8-138">See Also</span></span>  
 [<span data-ttu-id="5a4f8-139">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a4f8-139">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="5a4f8-140">IHostMalloc (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a4f8-140">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
