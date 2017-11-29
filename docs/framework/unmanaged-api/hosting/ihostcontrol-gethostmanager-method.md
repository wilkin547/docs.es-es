---
title: "IHostControl::GetHostManager (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostControl.GetHostManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostControl::GetHostManager
helpviewer_keywords:
- GetHostManager method [.NET Framework hosting]
- IHostControl::GetHostManager method [.NET Framework hosting]
ms.assetid: 0fa34bca-ed18-4626-9e78-d33684d18edb
topic_type: apiref
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c711fb2ddf5d21cd8e122a35ebd0b8a5ce0e752f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ihostcontrolgethostmanager-method"></a><span data-ttu-id="636cd-102">IHostControl::GetHostManager (Método)</span><span class="sxs-lookup"><span data-stu-id="636cd-102">IHostControl::GetHostManager Method</span></span>
<span data-ttu-id="636cd-103">Obtiene un puntero de interfaz a la implementación del host de la interfaz con los valores especificados `IID`.</span><span class="sxs-lookup"><span data-stu-id="636cd-103">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="636cd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="636cd-104">Syntax</span></span>  
  
```  
HRESULT GetHostManager (  
    [in] REFIID riid,  
    [out, iid_is(riid)] void** ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="636cd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="636cd-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="636cd-106">[in] El `IID` de la interfaz que common language runtime (CLR) está consultando.</span><span class="sxs-lookup"><span data-stu-id="636cd-106">[in] The `IID` of the interface that the common language runtime (CLR) is querying for.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="636cd-107">[out] Un puntero a la interfaz implementada por el host, o null si el host no admite esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="636cd-107">[out] A pointer to the host-implemented interface, or null if the host does not support this interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="636cd-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="636cd-108">Return Value</span></span>  
  
|<span data-ttu-id="636cd-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="636cd-109">HRESULT</span></span>|<span data-ttu-id="636cd-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="636cd-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="636cd-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="636cd-111">S_OK</span></span>|<span data-ttu-id="636cd-112">`GetHostManager`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="636cd-112">`GetHostManager` returned successfully.</span></span>|  
|<span data-ttu-id="636cd-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="636cd-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="636cd-114">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="636cd-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="636cd-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="636cd-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="636cd-116">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="636cd-116">The call timed out.</span></span>|  
|<span data-ttu-id="636cd-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="636cd-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="636cd-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="636cd-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="636cd-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="636cd-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="636cd-120">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="636cd-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="636cd-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="636cd-121">E_FAIL</span></span>|<span data-ttu-id="636cd-122">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="636cd-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="636cd-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="636cd-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="636cd-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="636cd-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="636cd-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="636cd-125">E_INVALIDARG</span></span>|<span data-ttu-id="636cd-126">Solicitado `IID` no es válido.</span><span class="sxs-lookup"><span data-stu-id="636cd-126">The requested `IID` is not valid.</span></span>|  
|<span data-ttu-id="636cd-127">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="636cd-127">E_NOINTERFACE</span></span>|<span data-ttu-id="636cd-128">No se admite la interfaz solicitada.</span><span class="sxs-lookup"><span data-stu-id="636cd-128">The requested interface is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="636cd-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="636cd-129">Remarks</span></span>  
 <span data-ttu-id="636cd-130">CLR consulta el host para determinar si admite una o varias de las interfaces siguientes:</span><span class="sxs-lookup"><span data-stu-id="636cd-130">The CLR queries the host to determine whether it supports one or more of the following interfaces:</span></span>  
  
-   [<span data-ttu-id="636cd-131">IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="636cd-131">IHostMemoryManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
  
-   [<span data-ttu-id="636cd-132">IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="636cd-132">IHostTaskManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
  
-   [<span data-ttu-id="636cd-133">IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="636cd-133">IHostThreadPoolManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
  
-   [<span data-ttu-id="636cd-134">IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="636cd-134">IHostIoCompletionManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
  
-   [<span data-ttu-id="636cd-135">IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="636cd-135">IHostSyncManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
  
-   [<span data-ttu-id="636cd-136">IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="636cd-136">IHostAssemblyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
  
-   [<span data-ttu-id="636cd-137">IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="636cd-137">IHostGCManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
  
-   [<span data-ttu-id="636cd-138">IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="636cd-138">IHostPolicyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
  
-   [<span data-ttu-id="636cd-139">IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="636cd-139">IHostSecurityManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
  
 <span data-ttu-id="636cd-140">Si el host admite la interfaz especificada, establece `ppObject` a su implementación de dicha interfaz.</span><span class="sxs-lookup"><span data-stu-id="636cd-140">If the host supports the specified interface, it sets `ppObject` to its implementation of that interface.</span></span> <span data-ttu-id="636cd-141">En caso contrario, establece `ppObject` en null.</span><span class="sxs-lookup"><span data-stu-id="636cd-141">Otherwise, it sets `ppObject` to null.</span></span>  
  
 <span data-ttu-id="636cd-142">El CLR no llama a `Release` para administradores de host, incluso cuando se cierra.</span><span class="sxs-lookup"><span data-stu-id="636cd-142">The CLR does not call `Release` on host managers, even when you shut it down.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="636cd-143">Requisitos</span><span class="sxs-lookup"><span data-stu-id="636cd-143">Requirements</span></span>  
 <span data-ttu-id="636cd-144">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="636cd-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="636cd-145">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="636cd-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="636cd-146">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="636cd-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="636cd-147">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="636cd-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="636cd-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="636cd-148">See Also</span></span>  
 [<span data-ttu-id="636cd-149">IHostControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="636cd-149">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
