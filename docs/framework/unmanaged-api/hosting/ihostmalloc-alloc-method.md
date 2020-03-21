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
ms.openlocfilehash: dded37fdef02963f60883b289462aa6a96693b3d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176310"
---
# <a name="ihostmallocalloc-method"></a><span data-ttu-id="36486-102">IHostMAlloc::Alloc (Método)</span><span class="sxs-lookup"><span data-stu-id="36486-102">IHostMAlloc::Alloc Method</span></span>
<span data-ttu-id="36486-103">Solicita que el host asigne la cantidad especificada de memoria del montón.</span><span class="sxs-lookup"><span data-stu-id="36486-103">Requests that the host allocate the specified amount of memory from the heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36486-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36486-104">Syntax</span></span>  
  
```cpp  
HRESULT Alloc (  
    [in] SIZE_T  cbSize,
    [in] EMemoryCriticalLevel dwCriticalLevel,
    [out] void** ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36486-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="36486-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="36486-106">[en] El tamaño, en bytes, de la solicitud de asignación de memoria actual.</span><span class="sxs-lookup"><span data-stu-id="36486-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="36486-107">[en] Uno de los [eMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) valores, que indica el impacto de un error de asignación.</span><span class="sxs-lookup"><span data-stu-id="36486-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="36486-108">[fuera] Un puntero a la memoria asignada, o null si no se pudo completar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="36486-108">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36486-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="36486-109">Return Value</span></span>  
  
|<span data-ttu-id="36486-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="36486-110">HRESULT</span></span>|<span data-ttu-id="36486-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="36486-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="36486-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="36486-112">S_OK</span></span>|<span data-ttu-id="36486-113">`Alloc`regresó con éxito.</span><span class="sxs-lookup"><span data-stu-id="36486-113">`Alloc` returned successfully.</span></span>|  
|<span data-ttu-id="36486-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="36486-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="36486-115">Common Language Runtime (CLR) no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="36486-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="36486-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="36486-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="36486-117">Se adelantó la llamada.</span><span class="sxs-lookup"><span data-stu-id="36486-117">The call timed out.</span></span>|  
|<span data-ttu-id="36486-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="36486-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="36486-119">El autor de la llamada no es el propietario de la cerradura.</span><span class="sxs-lookup"><span data-stu-id="36486-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="36486-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="36486-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="36486-121">Un evento se canceló mientras un hilo bloqueado o fibra lo esperaba.</span><span class="sxs-lookup"><span data-stu-id="36486-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="36486-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="36486-122">E_FAIL</span></span>|<span data-ttu-id="36486-123">Se ha producido un fallo catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="36486-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="36486-124">Cuando un método devuelve E_FAIL, CLR ya no se puede usar dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="36486-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="36486-125">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="36486-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="36486-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="36486-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="36486-127">No había suficiente memoria disponible para completar la solicitud de asignación.</span><span class="sxs-lookup"><span data-stu-id="36486-127">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36486-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="36486-128">Remarks</span></span>  
 <span data-ttu-id="36486-129">El CLR obtiene un puntero `IHostMalloc` de interfaz a una instancia mediante una llamada a la [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="36486-129">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36486-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="36486-130">Requirements</span></span>  
 <span data-ttu-id="36486-131">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36486-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36486-132">**Encabezado:** MScorEE.h</span><span class="sxs-lookup"><span data-stu-id="36486-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="36486-133">**Biblioteca:** Incluido como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="36486-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="36486-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36486-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36486-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="36486-135">See also</span></span>

- [<span data-ttu-id="36486-136">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="36486-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="36486-137">IHostMalloc (interfaz)</span><span class="sxs-lookup"><span data-stu-id="36486-137">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
