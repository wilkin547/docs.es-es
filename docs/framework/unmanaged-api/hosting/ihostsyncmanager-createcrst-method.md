---
title: IHostSyncManager::CreateCrst (Método)
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateCrst
helpviewer_keywords:
- CreateCrst method [.NET Framework hosting]
- IHostSyncManager::CreateCrst method [.NET Framework hosting]
ms.assetid: ac278cc8-2540-4a6c-b5c6-b90c3970b4f4
topic_type:
- apiref
ms.openlocfilehash: 03c0f94d10629b677cca4c4c456cdaab344cfcdd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139433"
---
# <a name="ihostsyncmanagercreatecrst-method"></a><span data-ttu-id="7bb2d-102">IHostSyncManager::CreateCrst (Método)</span><span class="sxs-lookup"><span data-stu-id="7bb2d-102">IHostSyncManager::CreateCrst Method</span></span>
<span data-ttu-id="7bb2d-103">Crea un objeto de sección crítica para la sincronización.</span><span class="sxs-lookup"><span data-stu-id="7bb2d-103">Creates a critical section object for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bb2d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7bb2d-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCrst (  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7bb2d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7bb2d-105">Parameters</span></span>  
 `ppCrst`  
 <span data-ttu-id="7bb2d-106">enuncia Un puntero a la dirección de una instancia de [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) implementada por el host, o null si no se pudo crear la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="7bb2d-106">[out] A pointer to the address of an [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance implemented by the host, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7bb2d-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7bb2d-107">Return Value</span></span>  
  
|<span data-ttu-id="7bb2d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7bb2d-108">HRESULT</span></span>|<span data-ttu-id="7bb2d-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="7bb2d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7bb2d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7bb2d-110">S_OK</span></span>|<span data-ttu-id="7bb2d-111">`CreateCrst` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="7bb2d-111">`CreateCrst` returned successfully.</span></span>|  
|<span data-ttu-id="7bb2d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7bb2d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7bb2d-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="7bb2d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7bb2d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7bb2d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7bb2d-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="7bb2d-115">The call timed out.</span></span>|  
|<span data-ttu-id="7bb2d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7bb2d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7bb2d-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="7bb2d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7bb2d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7bb2d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7bb2d-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="7bb2d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7bb2d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7bb2d-120">E_FAIL</span></span>|<span data-ttu-id="7bb2d-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="7bb2d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7bb2d-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="7bb2d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7bb2d-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7bb2d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7bb2d-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="7bb2d-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="7bb2d-125">No había suficiente memoria disponible para crear la sección crítica solicitada.</span><span class="sxs-lookup"><span data-stu-id="7bb2d-125">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7bb2d-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7bb2d-126">Remarks</span></span>  
 <span data-ttu-id="7bb2d-127">Los objetos de sección crítica proporcionan una sincronización similar a la que proporciona un objeto de exclusión mutua, salvo que las secciones críticas solo las pueden usar los subprocesos de un único proceso.</span><span class="sxs-lookup"><span data-stu-id="7bb2d-127">Critical section objects provide synchronization similar to that provided by a mutex object, except that critical sections can be used only by the threads of a single process.</span></span> <span data-ttu-id="7bb2d-128">`CreateCrst` refleja la función de `InitializeCriticalSection` de Win32.</span><span class="sxs-lookup"><span data-stu-id="7bb2d-128">`CreateCrst` mirrors the Win32 `InitializeCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bb2d-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7bb2d-129">Requirements</span></span>  
 <span data-ttu-id="7bb2d-130">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7bb2d-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bb2d-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7bb2d-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7bb2d-132">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7bb2d-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7bb2d-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bb2d-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bb2d-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="7bb2d-134">See also</span></span>

- [<span data-ttu-id="7bb2d-135">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7bb2d-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="7bb2d-136">IHostCrst (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7bb2d-136">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="7bb2d-137">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7bb2d-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="7bb2d-138">IHostSemaphore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7bb2d-138">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- <span data-ttu-id="7bb2d-139">[Mutexes](../../../standard/threading/mutexes.md) (Clases Mutex)</span><span class="sxs-lookup"><span data-stu-id="7bb2d-139">[Mutexes](../../../standard/threading/mutexes.md)</span></span>
- <span data-ttu-id="7bb2d-140">[Semaphore and SemaphoreSlim](../../../standard/threading/semaphore-and-semaphoreslim.md) (Clases Semaphore y SemaphoreSlim)</span><span class="sxs-lookup"><span data-stu-id="7bb2d-140">[Semaphore and SemaphoreSlim](../../../standard/threading/semaphore-and-semaphoreslim.md)</span></span>
