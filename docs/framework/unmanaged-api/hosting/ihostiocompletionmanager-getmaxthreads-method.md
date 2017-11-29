---
title: "IHostIoCompletionManager::GetMaxThreads (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.GetMaxThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::GetMaxThreads
helpviewer_keywords:
- IHostIoCompletionManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: e7a6cadc-2433-4472-a701-58891abcde45
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4e7df4acd435c767a1d0c3ae4484a236359cfb38
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ihostiocompletionmanagergetmaxthreads-method"></a><span data-ttu-id="4b3ee-102">IHostIoCompletionManager::GetMaxThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="4b3ee-102">IHostIoCompletionManager::GetMaxThreads Method</span></span>
<span data-ttu-id="4b3ee-103">Obtiene el número máximo de subprocesos que el host puede asignar para atender las solicitudes de E/S.</span><span class="sxs-lookup"><span data-stu-id="4b3ee-103">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b3ee-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4b3ee-104">Syntax</span></span>  
  
```  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxIoCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4b3ee-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4b3ee-105">Parameters</span></span>  
 `pdwMaxIoCompletionThreads`  
 <span data-ttu-id="4b3ee-106">[out] Un puntero al número máximo de subprocesos en el grupo de subprocesos que el host puede asignar para atender las solicitudes de E/S.</span><span class="sxs-lookup"><span data-stu-id="4b3ee-106">[out] A pointer to the maximum number of threads in the thread pool that the host can allot to service I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4b3ee-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4b3ee-107">Return Value</span></span>  
  
|<span data-ttu-id="4b3ee-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4b3ee-108">HRESULT</span></span>|<span data-ttu-id="4b3ee-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="4b3ee-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4b3ee-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4b3ee-110">S_OK</span></span>|<span data-ttu-id="4b3ee-111">`GetMaxThreads`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="4b3ee-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="4b3ee-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4b3ee-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4b3ee-113">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="4b3ee-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4b3ee-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4b3ee-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4b3ee-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="4b3ee-115">The call timed out.</span></span>|  
|<span data-ttu-id="4b3ee-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4b3ee-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4b3ee-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="4b3ee-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4b3ee-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4b3ee-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4b3ee-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="4b3ee-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4b3ee-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4b3ee-120">E_FAIL</span></span>|<span data-ttu-id="4b3ee-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="4b3ee-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4b3ee-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="4b3ee-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4b3ee-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4b3ee-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4b3ee-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="4b3ee-124">E_NOTIMPL</span></span>|<span data-ttu-id="4b3ee-125">El host no proporciona una implementación de `GetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="4b3ee-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b3ee-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4b3ee-126">Remarks</span></span>  
 <span data-ttu-id="4b3ee-127">Un host podría desear el control exclusivo sobre el número de subprocesos que se puede asignar para procesar las solicitudes de E/S, por razones de implementación, rendimiento o escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="4b3ee-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="4b3ee-128">Por este motivo, el host no tiene que implementar `GetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="4b3ee-128">For this reason, the host is not required to implement `GetMaxThreads`.</span></span> <span data-ttu-id="4b3ee-129">En este caso, el host debe devolver E_NOTIMPL desde este método.</span><span class="sxs-lookup"><span data-stu-id="4b3ee-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b3ee-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4b3ee-130">Requirements</span></span>  
 <span data-ttu-id="4b3ee-131">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b3ee-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b3ee-132">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4b3ee-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4b3ee-133">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4b3ee-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4b3ee-134">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b3ee-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b3ee-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b3ee-135">See Also</span></span>  
 [<span data-ttu-id="4b3ee-136">ICLRIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4b3ee-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="4b3ee-137">IHostIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4b3ee-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
