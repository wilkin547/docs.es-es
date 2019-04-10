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
ms.openlocfilehash: 345c7b88b6967773a185538943591383a686748c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224128"
---
# <a name="ihostiocompletionmanagersetmaxthreads-method"></a><span data-ttu-id="0fc3a-102">IHostIoCompletionManager::SetMaxThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="0fc3a-102">IHostIoCompletionManager::SetMaxThreads Method</span></span>
<span data-ttu-id="0fc3a-103">Establece el número máximo de subprocesos que el host asigna para atender las solicitudes de E/S.</span><span class="sxs-lookup"><span data-stu-id="0fc3a-103">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fc3a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0fc3a-104">Syntax</span></span>  
  
```  
HRESULT SetMaxThreads (  
    [in] DWORD dwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0fc3a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0fc3a-105">Parameters</span></span>  
 `dwMaxIoCompletionThreads`  
 <span data-ttu-id="0fc3a-106">[in] El número máximo de subprocesos para asignar las solicitudes de E/S.</span><span class="sxs-lookup"><span data-stu-id="0fc3a-106">[in] The maximum number of threads to allot for I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0fc3a-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0fc3a-107">Return Value</span></span>  
  
|<span data-ttu-id="0fc3a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0fc3a-108">HRESULT</span></span>|<span data-ttu-id="0fc3a-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="0fc3a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0fc3a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0fc3a-110">S_OK</span></span>|`SetMaxThreads` <span data-ttu-id="0fc3a-111">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="0fc3a-111">returned successfully.</span></span>|  
|<span data-ttu-id="0fc3a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0fc3a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0fc3a-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="0fc3a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0fc3a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0fc3a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0fc3a-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="0fc3a-115">The call timed out.</span></span>|  
|<span data-ttu-id="0fc3a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0fc3a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0fc3a-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="0fc3a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0fc3a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0fc3a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0fc3a-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="0fc3a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0fc3a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0fc3a-120">E_FAIL</span></span>|<span data-ttu-id="0fc3a-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="0fc3a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0fc3a-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="0fc3a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0fc3a-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0fc3a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0fc3a-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="0fc3a-124">E_NOTIMPL</span></span>|<span data-ttu-id="0fc3a-125">El host no proporciona una implementación de `SetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="0fc3a-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0fc3a-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0fc3a-126">Remarks</span></span>  
 `SetMaxThreads` <span data-ttu-id="0fc3a-127">Proporciona una oportunidad para definir el número máximo de subprocesos que están disponibles para atender las solicitudes de los puertos de E/S de CLR.</span><span class="sxs-lookup"><span data-stu-id="0fc3a-127">provides the CLR with an opportunity to set the maximum number of threads that are available to service requests on I/O ports.</span></span> <span data-ttu-id="0fc3a-128">Un host podría necesitar el control exclusivo sobre el tamaño del grupo de subprocesos, por motivos de implementación, rendimiento o escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="0fc3a-128">A host might need exclusive control over the size of the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="0fc3a-129">Por este motivo, no es necesario implementar el host `SetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="0fc3a-129">For this reason, the host is not required to implement `SetMaxThreads`.</span></span> <span data-ttu-id="0fc3a-130">En este caso, un host debe devolver E_NOTIMPL desde este método.</span><span class="sxs-lookup"><span data-stu-id="0fc3a-130">In this case, a host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fc3a-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0fc3a-131">Requirements</span></span>  
 <span data-ttu-id="0fc3a-132">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fc3a-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fc3a-133">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0fc3a-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0fc3a-134">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0fc3a-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="0fc3a-135">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0fc3a-135">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0fc3a-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="0fc3a-136">See also</span></span>

- [<span data-ttu-id="0fc3a-137">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0fc3a-137">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="0fc3a-138">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0fc3a-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
