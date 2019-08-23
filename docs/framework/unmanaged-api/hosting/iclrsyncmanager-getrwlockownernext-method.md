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
ms.openlocfilehash: dbc38d9cf88f2449bbf689e4cf1b4101f47a0577
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943261"
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a><span data-ttu-id="e5028-102">ICLRSyncManager::GetRWLockOwnerNext (Método)</span><span class="sxs-lookup"><span data-stu-id="e5028-102">ICLRSyncManager::GetRWLockOwnerNext Method</span></span>
<span data-ttu-id="e5028-103">Obtiene la siguiente instancia de [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) que está bloqueada en el bloqueo de lector-Writer actual.</span><span class="sxs-lookup"><span data-stu-id="e5028-103">Gets the next [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that is blocked on the current reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5028-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5028-104">Syntax</span></span>  
  
```  
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5028-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e5028-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="e5028-106">de Iterador que se creó mediante una llamada a [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span><span class="sxs-lookup"><span data-stu-id="e5028-106">[in] The iterator that was created by using a call to [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="e5028-107">enuncia Puntero al siguiente `IHostTask` que está esperando en el bloqueo, o null si no hay ninguna tarea en espera.</span><span class="sxs-lookup"><span data-stu-id="e5028-107">[out] A pointer to the next `IHostTask` that is waiting on the lock, or null if no task is waiting.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5028-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e5028-108">Return Value</span></span>  
  
|<span data-ttu-id="e5028-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e5028-109">HRESULT</span></span>|<span data-ttu-id="e5028-110">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e5028-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e5028-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e5028-111">S_OK</span></span>|<span data-ttu-id="e5028-112">`GetRWLockOwnerNext`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="e5028-112">`GetRWLockOwnerNext` returned successfully.</span></span>|  
|<span data-ttu-id="e5028-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e5028-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e5028-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="e5028-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e5028-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e5028-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e5028-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="e5028-116">The call timed out.</span></span>|  
|<span data-ttu-id="e5028-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e5028-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e5028-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="e5028-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e5028-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e5028-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e5028-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="e5028-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e5028-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e5028-121">E_FAIL</span></span>|<span data-ttu-id="e5028-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="e5028-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e5028-123">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="e5028-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e5028-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e5028-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5028-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e5028-125">Remarks</span></span>  
 <span data-ttu-id="e5028-126">Si `ppOwnerHostTask` se establece en null, la iteración ha finalizado y el host debe llamar al método [DeleteRWLockOwnerIterator (](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e5028-126">If `ppOwnerHostTask` is set to null, the iteration has terminated, and the host should call the [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5028-127">CLR llama `AddRef` a en el `IHostTask` que `ppOwnerHostTask` señala para evitar que esta tarea se salga mientras el host contiene el puntero.</span><span class="sxs-lookup"><span data-stu-id="e5028-127">The CLR calls `AddRef` on the `IHostTask` to which `ppOwnerHostTask` points to prevent this task from exiting while the host holds the pointer.</span></span> <span data-ttu-id="e5028-128">El host debe llamar `Release` a para reducir el recuento de referencias cuando termine.</span><span class="sxs-lookup"><span data-stu-id="e5028-128">The host must call `Release` to decrement the reference count when it is finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5028-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e5028-129">Requirements</span></span>  
 <span data-ttu-id="e5028-130">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5028-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5028-131">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e5028-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e5028-132">**Biblioteca** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e5028-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e5028-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5028-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5028-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5028-134">See also</span></span>

- [<span data-ttu-id="e5028-135">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e5028-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="e5028-136">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e5028-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
