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
ms.openlocfilehash: 6f58e2290afa166d48306c0bbb50edd1df36888b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804644"
---
# <a name="ihostmallocalloc-method"></a><span data-ttu-id="91df6-102">IHostMAlloc::Alloc (Método)</span><span class="sxs-lookup"><span data-stu-id="91df6-102">IHostMAlloc::Alloc Method</span></span>
<span data-ttu-id="91df6-103">Solicita que el host asigne la cantidad de memoria especificada del montón.</span><span class="sxs-lookup"><span data-stu-id="91df6-103">Requests that the host allocate the specified amount of memory from the heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91df6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="91df6-104">Syntax</span></span>  
  
```cpp  
HRESULT Alloc (  
    [in] SIZE_T  cbSize,
    [in] EMemoryCriticalLevel dwCriticalLevel,
    [out] void** ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91df6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="91df6-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="91df6-106">de Tamaño, en bytes, de la solicitud de asignación de memoria actual.</span><span class="sxs-lookup"><span data-stu-id="91df6-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="91df6-107">de Uno de los valores de [ememorycriticallevel (](ememorycriticallevel-enumeration.md) , que indica el impacto de un error de asignación.</span><span class="sxs-lookup"><span data-stu-id="91df6-107">[in] One of the [EMemoryCriticalLevel](ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="91df6-108">enuncia Puntero a la memoria asignada o null si no se pudo completar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="91df6-108">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="91df6-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="91df6-109">Return Value</span></span>  
  
|<span data-ttu-id="91df6-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="91df6-110">HRESULT</span></span>|<span data-ttu-id="91df6-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="91df6-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="91df6-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="91df6-112">S_OK</span></span>|<span data-ttu-id="91df6-113">`Alloc`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="91df6-113">`Alloc` returned successfully.</span></span>|  
|<span data-ttu-id="91df6-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="91df6-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="91df6-115">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="91df6-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="91df6-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="91df6-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="91df6-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="91df6-117">The call timed out.</span></span>|  
|<span data-ttu-id="91df6-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="91df6-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="91df6-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="91df6-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="91df6-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="91df6-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="91df6-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="91df6-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="91df6-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="91df6-122">E_FAIL</span></span>|<span data-ttu-id="91df6-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="91df6-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="91df6-124">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="91df6-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="91df6-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="91df6-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="91df6-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="91df6-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="91df6-127">No había suficiente memoria disponible para completar la solicitud de asignación.</span><span class="sxs-lookup"><span data-stu-id="91df6-127">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91df6-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="91df6-128">Remarks</span></span>  
 <span data-ttu-id="91df6-129">CLR obtiene un puntero de interfaz a una `IHostMalloc` instancia llamando al método [IHostMemoryManager:: CreateMAlloc (](ihostmemorymanager-createmalloc-method.md) .</span><span class="sxs-lookup"><span data-stu-id="91df6-129">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91df6-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="91df6-130">Requirements</span></span>  
 <span data-ttu-id="91df6-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91df6-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91df6-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="91df6-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="91df6-133">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="91df6-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="91df6-134">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91df6-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91df6-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="91df6-135">See also</span></span>

- [<span data-ttu-id="91df6-136">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="91df6-136">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="91df6-137">IHostMalloc (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="91df6-137">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
