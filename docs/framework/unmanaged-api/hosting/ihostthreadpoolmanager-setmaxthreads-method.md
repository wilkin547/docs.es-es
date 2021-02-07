---
description: 'Más información acerca de: IHostThreadPoolManager:: SetMaxThreads (método)'
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
ms.openlocfilehash: 83266b05f639c0aa63e492bca525cbbf09a30775
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671248"
---
# <a name="ihostthreadpoolmanagersetmaxthreads-method"></a><span data-ttu-id="906b1-103">IHostThreadPoolManager::SetMaxThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="906b1-103">IHostThreadPoolManager::SetMaxThreads Method</span></span>

<span data-ttu-id="906b1-104">Establece el número máximo de subprocesos que el host puede mantener en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="906b1-104">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="906b1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="906b1-105">Syntax</span></span>  
  
```cpp  
HRESULT SetMaxThreads (  
    [in] DWORD MaxThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="906b1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="906b1-106">Parameters</span></span>  

 `MaxThreads`  
 <span data-ttu-id="906b1-107">Número máximo de subprocesos de trabajo en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="906b1-107">The maximum number of worker threads in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="906b1-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="906b1-108">Return Value</span></span>  
  
|<span data-ttu-id="906b1-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="906b1-109">HRESULT</span></span>|<span data-ttu-id="906b1-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="906b1-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="906b1-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="906b1-111">S_OK</span></span>|<span data-ttu-id="906b1-112">`SetMaxThreads` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="906b1-112">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="906b1-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="906b1-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="906b1-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="906b1-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="906b1-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="906b1-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="906b1-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="906b1-116">The call timed out.</span></span>|  
|<span data-ttu-id="906b1-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="906b1-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="906b1-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="906b1-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="906b1-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="906b1-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="906b1-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="906b1-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="906b1-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="906b1-121">E_FAIL</span></span>|<span data-ttu-id="906b1-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="906b1-122">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="906b1-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="906b1-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="906b1-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="906b1-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="906b1-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="906b1-125">E_NOTIMPL</span></span>|<span data-ttu-id="906b1-126">El host no proporciona una implementación de `SetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="906b1-126">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="906b1-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="906b1-127">Remarks</span></span>  

 <span data-ttu-id="906b1-128">No se necesita un host para permitir que CLR configure el tamaño del grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="906b1-128">A host is not required to allow the CLR to configure the size of the thread pool.</span></span> <span data-ttu-id="906b1-129">Es posible que algunos hosts quieran un control exclusivo sobre el grupo de subprocesos, por motivos como la implementación, el rendimiento o la escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="906b1-129">Some hosts might want exclusive control over the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="906b1-130">En este caso, un host debe devolver un valor HRESULT de E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="906b1-130">In this case, a host should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="906b1-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="906b1-131">Requirements</span></span>  

 <span data-ttu-id="906b1-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="906b1-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="906b1-133">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="906b1-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="906b1-134">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="906b1-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="906b1-135">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="906b1-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="906b1-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="906b1-136">See also</span></span>

- <xref:System.Threading.ThreadPool.SetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="906b1-137">Método GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="906b1-137">GetMaxThreads Method</span></span>](ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="906b1-138">Método SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="906b1-138">SetMinThreads Method</span></span>](ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="906b1-139">IHostThreadPoolManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="906b1-139">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
