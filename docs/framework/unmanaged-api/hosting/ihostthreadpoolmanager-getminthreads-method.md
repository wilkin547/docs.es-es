---
title: IHostThreadPoolManager::GetMinThreads (Método)
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetMinThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMinThreads method [.NET Framework hosting]
- GetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: dc07232b-b2e4-4dab-87e2-3c955974ab48
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f1230a72d06677b4d36d10a8a31d63638c1fcd41
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796565"
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a><span data-ttu-id="8dc24-102">IHostThreadPoolManager::GetMinThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="8dc24-102">IHostThreadPoolManager::GetMinThreads Method</span></span>
<span data-ttu-id="8dc24-103">Obtiene el número mínimo de subprocesos inactivos que mantiene el host en el grupo de subprocesos en previsión de solicitudes.</span><span class="sxs-lookup"><span data-stu-id="8dc24-103">Gets the minimum number of idle threads that the host maintains in the thread pool in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dc24-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8dc24-104">Syntax</span></span>  
  
```  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8dc24-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8dc24-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="8dc24-106">[out] Un puntero al número mínimo de subprocesos de trabajo inactivos que el host mantiene actualmente.</span><span class="sxs-lookup"><span data-stu-id="8dc24-106">[out] A pointer to the minimum number of idle worker threads that the host currently maintains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8dc24-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8dc24-107">Return Value</span></span>  
  
|<span data-ttu-id="8dc24-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8dc24-108">HRESULT</span></span>|<span data-ttu-id="8dc24-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="8dc24-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8dc24-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8dc24-110">S_OK</span></span>|<span data-ttu-id="8dc24-111">`GetMinThreads` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="8dc24-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="8dc24-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8dc24-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8dc24-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="8dc24-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8dc24-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8dc24-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8dc24-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="8dc24-115">The call timed out.</span></span>|  
|<span data-ttu-id="8dc24-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8dc24-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8dc24-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="8dc24-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8dc24-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8dc24-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8dc24-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="8dc24-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8dc24-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8dc24-120">E_FAIL</span></span>|<span data-ttu-id="8dc24-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="8dc24-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8dc24-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="8dc24-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8dc24-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8dc24-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8dc24-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="8dc24-124">E_NOTIMPL</span></span>|<span data-ttu-id="8dc24-125">El host no proporciona una implementación de `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="8dc24-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8dc24-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8dc24-126">Remarks</span></span>  
 <span data-ttu-id="8dc24-127">El host no tiene que proporcionar una implementación de `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="8dc24-127">The host is not required to provide an implementation of `GetMinThreads`.</span></span> <span data-ttu-id="8dc24-128">En este caso, debe devolver un valor HRESULT de E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="8dc24-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8dc24-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8dc24-129">Requirements</span></span>  
 <span data-ttu-id="8dc24-130">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8dc24-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8dc24-131">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8dc24-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8dc24-132">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8dc24-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8dc24-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8dc24-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dc24-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="8dc24-134">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="8dc24-135">GetMaxThreads (método)</span><span class="sxs-lookup"><span data-stu-id="8dc24-135">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="8dc24-136">SetMinThreads (método)</span><span class="sxs-lookup"><span data-stu-id="8dc24-136">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="8dc24-137">IHostThreadPoolManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8dc24-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
