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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170698"
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a><span data-ttu-id="74104-102">IHostThreadPoolManager::GetMinThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="74104-102">IHostThreadPoolManager::GetMinThreads Method</span></span>
<span data-ttu-id="74104-103">Obtiene el número mínimo de subprocesos inactivos que mantiene el host en el grupo de subprocesos en previsión de solicitudes.</span><span class="sxs-lookup"><span data-stu-id="74104-103">Gets the minimum number of idle threads that the host maintains in the thread pool in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74104-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74104-104">Syntax</span></span>  
  
```  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74104-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="74104-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="74104-106">[out] Un puntero al número mínimo de subprocesos de trabajo inactivos que el host mantiene actualmente.</span><span class="sxs-lookup"><span data-stu-id="74104-106">[out] A pointer to the minimum number of idle worker threads that the host currently maintains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74104-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="74104-107">Return Value</span></span>  
  
|<span data-ttu-id="74104-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="74104-108">HRESULT</span></span>|<span data-ttu-id="74104-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="74104-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="74104-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="74104-110">S_OK</span></span>|`GetMinThreads` <span data-ttu-id="74104-111">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="74104-111">returned successfully.</span></span>|  
|<span data-ttu-id="74104-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="74104-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="74104-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="74104-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="74104-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="74104-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="74104-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="74104-115">The call timed out.</span></span>|  
|<span data-ttu-id="74104-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="74104-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="74104-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="74104-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="74104-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="74104-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="74104-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="74104-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="74104-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="74104-120">E_FAIL</span></span>|<span data-ttu-id="74104-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="74104-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="74104-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="74104-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="74104-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="74104-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="74104-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="74104-124">E_NOTIMPL</span></span>|<span data-ttu-id="74104-125">El host no proporciona una implementación de `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="74104-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74104-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="74104-126">Remarks</span></span>  
 <span data-ttu-id="74104-127">El host no tiene que proporcionar una implementación de `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="74104-127">The host is not required to provide an implementation of `GetMinThreads`.</span></span> <span data-ttu-id="74104-128">En este caso, debe devolver un valor HRESULT de E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="74104-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74104-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74104-129">Requirements</span></span>  
 <span data-ttu-id="74104-130">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74104-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74104-131">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="74104-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="74104-132">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="74104-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="74104-133">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="74104-133">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="74104-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="74104-134">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="74104-135">Método GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="74104-135">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="74104-136">Método SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="74104-136">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="74104-137">IHostThreadPoolManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="74104-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
