---
description: 'Más información acerca de: IHostThreadPoolManager:: GetMinThreads ((método)'
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
ms.openlocfilehash: 2ebb828f9bc6230b4b0237aa1494f428a1834139
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728402"
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a><span data-ttu-id="598c5-103">IHostThreadPoolManager::GetMinThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="598c5-103">IHostThreadPoolManager::GetMinThreads Method</span></span>

<span data-ttu-id="598c5-104">Obtiene el número mínimo de subprocesos inactivos que el host mantiene en el grupo de subprocesos en previsión de solicitudes.</span><span class="sxs-lookup"><span data-stu-id="598c5-104">Gets the minimum number of idle threads that the host maintains in the thread pool in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="598c5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="598c5-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="598c5-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="598c5-106">Parameters</span></span>  

 `MinThreads`  
 <span data-ttu-id="598c5-107">enuncia Puntero al número mínimo de subprocesos de trabajo inactivos que el host mantiene actualmente.</span><span class="sxs-lookup"><span data-stu-id="598c5-107">[out] A pointer to the minimum number of idle worker threads that the host currently maintains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="598c5-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="598c5-108">Return Value</span></span>  
  
|<span data-ttu-id="598c5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="598c5-109">HRESULT</span></span>|<span data-ttu-id="598c5-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="598c5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="598c5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="598c5-111">S_OK</span></span>|<span data-ttu-id="598c5-112">`GetMinThreads` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="598c5-112">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="598c5-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="598c5-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="598c5-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="598c5-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="598c5-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="598c5-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="598c5-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="598c5-116">The call timed out.</span></span>|  
|<span data-ttu-id="598c5-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="598c5-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="598c5-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="598c5-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="598c5-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="598c5-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="598c5-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="598c5-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="598c5-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="598c5-121">E_FAIL</span></span>|<span data-ttu-id="598c5-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="598c5-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="598c5-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="598c5-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="598c5-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="598c5-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="598c5-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="598c5-125">E_NOTIMPL</span></span>|<span data-ttu-id="598c5-126">El host no proporciona una implementación de `GetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="598c5-126">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="598c5-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="598c5-127">Remarks</span></span>  

 <span data-ttu-id="598c5-128">No es necesario que el host proporcione una implementación de `GetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="598c5-128">The host is not required to provide an implementation of `GetMinThreads`.</span></span> <span data-ttu-id="598c5-129">En este caso, debe devolver un valor HRESULT de E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="598c5-129">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="598c5-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="598c5-130">Requirements</span></span>  

 <span data-ttu-id="598c5-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="598c5-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="598c5-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="598c5-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="598c5-133">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="598c5-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="598c5-134">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="598c5-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="598c5-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="598c5-135">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="598c5-136">Método GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="598c5-136">GetMaxThreads Method</span></span>](ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="598c5-137">Método SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="598c5-137">SetMinThreads Method</span></span>](ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="598c5-138">IHostThreadPoolManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="598c5-138">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
