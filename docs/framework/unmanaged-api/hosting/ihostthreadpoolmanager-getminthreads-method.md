---
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
ms.openlocfilehash: ce1abb75c5135a9bb23f1ad2d2acbd40d9111b14
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122068"
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a><span data-ttu-id="254be-102">IHostThreadPoolManager::GetMinThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="254be-102">IHostThreadPoolManager::GetMinThreads Method</span></span>
<span data-ttu-id="254be-103">Obtiene el número mínimo de subprocesos inactivos que el host mantiene en el grupo de subprocesos en previsión de solicitudes.</span><span class="sxs-lookup"><span data-stu-id="254be-103">Gets the minimum number of idle threads that the host maintains in the thread pool in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="254be-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="254be-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="254be-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="254be-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="254be-106">enuncia Puntero al número mínimo de subprocesos de trabajo inactivos que el host mantiene actualmente.</span><span class="sxs-lookup"><span data-stu-id="254be-106">[out] A pointer to the minimum number of idle worker threads that the host currently maintains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="254be-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="254be-107">Return Value</span></span>  
  
|<span data-ttu-id="254be-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="254be-108">HRESULT</span></span>|<span data-ttu-id="254be-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="254be-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="254be-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="254be-110">S_OK</span></span>|<span data-ttu-id="254be-111">`GetMinThreads` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="254be-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="254be-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="254be-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="254be-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="254be-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="254be-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="254be-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="254be-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="254be-115">The call timed out.</span></span>|  
|<span data-ttu-id="254be-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="254be-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="254be-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="254be-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="254be-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="254be-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="254be-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="254be-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="254be-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="254be-120">E_FAIL</span></span>|<span data-ttu-id="254be-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="254be-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="254be-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="254be-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="254be-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="254be-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="254be-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="254be-124">E_NOTIMPL</span></span>|<span data-ttu-id="254be-125">El host no proporciona una implementación de `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="254be-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="254be-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="254be-126">Remarks</span></span>  
 <span data-ttu-id="254be-127">No es necesario que el host proporcione una implementación de `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="254be-127">The host is not required to provide an implementation of `GetMinThreads`.</span></span> <span data-ttu-id="254be-128">En este caso, debe devolver un valor HRESULT de E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="254be-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="254be-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="254be-129">Requirements</span></span>  
 <span data-ttu-id="254be-130">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="254be-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="254be-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="254be-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="254be-132">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="254be-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="254be-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="254be-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="254be-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="254be-134">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="254be-135">GetMaxThreads (método)</span><span class="sxs-lookup"><span data-stu-id="254be-135">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="254be-136">SetMinThreads (método)</span><span class="sxs-lookup"><span data-stu-id="254be-136">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="254be-137">IHostThreadPoolManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="254be-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
