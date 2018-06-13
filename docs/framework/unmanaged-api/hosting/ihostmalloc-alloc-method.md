---
title: IHostMAlloc::Alloc (Método)
ms.date: 03/30/2017
api_name:
- IHostMAlloc.Alloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::Alloc
helpviewer_keywords:
- Alloc method, IHostMAlloc interface [.NET Framework hosting]
- IHostMAlloc::Alloc method [.NET Framework hosting]
ms.assetid: a3007f5e-d75d-4b37-842b-704e9edced5e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7d67704aae80113bd41df5ea38acf2a794aacbac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439051"
---
# <a name="ihostmallocalloc-method"></a><span data-ttu-id="c0516-102">IHostMAlloc::Alloc (Método)</span><span class="sxs-lookup"><span data-stu-id="c0516-102">IHostMAlloc::Alloc Method</span></span>
<span data-ttu-id="c0516-103">Solicita que el host de asignar la cantidad especificada de memoria del montón.</span><span class="sxs-lookup"><span data-stu-id="c0516-103">Requests that the host allocate the specified amount of memory from the heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0516-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c0516-104">Syntax</span></span>  
  
```  
HRESULT Alloc (  
    [in] SIZE_T  cbSize,   
    [in] EMemoryCriticalLevel dwCriticalLevel,   
    [out] void** ppMem  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c0516-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c0516-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="c0516-106">[in] El tamaño, en bytes, de la solicitud de asignación de memoria actual.</span><span class="sxs-lookup"><span data-stu-id="c0516-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="c0516-107">[in] Uno de los [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) valores, que indican el impacto de un error de asignación.</span><span class="sxs-lookup"><span data-stu-id="c0516-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="c0516-108">[out] Un puntero a la memoria asignada, o null si no se pudo completar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="c0516-108">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c0516-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c0516-109">Return Value</span></span>  
  
|<span data-ttu-id="c0516-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c0516-110">HRESULT</span></span>|<span data-ttu-id="c0516-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="c0516-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c0516-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c0516-112">S_OK</span></span>|<span data-ttu-id="c0516-113">`Alloc` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="c0516-113">`Alloc` returned successfully.</span></span>|  
|<span data-ttu-id="c0516-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c0516-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c0516-115">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c0516-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c0516-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c0516-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c0516-117">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="c0516-117">The call timed out.</span></span>|  
|<span data-ttu-id="c0516-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c0516-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c0516-119">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="c0516-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c0516-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c0516-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c0516-121">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="c0516-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c0516-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c0516-122">E_FAIL</span></span>|<span data-ttu-id="c0516-123">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="c0516-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c0516-124">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="c0516-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c0516-125">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c0516-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c0516-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c0516-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="c0516-127">No había suficiente memoria disponible para completar la solicitud de asignación.</span><span class="sxs-lookup"><span data-stu-id="c0516-127">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0516-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c0516-128">Remarks</span></span>  
 <span data-ttu-id="c0516-129">CLR Obtiene un puntero de interfaz a una `IHostMalloc` instancia mediante una llamada a la [IHostMemoryManager:: CreateMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="c0516-129">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0516-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c0516-130">Requirements</span></span>  
 <span data-ttu-id="c0516-131">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0516-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0516-132">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c0516-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c0516-133">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c0516-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c0516-134">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0516-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0516-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0516-135">See Also</span></span>  
 [<span data-ttu-id="c0516-136">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c0516-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="c0516-137">IHostMalloc (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c0516-137">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
