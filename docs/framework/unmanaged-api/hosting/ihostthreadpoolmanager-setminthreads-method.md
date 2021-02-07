---
description: 'Más información acerca de: IHostThreadPoolManager:: SetMinThreads ((método)'
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
ms.openlocfilehash: 00d6bd8212ee95318bbe546da80ca34bff7d1324
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753762"
---
# <a name="ihostthreadpoolmanagersetminthreads-method"></a><span data-ttu-id="e51f6-103">IHostThreadPoolManager::SetMinThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="e51f6-103">IHostThreadPoolManager::SetMinThreads Method</span></span>

<span data-ttu-id="e51f6-104">Establece el número mínimo de subprocesos inactivos que el host debe mantener en previsión de las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="e51f6-104">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e51f6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e51f6-105">Syntax</span></span>  
  
```cpp  
HRESULT SetMinThreads (  
    [in] DWORD MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e51f6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e51f6-106">Parameters</span></span>  

 `MinThreads`  
 <span data-ttu-id="e51f6-107">de Nuevo número mínimo de subprocesos que debe mantener el host.</span><span class="sxs-lookup"><span data-stu-id="e51f6-107">[in] The new minimum number of threads that the host must maintain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e51f6-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e51f6-108">Return Value</span></span>  
  
|<span data-ttu-id="e51f6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e51f6-109">HRESULT</span></span>|<span data-ttu-id="e51f6-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="e51f6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e51f6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e51f6-111">S_OK</span></span>|<span data-ttu-id="e51f6-112">`SetMinThreads` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="e51f6-112">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="e51f6-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e51f6-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e51f6-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="e51f6-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e51f6-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e51f6-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e51f6-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="e51f6-116">The call timed out.</span></span>|  
|<span data-ttu-id="e51f6-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e51f6-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e51f6-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="e51f6-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e51f6-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e51f6-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e51f6-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="e51f6-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e51f6-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e51f6-121">E_FAIL</span></span>|<span data-ttu-id="e51f6-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="e51f6-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e51f6-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="e51f6-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e51f6-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e51f6-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e51f6-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="e51f6-125">E_NOTIMPL</span></span>|<span data-ttu-id="e51f6-126">El host no proporciona una implementación de `SetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="e51f6-126">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e51f6-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e51f6-127">Remarks</span></span>  

 <span data-ttu-id="e51f6-128">No es necesario que un host proporcione una implementación de `SetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="e51f6-128">A host is not required to provide an implementation of `SetMinThreads`.</span></span> <span data-ttu-id="e51f6-129">En este caso, debe devolver un valor HRESULT de E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="e51f6-129">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e51f6-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e51f6-130">Requirements</span></span>  

 <span data-ttu-id="e51f6-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e51f6-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e51f6-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e51f6-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e51f6-133">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e51f6-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e51f6-134">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e51f6-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e51f6-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="e51f6-135">See also</span></span>

- <xref:System.Threading.ThreadPool.SetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="e51f6-136">Método GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="e51f6-136">GetMinThreads Method</span></span>](ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="e51f6-137">Método SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="e51f6-137">SetMaxThreads Method</span></span>](ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="e51f6-138">IHostThreadPoolManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e51f6-138">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
