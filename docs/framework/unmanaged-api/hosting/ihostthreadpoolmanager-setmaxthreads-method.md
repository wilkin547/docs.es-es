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
ms.openlocfilehash: 30c4ff93688396dd9a6a8086fbb53ad1c763ead0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141302"
---
# <a name="ihostthreadpoolmanagersetmaxthreads-method"></a><span data-ttu-id="cce64-102">IHostThreadPoolManager::SetMaxThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="cce64-102">IHostThreadPoolManager::SetMaxThreads Method</span></span>
<span data-ttu-id="cce64-103">Establece el número máximo de subprocesos que el host puede mantener en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="cce64-103">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cce64-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cce64-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMaxThreads (  
    [in] DWORD MaxThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cce64-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cce64-105">Parameters</span></span>  
 `MaxThreads`  
 <span data-ttu-id="cce64-106">Número máximo de subprocesos de trabajo en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="cce64-106">The maximum number of worker threads in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cce64-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cce64-107">Return Value</span></span>  
  
|<span data-ttu-id="cce64-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cce64-108">HRESULT</span></span>|<span data-ttu-id="cce64-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="cce64-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cce64-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="cce64-110">S_OK</span></span>|<span data-ttu-id="cce64-111">`SetMaxThreads` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="cce64-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="cce64-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cce64-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cce64-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="cce64-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cce64-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cce64-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cce64-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="cce64-115">The call timed out.</span></span>|  
|<span data-ttu-id="cce64-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cce64-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cce64-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="cce64-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cce64-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cce64-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cce64-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="cce64-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cce64-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cce64-120">E_FAIL</span></span>|<span data-ttu-id="cce64-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="cce64-121">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="cce64-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="cce64-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cce64-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="cce64-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="cce64-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="cce64-124">E_NOTIMPL</span></span>|<span data-ttu-id="cce64-125">El host no proporciona una implementación de `SetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="cce64-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cce64-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cce64-126">Remarks</span></span>  
 <span data-ttu-id="cce64-127">No se necesita un host para permitir que CLR configure el tamaño del grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="cce64-127">A host is not required to allow the CLR to configure the size of the thread pool.</span></span> <span data-ttu-id="cce64-128">Es posible que algunos hosts quieran un control exclusivo sobre el grupo de subprocesos, por motivos como la implementación, el rendimiento o la escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="cce64-128">Some hosts might want exclusive control over the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="cce64-129">En este caso, un host debe devolver un valor HRESULT de E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="cce64-129">In this case, a host should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cce64-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cce64-130">Requirements</span></span>  
 <span data-ttu-id="cce64-131">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cce64-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cce64-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cce64-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cce64-133">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cce64-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cce64-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cce64-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cce64-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="cce64-135">See also</span></span>

- <xref:System.Threading.ThreadPool.SetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="cce64-136">GetMaxThreads (método)</span><span class="sxs-lookup"><span data-stu-id="cce64-136">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="cce64-137">SetMinThreads (método)</span><span class="sxs-lookup"><span data-stu-id="cce64-137">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="cce64-138">IHostThreadPoolManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cce64-138">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
