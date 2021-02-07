---
description: 'Más información acerca de: IHostMAlloc:: Alloc (método)'
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
ms.openlocfilehash: e0349c273ef9e3194bb8bad167510dd8fefcab62
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708244"
---
# <a name="ihostmallocalloc-method"></a><span data-ttu-id="bc040-103">IHostMAlloc::Alloc (Método)</span><span class="sxs-lookup"><span data-stu-id="bc040-103">IHostMAlloc::Alloc Method</span></span>

<span data-ttu-id="bc040-104">Solicita que el host asigne la cantidad de memoria especificada del montón.</span><span class="sxs-lookup"><span data-stu-id="bc040-104">Requests that the host allocate the specified amount of memory from the heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc040-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bc040-105">Syntax</span></span>  
  
```cpp  
HRESULT Alloc (  
    [in] SIZE_T  cbSize,
    [in] EMemoryCriticalLevel dwCriticalLevel,
    [out] void** ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc040-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bc040-106">Parameters</span></span>  

 `cbSize`  
 <span data-ttu-id="bc040-107">de Tamaño, en bytes, de la solicitud de asignación de memoria actual.</span><span class="sxs-lookup"><span data-stu-id="bc040-107">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="bc040-108">de Uno de los valores de [ememorycriticallevel (](ememorycriticallevel-enumeration.md) , que indica el impacto de un error de asignación.</span><span class="sxs-lookup"><span data-stu-id="bc040-108">[in] One of the [EMemoryCriticalLevel](ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="bc040-109">enuncia Puntero a la memoria asignada o null si no se pudo completar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="bc040-109">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bc040-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bc040-110">Return Value</span></span>  
  
|<span data-ttu-id="bc040-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bc040-111">HRESULT</span></span>|<span data-ttu-id="bc040-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="bc040-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bc040-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="bc040-113">S_OK</span></span>|<span data-ttu-id="bc040-114">`Alloc` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="bc040-114">`Alloc` returned successfully.</span></span>|  
|<span data-ttu-id="bc040-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bc040-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bc040-116">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="bc040-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bc040-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bc040-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bc040-118">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="bc040-118">The call timed out.</span></span>|  
|<span data-ttu-id="bc040-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bc040-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bc040-120">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="bc040-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bc040-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bc040-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bc040-122">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="bc040-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bc040-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bc040-123">E_FAIL</span></span>|<span data-ttu-id="bc040-124">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="bc040-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bc040-125">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="bc040-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bc040-126">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="bc040-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="bc040-127">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="bc040-127">E_OUTOFMEMORY</span></span>|<span data-ttu-id="bc040-128">No había suficiente memoria disponible para completar la solicitud de asignación.</span><span class="sxs-lookup"><span data-stu-id="bc040-128">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc040-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bc040-129">Remarks</span></span>  

 <span data-ttu-id="bc040-130">CLR obtiene un puntero de interfaz a una `IHostMalloc` instancia llamando al método [IHostMemoryManager:: CreateMAlloc (](ihostmemorymanager-createmalloc-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bc040-130">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc040-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bc040-131">Requirements</span></span>  

 <span data-ttu-id="bc040-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc040-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc040-133">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="bc040-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bc040-134">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bc040-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bc040-135">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc040-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc040-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc040-136">See also</span></span>

- [<span data-ttu-id="bc040-137">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bc040-137">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="bc040-138">IHostMalloc (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bc040-138">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
