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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 622b6c523adfb7bae2fc38826152ef69709568cc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931078"
---
# <a name="ihostsyncmanagercreatecrst-method"></a><span data-ttu-id="676f1-102">IHostSyncManager::CreateCrst (Método)</span><span class="sxs-lookup"><span data-stu-id="676f1-102">IHostSyncManager::CreateCrst Method</span></span>
<span data-ttu-id="676f1-103">Crea un objeto de sección crítica para la sincronización.</span><span class="sxs-lookup"><span data-stu-id="676f1-103">Creates a critical section object for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="676f1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="676f1-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCrst (  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="676f1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="676f1-105">Parameters</span></span>  
 `ppCrst`  
 <span data-ttu-id="676f1-106">enuncia Un puntero a la dirección de una instancia de [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) implementada por el host, o null si no se pudo crear la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="676f1-106">[out] A pointer to the address of an [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance implemented by the host, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="676f1-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="676f1-107">Return Value</span></span>  
  
|<span data-ttu-id="676f1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="676f1-108">HRESULT</span></span>|<span data-ttu-id="676f1-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="676f1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="676f1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="676f1-110">S_OK</span></span>|<span data-ttu-id="676f1-111">`CreateCrst`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="676f1-111">`CreateCrst` returned successfully.</span></span>|  
|<span data-ttu-id="676f1-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="676f1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="676f1-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="676f1-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="676f1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="676f1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="676f1-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="676f1-115">The call timed out.</span></span>|  
|<span data-ttu-id="676f1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="676f1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="676f1-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="676f1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="676f1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="676f1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="676f1-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="676f1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="676f1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="676f1-120">E_FAIL</span></span>|<span data-ttu-id="676f1-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="676f1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="676f1-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="676f1-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="676f1-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="676f1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="676f1-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="676f1-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="676f1-125">No había suficiente memoria disponible para crear la sección crítica solicitada.</span><span class="sxs-lookup"><span data-stu-id="676f1-125">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="676f1-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="676f1-126">Remarks</span></span>  
 <span data-ttu-id="676f1-127">Los objetos de sección crítica proporcionan una sincronización similar a la que proporciona un objeto de exclusión mutua, salvo que las secciones críticas solo las pueden usar los subprocesos de un único proceso.</span><span class="sxs-lookup"><span data-stu-id="676f1-127">Critical section objects provide synchronization similar to that provided by a mutex object, except that critical sections can be used only by the threads of a single process.</span></span> <span data-ttu-id="676f1-128">`CreateCrst`refleja la función `InitializeCriticalSection` de Win32.</span><span class="sxs-lookup"><span data-stu-id="676f1-128">`CreateCrst` mirrors the Win32 `InitializeCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="676f1-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="676f1-129">Requirements</span></span>  
 <span data-ttu-id="676f1-130">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="676f1-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="676f1-131">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="676f1-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="676f1-132">**Biblioteca** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="676f1-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="676f1-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="676f1-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="676f1-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="676f1-134">See also</span></span>

- [<span data-ttu-id="676f1-135">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="676f1-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="676f1-136">IHostCrst (interfaz)</span><span class="sxs-lookup"><span data-stu-id="676f1-136">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="676f1-137">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="676f1-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="676f1-138">IHostSemaphore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="676f1-138">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- <span data-ttu-id="676f1-139">[Mutexes](../../../standard/threading/mutexes.md) (Clases Mutex)</span><span class="sxs-lookup"><span data-stu-id="676f1-139">[Mutexes](../../../standard/threading/mutexes.md)</span></span>
- <span data-ttu-id="676f1-140">[Semaphore and SemaphoreSlim](../../../standard/threading/semaphore-and-semaphoreslim.md) (Clases Semaphore y SemaphoreSlim)</span><span class="sxs-lookup"><span data-stu-id="676f1-140">[Semaphore and SemaphoreSlim](../../../standard/threading/semaphore-and-semaphoreslim.md)</span></span>
