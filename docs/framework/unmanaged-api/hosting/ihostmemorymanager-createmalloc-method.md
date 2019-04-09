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
ms.openlocfilehash: 194e9b73610ccb7282babf266eea2968a4f035ac
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59179132"
---
# <a name="ihostmemorymanagercreatemalloc-method"></a><span data-ttu-id="556c9-102">IHostMemoryManager::CreateMAlloc (Método)</span><span class="sxs-lookup"><span data-stu-id="556c9-102">IHostMemoryManager::CreateMAlloc Method</span></span>
<span data-ttu-id="556c9-103">Obtiene un puntero de interfaz a un [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instancia que se usa para realizar solicitudes de asignación de un montón creado por el host.</span><span class="sxs-lookup"><span data-stu-id="556c9-103">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to make allocation requests from a heap created by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="556c9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="556c9-104">Syntax</span></span>  
  
```  
HRESULT CreateMalloc (  
    [in]  DWORD         dwMallocType,  
    [out] IHostMalloc **ppMalloc  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="556c9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="556c9-105">Parameters</span></span>  
 `dwMallocType`  
 <span data-ttu-id="556c9-106">[in] Una combinación de [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) marcas que especifica las características de la memoria que se está asignando.</span><span class="sxs-lookup"><span data-stu-id="556c9-106">[in] A combination of [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) flags that specifies the characteristics of the memory that is being allocated.</span></span>  
  
 `ppMAlloc`  
 <span data-ttu-id="556c9-107">[out] Un puntero a la dirección de un `IHostMAlloc` instancia proporcionada por el host.</span><span class="sxs-lookup"><span data-stu-id="556c9-107">[out] A pointer to the address of an `IHostMAlloc` instance provided by the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="556c9-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="556c9-108">Return Value</span></span>  
  
|<span data-ttu-id="556c9-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="556c9-109">HRESULT</span></span>|<span data-ttu-id="556c9-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="556c9-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="556c9-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="556c9-111">S_OK</span></span>|`CreateMAlloc` <span data-ttu-id="556c9-112">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="556c9-112">returned successfully.</span></span>|  
|<span data-ttu-id="556c9-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="556c9-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="556c9-114">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="556c9-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="556c9-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="556c9-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="556c9-116">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="556c9-116">The call timed out.</span></span>|  
|<span data-ttu-id="556c9-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="556c9-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="556c9-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="556c9-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="556c9-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="556c9-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="556c9-120">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="556c9-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="556c9-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="556c9-121">E_FAIL</span></span>|<span data-ttu-id="556c9-122">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="556c9-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="556c9-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="556c9-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="556c9-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="556c9-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="556c9-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="556c9-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="556c9-126">No hay suficiente memoria física no estaba disponible para completar la solicitud de asignación.</span><span class="sxs-lookup"><span data-stu-id="556c9-126">Not enough physical memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="556c9-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="556c9-127">Remarks</span></span>  
 `CreateMAlloc` <span data-ttu-id="556c9-128">Devuelve un objeto que permite que el CLR realizar solicitudes de asignación a través del host en lugar de usar las funciones estándar de Win32.</span><span class="sxs-lookup"><span data-stu-id="556c9-128">returns an object that allows the CLR to make allocation requests through the host instead of using the standard Win32 functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="556c9-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="556c9-129">Requirements</span></span>  
 <span data-ttu-id="556c9-130">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="556c9-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="556c9-131">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="556c9-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="556c9-132">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="556c9-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="556c9-133">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="556c9-133">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="556c9-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="556c9-134">See also</span></span>

- [<span data-ttu-id="556c9-135">IHostMalloc (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="556c9-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
- [<span data-ttu-id="556c9-136">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="556c9-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
