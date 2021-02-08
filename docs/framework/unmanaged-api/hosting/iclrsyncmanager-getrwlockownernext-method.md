---
description: 'Más información acerca de: ICLRSyncManager:: GetRWLockOwnerNext ((método)'
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
ms.openlocfilehash: f49bdd5065ac896147967c0a013347ab39ce1eff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785008"
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a><span data-ttu-id="6d53a-103">ICLRSyncManager::GetRWLockOwnerNext (Método)</span><span class="sxs-lookup"><span data-stu-id="6d53a-103">ICLRSyncManager::GetRWLockOwnerNext Method</span></span>

<span data-ttu-id="6d53a-104">Obtiene la siguiente instancia de [IHostTask](ihosttask-interface.md) que está bloqueada en el bloqueo de lector-Writer actual.</span><span class="sxs-lookup"><span data-stu-id="6d53a-104">Gets the next [IHostTask](ihosttask-interface.md) instance that is blocked on the current reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d53a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d53a-105">Syntax</span></span>  
  
```cpp
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d53a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6d53a-106">Parameters</span></span>  

 `Iterator`  
 <span data-ttu-id="6d53a-107">de Iterador que se creó mediante una llamada a [CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md).</span><span class="sxs-lookup"><span data-stu-id="6d53a-107">[in] The iterator that was created by using a call to [CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="6d53a-108">enuncia Puntero al siguiente `IHostTask` que está esperando en el bloqueo, o null si no hay ninguna tarea en espera.</span><span class="sxs-lookup"><span data-stu-id="6d53a-108">[out] A pointer to the next `IHostTask` that is waiting on the lock, or null if no task is waiting.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6d53a-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6d53a-109">Return Value</span></span>  
  
|<span data-ttu-id="6d53a-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6d53a-110">HRESULT</span></span>|<span data-ttu-id="6d53a-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d53a-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6d53a-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="6d53a-112">S_OK</span></span>|<span data-ttu-id="6d53a-113">`GetRWLockOwnerNext` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="6d53a-113">`GetRWLockOwnerNext` returned successfully.</span></span>|  
|<span data-ttu-id="6d53a-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6d53a-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6d53a-115">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="6d53a-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6d53a-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6d53a-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6d53a-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="6d53a-117">The call timed out.</span></span>|  
|<span data-ttu-id="6d53a-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6d53a-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6d53a-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="6d53a-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6d53a-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6d53a-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6d53a-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="6d53a-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6d53a-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6d53a-122">E_FAIL</span></span>|<span data-ttu-id="6d53a-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="6d53a-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6d53a-124">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="6d53a-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6d53a-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6d53a-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d53a-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6d53a-126">Remarks</span></span>  

 <span data-ttu-id="6d53a-127">Si `ppOwnerHostTask` se establece en null, la iteración ha finalizado y el host debe llamar al método [DeleteRWLockOwnerIterator (](iclrsyncmanager-deleterwlockowneriterator-method.md) .</span><span class="sxs-lookup"><span data-stu-id="6d53a-127">If `ppOwnerHostTask` is set to null, the iteration has terminated, and the host should call the [DeleteRWLockOwnerIterator](iclrsyncmanager-deleterwlockowneriterator-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6d53a-128">CLR llama a `AddRef` en el `IHostTask` que `ppOwnerHostTask` señala para evitar que esta tarea se salga mientras el host contiene el puntero.</span><span class="sxs-lookup"><span data-stu-id="6d53a-128">The CLR calls `AddRef` on the `IHostTask` to which `ppOwnerHostTask` points to prevent this task from exiting while the host holds the pointer.</span></span> <span data-ttu-id="6d53a-129">El host debe llamar `Release` a para reducir el recuento de referencias cuando termine.</span><span class="sxs-lookup"><span data-stu-id="6d53a-129">The host must call `Release` to decrement the reference count when it is finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d53a-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6d53a-130">Requirements</span></span>  

 <span data-ttu-id="6d53a-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d53a-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d53a-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6d53a-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6d53a-133">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6d53a-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6d53a-134">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d53a-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d53a-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d53a-135">See also</span></span>

- [<span data-ttu-id="6d53a-136">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6d53a-136">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="6d53a-137">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6d53a-137">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
