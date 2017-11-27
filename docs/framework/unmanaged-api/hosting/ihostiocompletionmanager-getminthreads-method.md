---
title: "IHostIoCompletionManager::GetMinThreads (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.GetMinThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::GetMinThreads
helpviewer_keywords:
- GetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetMinThreads method [.NET Framework hosting]
ms.assetid: d7a7f733-677d-481c-b3d5-444fcc502b8e
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6fb9369b67cd79c6e83dc13e2a1090ae611a5e5a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ihostiocompletionmanagergetminthreads-method"></a><span data-ttu-id="cbf16-102">IHostIoCompletionManager::GetMinThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="cbf16-102">IHostIoCompletionManager::GetMinThreads Method</span></span>
<span data-ttu-id="cbf16-103">Obtiene el número mínimo de subprocesos que el host proporciona para procesar las solicitudes de E/S.</span><span class="sxs-lookup"><span data-stu-id="cbf16-103">Gets the minimum number of threads that the host provides for processing I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbf16-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cbf16-104">Syntax</span></span>  
  
```  
HRESULT GetMinThreads (  
    [out] DWORD *pdwMinIOCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cbf16-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cbf16-105">Parameters</span></span>  
 `pdwMinIOCompletionThreads`  
 <span data-ttu-id="cbf16-106">[out] Un puntero al número mínimo de subprocesos que el host proporciona a las solicitudes de E/S del proceso.</span><span class="sxs-lookup"><span data-stu-id="cbf16-106">[out] A pointer to the minimum number of threads that the host provides to process I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cbf16-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cbf16-107">Return Value</span></span>  
  
|<span data-ttu-id="cbf16-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cbf16-108">HRESULT</span></span>|<span data-ttu-id="cbf16-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="cbf16-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cbf16-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="cbf16-110">S_OK</span></span>|<span data-ttu-id="cbf16-111">`GetMinThreads`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="cbf16-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="cbf16-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cbf16-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cbf16-113">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="cbf16-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cbf16-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cbf16-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cbf16-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="cbf16-115">The call timed out.</span></span>|  
|<span data-ttu-id="cbf16-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cbf16-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cbf16-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="cbf16-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cbf16-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cbf16-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cbf16-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="cbf16-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cbf16-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cbf16-120">E_FAIL</span></span>|<span data-ttu-id="cbf16-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="cbf16-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cbf16-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="cbf16-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cbf16-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="cbf16-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="cbf16-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="cbf16-124">E_NOTIMPL</span></span>|<span data-ttu-id="cbf16-125">El host no proporciona una implementación de `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="cbf16-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cbf16-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cbf16-126">Remarks</span></span>  
 <span data-ttu-id="cbf16-127">Un host podría desear el control exclusivo sobre el número de subprocesos asignados para atender las solicitudes de E/S, por razones de implementación, rendimiento o escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="cbf16-127">A host might want exclusive control over the number of threads allotted to service I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="cbf16-128">Por este motivo, el host no tiene que implementar `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="cbf16-128">For this reason, the host is not required to implement `GetMinThreads`.</span></span> <span data-ttu-id="cbf16-129">En este caso, el host debe devolver E_NOTIMPL desde este método.</span><span class="sxs-lookup"><span data-stu-id="cbf16-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbf16-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cbf16-130">Requirements</span></span>  
 <span data-ttu-id="cbf16-131">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbf16-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbf16-132">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cbf16-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cbf16-133">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cbf16-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cbf16-134">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbf16-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbf16-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="cbf16-135">See Also</span></span>  
 [<span data-ttu-id="cbf16-136">ICLRIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cbf16-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="cbf16-137">IHostIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cbf16-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
