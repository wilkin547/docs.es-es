---
title: IHostThreadPoolManager::GetAvailableThreads (Método)
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: 61d26dfd-7f24-4e7d-a63e-b30a463f08e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a8350140bb0871acc560163848ac50eafef42f01
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441220"
---
# <a name="ihostthreadpoolmanagergetavailablethreads-method"></a><span data-ttu-id="639fb-102">IHostThreadPoolManager::GetAvailableThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="639fb-102">IHostThreadPoolManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="639fb-103">Obtiene el número de subprocesos en el grupo de subprocesos que no se están procesando actualmente elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="639fb-103">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="639fb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="639fb-104">Syntax</span></span>  
  
```  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableWorkerThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="639fb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="639fb-105">Parameters</span></span>  
 `pdwAvailableWorkerThreads`  
 <span data-ttu-id="639fb-106">[out] Puntero al número de subprocesos en el grupo de subprocesos que no se están procesando actualmente elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="639fb-106">[out] Pointer to the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="639fb-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="639fb-107">Return Value</span></span>  
  
|<span data-ttu-id="639fb-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="639fb-108">HRESULT</span></span>|<span data-ttu-id="639fb-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="639fb-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="639fb-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="639fb-110">S_OK</span></span>|<span data-ttu-id="639fb-111">`GetAvailableThreads` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="639fb-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="639fb-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="639fb-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="639fb-113">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="639fb-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="639fb-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="639fb-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="639fb-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="639fb-115">The call timed out.</span></span>|  
|<span data-ttu-id="639fb-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="639fb-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="639fb-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="639fb-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="639fb-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="639fb-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="639fb-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="639fb-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="639fb-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="639fb-120">E_FAIL</span></span>|<span data-ttu-id="639fb-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="639fb-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="639fb-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="639fb-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="639fb-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="639fb-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="639fb-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="639fb-124">E_NOTIMPL</span></span>|<span data-ttu-id="639fb-125">El host no proporciona una implementación de `GetAvailableThreads`.</span><span class="sxs-lookup"><span data-stu-id="639fb-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="639fb-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="639fb-126">Remarks</span></span>  
 <span data-ttu-id="639fb-127">Si el host no proporciona una implementación de `GetAvailableThreads`, debe devolver un valor HRESULT de E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="639fb-127">If the host does not provide an implementation of `GetAvailableThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="639fb-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="639fb-128">Requirements</span></span>  
 <span data-ttu-id="639fb-129">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="639fb-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="639fb-130">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="639fb-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="639fb-131">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="639fb-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="639fb-132">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="639fb-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="639fb-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="639fb-133">See Also</span></span>  
 <xref:System.Threading.ThreadPool.GetAvailableThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="639fb-134">IHostThreadPoolManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="639fb-134">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
