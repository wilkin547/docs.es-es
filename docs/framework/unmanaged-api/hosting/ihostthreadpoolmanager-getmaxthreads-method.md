---
title: "IHostThreadPoolManager::GetMaxThreads (Método)"
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
- IHostThreadPoolManager.GetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: db268876-6178-4a81-aca3-318ee7f96001
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 84867f1b5dfdcfd7a50d01c9e51cb0c42da62f0e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a><span data-ttu-id="ce524-102">IHostThreadPoolManager::GetMaxThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="ce524-102">IHostThreadPoolManager::GetMaxThreads Method</span></span>
<span data-ttu-id="ce524-103">Obtiene el número máximo de subprocesos que el host mantiene simultáneamente en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="ce524-103">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce524-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ce524-104">Syntax</span></span>  
  
```  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ce524-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ce524-105">Parameters</span></span>  
 `pdwMaxWorkerThreads`  
 <span data-ttu-id="ce524-106">[out] Un puntero al número máximo de subprocesos que el host mantiene en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="ce524-106">[out] A pointer to the maximum number of threads that the host maintains in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ce524-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ce524-107">Return Value</span></span>  
  
|<span data-ttu-id="ce524-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ce524-108">HRESULT</span></span>|<span data-ttu-id="ce524-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="ce524-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ce524-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ce524-110">S_OK</span></span>|<span data-ttu-id="ce524-111">`GetMaxThreads`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ce524-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="ce524-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ce524-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ce524-113">Common language runtime (CLR (no se ha cargado en un proceso, o el CLR se encuentra en un estado donde no se puede ejecutar código administrado o en proceso de la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="ce524-113">The common language runtime (CLR( has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ce524-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ce524-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ce524-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="ce524-115">The call timed out.</span></span>|  
|<span data-ttu-id="ce524-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ce524-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ce524-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ce524-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ce524-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ce524-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ce524-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="ce524-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ce524-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ce524-120">E_FAIL</span></span>|<span data-ttu-id="ce524-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="ce524-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ce524-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="ce524-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ce524-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ce524-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ce524-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="ce524-124">E_NOTIMPL</span></span>|<span data-ttu-id="ce524-125">El host no proporciona una implementación de `GetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="ce524-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce524-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ce524-126">Remarks</span></span>  
 <span data-ttu-id="ce524-127">CLR llama `GetMaxThreads` para determinar el número total de subprocesos en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="ce524-127">The CLR calls `GetMaxThreads` to determine the total number of threads in the thread pool.</span></span> <span data-ttu-id="ce524-128">El [GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) método obtiene el número de subprocesos que no se están procesando actualmente elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ce524-128">The [GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) method gets the number of threads that are not currently processing work items.</span></span> <span data-ttu-id="ce524-129">Todas las solicitudes por encima del valor devuelto de la `pdwMaxWorkerThreads` parámetro permanecen en la cola hasta que haya disponibles subprocesos.</span><span class="sxs-lookup"><span data-stu-id="ce524-129">All requests above the returned value of the `pdwMaxWorkerThreads` parameter remain queued until threads become available.</span></span>  
  
 <span data-ttu-id="ce524-130">Si el host no proporciona una implementación de `GetMaxThreads`, debe devolver un valor HRESULT de E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="ce524-130">If the host does not provide an implementation of `GetMaxThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce524-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ce524-131">Requirements</span></span>  
 <span data-ttu-id="ce524-132">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce524-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce524-133">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ce524-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ce524-134">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ce524-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ce524-135">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce524-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce524-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce524-136">See Also</span></span>  
 <xref:System.Threading.ThreadPool.GetMaxThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="ce524-137">GetMinThreads (método)</span><span class="sxs-lookup"><span data-stu-id="ce524-137">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)  
 [<span data-ttu-id="ce524-138">SetMaxThreads (método)</span><span class="sxs-lookup"><span data-stu-id="ce524-138">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)  
 [<span data-ttu-id="ce524-139">IHostThreadPoolManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ce524-139">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
