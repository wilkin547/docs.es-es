---
title: IHostIoCompletionManager::SetMinThreads (Método)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 55570050a4053eac6327f9d7887c2fcd08eceab7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780733"
---
# <a name="ihostiocompletionmanagersetminthreads-method"></a><span data-ttu-id="71dc7-102">IHostIoCompletionManager::SetMinThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="71dc7-102">IHostIoCompletionManager::SetMinThreads Method</span></span>
<span data-ttu-id="71dc7-103">Establece el número mínimo de subprocesos que el host debe asignar a la finalización de E/S.</span><span class="sxs-lookup"><span data-stu-id="71dc7-103">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71dc7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="71dc7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMinThreads (  
    [in] DWORD dwMinIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71dc7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="71dc7-105">Parameters</span></span>  
 `dwMinIoCompletionThreads`  
 <span data-ttu-id="71dc7-106">[in] El número mínimo de subprocesos de finalización de E/S que debe crear el host.</span><span class="sxs-lookup"><span data-stu-id="71dc7-106">[in] The minimum number of I/O completion threads that the host should create.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71dc7-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="71dc7-107">Return Value</span></span>  
  
|<span data-ttu-id="71dc7-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="71dc7-108">HRESULT</span></span>|<span data-ttu-id="71dc7-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="71dc7-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="71dc7-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="71dc7-110">S_OK</span></span>|<span data-ttu-id="71dc7-111">`SetMinThreads` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="71dc7-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="71dc7-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="71dc7-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="71dc7-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="71dc7-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="71dc7-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="71dc7-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="71dc7-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="71dc7-115">The call timed out.</span></span>|  
|<span data-ttu-id="71dc7-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="71dc7-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="71dc7-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="71dc7-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="71dc7-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="71dc7-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="71dc7-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="71dc7-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="71dc7-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="71dc7-120">E_FAIL</span></span>|<span data-ttu-id="71dc7-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="71dc7-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="71dc7-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="71dc7-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="71dc7-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="71dc7-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="71dc7-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="71dc7-124">E_NOTIMPL</span></span>|<span data-ttu-id="71dc7-125">El host no proporciona una implementación de `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="71dc7-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71dc7-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="71dc7-126">Remarks</span></span>  
 <span data-ttu-id="71dc7-127">Un host podría desear el control exclusivo sobre el número de subprocesos que se puede asignar para procesar las solicitudes de E/S, por motivos de implementación, rendimiento o escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="71dc7-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="71dc7-128">Por este motivo, no es necesario implementar el host `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="71dc7-128">For this reason, the host is not required to implement `SetMinThreads`.</span></span> <span data-ttu-id="71dc7-129">En este caso, el host debe devolver E_NOTIMPL desde este método.</span><span class="sxs-lookup"><span data-stu-id="71dc7-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71dc7-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="71dc7-130">Requirements</span></span>  
 <span data-ttu-id="71dc7-131">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71dc7-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71dc7-132">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="71dc7-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="71dc7-133">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="71dc7-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71dc7-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71dc7-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71dc7-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="71dc7-135">See also</span></span>

- [<span data-ttu-id="71dc7-136">ICLRIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="71dc7-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="71dc7-137">SetMaxThreads (método)</span><span class="sxs-lookup"><span data-stu-id="71dc7-137">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)
- [<span data-ttu-id="71dc7-138">IHostIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="71dc7-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
