---
title: "IHostIoCompletionManager::SetMinThreads (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostIoCompletionManager.SetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: dea34b81-8d2b-4cc3-8696-0ad4291d8a92
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1bd64554278fe3c684fadf95f66ce15920827908
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostiocompletionmanagersetminthreads-method"></a><span data-ttu-id="6baf2-102">IHostIoCompletionManager::SetMinThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="6baf2-102">IHostIoCompletionManager::SetMinThreads Method</span></span>
<span data-ttu-id="6baf2-103">Establece el número mínimo de subprocesos que el host debe asignar a la finalización de E/S.</span><span class="sxs-lookup"><span data-stu-id="6baf2-103">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6baf2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6baf2-104">Syntax</span></span>  
  
```  
HRESULT SetMinThreads (  
    [in] DWORD dwMinIoCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6baf2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6baf2-105">Parameters</span></span>  
 `dwMinIoCompletionThreads`  
 <span data-ttu-id="6baf2-106">[in] El número mínimo de subprocesos de finalización de E/S que debe crear el host.</span><span class="sxs-lookup"><span data-stu-id="6baf2-106">[in] The minimum number of I/O completion threads that the host should create.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6baf2-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6baf2-107">Return Value</span></span>  
  
|<span data-ttu-id="6baf2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6baf2-108">HRESULT</span></span>|<span data-ttu-id="6baf2-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="6baf2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6baf2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6baf2-110">S_OK</span></span>|<span data-ttu-id="6baf2-111">`SetMinThreads`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="6baf2-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="6baf2-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6baf2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6baf2-113">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="6baf2-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6baf2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6baf2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6baf2-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="6baf2-115">The call timed out.</span></span>|  
|<span data-ttu-id="6baf2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6baf2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6baf2-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="6baf2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6baf2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6baf2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6baf2-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="6baf2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6baf2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6baf2-120">E_FAIL</span></span>|<span data-ttu-id="6baf2-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="6baf2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6baf2-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="6baf2-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6baf2-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6baf2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6baf2-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="6baf2-124">E_NOTIMPL</span></span>|<span data-ttu-id="6baf2-125">El host no proporciona una implementación de `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="6baf2-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6baf2-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6baf2-126">Remarks</span></span>  
 <span data-ttu-id="6baf2-127">Un host podría desear el control exclusivo sobre el número de subprocesos que se puede asignar para procesar las solicitudes de E/S, por razones de implementación, rendimiento o escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="6baf2-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="6baf2-128">Por este motivo, el host no tiene que implementar `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="6baf2-128">For this reason, the host is not required to implement `SetMinThreads`.</span></span> <span data-ttu-id="6baf2-129">En este caso, el host debe devolver E_NOTIMPL desde este método.</span><span class="sxs-lookup"><span data-stu-id="6baf2-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6baf2-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6baf2-130">Requirements</span></span>  
 <span data-ttu-id="6baf2-131">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6baf2-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6baf2-132">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6baf2-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6baf2-133">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6baf2-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6baf2-134">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6baf2-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6baf2-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="6baf2-135">See Also</span></span>  
 [<span data-ttu-id="6baf2-136">ICLRIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6baf2-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="6baf2-137">SetMaxThreads (método)</span><span class="sxs-lookup"><span data-stu-id="6baf2-137">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)  
 [<span data-ttu-id="6baf2-138">IHostIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6baf2-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
