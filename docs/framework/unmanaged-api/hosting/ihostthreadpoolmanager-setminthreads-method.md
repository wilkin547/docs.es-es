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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c79f18c1deec4183a5a736c5acf88e9a1fd8021
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749097"
---
# <a name="ihostthreadpoolmanagersetminthreads-method"></a><span data-ttu-id="0c880-102">IHostThreadPoolManager::SetMinThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="0c880-102">IHostThreadPoolManager::SetMinThreads Method</span></span>
<span data-ttu-id="0c880-103">Establece el número mínimo de subprocesos inactivos que el host debe mantener en previsión de solicitudes.</span><span class="sxs-lookup"><span data-stu-id="0c880-103">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c880-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0c880-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMinThreads (  
    [in] DWORD MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c880-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0c880-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="0c880-106">[in] El nuevo número mínimo de subprocesos que el host debe mantener.</span><span class="sxs-lookup"><span data-stu-id="0c880-106">[in] The new minimum number of threads that the host must maintain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c880-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0c880-107">Return Value</span></span>  
  
|<span data-ttu-id="0c880-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0c880-108">HRESULT</span></span>|<span data-ttu-id="0c880-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0c880-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0c880-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0c880-110">S_OK</span></span>|<span data-ttu-id="0c880-111">`SetMinThreads` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="0c880-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="0c880-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0c880-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0c880-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="0c880-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0c880-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0c880-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0c880-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="0c880-115">The call timed out.</span></span>|  
|<span data-ttu-id="0c880-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0c880-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0c880-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="0c880-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0c880-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0c880-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0c880-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="0c880-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0c880-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0c880-120">E_FAIL</span></span>|<span data-ttu-id="0c880-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="0c880-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0c880-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="0c880-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0c880-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0c880-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0c880-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="0c880-124">E_NOTIMPL</span></span>|<span data-ttu-id="0c880-125">El host no proporciona una implementación de `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="0c880-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c880-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0c880-126">Remarks</span></span>  
 <span data-ttu-id="0c880-127">No es necesario proporcionar una implementación de un host `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="0c880-127">A host is not required to provide an implementation of `SetMinThreads`.</span></span> <span data-ttu-id="0c880-128">En este caso, debe devolver un valor HRESULT de E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="0c880-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c880-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0c880-129">Requirements</span></span>  
 <span data-ttu-id="0c880-130">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c880-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c880-131">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0c880-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0c880-132">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0c880-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0c880-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c880-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c880-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c880-134">See also</span></span>

- <xref:System.Threading.ThreadPool.SetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="0c880-135">GetMinThreads (método)</span><span class="sxs-lookup"><span data-stu-id="0c880-135">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="0c880-136">SetMaxThreads (método)</span><span class="sxs-lookup"><span data-stu-id="0c880-136">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="0c880-137">IHostThreadPoolManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0c880-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
