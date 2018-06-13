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
ms.openlocfilehash: 101a652aa77e587003fb7e773e00ba9b77461a06
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441898"
---
# <a name="ihostsyncmanagercreatecrst-method"></a><span data-ttu-id="1e007-102">IHostSyncManager::CreateCrst (Método)</span><span class="sxs-lookup"><span data-stu-id="1e007-102">IHostSyncManager::CreateCrst Method</span></span>
<span data-ttu-id="1e007-103">Crea un objeto de sección crítica para la sincronización.</span><span class="sxs-lookup"><span data-stu-id="1e007-103">Creates a critical section object for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e007-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1e007-104">Syntax</span></span>  
  
```  
HRESULT CreateCrst (  
    [out] IHostCrst** ppCrst  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1e007-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1e007-105">Parameters</span></span>  
 `ppCrst`  
 <span data-ttu-id="1e007-106">[out] Un puntero a la dirección de un [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instancia implementada por el host, o null si no se pudo crear la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="1e007-106">[out] A pointer to the address of an [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance implemented by the host, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1e007-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1e007-107">Return Value</span></span>  
  
|<span data-ttu-id="1e007-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1e007-108">HRESULT</span></span>|<span data-ttu-id="1e007-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="1e007-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1e007-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1e007-110">S_OK</span></span>|<span data-ttu-id="1e007-111">`CreateCrst` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="1e007-111">`CreateCrst` returned successfully.</span></span>|  
|<span data-ttu-id="1e007-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1e007-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1e007-113">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="1e007-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1e007-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1e007-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1e007-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="1e007-115">The call timed out.</span></span>|  
|<span data-ttu-id="1e007-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1e007-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1e007-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="1e007-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1e007-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1e007-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1e007-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="1e007-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1e007-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1e007-120">E_FAIL</span></span>|<span data-ttu-id="1e007-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="1e007-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1e007-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="1e007-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1e007-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1e007-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1e007-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="1e007-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="1e007-125">No había memoria suficiente disponible para crear la sección crítica solicitada.</span><span class="sxs-lookup"><span data-stu-id="1e007-125">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e007-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1e007-126">Remarks</span></span>  
 <span data-ttu-id="1e007-127">Los objetos de sección crítica proporcionan sincronización similar a la proporcionada por un objeto de exclusión mutua, salvo que las secciones críticas pueden usarse únicamente por los subprocesos de un único proceso.</span><span class="sxs-lookup"><span data-stu-id="1e007-127">Critical section objects provide synchronization similar to that provided by a mutex object, except that critical sections can be used only by the threads of a single process.</span></span> <span data-ttu-id="1e007-128">`CreateCrst` refleja el Win32 `InitializeCriticalSection` función.</span><span class="sxs-lookup"><span data-stu-id="1e007-128">`CreateCrst` mirrors the Win32 `InitializeCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e007-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1e007-129">Requirements</span></span>  
 <span data-ttu-id="1e007-130">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e007-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e007-131">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1e007-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1e007-132">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1e007-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1e007-133">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e007-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e007-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e007-134">See Also</span></span>  
 [<span data-ttu-id="1e007-135">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1e007-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="1e007-136">IHostCrst (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1e007-136">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [<span data-ttu-id="1e007-137">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1e007-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="1e007-138">IHostSemaphore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1e007-138">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 <span data-ttu-id="1e007-139">[Mutexes](../../../../docs/standard/threading/mutexes.md) (Clases Mutex)</span><span class="sxs-lookup"><span data-stu-id="1e007-139">[Mutexes](../../../../docs/standard/threading/mutexes.md)</span></span>  
 <span data-ttu-id="1e007-140">[Semaphore and SemaphoreSlim](../../../../docs/standard/threading/semaphore-and-semaphoreslim.md) (Clases Semaphore y SemaphoreSlim)</span><span class="sxs-lookup"><span data-stu-id="1e007-140">[Semaphore and SemaphoreSlim](../../../../docs/standard/threading/semaphore-and-semaphoreslim.md)</span></span>
