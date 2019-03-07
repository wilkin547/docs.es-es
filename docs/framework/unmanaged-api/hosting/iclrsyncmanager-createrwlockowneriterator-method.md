---
title: ICLRSyncManager::CreateRWLockOwnerIterator (Método)
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.CreateRWLockOwnerIterator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::CreateRWLockOwnerIterator
helpviewer_keywords:
- ICLRSyncManager::CreateRWLockOwnerIterator method [.NET Framework hosting]
- CreateRWLockOwnerIterator method [.NET Framework hosting]
ms.assetid: b5535b87-9439-424e-b9b3-7d6fafb9819e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b2b9c2fb2a4ddcc39c7690d832a94d772e8b82a3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497085"
---
# <a name="iclrsyncmanagercreaterwlockowneriterator-method"></a><span data-ttu-id="88239-102">ICLRSyncManager::CreateRWLockOwnerIterator (Método)</span><span class="sxs-lookup"><span data-stu-id="88239-102">ICLRSyncManager::CreateRWLockOwnerIterator Method</span></span>
<span data-ttu-id="88239-103">Solicita que common language runtime (CLR) crea un iterador para el host se utiliza para determinar el conjunto de tareas que esperan en un bloqueo de lector y escritor.</span><span class="sxs-lookup"><span data-stu-id="88239-103">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88239-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="88239-104">Syntax</span></span>  
  
```  
HRESULT CreateRWLockOwnerIterator (  
    [in]  SIZE_T    cookie,  
    [out] SIZE_T   *pIterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88239-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="88239-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="88239-106">[in] La cookie asociada con el bloqueo de lector y escritor.</span><span class="sxs-lookup"><span data-stu-id="88239-106">[in] The cookie associated with the desired reader-writer lock.</span></span>  
  
 `pIterator`  
 <span data-ttu-id="88239-107">[out] Un puntero a un iterador que puede pasarse a la [GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md) y [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) métodos.</span><span class="sxs-lookup"><span data-stu-id="88239-107">[out] A pointer to an iterator that can be passed to the [GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md) and [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="88239-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="88239-108">Return Value</span></span>  
  
|<span data-ttu-id="88239-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="88239-109">HRESULT</span></span>|<span data-ttu-id="88239-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="88239-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="88239-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="88239-111">S_OK</span></span>|<span data-ttu-id="88239-112">`CreateRWLockOwnerIterator` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="88239-112">`CreateRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="88239-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="88239-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="88239-114">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="88239-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="88239-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="88239-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="88239-116">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="88239-116">The call timed out.</span></span>|  
|<span data-ttu-id="88239-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="88239-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="88239-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="88239-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="88239-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="88239-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="88239-120">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="88239-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="88239-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="88239-121">E_FAIL</span></span>|<span data-ttu-id="88239-122">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="88239-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="88239-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="88239-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="88239-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="88239-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="88239-125">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="88239-125">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="88239-126">`CreateRWLockOwnerIterator` se llamó en un subproceso que se está ejecutando código administrado.</span><span class="sxs-lookup"><span data-stu-id="88239-126">`CreateRWLockOwnerIterator` was called on a thread that is currently running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88239-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="88239-127">Remarks</span></span>  
 <span data-ttu-id="88239-128">Hosts normalmente llamar el `CreateRWLockOwnerIterator`, `DeleteRWLockOwnerIterator`, y `GetRWLockOwnerNext` métodos durante la detección de interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="88239-128">Hosts typically call the `CreateRWLockOwnerIterator`, `DeleteRWLockOwnerIterator`, and `GetRWLockOwnerNext` methods during deadlock detection.</span></span> <span data-ttu-id="88239-129">El host es responsable de garantizar que el bloqueo de lector y escritor sigue siendo válido, ya que el CLR realiza ningún intento para mantener activo el bloqueo de lector y escritor.</span><span class="sxs-lookup"><span data-stu-id="88239-129">The host is responsible for ensuring that the reader-writer lock is still valid, because the CLR makes no attempt to keep the reader-writer lock alive.</span></span> <span data-ttu-id="88239-130">Existen varias estrategias para el host garantizar la validez del bloqueo:</span><span class="sxs-lookup"><span data-stu-id="88239-130">Several strategies are available for the host to ensure the validity of the lock:</span></span>  
  
-   <span data-ttu-id="88239-131">El host puede bloquear las llamadas de liberación en el bloqueo de lector y escritor (por ejemplo, [IHostSemaphore:: ReleaseSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)) asegurándose de que este bloque no causar un interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="88239-131">The host can block release calls on the reader-writer lock (for example, [IHostSemaphore::ReleaseSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)) while ensuring that this block does not cause deadlock.</span></span>  
  
-   <span data-ttu-id="88239-132">El host puede bloquear la salida de espera en el objeto de evento asociado con el bloqueo de lector y escritor, vuelva a asegurarse de que este bloque no causar un interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="88239-132">The host can block the exit from waiting on the event object associated with the reader-writer lock, again ensuring that this block does not cause deadlock.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="88239-133">`CreateRWLockOwnerIterator` debe llamarse únicamente en los subprocesos que se están ejecutando código no administrado.</span><span class="sxs-lookup"><span data-stu-id="88239-133">`CreateRWLockOwnerIterator` must be called only on threads that are currently executing unmanaged code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88239-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="88239-134">Requirements</span></span>  
 <span data-ttu-id="88239-135">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88239-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88239-136">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="88239-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="88239-137">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="88239-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="88239-138">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88239-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88239-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="88239-139">See also</span></span>
- [<span data-ttu-id="88239-140">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="88239-140">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="88239-141">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="88239-141">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
