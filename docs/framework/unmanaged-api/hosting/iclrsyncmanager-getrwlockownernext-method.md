---
title: ICLRSyncManager::GetRWLockOwnerNext (Método)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4725feff4645ec207be6e6afc7d1e1d38eca36ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435215"
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a><span data-ttu-id="08fe9-102">ICLRSyncManager::GetRWLockOwnerNext (Método)</span><span class="sxs-lookup"><span data-stu-id="08fe9-102">ICLRSyncManager::GetRWLockOwnerNext Method</span></span>
<span data-ttu-id="08fe9-103">Obtiene el siguiente [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instancia que está bloqueado en el bloqueo de lector y escritor actual.</span><span class="sxs-lookup"><span data-stu-id="08fe9-103">Gets the next [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that is blocked on the current reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08fe9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="08fe9-104">Syntax</span></span>  
  
```  
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="08fe9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="08fe9-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="08fe9-106">[in] El iterador que se creó mediante una llamada a [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span><span class="sxs-lookup"><span data-stu-id="08fe9-106">[in] The iterator that was created by using a call to [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="08fe9-107">[out] Un puntero a la siguiente `IHostTask` que está esperando el bloqueo, o null si no hay ninguna tarea está esperando.</span><span class="sxs-lookup"><span data-stu-id="08fe9-107">[out] A pointer to the next `IHostTask` that is waiting on the lock, or null if no task is waiting.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08fe9-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="08fe9-108">Return Value</span></span>  
  
|<span data-ttu-id="08fe9-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="08fe9-109">HRESULT</span></span>|<span data-ttu-id="08fe9-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="08fe9-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="08fe9-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="08fe9-111">S_OK</span></span>|<span data-ttu-id="08fe9-112">`GetRWLockOwnerNext` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="08fe9-112">`GetRWLockOwnerNext` returned successfully.</span></span>|  
|<span data-ttu-id="08fe9-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="08fe9-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="08fe9-114">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="08fe9-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="08fe9-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="08fe9-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="08fe9-116">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="08fe9-116">The call timed out.</span></span>|  
|<span data-ttu-id="08fe9-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="08fe9-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="08fe9-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="08fe9-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="08fe9-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="08fe9-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="08fe9-120">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="08fe9-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="08fe9-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="08fe9-121">E_FAIL</span></span>|<span data-ttu-id="08fe9-122">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="08fe9-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="08fe9-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="08fe9-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="08fe9-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="08fe9-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08fe9-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="08fe9-125">Remarks</span></span>  
 <span data-ttu-id="08fe9-126">Si `ppOwnerHostTask` se establece en null, la iteración ha finalizado y el host debe llamar a la [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="08fe9-126">If `ppOwnerHostTask` is set to null, the iteration has terminated, and the host should call the [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08fe9-127">CLR llama `AddRef` en el `IHostTask` a la que `ppOwnerHostTask` puntos para evitar que esta tarea salga mientras el host mantiene el puntero.</span><span class="sxs-lookup"><span data-stu-id="08fe9-127">The CLR calls `AddRef` on the `IHostTask` to which `ppOwnerHostTask` points to prevent this task from exiting while the host holds the pointer.</span></span> <span data-ttu-id="08fe9-128">El host debe llamar a `Release` para reducir el recuento de referencias cuando haya finalizado.</span><span class="sxs-lookup"><span data-stu-id="08fe9-128">The host must call `Release` to decrement the reference count when it is finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08fe9-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="08fe9-129">Requirements</span></span>  
 <span data-ttu-id="08fe9-130">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08fe9-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08fe9-131">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="08fe9-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="08fe9-132">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="08fe9-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="08fe9-133">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08fe9-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08fe9-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="08fe9-134">See Also</span></span>  
 [<span data-ttu-id="08fe9-135">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="08fe9-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="08fe9-136">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="08fe9-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
