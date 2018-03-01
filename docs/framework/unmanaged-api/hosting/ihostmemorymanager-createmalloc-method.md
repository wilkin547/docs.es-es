---
title: "IHostMemoryManager::CreateMAlloc (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 19b43ccf7cb2429c28c052ab8ab3a009ec4a30a4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmemorymanagercreatemalloc-method"></a><span data-ttu-id="2df1d-102">IHostMemoryManager::CreateMAlloc (Método)</span><span class="sxs-lookup"><span data-stu-id="2df1d-102">IHostMemoryManager::CreateMAlloc Method</span></span>
<span data-ttu-id="2df1d-103">Obtiene un puntero de interfaz a una [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instancia que se utiliza para realizar solicitudes de asignación de un montón creado por el host.</span><span class="sxs-lookup"><span data-stu-id="2df1d-103">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to make allocation requests from a heap created by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2df1d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2df1d-104">Syntax</span></span>  
  
```  
HRESULT CreateMalloc (  
    [in]  DWORD         dwMallocType,  
    [out] IHostMalloc **ppMalloc  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2df1d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2df1d-105">Parameters</span></span>  
 `dwMallocType`  
 <span data-ttu-id="2df1d-106">[in] Una combinación de [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) marcas que especifica las características de la memoria que se asigna.</span><span class="sxs-lookup"><span data-stu-id="2df1d-106">[in] A combination of [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) flags that specifies the characteristics of the memory that is being allocated.</span></span>  
  
 `ppMAlloc`  
 <span data-ttu-id="2df1d-107">[out] Un puntero a la dirección de un `IHostMAlloc` instancia proporcionada por el host.</span><span class="sxs-lookup"><span data-stu-id="2df1d-107">[out] A pointer to the address of an `IHostMAlloc` instance provided by the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2df1d-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2df1d-108">Return Value</span></span>  
  
|<span data-ttu-id="2df1d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2df1d-109">HRESULT</span></span>|<span data-ttu-id="2df1d-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="2df1d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2df1d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2df1d-111">S_OK</span></span>|<span data-ttu-id="2df1d-112">`CreateMAlloc`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="2df1d-112">`CreateMAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="2df1d-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2df1d-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2df1d-114">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="2df1d-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2df1d-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2df1d-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2df1d-116">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="2df1d-116">The call timed out.</span></span>|  
|<span data-ttu-id="2df1d-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2df1d-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2df1d-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="2df1d-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2df1d-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2df1d-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2df1d-120">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="2df1d-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2df1d-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2df1d-121">E_FAIL</span></span>|<span data-ttu-id="2df1d-122">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="2df1d-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2df1d-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="2df1d-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2df1d-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2df1d-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2df1d-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="2df1d-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="2df1d-126">No hay suficiente memoria física estaba disponible para completar la solicitud de asignación.</span><span class="sxs-lookup"><span data-stu-id="2df1d-126">Not enough physical memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2df1d-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2df1d-127">Remarks</span></span>  
 <span data-ttu-id="2df1d-128">`CreateMAlloc`Devuelve un objeto que permite que el CLR debe realizar solicitudes de asignación a través del host en lugar de utilizar las funciones estándar de Win32.</span><span class="sxs-lookup"><span data-stu-id="2df1d-128">`CreateMAlloc` returns an object that allows the CLR to make allocation requests through the host instead of using the standard Win32 functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2df1d-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2df1d-129">Requirements</span></span>  
 <span data-ttu-id="2df1d-130">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2df1d-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2df1d-131">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2df1d-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2df1d-132">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2df1d-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2df1d-133">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2df1d-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2df1d-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="2df1d-134">See Also</span></span>  
 [<span data-ttu-id="2df1d-135">IHostMalloc (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2df1d-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 [<span data-ttu-id="2df1d-136">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2df1d-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
