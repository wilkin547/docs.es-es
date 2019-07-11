---
title: IHostIoCompletionManager::GetAvailableThreads (Método)
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: bab363d1-b859-47a4-9884-5661c611cce7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4316412cec26ae5698918ff65b2da65de9f36ff2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779617"
---
# <a name="ihostiocompletionmanagergetavailablethreads-method"></a><span data-ttu-id="b3f3c-102">IHostIoCompletionManager::GetAvailableThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="b3f3c-102">IHostIoCompletionManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="b3f3c-103">Obtiene el número de subprocesos de finalización de E/S, del número total de subprocesos administrados por el host, que no están atendiendo las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="b3f3c-103">Gets the number of I/O completion threads, of the total number of threads managed by the host, that are not currently servicing requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3f3c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b3f3c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3f3c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b3f3c-105">Parameters</span></span>  
 `pdwAvailableIoCompletionThreads`  
 <span data-ttu-id="b3f3c-106">[out] Un puntero al número de subprocesos de finalización de E/S administrados por el host que están actualmente disponibles para atender las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="b3f3c-106">[out] A pointer to the number of I/O completion threads managed by the host that are currently available to service requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3f3c-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b3f3c-107">Return Value</span></span>  
  
|<span data-ttu-id="b3f3c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b3f3c-108">HRESULT</span></span>|<span data-ttu-id="b3f3c-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b3f3c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b3f3c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b3f3c-110">S_OK</span></span>|<span data-ttu-id="b3f3c-111">`GetAvailableThreads` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b3f3c-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="b3f3c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b3f3c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b3f3c-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="b3f3c-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b3f3c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b3f3c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b3f3c-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="b3f3c-115">The call timed out.</span></span>|  
|<span data-ttu-id="b3f3c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b3f3c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b3f3c-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="b3f3c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b3f3c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b3f3c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b3f3c-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="b3f3c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b3f3c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b3f3c-120">E_FAIL</span></span>|<span data-ttu-id="b3f3c-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="b3f3c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b3f3c-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="b3f3c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b3f3c-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b3f3c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b3f3c-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="b3f3c-124">E_NOTIMPL</span></span>|<span data-ttu-id="b3f3c-125">El host no proporciona una implementación de `GetAvailableThreads`.</span><span class="sxs-lookup"><span data-stu-id="b3f3c-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3f3c-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b3f3c-126">Remarks</span></span>  
 <span data-ttu-id="b3f3c-127">Un host podría desear el control exclusivo sobre el tamaño del grupo de subprocesos de finalización de E/S, por motivos de implementación, rendimiento o escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="b3f3c-127">A host might want exclusive control over the size of the I/O completion thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="b3f3c-128">Por lo tanto, no es necesario para implementar el host `GetAvailableThreads`.</span><span class="sxs-lookup"><span data-stu-id="b3f3c-128">Therefore, the host is not required to implement `GetAvailableThreads`.</span></span> <span data-ttu-id="b3f3c-129">En este caso, el host debe devolver E_NOTIMPL desde este método.</span><span class="sxs-lookup"><span data-stu-id="b3f3c-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3f3c-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b3f3c-130">Requirements</span></span>  
 <span data-ttu-id="b3f3c-131">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3f3c-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3f3c-132">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b3f3c-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b3f3c-133">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b3f3c-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b3f3c-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3f3c-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3f3c-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3f3c-135">See also</span></span>

- [<span data-ttu-id="b3f3c-136">ICLRIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b3f3c-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="b3f3c-137">IHostIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b3f3c-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
