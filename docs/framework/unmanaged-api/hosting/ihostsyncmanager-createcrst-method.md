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
ms.openlocfilehash: 27861a9258916f4c188d981c44833e5be4c507f2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682890"
---
# <a name="ihostsyncmanagercreatecrst-method"></a><span data-ttu-id="5d23c-102">IHostSyncManager::CreateCrst (Método)</span><span class="sxs-lookup"><span data-stu-id="5d23c-102">IHostSyncManager::CreateCrst Method</span></span>

<span data-ttu-id="5d23c-103">Crea un objeto de sección crítica para la sincronización.</span><span class="sxs-lookup"><span data-stu-id="5d23c-103">Creates a critical section object for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d23c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d23c-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCrst (  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d23c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5d23c-105">Parameters</span></span>  

 `ppCrst`  
 <span data-ttu-id="5d23c-106">enuncia Un puntero a la dirección de una instancia de [IHostCrst](ihostcrst-interface.md) implementada por el host, o null si no se pudo crear la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="5d23c-106">[out] A pointer to the address of an [IHostCrst](ihostcrst-interface.md) instance implemented by the host, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d23c-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5d23c-107">Return Value</span></span>  
  
|<span data-ttu-id="5d23c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5d23c-108">HRESULT</span></span>|<span data-ttu-id="5d23c-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d23c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5d23c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5d23c-110">S_OK</span></span>|<span data-ttu-id="5d23c-111">`CreateCrst` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="5d23c-111">`CreateCrst` returned successfully.</span></span>|  
|<span data-ttu-id="5d23c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5d23c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5d23c-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="5d23c-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5d23c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5d23c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5d23c-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5d23c-115">The call timed out.</span></span>|  
|<span data-ttu-id="5d23c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5d23c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5d23c-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="5d23c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5d23c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5d23c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5d23c-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="5d23c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5d23c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5d23c-120">E_FAIL</span></span>|<span data-ttu-id="5d23c-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="5d23c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5d23c-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="5d23c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5d23c-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5d23c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5d23c-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="5d23c-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="5d23c-125">No había suficiente memoria disponible para crear la sección crítica solicitada.</span><span class="sxs-lookup"><span data-stu-id="5d23c-125">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d23c-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5d23c-126">Remarks</span></span>  

 <span data-ttu-id="5d23c-127">Los objetos de sección crítica proporcionan una sincronización similar a la que proporciona un objeto de exclusión mutua, salvo que las secciones críticas solo las pueden usar los subprocesos de un único proceso.</span><span class="sxs-lookup"><span data-stu-id="5d23c-127">Critical section objects provide synchronization similar to that provided by a mutex object, except that critical sections can be used only by the threads of a single process.</span></span> <span data-ttu-id="5d23c-128">`CreateCrst` refleja la función de Win32 `InitializeCriticalSection` .</span><span class="sxs-lookup"><span data-stu-id="5d23c-128">`CreateCrst` mirrors the Win32 `InitializeCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d23c-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5d23c-129">Requirements</span></span>  

 <span data-ttu-id="5d23c-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d23c-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d23c-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5d23c-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5d23c-132">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5d23c-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d23c-133">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d23c-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d23c-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5d23c-134">See also</span></span>

- [<span data-ttu-id="5d23c-135">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5d23c-135">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="5d23c-136">IHostCrst (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5d23c-136">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="5d23c-137">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5d23c-137">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="5d23c-138">IHostSemaphore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5d23c-138">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- <span data-ttu-id="5d23c-139">[Mutexes](../../../standard/threading/mutexes.md) (Clases Mutex)</span><span class="sxs-lookup"><span data-stu-id="5d23c-139">[Mutexes](../../../standard/threading/mutexes.md)</span></span>
- [<span data-ttu-id="5d23c-140">Semaphore y SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="5d23c-140">Semaphore and SemaphoreSlim</span></span>](../../../standard/threading/semaphore-and-semaphoreslim.md)
