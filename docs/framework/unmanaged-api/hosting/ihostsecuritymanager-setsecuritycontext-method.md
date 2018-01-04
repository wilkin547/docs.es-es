---
title: "IHostSecurityManager::SetSecurityContext (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager.SetSecurityContext
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager::SetSecurityContext
helpviewer_keywords:
- SetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::SetSecurityContext method [.NET Framework hosting]
ms.assetid: e4372384-ee69-48d7-97e0-8fab7866597a
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 29a7652e20c08b9de584a9e11ac343ad92f40653
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a><span data-ttu-id="190d1-102">IHostSecurityManager::SetSecurityContext (Método)</span><span class="sxs-lookup"><span data-stu-id="190d1-102">IHostSecurityManager::SetSecurityContext Method</span></span>
<span data-ttu-id="190d1-103">Establece el contexto de seguridad del subproceso actualmente en ejecución.</span><span class="sxs-lookup"><span data-stu-id="190d1-103">Sets the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="190d1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="190d1-104">Syntax</span></span>  
  
```  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="190d1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="190d1-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="190d1-106">[in] Uno de los [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) valores, que indica el tipo de contexto que common language runtime (CLR) está colocando en el host.</span><span class="sxs-lookup"><span data-stu-id="190d1-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of context the common language runtime (CLR) is placing on the host.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="190d1-107">[out] Un puntero a la dirección de un nuevo [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="190d1-107">[out] A pointer to the address of a new [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="190d1-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="190d1-108">Return Value</span></span>  
  
|<span data-ttu-id="190d1-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="190d1-109">HRESULT</span></span>|<span data-ttu-id="190d1-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="190d1-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="190d1-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="190d1-111">S_OK</span></span>|<span data-ttu-id="190d1-112">`SetSecurityContext`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="190d1-112">`SetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="190d1-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="190d1-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="190d1-114">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="190d1-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="190d1-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="190d1-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="190d1-116">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="190d1-116">The call timed out.</span></span>|  
|<span data-ttu-id="190d1-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="190d1-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="190d1-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="190d1-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="190d1-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="190d1-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="190d1-120">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="190d1-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="190d1-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="190d1-121">E_FAIL</span></span>|<span data-ttu-id="190d1-122">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="190d1-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="190d1-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="190d1-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="190d1-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="190d1-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="190d1-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="190d1-125">Remarks</span></span>  
 <span data-ttu-id="190d1-126">CLR llama `SetSecurityContext` en diversos escenarios.</span><span class="sxs-lookup"><span data-stu-id="190d1-126">The CLR calls `SetSecurityContext` in several scenarios.</span></span> <span data-ttu-id="190d1-127">Antes de ejecutar los finalizadores y los constructores de módulo y las clases, CLR llama `SetSecurityContext` para proteger al host de errores de ejecución.</span><span class="sxs-lookup"><span data-stu-id="190d1-127">Before it executes class and module constructors and finalizers, the CLR calls `SetSecurityContext` to protect the host from execution failures.</span></span> <span data-ttu-id="190d1-128">A continuación, restablece el contexto de seguridad a su estado original tras la ejecución del constructor o finalizador, utilizando otra llamada a `SetSecurityContext`.</span><span class="sxs-lookup"><span data-stu-id="190d1-128">It then resets the security context to its original state after execution of the constructor or finalizer, by using another call to `SetSecurityContext`.</span></span> <span data-ttu-id="190d1-129">Un patrón similar se produce con la finalización de E/S.</span><span class="sxs-lookup"><span data-stu-id="190d1-129">A similar pattern occurs with I/O completion.</span></span> <span data-ttu-id="190d1-130">Si el host implementa [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), CLR llama `SetSecurityContext` después de las llamadas de host [ICLRIoCompletionManager:: OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span><span class="sxs-lookup"><span data-stu-id="190d1-130">If the host implements [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), the CLR calls `SetSecurityContext` after the host calls [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
 <span data-ttu-id="190d1-131">En los puntos asincrónicos en subprocesos de trabajo, CLR llama `SetSecurityContext` en <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> o en [IHostThreadPoolManager:: QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md), dependiendo de si el host o CLR está implementando el grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="190d1-131">At asynchronous points in worker threads, the CLR calls `SetSecurityContext` within <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> or within [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md), depending on whether the host or the CLR is implementing the thread pool.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="190d1-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="190d1-132">Requirements</span></span>  
 <span data-ttu-id="190d1-133">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="190d1-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="190d1-134">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="190d1-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="190d1-135">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="190d1-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="190d1-136">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="190d1-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="190d1-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="190d1-137">See Also</span></span>  
 <xref:System.Threading.ThreadPool?displayProperty=nameWithType>  
 [<span data-ttu-id="190d1-138">EContextType (enumeración)</span><span class="sxs-lookup"><span data-stu-id="190d1-138">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)  
 [<span data-ttu-id="190d1-139">ICLRIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="190d1-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="190d1-140">IHostIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="190d1-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 [<span data-ttu-id="190d1-141">IHostSecurityContext (interfaz)</span><span class="sxs-lookup"><span data-stu-id="190d1-141">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="190d1-142">IHostSecurityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="190d1-142">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="190d1-143">IHostThreadPoolManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="190d1-143">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
