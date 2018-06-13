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
ms.openlocfilehash: 355d2e259adb13da44b09e19872337c17ac20ade
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439327"
---
# <a name="ihostcontrolgethostmanager-method"></a><span data-ttu-id="0b2ff-102">IHostControl::GetHostManager (Método)</span><span class="sxs-lookup"><span data-stu-id="0b2ff-102">IHostControl::GetHostManager Method</span></span>
<span data-ttu-id="0b2ff-103">Obtiene un puntero de interfaz a la implementación del host de la interfaz con los valores especificados `IID`.</span><span class="sxs-lookup"><span data-stu-id="0b2ff-103">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b2ff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0b2ff-104">Syntax</span></span>  
  
```  
HRESULT GetHostManager (  
    [in] REFIID riid,  
    [out, iid_is(riid)] void** ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0b2ff-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0b2ff-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="0b2ff-106">[in] El `IID` de la interfaz que common language runtime (CLR) está consultando.</span><span class="sxs-lookup"><span data-stu-id="0b2ff-106">[in] The `IID` of the interface that the common language runtime (CLR) is querying for.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="0b2ff-107">[out] Un puntero a la interfaz implementada por el host, o null si el host no admite esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="0b2ff-107">[out] A pointer to the host-implemented interface, or null if the host does not support this interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0b2ff-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0b2ff-108">Return Value</span></span>  
  
|<span data-ttu-id="0b2ff-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0b2ff-109">HRESULT</span></span>|<span data-ttu-id="0b2ff-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="0b2ff-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0b2ff-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0b2ff-111">S_OK</span></span>|<span data-ttu-id="0b2ff-112">`GetHostManager` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="0b2ff-112">`GetHostManager` returned successfully.</span></span>|  
|<span data-ttu-id="0b2ff-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0b2ff-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0b2ff-114">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="0b2ff-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0b2ff-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0b2ff-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0b2ff-116">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="0b2ff-116">The call timed out.</span></span>|  
|<span data-ttu-id="0b2ff-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0b2ff-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0b2ff-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="0b2ff-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0b2ff-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0b2ff-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0b2ff-120">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="0b2ff-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0b2ff-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0b2ff-121">E_FAIL</span></span>|<span data-ttu-id="0b2ff-122">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="0b2ff-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0b2ff-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="0b2ff-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0b2ff-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0b2ff-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0b2ff-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0b2ff-125">E_INVALIDARG</span></span>|<span data-ttu-id="0b2ff-126">Solicitado `IID` no es válido.</span><span class="sxs-lookup"><span data-stu-id="0b2ff-126">The requested `IID` is not valid.</span></span>|  
|<span data-ttu-id="0b2ff-127">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="0b2ff-127">E_NOINTERFACE</span></span>|<span data-ttu-id="0b2ff-128">No se admite la interfaz solicitada.</span><span class="sxs-lookup"><span data-stu-id="0b2ff-128">The requested interface is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b2ff-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0b2ff-129">Remarks</span></span>  
 <span data-ttu-id="0b2ff-130">CLR consulta el host para determinar si admite una o varias de las interfaces siguientes:</span><span class="sxs-lookup"><span data-stu-id="0b2ff-130">The CLR queries the host to determine whether it supports one or more of the following interfaces:</span></span>  
  
-   [<span data-ttu-id="0b2ff-131">IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="0b2ff-131">IHostMemoryManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
  
-   [<span data-ttu-id="0b2ff-132">IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="0b2ff-132">IHostTaskManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
  
-   [<span data-ttu-id="0b2ff-133">IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="0b2ff-133">IHostThreadPoolManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
  
-   [<span data-ttu-id="0b2ff-134">IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="0b2ff-134">IHostIoCompletionManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
  
-   [<span data-ttu-id="0b2ff-135">IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="0b2ff-135">IHostSyncManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
  
-   [<span data-ttu-id="0b2ff-136">IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="0b2ff-136">IHostAssemblyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
  
-   [<span data-ttu-id="0b2ff-137">IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="0b2ff-137">IHostGCManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
  
-   [<span data-ttu-id="0b2ff-138">IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="0b2ff-138">IHostPolicyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
  
-   [<span data-ttu-id="0b2ff-139">IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="0b2ff-139">IHostSecurityManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
  
 <span data-ttu-id="0b2ff-140">Si el host admite la interfaz especificada, establece `ppObject` a su implementación de dicha interfaz.</span><span class="sxs-lookup"><span data-stu-id="0b2ff-140">If the host supports the specified interface, it sets `ppObject` to its implementation of that interface.</span></span> <span data-ttu-id="0b2ff-141">En caso contrario, establece `ppObject` en null.</span><span class="sxs-lookup"><span data-stu-id="0b2ff-141">Otherwise, it sets `ppObject` to null.</span></span>  
  
 <span data-ttu-id="0b2ff-142">El CLR no llama a `Release` para administradores de host, incluso cuando se cierra.</span><span class="sxs-lookup"><span data-stu-id="0b2ff-142">The CLR does not call `Release` on host managers, even when you shut it down.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b2ff-143">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0b2ff-143">Requirements</span></span>  
 <span data-ttu-id="0b2ff-144">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b2ff-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b2ff-145">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0b2ff-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0b2ff-146">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0b2ff-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0b2ff-147">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b2ff-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b2ff-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b2ff-148">See Also</span></span>  
 [<span data-ttu-id="0b2ff-149">IHostControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0b2ff-149">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
