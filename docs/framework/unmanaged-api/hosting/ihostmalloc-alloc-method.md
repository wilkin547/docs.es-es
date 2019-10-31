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
ms.openlocfilehash: 9837e4e3428a0293c8e689b3f3e081aa07f055b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192070"
---
# <a name="ihostmallocalloc-method"></a><span data-ttu-id="e0be8-102">IHostMAlloc::Alloc (Método)</span><span class="sxs-lookup"><span data-stu-id="e0be8-102">IHostMAlloc::Alloc Method</span></span>
<span data-ttu-id="e0be8-103">Solicita que el host asigne la cantidad de memoria especificada del montón.</span><span class="sxs-lookup"><span data-stu-id="e0be8-103">Requests that the host allocate the specified amount of memory from the heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0be8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e0be8-104">Syntax</span></span>  
  
```cpp  
HRESULT Alloc (  
    [in] SIZE_T  cbSize,   
    [in] EMemoryCriticalLevel dwCriticalLevel,   
    [out] void** ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0be8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e0be8-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="e0be8-106">de Tamaño, en bytes, de la solicitud de asignación de memoria actual.</span><span class="sxs-lookup"><span data-stu-id="e0be8-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="e0be8-107">de Uno de los valores de [ememorycriticallevel (](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) , que indica el impacto de un error de asignación.</span><span class="sxs-lookup"><span data-stu-id="e0be8-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="e0be8-108">enuncia Puntero a la memoria asignada o null si no se pudo completar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="e0be8-108">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0be8-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e0be8-109">Return Value</span></span>  
  
|<span data-ttu-id="e0be8-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e0be8-110">HRESULT</span></span>|<span data-ttu-id="e0be8-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0be8-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e0be8-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="e0be8-112">S_OK</span></span>|<span data-ttu-id="e0be8-113">`Alloc` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="e0be8-113">`Alloc` returned successfully.</span></span>|  
|<span data-ttu-id="e0be8-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e0be8-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e0be8-115">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="e0be8-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e0be8-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e0be8-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e0be8-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="e0be8-117">The call timed out.</span></span>|  
|<span data-ttu-id="e0be8-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e0be8-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e0be8-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="e0be8-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e0be8-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e0be8-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e0be8-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="e0be8-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e0be8-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e0be8-122">E_FAIL</span></span>|<span data-ttu-id="e0be8-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="e0be8-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e0be8-124">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="e0be8-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e0be8-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e0be8-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e0be8-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="e0be8-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="e0be8-127">No había suficiente memoria disponible para completar la solicitud de asignación.</span><span class="sxs-lookup"><span data-stu-id="e0be8-127">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0be8-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e0be8-128">Remarks</span></span>  
 <span data-ttu-id="e0be8-129">CLR obtiene un puntero de interfaz a una instancia de `IHostMalloc` llamando al método [IHostMemoryManager:: CreateMAlloc (](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e0be8-129">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0be8-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e0be8-130">Requirements</span></span>  
 <span data-ttu-id="e0be8-131">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0be8-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0be8-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e0be8-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e0be8-133">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e0be8-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e0be8-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0be8-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0be8-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0be8-135">See also</span></span>

- [<span data-ttu-id="e0be8-136">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e0be8-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="e0be8-137">IHostMalloc (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e0be8-137">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
