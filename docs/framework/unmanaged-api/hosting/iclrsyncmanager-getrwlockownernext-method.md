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
ms.openlocfilehash: 93a8b3884d831b7da412b6c53dd599af216cbbf2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728321"
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a><span data-ttu-id="fc499-102">ICLRSyncManager::GetRWLockOwnerNext (Método)</span><span class="sxs-lookup"><span data-stu-id="fc499-102">ICLRSyncManager::GetRWLockOwnerNext Method</span></span>

<span data-ttu-id="fc499-103">Obtiene la siguiente instancia de [IHostTask](ihosttask-interface.md) que está bloqueada en el bloqueo de lector-Writer actual.</span><span class="sxs-lookup"><span data-stu-id="fc499-103">Gets the next [IHostTask](ihosttask-interface.md) instance that is blocked on the current reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc499-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc499-104">Syntax</span></span>  
  
```cpp
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc499-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fc499-105">Parameters</span></span>  

 `Iterator`  
 <span data-ttu-id="fc499-106">de Iterador que se creó mediante una llamada a [CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md).</span><span class="sxs-lookup"><span data-stu-id="fc499-106">[in] The iterator that was created by using a call to [CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="fc499-107">enuncia Puntero al siguiente `IHostTask` que está esperando en el bloqueo, o null si no hay ninguna tarea en espera.</span><span class="sxs-lookup"><span data-stu-id="fc499-107">[out] A pointer to the next `IHostTask` that is waiting on the lock, or null if no task is waiting.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fc499-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fc499-108">Return Value</span></span>  
  
|<span data-ttu-id="fc499-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fc499-109">HRESULT</span></span>|<span data-ttu-id="fc499-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc499-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fc499-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="fc499-111">S_OK</span></span>|<span data-ttu-id="fc499-112">`GetRWLockOwnerNext` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="fc499-112">`GetRWLockOwnerNext` returned successfully.</span></span>|  
|<span data-ttu-id="fc499-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fc499-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fc499-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="fc499-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fc499-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fc499-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fc499-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="fc499-116">The call timed out.</span></span>|  
|<span data-ttu-id="fc499-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fc499-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fc499-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="fc499-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fc499-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fc499-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fc499-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="fc499-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fc499-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fc499-121">E_FAIL</span></span>|<span data-ttu-id="fc499-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="fc499-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fc499-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="fc499-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fc499-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fc499-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc499-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fc499-125">Remarks</span></span>  

 <span data-ttu-id="fc499-126">Si `ppOwnerHostTask` se establece en null, la iteración ha finalizado y el host debe llamar al método [DeleteRWLockOwnerIterator (](iclrsyncmanager-deleterwlockowneriterator-method.md) .</span><span class="sxs-lookup"><span data-stu-id="fc499-126">If `ppOwnerHostTask` is set to null, the iteration has terminated, and the host should call the [DeleteRWLockOwnerIterator](iclrsyncmanager-deleterwlockowneriterator-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fc499-127">CLR llama a `AddRef` en el `IHostTask` que `ppOwnerHostTask` señala para evitar que esta tarea se salga mientras el host contiene el puntero.</span><span class="sxs-lookup"><span data-stu-id="fc499-127">The CLR calls `AddRef` on the `IHostTask` to which `ppOwnerHostTask` points to prevent this task from exiting while the host holds the pointer.</span></span> <span data-ttu-id="fc499-128">El host debe llamar `Release` a para reducir el recuento de referencias cuando termine.</span><span class="sxs-lookup"><span data-stu-id="fc499-128">The host must call `Release` to decrement the reference count when it is finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc499-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fc499-129">Requirements</span></span>  

 <span data-ttu-id="fc499-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc499-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc499-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fc499-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fc499-132">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fc499-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fc499-133">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc499-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc499-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fc499-134">See also</span></span>

- [<span data-ttu-id="fc499-135">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fc499-135">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="fc499-136">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fc499-136">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
