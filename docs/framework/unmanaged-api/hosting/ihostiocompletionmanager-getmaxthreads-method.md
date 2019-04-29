---
title: IHostIoCompletionManager::GetMaxThreads (Método)
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetMaxThreads
helpviewer_keywords:
- IHostIoCompletionManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: e7a6cadc-2433-4472-a701-58891abcde45
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8875fb24512ddfea57d5f9249e58de3c12b8c507
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796857"
---
# <a name="ihostiocompletionmanagergetmaxthreads-method"></a><span data-ttu-id="2f07c-102">IHostIoCompletionManager::GetMaxThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="2f07c-102">IHostIoCompletionManager::GetMaxThreads Method</span></span>
<span data-ttu-id="2f07c-103">Obtiene el número máximo de subprocesos que el host puede asignar para atender las solicitudes de E/S.</span><span class="sxs-lookup"><span data-stu-id="2f07c-103">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f07c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2f07c-104">Syntax</span></span>  
  
```  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f07c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2f07c-105">Parameters</span></span>  
 `pdwMaxIoCompletionThreads`  
 <span data-ttu-id="2f07c-106">[out] Un puntero al número máximo de subprocesos en el grupo de subprocesos que el host puede asignar para atender las solicitudes de E/S.</span><span class="sxs-lookup"><span data-stu-id="2f07c-106">[out] A pointer to the maximum number of threads in the thread pool that the host can allot to service I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2f07c-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2f07c-107">Return Value</span></span>  
  
|<span data-ttu-id="2f07c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2f07c-108">HRESULT</span></span>|<span data-ttu-id="2f07c-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f07c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2f07c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2f07c-110">S_OK</span></span>|<span data-ttu-id="2f07c-111">`GetMaxThreads` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="2f07c-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="2f07c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2f07c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2f07c-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="2f07c-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2f07c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2f07c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2f07c-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="2f07c-115">The call timed out.</span></span>|  
|<span data-ttu-id="2f07c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2f07c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2f07c-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="2f07c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2f07c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2f07c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2f07c-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="2f07c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2f07c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2f07c-120">E_FAIL</span></span>|<span data-ttu-id="2f07c-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="2f07c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2f07c-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="2f07c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2f07c-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2f07c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2f07c-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="2f07c-124">E_NOTIMPL</span></span>|<span data-ttu-id="2f07c-125">El host no proporciona una implementación de `GetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="2f07c-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f07c-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2f07c-126">Remarks</span></span>  
 <span data-ttu-id="2f07c-127">Un host podría desear el control exclusivo sobre el número de subprocesos que se puede asignar para procesar las solicitudes de E/S, por motivos de implementación, rendimiento o escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="2f07c-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="2f07c-128">Por este motivo, no es necesario implementar el host `GetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="2f07c-128">For this reason, the host is not required to implement `GetMaxThreads`.</span></span> <span data-ttu-id="2f07c-129">En este caso, el host debe devolver E_NOTIMPL desde este método.</span><span class="sxs-lookup"><span data-stu-id="2f07c-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f07c-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2f07c-130">Requirements</span></span>  
 <span data-ttu-id="2f07c-131">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f07c-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f07c-132">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2f07c-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2f07c-133">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2f07c-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2f07c-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f07c-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f07c-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f07c-135">See also</span></span>

- [<span data-ttu-id="2f07c-136">ICLRIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2f07c-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="2f07c-137">IHostIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2f07c-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
