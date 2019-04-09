---
title: IHostIoCompletionManager::GetMinThreads (Método)
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetMinThreads
helpviewer_keywords:
- GetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetMinThreads method [.NET Framework hosting]
ms.assetid: d7a7f733-677d-481c-b3d5-444fcc502b8e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: faac5adccecdd0aeecede3b4f50a4db554e3d162
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59077165"
---
# <a name="ihostiocompletionmanagergetminthreads-method"></a><span data-ttu-id="2c88b-102">IHostIoCompletionManager::GetMinThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="2c88b-102">IHostIoCompletionManager::GetMinThreads Method</span></span>
<span data-ttu-id="2c88b-103">Obtiene el número mínimo de subprocesos que proporciona el host para procesar las solicitudes de E/S.</span><span class="sxs-lookup"><span data-stu-id="2c88b-103">Gets the minimum number of threads that the host provides for processing I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c88b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2c88b-104">Syntax</span></span>  
  
```  
HRESULT GetMinThreads (  
    [out] DWORD *pdwMinIOCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c88b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2c88b-105">Parameters</span></span>  
 `pdwMinIOCompletionThreads`  
 <span data-ttu-id="2c88b-106">[out] Un puntero al número mínimo de subprocesos que el host proporciona a las solicitudes de E/S del proceso.</span><span class="sxs-lookup"><span data-stu-id="2c88b-106">[out] A pointer to the minimum number of threads that the host provides to process I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c88b-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2c88b-107">Return Value</span></span>  
  
|<span data-ttu-id="2c88b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2c88b-108">HRESULT</span></span>|<span data-ttu-id="2c88b-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="2c88b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2c88b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2c88b-110">S_OK</span></span>|`GetMinThreads` <span data-ttu-id="2c88b-111">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="2c88b-111">returned successfully.</span></span>|  
|<span data-ttu-id="2c88b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2c88b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2c88b-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="2c88b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2c88b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2c88b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2c88b-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="2c88b-115">The call timed out.</span></span>|  
|<span data-ttu-id="2c88b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2c88b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2c88b-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="2c88b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2c88b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2c88b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2c88b-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="2c88b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2c88b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2c88b-120">E_FAIL</span></span>|<span data-ttu-id="2c88b-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="2c88b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2c88b-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="2c88b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2c88b-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2c88b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2c88b-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="2c88b-124">E_NOTIMPL</span></span>|<span data-ttu-id="2c88b-125">El host no proporciona una implementación de `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="2c88b-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c88b-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2c88b-126">Remarks</span></span>  
 <span data-ttu-id="2c88b-127">Un host podría desear el control exclusivo sobre el número de subprocesos asignados para atender las solicitudes de E/S, por motivos de implementación, rendimiento o escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="2c88b-127">A host might want exclusive control over the number of threads allotted to service I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="2c88b-128">Por este motivo, no es necesario implementar el host `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="2c88b-128">For this reason, the host is not required to implement `GetMinThreads`.</span></span> <span data-ttu-id="2c88b-129">En este caso, el host debe devolver E_NOTIMPL desde este método.</span><span class="sxs-lookup"><span data-stu-id="2c88b-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c88b-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2c88b-130">Requirements</span></span>  
 <span data-ttu-id="2c88b-131">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c88b-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c88b-132">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2c88b-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2c88b-133">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2c88b-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="2c88b-134">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="2c88b-134">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2c88b-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c88b-135">See also</span></span>

- [<span data-ttu-id="2c88b-136">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2c88b-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="2c88b-137">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2c88b-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
