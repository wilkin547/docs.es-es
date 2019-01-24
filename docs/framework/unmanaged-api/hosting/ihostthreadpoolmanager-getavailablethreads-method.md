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
ms.openlocfilehash: 5cb2c7aa5b2bb301cf047ee465ac2e3a755974e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54615314"
---
# <a name="ihostthreadpoolmanagergetavailablethreads-method"></a><span data-ttu-id="1b273-102">IHostThreadPoolManager::GetAvailableThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="1b273-102">IHostThreadPoolManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="1b273-103">Obtiene el número de subprocesos en el grupo de subprocesos que no se están procesando actualmente elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1b273-103">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b273-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1b273-104">Syntax</span></span>  
  
```  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableWorkerThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1b273-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1b273-105">Parameters</span></span>  
 `pdwAvailableWorkerThreads`  
 <span data-ttu-id="1b273-106">[out] Puntero al número de subprocesos en el grupo de subprocesos que no se están procesando actualmente elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1b273-106">[out] Pointer to the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b273-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1b273-107">Return Value</span></span>  
  
|<span data-ttu-id="1b273-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1b273-108">HRESULT</span></span>|<span data-ttu-id="1b273-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="1b273-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1b273-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1b273-110">S_OK</span></span>|<span data-ttu-id="1b273-111">`GetAvailableThreads` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="1b273-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="1b273-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1b273-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1b273-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="1b273-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1b273-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1b273-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1b273-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="1b273-115">The call timed out.</span></span>|  
|<span data-ttu-id="1b273-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1b273-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1b273-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="1b273-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1b273-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1b273-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1b273-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="1b273-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1b273-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1b273-120">E_FAIL</span></span>|<span data-ttu-id="1b273-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="1b273-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1b273-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="1b273-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1b273-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1b273-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1b273-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="1b273-124">E_NOTIMPL</span></span>|<span data-ttu-id="1b273-125">El host no proporciona una implementación de `GetAvailableThreads`.</span><span class="sxs-lookup"><span data-stu-id="1b273-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b273-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1b273-126">Remarks</span></span>  
 <span data-ttu-id="1b273-127">Si el host no proporciona una implementación de `GetAvailableThreads`, debe devolver un valor HRESULT de E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="1b273-127">If the host does not provide an implementation of `GetAvailableThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b273-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1b273-128">Requirements</span></span>  
 <span data-ttu-id="1b273-129">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b273-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b273-130">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1b273-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1b273-131">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1b273-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1b273-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b273-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b273-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b273-133">See also</span></span>
- <xref:System.Threading.ThreadPool.GetAvailableThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="1b273-134">IHostThreadPoolManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1b273-134">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
