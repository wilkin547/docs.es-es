---
title: IHostMemoryManager::CreateMAlloc (Método)
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.CreateMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::CreateMAlloc
helpviewer_keywords:
- CreateAlloc method [.NET Framework hosting]
- IHostMemoryManager::CreateMAlloc method [.NET Framework hosting]
ms.assetid: 9ee6e052-bef7-4350-9e4f-edfffd99ad6f
topic_type:
- apiref
ms.openlocfilehash: 8bcb01f4a19e6043bd59fe6f1565cdf35ed1f77c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136723"
---
# <a name="ihostmemorymanagercreatemalloc-method"></a><span data-ttu-id="e4e80-102">IHostMemoryManager::CreateMAlloc (Método)</span><span class="sxs-lookup"><span data-stu-id="e4e80-102">IHostMemoryManager::CreateMAlloc Method</span></span>
<span data-ttu-id="e4e80-103">Obtiene un puntero de interfaz a una instancia de [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) que se utiliza para hacer solicitudes de asignación de un montón creado por el host.</span><span class="sxs-lookup"><span data-stu-id="e4e80-103">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to make allocation requests from a heap created by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4e80-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4e80-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateMalloc (  
    [in]  DWORD         dwMallocType,  
    [out] IHostMalloc **ppMalloc  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4e80-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e4e80-105">Parameters</span></span>  
 `dwMallocType`  
 <span data-ttu-id="e4e80-106">de Combinación de marcas [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) que especifica las características de la memoria que se va a asignar.</span><span class="sxs-lookup"><span data-stu-id="e4e80-106">[in] A combination of [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) flags that specifies the characteristics of the memory that is being allocated.</span></span>  
  
 `ppMAlloc`  
 <span data-ttu-id="e4e80-107">enuncia Puntero a la dirección de una instancia de `IHostMAlloc` proporcionada por el host.</span><span class="sxs-lookup"><span data-stu-id="e4e80-107">[out] A pointer to the address of an `IHostMAlloc` instance provided by the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e4e80-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e4e80-108">Return Value</span></span>  
  
|<span data-ttu-id="e4e80-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e4e80-109">HRESULT</span></span>|<span data-ttu-id="e4e80-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4e80-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e4e80-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e4e80-111">S_OK</span></span>|<span data-ttu-id="e4e80-112">`CreateMAlloc` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="e4e80-112">`CreateMAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="e4e80-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e4e80-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e4e80-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="e4e80-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e4e80-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e4e80-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e4e80-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="e4e80-116">The call timed out.</span></span>|  
|<span data-ttu-id="e4e80-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e4e80-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e4e80-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="e4e80-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e4e80-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e4e80-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e4e80-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="e4e80-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e4e80-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e4e80-121">E_FAIL</span></span>|<span data-ttu-id="e4e80-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="e4e80-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e4e80-123">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="e4e80-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e4e80-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e4e80-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e4e80-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="e4e80-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="e4e80-126">No había suficiente memoria física disponible para completar la solicitud de asignación.</span><span class="sxs-lookup"><span data-stu-id="e4e80-126">Not enough physical memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4e80-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e4e80-127">Remarks</span></span>  
 <span data-ttu-id="e4e80-128">`CreateMAlloc` devuelve un objeto que permite que CLR realice solicitudes de asignación a través del host en lugar de usar las funciones estándar de Win32.</span><span class="sxs-lookup"><span data-stu-id="e4e80-128">`CreateMAlloc` returns an object that allows the CLR to make allocation requests through the host instead of using the standard Win32 functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4e80-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e4e80-129">Requirements</span></span>  
 <span data-ttu-id="e4e80-130">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4e80-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4e80-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e4e80-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e4e80-132">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e4e80-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e4e80-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4e80-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4e80-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4e80-134">See also</span></span>

- [<span data-ttu-id="e4e80-135">IHostMalloc (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e4e80-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
- [<span data-ttu-id="e4e80-136">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e4e80-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
