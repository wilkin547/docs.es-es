---
title: IHostThreadPoolManager::SetMinThreads (Método)
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.SetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: 10409db9-9fd2-4e4d-b8cd-cf6fec0afaa2
topic_type:
- apiref
ms.openlocfilehash: f2d2665382559596563d9b155d2afa4d99c91ee7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141259"
---
# <a name="ihostthreadpoolmanagersetminthreads-method"></a><span data-ttu-id="71735-102">IHostThreadPoolManager::SetMinThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="71735-102">IHostThreadPoolManager::SetMinThreads Method</span></span>
<span data-ttu-id="71735-103">Establece el número mínimo de subprocesos inactivos que el host debe mantener en previsión de las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="71735-103">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71735-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="71735-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMinThreads (  
    [in] DWORD MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71735-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="71735-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="71735-106">de Nuevo número mínimo de subprocesos que debe mantener el host.</span><span class="sxs-lookup"><span data-stu-id="71735-106">[in] The new minimum number of threads that the host must maintain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71735-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="71735-107">Return Value</span></span>  
  
|<span data-ttu-id="71735-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="71735-108">HRESULT</span></span>|<span data-ttu-id="71735-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="71735-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="71735-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="71735-110">S_OK</span></span>|<span data-ttu-id="71735-111">`SetMinThreads` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="71735-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="71735-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="71735-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="71735-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="71735-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="71735-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="71735-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="71735-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="71735-115">The call timed out.</span></span>|  
|<span data-ttu-id="71735-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="71735-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="71735-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="71735-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="71735-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="71735-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="71735-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="71735-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="71735-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="71735-120">E_FAIL</span></span>|<span data-ttu-id="71735-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="71735-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="71735-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="71735-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="71735-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="71735-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="71735-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="71735-124">E_NOTIMPL</span></span>|<span data-ttu-id="71735-125">El host no proporciona una implementación de `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="71735-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71735-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="71735-126">Remarks</span></span>  
 <span data-ttu-id="71735-127">No es necesario que un host proporcione una implementación de `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="71735-127">A host is not required to provide an implementation of `SetMinThreads`.</span></span> <span data-ttu-id="71735-128">En este caso, debe devolver un valor HRESULT de E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="71735-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71735-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="71735-129">Requirements</span></span>  
 <span data-ttu-id="71735-130">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71735-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71735-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="71735-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="71735-132">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="71735-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71735-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71735-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71735-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="71735-134">See also</span></span>

- <xref:System.Threading.ThreadPool.SetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="71735-135">GetMinThreads (método)</span><span class="sxs-lookup"><span data-stu-id="71735-135">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="71735-136">SetMaxThreads (método)</span><span class="sxs-lookup"><span data-stu-id="71735-136">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="71735-137">IHostThreadPoolManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="71735-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
