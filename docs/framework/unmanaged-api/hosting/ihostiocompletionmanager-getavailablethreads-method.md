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
ms.openlocfilehash: bb5de5b46a46d5caa74b83f16d943edc39d08b01
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441843"
---
# <a name="ihostiocompletionmanagergetavailablethreads-method"></a><span data-ttu-id="873a1-102">IHostIoCompletionManager::GetAvailableThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="873a1-102">IHostIoCompletionManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="873a1-103">Obtiene el número de subprocesos de finalización de E/S, del número total de subprocesos administrados por el host, que no están atendiendo solicitudes actualmente.</span><span class="sxs-lookup"><span data-stu-id="873a1-103">Gets the number of I/O completion threads, of the total number of threads managed by the host, that are not currently servicing requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="873a1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="873a1-104">Syntax</span></span>  
  
```  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableIoCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="873a1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="873a1-105">Parameters</span></span>  
 `pdwAvailableIoCompletionThreads`  
 <span data-ttu-id="873a1-106">[out] Un puntero al número de subprocesos de finalización de E/S administrados por el host que están actualmente disponibles para atender las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="873a1-106">[out] A pointer to the number of I/O completion threads managed by the host that are currently available to service requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="873a1-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="873a1-107">Return Value</span></span>  
  
|<span data-ttu-id="873a1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="873a1-108">HRESULT</span></span>|<span data-ttu-id="873a1-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="873a1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="873a1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="873a1-110">S_OK</span></span>|<span data-ttu-id="873a1-111">`GetAvailableThreads` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="873a1-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="873a1-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="873a1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="873a1-113">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="873a1-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="873a1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="873a1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="873a1-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="873a1-115">The call timed out.</span></span>|  
|<span data-ttu-id="873a1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="873a1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="873a1-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="873a1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="873a1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="873a1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="873a1-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="873a1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="873a1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="873a1-120">E_FAIL</span></span>|<span data-ttu-id="873a1-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="873a1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="873a1-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="873a1-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="873a1-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="873a1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="873a1-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="873a1-124">E_NOTIMPL</span></span>|<span data-ttu-id="873a1-125">El host no proporciona una implementación de `GetAvailableThreads`.</span><span class="sxs-lookup"><span data-stu-id="873a1-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="873a1-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="873a1-126">Remarks</span></span>  
 <span data-ttu-id="873a1-127">Un host podría desear el control exclusivo sobre el tamaño del grupo de subprocesos de finalización de E/S, por razones de implementación, rendimiento o escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="873a1-127">A host might want exclusive control over the size of the I/O completion thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="873a1-128">Por lo tanto, el host no tiene que implementar `GetAvailableThreads`.</span><span class="sxs-lookup"><span data-stu-id="873a1-128">Therefore, the host is not required to implement `GetAvailableThreads`.</span></span> <span data-ttu-id="873a1-129">En este caso, el host debe devolver E_NOTIMPL desde este método.</span><span class="sxs-lookup"><span data-stu-id="873a1-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="873a1-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="873a1-130">Requirements</span></span>  
 <span data-ttu-id="873a1-131">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="873a1-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="873a1-132">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="873a1-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="873a1-133">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="873a1-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="873a1-134">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="873a1-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="873a1-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="873a1-135">See Also</span></span>  
 [<span data-ttu-id="873a1-136">ICLRIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="873a1-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="873a1-137">IHostIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="873a1-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
