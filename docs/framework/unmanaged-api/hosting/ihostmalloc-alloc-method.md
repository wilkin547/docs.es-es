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
ms.openlocfilehash: 32499e74e8af9a865347bd800d3db4c303a7344c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59126391"
---
# <a name="ihostmallocalloc-method"></a><span data-ttu-id="6ccd6-102">IHostMAlloc::Alloc (Método)</span><span class="sxs-lookup"><span data-stu-id="6ccd6-102">IHostMAlloc::Alloc Method</span></span>
<span data-ttu-id="6ccd6-103">Solicita que el host de asignar la cantidad de memoria especificada desde el montón.</span><span class="sxs-lookup"><span data-stu-id="6ccd6-103">Requests that the host allocate the specified amount of memory from the heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ccd6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6ccd6-104">Syntax</span></span>  
  
```  
HRESULT Alloc (  
    [in] SIZE_T  cbSize,   
    [in] EMemoryCriticalLevel dwCriticalLevel,   
    [out] void** ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ccd6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6ccd6-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="6ccd6-106">[in] El tamaño, en bytes, de la solicitud de asignación de memoria actual.</span><span class="sxs-lookup"><span data-stu-id="6ccd6-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="6ccd6-107">[in] Uno de los [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) valores, que indica el impacto de un error de asignación.</span><span class="sxs-lookup"><span data-stu-id="6ccd6-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="6ccd6-108">[out] Un puntero a la memoria asignada, o null si no se pudo completar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="6ccd6-108">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6ccd6-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6ccd6-109">Return Value</span></span>  
  
|<span data-ttu-id="6ccd6-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6ccd6-110">HRESULT</span></span>|<span data-ttu-id="6ccd6-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="6ccd6-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6ccd6-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="6ccd6-112">S_OK</span></span>|`Alloc` <span data-ttu-id="6ccd6-113">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="6ccd6-113">returned successfully.</span></span>|  
|<span data-ttu-id="6ccd6-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6ccd6-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6ccd6-115">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="6ccd6-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6ccd6-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6ccd6-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6ccd6-117">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="6ccd6-117">The call timed out.</span></span>|  
|<span data-ttu-id="6ccd6-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6ccd6-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6ccd6-119">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="6ccd6-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6ccd6-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6ccd6-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6ccd6-121">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="6ccd6-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6ccd6-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6ccd6-122">E_FAIL</span></span>|<span data-ttu-id="6ccd6-123">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="6ccd6-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6ccd6-124">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="6ccd6-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6ccd6-125">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6ccd6-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6ccd6-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="6ccd6-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="6ccd6-127">No había suficiente memoria disponible para completar la solicitud de asignación.</span><span class="sxs-lookup"><span data-stu-id="6ccd6-127">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ccd6-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6ccd6-128">Remarks</span></span>  
 <span data-ttu-id="6ccd6-129">CLR Obtiene un puntero de interfaz a un `IHostMalloc` instancia mediante una llamada a la [IHostMemoryManager:: CreateMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="6ccd6-129">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ccd6-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6ccd6-130">Requirements</span></span>  
 <span data-ttu-id="6ccd6-131">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ccd6-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ccd6-132">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6ccd6-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6ccd6-133">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6ccd6-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="6ccd6-134">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="6ccd6-134">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6ccd6-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ccd6-135">See also</span></span>

- [<span data-ttu-id="6ccd6-136">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6ccd6-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="6ccd6-137">IHostMalloc (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6ccd6-137">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
