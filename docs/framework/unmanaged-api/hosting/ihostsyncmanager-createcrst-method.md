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
ms.openlocfilehash: 8b63b283a28ed27a70698c45bdc87d63fef0daf8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117954"
---
# <a name="ihostsyncmanagercreatecrst-method"></a><span data-ttu-id="0d6d1-102">IHostSyncManager::CreateCrst (Método)</span><span class="sxs-lookup"><span data-stu-id="0d6d1-102">IHostSyncManager::CreateCrst Method</span></span>
<span data-ttu-id="0d6d1-103">Crea un objeto de sección crítica para la sincronización.</span><span class="sxs-lookup"><span data-stu-id="0d6d1-103">Creates a critical section object for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d6d1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0d6d1-104">Syntax</span></span>  
  
```  
HRESULT CreateCrst (  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d6d1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0d6d1-105">Parameters</span></span>  
 `ppCrst`  
 <span data-ttu-id="0d6d1-106">[out] Un puntero a la dirección de un [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instancia implementada por el host, o null si no se pudo crear la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="0d6d1-106">[out] A pointer to the address of an [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance implemented by the host, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d6d1-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0d6d1-107">Return Value</span></span>  
  
|<span data-ttu-id="0d6d1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0d6d1-108">HRESULT</span></span>|<span data-ttu-id="0d6d1-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="0d6d1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0d6d1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0d6d1-110">S_OK</span></span>|`CreateCrst` <span data-ttu-id="0d6d1-111">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="0d6d1-111">returned successfully.</span></span>|  
|<span data-ttu-id="0d6d1-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0d6d1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0d6d1-113">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="0d6d1-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0d6d1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0d6d1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0d6d1-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="0d6d1-115">The call timed out.</span></span>|  
|<span data-ttu-id="0d6d1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0d6d1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0d6d1-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="0d6d1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0d6d1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0d6d1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0d6d1-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="0d6d1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0d6d1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0d6d1-120">E_FAIL</span></span>|<span data-ttu-id="0d6d1-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="0d6d1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0d6d1-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="0d6d1-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0d6d1-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0d6d1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0d6d1-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="0d6d1-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="0d6d1-125">No había suficiente memoria disponible para crear la sección crítica solicitada.</span><span class="sxs-lookup"><span data-stu-id="0d6d1-125">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d6d1-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0d6d1-126">Remarks</span></span>  
 <span data-ttu-id="0d6d1-127">Objetos de sección crítica proporcionan sincronización similar a la proporciona un objeto de exclusión mutua, salvo que se pueden usar las secciones críticas únicamente por los subprocesos de un único proceso.</span><span class="sxs-lookup"><span data-stu-id="0d6d1-127">Critical section objects provide synchronization similar to that provided by a mutex object, except that critical sections can be used only by the threads of a single process.</span></span> `CreateCrst` <span data-ttu-id="0d6d1-128">refleja el Win32 `InitializeCriticalSection` función.</span><span class="sxs-lookup"><span data-stu-id="0d6d1-128">mirrors the Win32 `InitializeCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d6d1-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0d6d1-129">Requirements</span></span>  
 <span data-ttu-id="0d6d1-130">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d6d1-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d6d1-131">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0d6d1-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0d6d1-132">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0d6d1-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="0d6d1-133">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0d6d1-133">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0d6d1-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d6d1-134">See also</span></span>

- [<span data-ttu-id="0d6d1-135">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0d6d1-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="0d6d1-136">IHostCrst (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0d6d1-136">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="0d6d1-137">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0d6d1-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="0d6d1-138">IHostSemaphore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0d6d1-138">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="0d6d1-139">Mutexes</span><span class="sxs-lookup"><span data-stu-id="0d6d1-139">Mutexes</span></span>](../../../../docs/standard/threading/mutexes.md)
- [<span data-ttu-id="0d6d1-140">Semaphore y SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="0d6d1-140">Semaphore and SemaphoreSlim</span></span>](../../../../docs/standard/threading/semaphore-and-semaphoreslim.md)
