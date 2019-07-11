---
title: IHostControl::GetHostManager (Método)
ms.date: 03/30/2017
api_name:
- IHostControl.GetHostManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl::GetHostManager
helpviewer_keywords:
- GetHostManager method [.NET Framework hosting]
- IHostControl::GetHostManager method [.NET Framework hosting]
ms.assetid: 0fa34bca-ed18-4626-9e78-d33684d18edb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b6187da564a62b8c30abdc6a150f0df45d565615
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763872"
---
# <a name="ihostcontrolgethostmanager-method"></a><span data-ttu-id="a2c53-102">IHostControl::GetHostManager (Método)</span><span class="sxs-lookup"><span data-stu-id="a2c53-102">IHostControl::GetHostManager Method</span></span>
<span data-ttu-id="a2c53-103">Obtiene un puntero de interfaz a la implementación del host de la interfaz con los valores especificados `IID`.</span><span class="sxs-lookup"><span data-stu-id="a2c53-103">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2c53-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a2c53-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHostManager (  
    [in] REFIID riid,  
    [out, iid_is(riid)] void** ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2c53-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a2c53-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="a2c53-106">[in] El `IID` de la interfaz que common language runtime (CLR) está consultando.</span><span class="sxs-lookup"><span data-stu-id="a2c53-106">[in] The `IID` of the interface that the common language runtime (CLR) is querying for.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="a2c53-107">[out] Un puntero a la interfaz implementada por el host, o null si el host no admite esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="a2c53-107">[out] A pointer to the host-implemented interface, or null if the host does not support this interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a2c53-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a2c53-108">Return Value</span></span>  
  
|<span data-ttu-id="a2c53-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a2c53-109">HRESULT</span></span>|<span data-ttu-id="a2c53-110">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a2c53-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a2c53-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a2c53-111">S_OK</span></span>|<span data-ttu-id="a2c53-112">`GetHostManager` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a2c53-112">`GetHostManager` returned successfully.</span></span>|  
|<span data-ttu-id="a2c53-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a2c53-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a2c53-114">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="a2c53-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a2c53-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a2c53-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a2c53-116">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="a2c53-116">The call timed out.</span></span>|  
|<span data-ttu-id="a2c53-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a2c53-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a2c53-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a2c53-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a2c53-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a2c53-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a2c53-120">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="a2c53-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a2c53-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a2c53-121">E_FAIL</span></span>|<span data-ttu-id="a2c53-122">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="a2c53-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a2c53-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="a2c53-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a2c53-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a2c53-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a2c53-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a2c53-125">E_INVALIDARG</span></span>|<span data-ttu-id="a2c53-126">Solicitado `IID` no es válido.</span><span class="sxs-lookup"><span data-stu-id="a2c53-126">The requested `IID` is not valid.</span></span>|  
|<span data-ttu-id="a2c53-127">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="a2c53-127">E_NOINTERFACE</span></span>|<span data-ttu-id="a2c53-128">No se admite la interfaz solicitada.</span><span class="sxs-lookup"><span data-stu-id="a2c53-128">The requested interface is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2c53-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a2c53-129">Remarks</span></span>  
 <span data-ttu-id="a2c53-130">El CLR consulta el host para determinar si admite una o varias de las interfaces siguientes:</span><span class="sxs-lookup"><span data-stu-id="a2c53-130">The CLR queries the host to determine whether it supports one or more of the following interfaces:</span></span>  
  
- [<span data-ttu-id="a2c53-131">IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="a2c53-131">IHostMemoryManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
  
- [<span data-ttu-id="a2c53-132">IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="a2c53-132">IHostTaskManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
  
- [<span data-ttu-id="a2c53-133">IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="a2c53-133">IHostThreadPoolManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
  
- [<span data-ttu-id="a2c53-134">IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="a2c53-134">IHostIoCompletionManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
  
- [<span data-ttu-id="a2c53-135">IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="a2c53-135">IHostSyncManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
  
- [<span data-ttu-id="a2c53-136">IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="a2c53-136">IHostAssemblyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
  
- [<span data-ttu-id="a2c53-137">IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="a2c53-137">IHostGCManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
  
- [<span data-ttu-id="a2c53-138">IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="a2c53-138">IHostPolicyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
  
- [<span data-ttu-id="a2c53-139">IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="a2c53-139">IHostSecurityManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
  
 <span data-ttu-id="a2c53-140">Si el host admite la interfaz especificada, establece `ppObject` a su implementación de dicha interfaz.</span><span class="sxs-lookup"><span data-stu-id="a2c53-140">If the host supports the specified interface, it sets `ppObject` to its implementation of that interface.</span></span> <span data-ttu-id="a2c53-141">De lo contrario, establece `ppObject` en null.</span><span class="sxs-lookup"><span data-stu-id="a2c53-141">Otherwise, it sets `ppObject` to null.</span></span>  
  
 <span data-ttu-id="a2c53-142">El CLR no llama a `Release` en administradores de host, incluso cuando se cierra.</span><span class="sxs-lookup"><span data-stu-id="a2c53-142">The CLR does not call `Release` on host managers, even when you shut it down.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2c53-143">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a2c53-143">Requirements</span></span>  
 <span data-ttu-id="a2c53-144">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2c53-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2c53-145">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a2c53-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a2c53-146">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a2c53-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a2c53-147">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2c53-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2c53-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2c53-148">See also</span></span>

- [<span data-ttu-id="a2c53-149">IHostControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a2c53-149">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
