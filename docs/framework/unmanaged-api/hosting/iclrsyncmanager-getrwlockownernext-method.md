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
ms.openlocfilehash: 860a818b08cb88b0fa17adccdfac5c81c0ec502c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130558"
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a><span data-ttu-id="24240-102">ICLRSyncManager::GetRWLockOwnerNext (Método)</span><span class="sxs-lookup"><span data-stu-id="24240-102">ICLRSyncManager::GetRWLockOwnerNext Method</span></span>
<span data-ttu-id="24240-103">Obtiene la siguiente instancia de [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) que está bloqueada en el bloqueo de lector-Writer actual.</span><span class="sxs-lookup"><span data-stu-id="24240-103">Gets the next [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that is blocked on the current reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24240-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="24240-104">Syntax</span></span>  
  
```cpp
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24240-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="24240-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="24240-106">de Iterador que se creó mediante una llamada a [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span><span class="sxs-lookup"><span data-stu-id="24240-106">[in] The iterator that was created by using a call to [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="24240-107">enuncia Puntero al siguiente `IHostTask` que está esperando en el bloqueo, o null si no hay ninguna tarea en espera.</span><span class="sxs-lookup"><span data-stu-id="24240-107">[out] A pointer to the next `IHostTask` that is waiting on the lock, or null if no task is waiting.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="24240-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="24240-108">Return Value</span></span>  
  
|<span data-ttu-id="24240-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="24240-109">HRESULT</span></span>|<span data-ttu-id="24240-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="24240-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="24240-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="24240-111">S_OK</span></span>|<span data-ttu-id="24240-112">`GetRWLockOwnerNext` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="24240-112">`GetRWLockOwnerNext` returned successfully.</span></span>|  
|<span data-ttu-id="24240-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="24240-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="24240-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="24240-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="24240-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="24240-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="24240-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="24240-116">The call timed out.</span></span>|  
|<span data-ttu-id="24240-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="24240-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="24240-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="24240-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="24240-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="24240-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="24240-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="24240-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="24240-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="24240-121">E_FAIL</span></span>|<span data-ttu-id="24240-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="24240-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="24240-123">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="24240-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="24240-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="24240-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24240-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="24240-125">Remarks</span></span>  
 <span data-ttu-id="24240-126">Si `ppOwnerHostTask` se establece en null, la iteración ha finalizado y el host debe llamar al método [DeleteRWLockOwnerIterator (](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) .</span><span class="sxs-lookup"><span data-stu-id="24240-126">If `ppOwnerHostTask` is set to null, the iteration has terminated, and the host should call the [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="24240-127">CLR llama `AddRef` en el `IHostTask` al que apunta `ppOwnerHostTask` para evitar que esta tarea se cierre mientras el host contiene el puntero.</span><span class="sxs-lookup"><span data-stu-id="24240-127">The CLR calls `AddRef` on the `IHostTask` to which `ppOwnerHostTask` points to prevent this task from exiting while the host holds the pointer.</span></span> <span data-ttu-id="24240-128">El host debe llamar a `Release` para reducir el recuento de referencias cuando haya finalizado.</span><span class="sxs-lookup"><span data-stu-id="24240-128">The host must call `Release` to decrement the reference count when it is finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24240-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="24240-129">Requirements</span></span>  
 <span data-ttu-id="24240-130">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24240-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24240-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="24240-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="24240-132">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="24240-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="24240-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24240-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24240-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="24240-134">See also</span></span>

- [<span data-ttu-id="24240-135">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="24240-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="24240-136">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="24240-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
