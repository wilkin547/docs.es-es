---
description: 'Más información acerca de: IHostThreadPoolManager:: GetMaxThreads (método)'
title: IHostThreadPoolManager::GetMaxThreads (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: e8cae2aa29a50ef58a5b87deba9e275a441d43ef
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728390"
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a><span data-ttu-id="a530b-103">IHostThreadPoolManager::GetMaxThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="a530b-103">IHostThreadPoolManager::GetMaxThreads Method</span></span>

<span data-ttu-id="a530b-104">Obtiene el número máximo de subprocesos que el host mantiene simultáneamente en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="a530b-104">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a530b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a530b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a530b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a530b-106">Parameters</span></span>  

 `pdwMaxWorkerThreads`  
 <span data-ttu-id="a530b-107">enuncia Puntero al número máximo de subprocesos que el host mantiene en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="a530b-107">[out] A pointer to the maximum number of threads that the host maintains in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a530b-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a530b-108">Return Value</span></span>  
  
|<span data-ttu-id="a530b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a530b-109">HRESULT</span></span>|<span data-ttu-id="a530b-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="a530b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a530b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a530b-111">S_OK</span></span>|<span data-ttu-id="a530b-112">`GetMaxThreads` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a530b-112">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="a530b-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a530b-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a530b-114">El Common Language Runtime (CLR (no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente).</span><span class="sxs-lookup"><span data-stu-id="a530b-114">The common language runtime (CLR( has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a530b-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a530b-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a530b-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a530b-116">The call timed out.</span></span>|  
|<span data-ttu-id="a530b-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a530b-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a530b-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a530b-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a530b-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a530b-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a530b-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="a530b-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a530b-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a530b-121">E_FAIL</span></span>|<span data-ttu-id="a530b-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="a530b-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a530b-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a530b-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a530b-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a530b-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a530b-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="a530b-125">E_NOTIMPL</span></span>|<span data-ttu-id="a530b-126">El host no proporciona una implementación de `GetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="a530b-126">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a530b-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a530b-127">Remarks</span></span>  

 <span data-ttu-id="a530b-128">CLR llama `GetMaxThreads` a para determinar el número total de subprocesos del grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="a530b-128">The CLR calls `GetMaxThreads` to determine the total number of threads in the thread pool.</span></span> <span data-ttu-id="a530b-129">El método [GetAvailableThreads](ihostthreadpoolmanager-getavailablethreads-method.md) obtiene el número de subprocesos que no están procesando actualmente los elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a530b-129">The [GetAvailableThreads](ihostthreadpoolmanager-getavailablethreads-method.md) method gets the number of threads that are not currently processing work items.</span></span> <span data-ttu-id="a530b-130">Todas las solicitudes por encima del valor devuelto del `pdwMaxWorkerThreads` parámetro permanecen en la cola hasta que los subprocesos están disponibles.</span><span class="sxs-lookup"><span data-stu-id="a530b-130">All requests above the returned value of the `pdwMaxWorkerThreads` parameter remain queued until threads become available.</span></span>  
  
 <span data-ttu-id="a530b-131">Si el host no proporciona una implementación de `GetMaxThreads` , debe devolver un valor HRESULT de E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="a530b-131">If the host does not provide an implementation of `GetMaxThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a530b-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a530b-132">Requirements</span></span>  

 <span data-ttu-id="a530b-133">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a530b-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a530b-134">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a530b-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a530b-135">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a530b-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a530b-136">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a530b-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a530b-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="a530b-137">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="a530b-138">Método GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="a530b-138">GetMinThreads Method</span></span>](ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="a530b-139">Método SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="a530b-139">SetMaxThreads Method</span></span>](ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="a530b-140">IHostThreadPoolManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a530b-140">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
