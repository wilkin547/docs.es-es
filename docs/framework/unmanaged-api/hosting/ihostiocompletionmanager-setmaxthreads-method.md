---
title: IHostIoCompletionManager::SetMaxThreads (Método)
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetMaxThreads
helpviewer_keywords:
- IHostIoCompletionManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: ebad4f40-d9f1-4dc6-9b27-a89c9eb3926f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a810f3a25dc90ddb234c70ca3fa5130039350136
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438826"
---
# <a name="ihostiocompletionmanagersetmaxthreads-method"></a><span data-ttu-id="65f93-102">IHostIoCompletionManager::SetMaxThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="65f93-102">IHostIoCompletionManager::SetMaxThreads Method</span></span>
<span data-ttu-id="65f93-103">Establece el número máximo de subprocesos que el host asigna para atender las solicitudes de E/S.</span><span class="sxs-lookup"><span data-stu-id="65f93-103">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65f93-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="65f93-104">Syntax</span></span>  
  
```  
HRESULT SetMaxThreads (  
    [in] DWORD dwMaxIoCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="65f93-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="65f93-105">Parameters</span></span>  
 `dwMaxIoCompletionThreads`  
 <span data-ttu-id="65f93-106">[in] El número máximo de subprocesos para asignar las solicitudes de E/S.</span><span class="sxs-lookup"><span data-stu-id="65f93-106">[in] The maximum number of threads to allot for I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65f93-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="65f93-107">Return Value</span></span>  
  
|<span data-ttu-id="65f93-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="65f93-108">HRESULT</span></span>|<span data-ttu-id="65f93-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="65f93-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="65f93-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="65f93-110">S_OK</span></span>|<span data-ttu-id="65f93-111">`SetMaxThreads` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="65f93-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="65f93-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="65f93-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="65f93-113">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="65f93-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="65f93-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="65f93-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="65f93-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="65f93-115">The call timed out.</span></span>|  
|<span data-ttu-id="65f93-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="65f93-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="65f93-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="65f93-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="65f93-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="65f93-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="65f93-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="65f93-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="65f93-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="65f93-120">E_FAIL</span></span>|<span data-ttu-id="65f93-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="65f93-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="65f93-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="65f93-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="65f93-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="65f93-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="65f93-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="65f93-124">E_NOTIMPL</span></span>|<span data-ttu-id="65f93-125">El host no proporciona una implementación de `SetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="65f93-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65f93-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="65f93-126">Remarks</span></span>  
 <span data-ttu-id="65f93-127">`SetMaxThreads` brinda la oportunidad para establecer el número máximo de subprocesos que están disponibles para atender las solicitudes en los puertos de E/S de CLR.</span><span class="sxs-lookup"><span data-stu-id="65f93-127">`SetMaxThreads` provides the CLR with an opportunity to set the maximum number of threads that are available to service requests on I/O ports.</span></span> <span data-ttu-id="65f93-128">Un host podría necesitar el control exclusivo sobre el tamaño del grupo de subprocesos, por razones de implementación, rendimiento o escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="65f93-128">A host might need exclusive control over the size of the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="65f93-129">Por este motivo, el host no tiene que implementar `SetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="65f93-129">For this reason, the host is not required to implement `SetMaxThreads`.</span></span> <span data-ttu-id="65f93-130">En este caso, un host debe devolver E_NOTIMPL desde este método.</span><span class="sxs-lookup"><span data-stu-id="65f93-130">In this case, a host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65f93-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="65f93-131">Requirements</span></span>  
 <span data-ttu-id="65f93-132">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65f93-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65f93-133">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="65f93-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="65f93-134">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="65f93-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="65f93-135">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65f93-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65f93-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="65f93-136">See Also</span></span>  
 [<span data-ttu-id="65f93-137">ICLRIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="65f93-137">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="65f93-138">IHostIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="65f93-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
