---
title: "IHostThreadPoolManager::SetMinThreads (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager.SetMinThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: 10409db9-9fd2-4e4d-b8cd-cf6fec0afaa2
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ab0b107c050b1c4b686f761ede75ea2349825270
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ihostthreadpoolmanagersetminthreads-method"></a><span data-ttu-id="b4f06-102">IHostThreadPoolManager::SetMinThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="b4f06-102">IHostThreadPoolManager::SetMinThreads Method</span></span>
<span data-ttu-id="b4f06-103">Establece el número mínimo de subprocesos inactivos que el host debe mantener en previsión de solicitudes.</span><span class="sxs-lookup"><span data-stu-id="b4f06-103">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4f06-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4f06-104">Syntax</span></span>  
  
```  
HRESULT SetMinThreads (  
    [in] DWORD MinThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b4f06-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b4f06-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="b4f06-106">[in] El nuevo número mínimo de subprocesos que el host debe mantener.</span><span class="sxs-lookup"><span data-stu-id="b4f06-106">[in] The new minimum number of threads that the host must maintain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b4f06-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b4f06-107">Return Value</span></span>  
  
|<span data-ttu-id="b4f06-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b4f06-108">HRESULT</span></span>|<span data-ttu-id="b4f06-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4f06-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b4f06-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b4f06-110">S_OK</span></span>|<span data-ttu-id="b4f06-111">`SetMinThreads`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b4f06-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="b4f06-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b4f06-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b4f06-113">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="b4f06-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b4f06-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b4f06-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b4f06-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="b4f06-115">The call timed out.</span></span>|  
|<span data-ttu-id="b4f06-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b4f06-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b4f06-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="b4f06-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b4f06-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b4f06-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b4f06-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="b4f06-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b4f06-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b4f06-120">E_FAIL</span></span>|<span data-ttu-id="b4f06-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="b4f06-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b4f06-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="b4f06-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b4f06-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b4f06-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b4f06-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="b4f06-124">E_NOTIMPL</span></span>|<span data-ttu-id="b4f06-125">El host no proporciona una implementación de `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="b4f06-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4f06-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b4f06-126">Remarks</span></span>  
 <span data-ttu-id="b4f06-127">No es necesario proporcionar una implementación de un host `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="b4f06-127">A host is not required to provide an implementation of `SetMinThreads`.</span></span> <span data-ttu-id="b4f06-128">En este caso, debe devolver un valor HRESULT de E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="b4f06-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4f06-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b4f06-129">Requirements</span></span>  
 <span data-ttu-id="b4f06-130">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4f06-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4f06-131">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b4f06-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b4f06-132">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b4f06-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4f06-133">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4f06-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4f06-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4f06-134">See Also</span></span>  
 <xref:System.Threading.ThreadPool.SetMinThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="b4f06-135">GetMinThreads (método)</span><span class="sxs-lookup"><span data-stu-id="b4f06-135">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)  
 [<span data-ttu-id="b4f06-136">SetMaxThreads (método)</span><span class="sxs-lookup"><span data-stu-id="b4f06-136">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)  
 [<span data-ttu-id="b4f06-137">IHostThreadPoolManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4f06-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
