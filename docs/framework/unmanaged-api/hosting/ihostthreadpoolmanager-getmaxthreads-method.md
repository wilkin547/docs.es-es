---
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
ms.openlocfilehash: efbfa310c90f48c99219cb185f090a1b854949a2
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842288"
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a><span data-ttu-id="8440c-102">IHostThreadPoolManager::GetMaxThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="8440c-102">IHostThreadPoolManager::GetMaxThreads Method</span></span>
<span data-ttu-id="8440c-103">Obtiene el número máximo de subprocesos que el host mantiene simultáneamente en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="8440c-103">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8440c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8440c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8440c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8440c-105">Parameters</span></span>  
 `pdwMaxWorkerThreads`  
 <span data-ttu-id="8440c-106">enuncia Puntero al número máximo de subprocesos que el host mantiene en el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="8440c-106">[out] A pointer to the maximum number of threads that the host maintains in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8440c-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8440c-107">Return Value</span></span>  
  
|<span data-ttu-id="8440c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8440c-108">HRESULT</span></span>|<span data-ttu-id="8440c-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="8440c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8440c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8440c-110">S_OK</span></span>|<span data-ttu-id="8440c-111">`GetMaxThreads`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="8440c-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="8440c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8440c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8440c-113">El Common Language Runtime (CLR (no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente).</span><span class="sxs-lookup"><span data-stu-id="8440c-113">The common language runtime (CLR( has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8440c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8440c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8440c-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8440c-115">The call timed out.</span></span>|  
|<span data-ttu-id="8440c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8440c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8440c-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="8440c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8440c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8440c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8440c-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="8440c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8440c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8440c-120">E_FAIL</span></span>|<span data-ttu-id="8440c-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="8440c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8440c-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="8440c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8440c-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8440c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8440c-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="8440c-124">E_NOTIMPL</span></span>|<span data-ttu-id="8440c-125">El host no proporciona una implementación de `GetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="8440c-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8440c-126">Notas</span><span class="sxs-lookup"><span data-stu-id="8440c-126">Remarks</span></span>  
 <span data-ttu-id="8440c-127">CLR llama `GetMaxThreads` a para determinar el número total de subprocesos del grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="8440c-127">The CLR calls `GetMaxThreads` to determine the total number of threads in the thread pool.</span></span> <span data-ttu-id="8440c-128">El método [GetAvailableThreads](ihostthreadpoolmanager-getavailablethreads-method.md) obtiene el número de subprocesos que no están procesando actualmente los elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8440c-128">The [GetAvailableThreads](ihostthreadpoolmanager-getavailablethreads-method.md) method gets the number of threads that are not currently processing work items.</span></span> <span data-ttu-id="8440c-129">Todas las solicitudes por encima del valor devuelto del `pdwMaxWorkerThreads` parámetro permanecen en la cola hasta que los subprocesos están disponibles.</span><span class="sxs-lookup"><span data-stu-id="8440c-129">All requests above the returned value of the `pdwMaxWorkerThreads` parameter remain queued until threads become available.</span></span>  
  
 <span data-ttu-id="8440c-130">Si el host no proporciona una implementación de `GetMaxThreads` , debe devolver un valor HRESULT de E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="8440c-130">If the host does not provide an implementation of `GetMaxThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8440c-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8440c-131">Requirements</span></span>  
 <span data-ttu-id="8440c-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8440c-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8440c-133">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8440c-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8440c-134">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8440c-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8440c-135">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8440c-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8440c-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="8440c-136">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="8440c-137">Método GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="8440c-137">GetMinThreads Method</span></span>](ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="8440c-138">Método SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="8440c-138">SetMaxThreads Method</span></span>](ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="8440c-139">IHostThreadPoolManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8440c-139">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
