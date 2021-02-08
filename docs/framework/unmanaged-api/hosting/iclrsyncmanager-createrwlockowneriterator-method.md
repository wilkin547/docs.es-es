---
description: 'Más información acerca de: ICLRSyncManager:: CreateRWLockOwnerIterator (método)'
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
ms.openlocfilehash: c6997b7720586f422cba3c96ca06a93f747d05bc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781784"
---
# <a name="iclrsyncmanagercreaterwlockowneriterator-method"></a><span data-ttu-id="d1fe2-103">ICLRSyncManager::CreateRWLockOwnerIterator (Método)</span><span class="sxs-lookup"><span data-stu-id="d1fe2-103">ICLRSyncManager::CreateRWLockOwnerIterator Method</span></span>

<span data-ttu-id="d1fe2-104">Solicita que el Common Language Runtime (CLR) cree un iterador para que lo use el host con el fin de determinar el conjunto de tareas que esperan en un bloqueo de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="d1fe2-104">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1fe2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d1fe2-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockOwnerIterator (  
    [in]  SIZE_T    cookie,  
    [out] SIZE_T   *pIterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1fe2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d1fe2-106">Parameters</span></span>  

 `cookie`  
 <span data-ttu-id="d1fe2-107">de Cookie asociada con el bloqueo de lector-escritor deseado.</span><span class="sxs-lookup"><span data-stu-id="d1fe2-107">[in] The cookie associated with the desired reader-writer lock.</span></span>  
  
 `pIterator`  
 <span data-ttu-id="d1fe2-108">enuncia Un puntero a un iterador que se puede pasar a los métodos [GetRWLockOwnerNext (](iclrsyncmanager-getrwlockownernext-method.md) y [DeleteRWLockOwnerIterator (](iclrsyncmanager-deleterwlockowneriterator-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d1fe2-108">[out] A pointer to an iterator that can be passed to the [GetRWLockOwnerNext](iclrsyncmanager-getrwlockownernext-method.md) and [DeleteRWLockOwnerIterator](iclrsyncmanager-deleterwlockowneriterator-method.md) methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d1fe2-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d1fe2-109">Return Value</span></span>  
  
|<span data-ttu-id="d1fe2-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d1fe2-110">HRESULT</span></span>|<span data-ttu-id="d1fe2-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="d1fe2-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d1fe2-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="d1fe2-112">S_OK</span></span>|<span data-ttu-id="d1fe2-113">`CreateRWLockOwnerIterator` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="d1fe2-113">`CreateRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="d1fe2-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d1fe2-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d1fe2-115">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="d1fe2-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d1fe2-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d1fe2-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d1fe2-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d1fe2-117">The call timed out.</span></span>|  
|<span data-ttu-id="d1fe2-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d1fe2-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d1fe2-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="d1fe2-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d1fe2-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d1fe2-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d1fe2-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="d1fe2-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d1fe2-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d1fe2-122">E_FAIL</span></span>|<span data-ttu-id="d1fe2-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="d1fe2-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d1fe2-124">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="d1fe2-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d1fe2-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d1fe2-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d1fe2-126">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="d1fe2-126">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="d1fe2-127">`CreateRWLockOwnerIterator` se llamó a en un subproceso que está ejecutando código administrado actualmente.</span><span class="sxs-lookup"><span data-stu-id="d1fe2-127">`CreateRWLockOwnerIterator` was called on a thread that is currently running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1fe2-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d1fe2-128">Remarks</span></span>  

 <span data-ttu-id="d1fe2-129">Normalmente, los hosts llaman a los `CreateRWLockOwnerIterator` `DeleteRWLockOwnerIterator` métodos, y `GetRWLockOwnerNext` durante la detección de interbloqueos.</span><span class="sxs-lookup"><span data-stu-id="d1fe2-129">Hosts typically call the `CreateRWLockOwnerIterator`, `DeleteRWLockOwnerIterator`, and `GetRWLockOwnerNext` methods during deadlock detection.</span></span> <span data-ttu-id="d1fe2-130">El host es responsable de garantizar que el bloqueo de lector-Writer sigue siendo válido, porque CLR no realiza ningún intento de mantener activo el bloqueo del sistema de lectura.</span><span class="sxs-lookup"><span data-stu-id="d1fe2-130">The host is responsible for ensuring that the reader-writer lock is still valid, because the CLR makes no attempt to keep the reader-writer lock alive.</span></span> <span data-ttu-id="d1fe2-131">Hay varias estrategias disponibles para que el host garantice la validez del bloqueo:</span><span class="sxs-lookup"><span data-stu-id="d1fe2-131">Several strategies are available for the host to ensure the validity of the lock:</span></span>  
  
- <span data-ttu-id="d1fe2-132">El host puede bloquear las llamadas de liberación en el bloqueo de lectura y escritura (por ejemplo, [IHostSemaphore:: ReleaseSemaphore (](ihostsemaphore-releasesemaphore-method.md)) al tiempo que se garantiza que este bloque no cause interbloqueos.</span><span class="sxs-lookup"><span data-stu-id="d1fe2-132">The host can block release calls on the reader-writer lock (for example, [IHostSemaphore::ReleaseSemaphore](ihostsemaphore-releasesemaphore-method.md)) while ensuring that this block does not cause deadlock.</span></span>  
  
- <span data-ttu-id="d1fe2-133">El host puede impedir que la salida espere en el objeto de evento asociado al bloqueo lector-escritor, asegurándose de nuevo de que este bloque no cause ningún interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="d1fe2-133">The host can block the exit from waiting on the event object associated with the reader-writer lock, again ensuring that this block does not cause deadlock.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d1fe2-134">`CreateRWLockOwnerIterator` solo se debe llamar a en subprocesos que ejecutan actualmente código no administrado.</span><span class="sxs-lookup"><span data-stu-id="d1fe2-134">`CreateRWLockOwnerIterator` must be called only on threads that are currently executing unmanaged code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1fe2-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d1fe2-135">Requirements</span></span>  

 <span data-ttu-id="d1fe2-136">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1fe2-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1fe2-137">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d1fe2-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d1fe2-138">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d1fe2-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d1fe2-139">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1fe2-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1fe2-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1fe2-140">See also</span></span>

- [<span data-ttu-id="d1fe2-141">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d1fe2-141">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="d1fe2-142">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d1fe2-142">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
