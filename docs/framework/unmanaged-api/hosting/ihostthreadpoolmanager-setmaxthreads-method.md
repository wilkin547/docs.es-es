---
title: IHostThreadPoolManager::SetMaxThreads (Método)
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.SetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::SetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: 77cfd347-95c2-4425-b807-4ecc2a8d4578
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0df8d11bba870dfec880401064ec3f78f5f04e1f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59081481"
---
# <a name="ihostthreadpoolmanagersetmaxthreads-method"></a><span data-ttu-id="ae30a-102">IHostThreadPoolManager::SetMaxThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="ae30a-102">IHostThreadPoolManager::SetMaxThreads Method</span></span>
<span data-ttu-id="ae30a-103">Establece el número máximo de subprocesos que el host puede mantener en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="ae30a-103">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae30a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ae30a-104">Syntax</span></span>  
  
```  
HRESULT SetMaxThreads (  
    [in] DWORD MaxThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae30a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ae30a-105">Parameters</span></span>  
 `MaxThreads`  
 <span data-ttu-id="ae30a-106">Número máximo de subprocesos de trabajo en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="ae30a-106">The maximum number of worker threads in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae30a-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ae30a-107">Return Value</span></span>  
  
|<span data-ttu-id="ae30a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ae30a-108">HRESULT</span></span>|<span data-ttu-id="ae30a-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="ae30a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ae30a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ae30a-110">S_OK</span></span>|<span data-ttu-id="ae30a-111">`SetMaxThreads` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ae30a-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="ae30a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ae30a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ae30a-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="ae30a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ae30a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ae30a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ae30a-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="ae30a-115">The call timed out.</span></span>|  
|<span data-ttu-id="ae30a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ae30a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ae30a-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ae30a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ae30a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ae30a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ae30a-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="ae30a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ae30a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ae30a-120">E_FAIL</span></span>|<span data-ttu-id="ae30a-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="ae30a-121">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="ae30a-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="ae30a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ae30a-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ae30a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ae30a-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="ae30a-124">E_NOTIMPL</span></span>|<span data-ttu-id="ae30a-125">El host no proporciona una implementación de `SetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="ae30a-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae30a-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ae30a-126">Remarks</span></span>  
 <span data-ttu-id="ae30a-127">No es necesario para permitir que el CLR configurar el tamaño del grupo de subprocesos de un host.</span><span class="sxs-lookup"><span data-stu-id="ae30a-127">A host is not required to allow the CLR to configure the size of the thread pool.</span></span> <span data-ttu-id="ae30a-128">Algunos hosts podría control exclusivo sobre el grupo de subprocesos, por motivos de implementación, rendimiento o escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="ae30a-128">Some hosts might want exclusive control over the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="ae30a-129">En este caso, un host debe devolver un valor HRESULT de E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="ae30a-129">In this case, a host should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae30a-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ae30a-130">Requirements</span></span>  
 <span data-ttu-id="ae30a-131">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae30a-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae30a-132">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ae30a-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ae30a-133">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ae30a-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ae30a-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae30a-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae30a-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae30a-135">See also</span></span>

- <xref:System.Threading.ThreadPool.SetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="ae30a-136">GetMaxThreads (método)</span><span class="sxs-lookup"><span data-stu-id="ae30a-136">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="ae30a-137">SetMinThreads (método)</span><span class="sxs-lookup"><span data-stu-id="ae30a-137">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="ae30a-138">IHostThreadPoolManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ae30a-138">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
