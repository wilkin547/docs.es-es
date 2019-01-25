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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ede65c03d0756ddab3314c04cf443c29dcea7801
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582518"
---
# <a name="ihostmemorymanagercreatemalloc-method"></a><span data-ttu-id="a7e8b-102">IHostMemoryManager::CreateMAlloc (Método)</span><span class="sxs-lookup"><span data-stu-id="a7e8b-102">IHostMemoryManager::CreateMAlloc Method</span></span>
<span data-ttu-id="a7e8b-103">Obtiene un puntero de interfaz a un [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instancia que se usa para realizar solicitudes de asignación de un montón creado por el host.</span><span class="sxs-lookup"><span data-stu-id="a7e8b-103">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to make allocation requests from a heap created by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7e8b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a7e8b-104">Syntax</span></span>  
  
```  
HRESULT CreateMalloc (  
    [in]  DWORD         dwMallocType,  
    [out] IHostMalloc **ppMalloc  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a7e8b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a7e8b-105">Parameters</span></span>  
 `dwMallocType`  
 <span data-ttu-id="a7e8b-106">[in] Una combinación de [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) marcas que especifica las características de la memoria que se está asignando.</span><span class="sxs-lookup"><span data-stu-id="a7e8b-106">[in] A combination of [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) flags that specifies the characteristics of the memory that is being allocated.</span></span>  
  
 `ppMAlloc`  
 <span data-ttu-id="a7e8b-107">[out] Un puntero a la dirección de un `IHostMAlloc` instancia proporcionada por el host.</span><span class="sxs-lookup"><span data-stu-id="a7e8b-107">[out] A pointer to the address of an `IHostMAlloc` instance provided by the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7e8b-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a7e8b-108">Return Value</span></span>  
  
|<span data-ttu-id="a7e8b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a7e8b-109">HRESULT</span></span>|<span data-ttu-id="a7e8b-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7e8b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a7e8b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a7e8b-111">S_OK</span></span>|<span data-ttu-id="a7e8b-112">`CreateMAlloc` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a7e8b-112">`CreateMAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="a7e8b-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a7e8b-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a7e8b-114">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="a7e8b-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a7e8b-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a7e8b-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a7e8b-116">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="a7e8b-116">The call timed out.</span></span>|  
|<span data-ttu-id="a7e8b-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a7e8b-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a7e8b-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a7e8b-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a7e8b-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a7e8b-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a7e8b-120">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="a7e8b-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a7e8b-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a7e8b-121">E_FAIL</span></span>|<span data-ttu-id="a7e8b-122">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="a7e8b-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a7e8b-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="a7e8b-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a7e8b-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a7e8b-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a7e8b-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a7e8b-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="a7e8b-126">No hay suficiente memoria física no estaba disponible para completar la solicitud de asignación.</span><span class="sxs-lookup"><span data-stu-id="a7e8b-126">Not enough physical memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7e8b-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a7e8b-127">Remarks</span></span>  
 <span data-ttu-id="a7e8b-128">`CreateMAlloc` Devuelve un objeto que permite que el CLR realizar solicitudes de asignación a través del host en lugar de usar las funciones estándar de Win32.</span><span class="sxs-lookup"><span data-stu-id="a7e8b-128">`CreateMAlloc` returns an object that allows the CLR to make allocation requests through the host instead of using the standard Win32 functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7e8b-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a7e8b-129">Requirements</span></span>  
 <span data-ttu-id="a7e8b-130">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7e8b-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7e8b-131">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a7e8b-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a7e8b-132">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a7e8b-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a7e8b-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7e8b-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7e8b-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7e8b-134">See also</span></span>
- [<span data-ttu-id="a7e8b-135">IHostMalloc (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a7e8b-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
- [<span data-ttu-id="a7e8b-136">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a7e8b-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
