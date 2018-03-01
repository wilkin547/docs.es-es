---
title: "ICLRSyncManager::GetRWLockOwnerNext (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRSyncManager.GetRWLockOwnerNext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::GetRWLockOwnerNext
helpviewer_keywords:
- ICLRSyncManager::GetRWLockOwnerNext method [.NET Framework hosting]
- GetRWLockOwnerNext method [.NET Framework hosting]
ms.assetid: 0e025b6a-280e-40a2-a2d0-b15f58777b81
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1181cbb71aa30281fbff634354162e1f245d05fe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a><span data-ttu-id="1093a-102">ICLRSyncManager::GetRWLockOwnerNext (Método)</span><span class="sxs-lookup"><span data-stu-id="1093a-102">ICLRSyncManager::GetRWLockOwnerNext Method</span></span>
<span data-ttu-id="1093a-103">Obtiene el siguiente [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instancia que está bloqueado en el bloqueo de lector y escritor actual.</span><span class="sxs-lookup"><span data-stu-id="1093a-103">Gets the next [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that is blocked on the current reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1093a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1093a-104">Syntax</span></span>  
  
```  
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1093a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1093a-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="1093a-106">[in] El iterador que se creó mediante una llamada a [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span><span class="sxs-lookup"><span data-stu-id="1093a-106">[in] The iterator that was created by using a call to [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="1093a-107">[out] Un puntero a la siguiente `IHostTask` que está esperando el bloqueo, o null si no hay ninguna tarea está esperando.</span><span class="sxs-lookup"><span data-stu-id="1093a-107">[out] A pointer to the next `IHostTask` that is waiting on the lock, or null if no task is waiting.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1093a-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1093a-108">Return Value</span></span>  
  
|<span data-ttu-id="1093a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1093a-109">HRESULT</span></span>|<span data-ttu-id="1093a-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="1093a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1093a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="1093a-111">S_OK</span></span>|<span data-ttu-id="1093a-112">`GetRWLockOwnerNext`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="1093a-112">`GetRWLockOwnerNext` returned successfully.</span></span>|  
|<span data-ttu-id="1093a-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1093a-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1093a-114">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="1093a-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1093a-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1093a-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1093a-116">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="1093a-116">The call timed out.</span></span>|  
|<span data-ttu-id="1093a-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1093a-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1093a-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="1093a-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1093a-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1093a-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1093a-120">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="1093a-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1093a-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1093a-121">E_FAIL</span></span>|<span data-ttu-id="1093a-122">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="1093a-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1093a-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="1093a-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1093a-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1093a-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1093a-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1093a-125">Remarks</span></span>  
 <span data-ttu-id="1093a-126">Si `ppOwnerHostTask` se establece en null, la iteración ha finalizado y el host debe llamar a la [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="1093a-126">If `ppOwnerHostTask` is set to null, the iteration has terminated, and the host should call the [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1093a-127">CLR llama `AddRef` en el `IHostTask` a la que `ppOwnerHostTask` puntos para evitar que esta tarea salga mientras el host mantiene el puntero.</span><span class="sxs-lookup"><span data-stu-id="1093a-127">The CLR calls `AddRef` on the `IHostTask` to which `ppOwnerHostTask` points to prevent this task from exiting while the host holds the pointer.</span></span> <span data-ttu-id="1093a-128">El host debe llamar a `Release` para reducir el recuento de referencias cuando haya finalizado.</span><span class="sxs-lookup"><span data-stu-id="1093a-128">The host must call `Release` to decrement the reference count when it is finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1093a-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1093a-129">Requirements</span></span>  
 <span data-ttu-id="1093a-130">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1093a-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1093a-131">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1093a-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1093a-132">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1093a-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1093a-133">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1093a-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1093a-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="1093a-134">See Also</span></span>  
 [<span data-ttu-id="1093a-135">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1093a-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="1093a-136">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1093a-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
