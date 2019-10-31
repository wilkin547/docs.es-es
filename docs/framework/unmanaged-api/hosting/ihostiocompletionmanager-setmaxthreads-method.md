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
ms.openlocfilehash: 7a16c141d9d07af82bd984955e06199e66ce3bbf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133760"
---
# <a name="ihostiocompletionmanagersetmaxthreads-method"></a><span data-ttu-id="637c2-102">IHostIoCompletionManager::SetMaxThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="637c2-102">IHostIoCompletionManager::SetMaxThreads Method</span></span>
<span data-ttu-id="637c2-103">Establece el número máximo de subprocesos que el host asigna a las solicitudes de e/s de servicio.</span><span class="sxs-lookup"><span data-stu-id="637c2-103">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="637c2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="637c2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMaxThreads (  
    [in] DWORD dwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="637c2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="637c2-105">Parameters</span></span>  
 `dwMaxIoCompletionThreads`  
 <span data-ttu-id="637c2-106">de Número máximo de subprocesos que se van a asignar para solicitudes de e/s.</span><span class="sxs-lookup"><span data-stu-id="637c2-106">[in] The maximum number of threads to allot for I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="637c2-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="637c2-107">Return Value</span></span>  
  
|<span data-ttu-id="637c2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="637c2-108">HRESULT</span></span>|<span data-ttu-id="637c2-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="637c2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="637c2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="637c2-110">S_OK</span></span>|<span data-ttu-id="637c2-111">`SetMaxThreads` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="637c2-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="637c2-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="637c2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="637c2-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="637c2-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="637c2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="637c2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="637c2-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="637c2-115">The call timed out.</span></span>|  
|<span data-ttu-id="637c2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="637c2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="637c2-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="637c2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="637c2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="637c2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="637c2-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="637c2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="637c2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="637c2-120">E_FAIL</span></span>|<span data-ttu-id="637c2-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="637c2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="637c2-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="637c2-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="637c2-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="637c2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="637c2-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="637c2-124">E_NOTIMPL</span></span>|<span data-ttu-id="637c2-125">El host no proporciona una implementación de `SetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="637c2-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="637c2-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="637c2-126">Remarks</span></span>  
 <span data-ttu-id="637c2-127">`SetMaxThreads` proporciona a CLR la oportunidad de establecer el número máximo de subprocesos que están disponibles para las solicitudes de servicio en los puertos de e/s.</span><span class="sxs-lookup"><span data-stu-id="637c2-127">`SetMaxThreads` provides the CLR with an opportunity to set the maximum number of threads that are available to service requests on I/O ports.</span></span> <span data-ttu-id="637c2-128">Es posible que un host necesite un control exclusivo sobre el tamaño del grupo de subprocesos, por motivos como la implementación, el rendimiento o la escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="637c2-128">A host might need exclusive control over the size of the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="637c2-129">Por esta razón, no es necesario que el host implemente `SetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="637c2-129">For this reason, the host is not required to implement `SetMaxThreads`.</span></span> <span data-ttu-id="637c2-130">En este caso, un host debe devolver E_NOTIMPL desde este método.</span><span class="sxs-lookup"><span data-stu-id="637c2-130">In this case, a host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="637c2-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="637c2-131">Requirements</span></span>  
 <span data-ttu-id="637c2-132">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="637c2-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="637c2-133">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="637c2-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="637c2-134">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="637c2-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="637c2-135">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="637c2-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="637c2-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="637c2-136">See also</span></span>

- [<span data-ttu-id="637c2-137">ICLRIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="637c2-137">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="637c2-138">IHostIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="637c2-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
