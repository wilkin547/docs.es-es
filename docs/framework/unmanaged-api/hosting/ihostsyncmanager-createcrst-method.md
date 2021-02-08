---
description: 'Más información acerca de: IHostSyncManager:: Createcrst ((método)'
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
ms.openlocfilehash: 7d1880f1553d159f62efe65afe8368a60b5bf9cc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784813"
---
# <a name="ihostsyncmanagercreatecrst-method"></a><span data-ttu-id="00686-103">IHostSyncManager::CreateCrst (Método)</span><span class="sxs-lookup"><span data-stu-id="00686-103">IHostSyncManager::CreateCrst Method</span></span>

<span data-ttu-id="00686-104">Crea un objeto de sección crítica para la sincronización.</span><span class="sxs-lookup"><span data-stu-id="00686-104">Creates a critical section object for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00686-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="00686-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateCrst (  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00686-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="00686-106">Parameters</span></span>  

 `ppCrst`  
 <span data-ttu-id="00686-107">enuncia Un puntero a la dirección de una instancia de [IHostCrst](ihostcrst-interface.md) implementada por el host, o null si no se pudo crear la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="00686-107">[out] A pointer to the address of an [IHostCrst](ihostcrst-interface.md) instance implemented by the host, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="00686-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="00686-108">Return Value</span></span>  
  
|<span data-ttu-id="00686-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="00686-109">HRESULT</span></span>|<span data-ttu-id="00686-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="00686-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="00686-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="00686-111">S_OK</span></span>|<span data-ttu-id="00686-112">`CreateCrst` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="00686-112">`CreateCrst` returned successfully.</span></span>|  
|<span data-ttu-id="00686-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="00686-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="00686-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="00686-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="00686-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="00686-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="00686-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="00686-116">The call timed out.</span></span>|  
|<span data-ttu-id="00686-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="00686-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="00686-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="00686-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="00686-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="00686-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="00686-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="00686-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="00686-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="00686-121">E_FAIL</span></span>|<span data-ttu-id="00686-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="00686-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="00686-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="00686-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="00686-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="00686-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="00686-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="00686-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="00686-126">No había suficiente memoria disponible para crear la sección crítica solicitada.</span><span class="sxs-lookup"><span data-stu-id="00686-126">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00686-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="00686-127">Remarks</span></span>  

 <span data-ttu-id="00686-128">Los objetos de sección crítica proporcionan una sincronización similar a la que proporciona un objeto de exclusión mutua, salvo que las secciones críticas solo las pueden usar los subprocesos de un único proceso.</span><span class="sxs-lookup"><span data-stu-id="00686-128">Critical section objects provide synchronization similar to that provided by a mutex object, except that critical sections can be used only by the threads of a single process.</span></span> <span data-ttu-id="00686-129">`CreateCrst` refleja la función de Win32 `InitializeCriticalSection` .</span><span class="sxs-lookup"><span data-stu-id="00686-129">`CreateCrst` mirrors the Win32 `InitializeCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00686-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="00686-130">Requirements</span></span>  

 <span data-ttu-id="00686-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00686-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00686-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="00686-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="00686-133">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="00686-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="00686-134">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00686-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00686-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="00686-135">See also</span></span>

- [<span data-ttu-id="00686-136">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="00686-136">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="00686-137">IHostCrst (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="00686-137">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="00686-138">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="00686-138">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="00686-139">IHostSemaphore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="00686-139">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- <span data-ttu-id="00686-140">[Mutexes](../../../standard/threading/mutexes.md) (Clases Mutex)</span><span class="sxs-lookup"><span data-stu-id="00686-140">[Mutexes](../../../standard/threading/mutexes.md)</span></span>
- [<span data-ttu-id="00686-141">Semaphore y SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="00686-141">Semaphore and SemaphoreSlim</span></span>](../../../standard/threading/semaphore-and-semaphoreslim.md)
