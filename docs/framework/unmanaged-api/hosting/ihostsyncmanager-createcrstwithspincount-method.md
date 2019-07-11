---
title: IHostSyncManager::CreateCrstWithSpinCount (Método)
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateCrstWithSpinCount
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateCrstWithSpinCount
helpviewer_keywords:
- CreateCrstWithSpinCount method [.NET Framework hosting]
- IHostSyncManager::CreateCrstWithSpinCount method [.NET Framework hosting]
ms.assetid: 7280fa8c-3639-4abf-91cb-bc343da742d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 16fcc631e7e734e1bce4566f31d209a8433fbfdf
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753443"
---
# <a name="ihostsyncmanagercreatecrstwithspincount-method"></a><span data-ttu-id="03085-102">IHostSyncManager::CreateCrstWithSpinCount (Método)</span><span class="sxs-lookup"><span data-stu-id="03085-102">IHostSyncManager::CreateCrstWithSpinCount Method</span></span>
<span data-ttu-id="03085-103">Crea un objeto de sección crítica con recuento de rotación para la sincronización.</span><span class="sxs-lookup"><span data-stu-id="03085-103">Creates a critical section object with spin count for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03085-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03085-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCrstWithSpinCount (  
    [in]  DWORD dwSpinCount,  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03085-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="03085-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="03085-106">[in] Especifica el recuento circular para el objeto de sección crítica.</span><span class="sxs-lookup"><span data-stu-id="03085-106">[in] Specifies the spin count for the critical section object.</span></span>  
  
 `ppCrst`  
 <span data-ttu-id="03085-107">[out] Un puntero a la dirección de un [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) de instancia, o null si no se pudo crear la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="03085-107">[out] A pointer to the address of an [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="03085-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="03085-108">Return Value</span></span>  
  
|<span data-ttu-id="03085-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="03085-109">HRESULT</span></span>|<span data-ttu-id="03085-110">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="03085-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="03085-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="03085-111">S_OK</span></span>|<span data-ttu-id="03085-112">`CreateCrstWithSpinCount` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="03085-112">`CreateCrstWithSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="03085-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="03085-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="03085-114">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="03085-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="03085-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="03085-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="03085-116">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="03085-116">The call timed out.</span></span>|  
|<span data-ttu-id="03085-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="03085-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="03085-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="03085-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="03085-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="03085-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="03085-120">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="03085-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="03085-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="03085-121">E_FAIL</span></span>|<span data-ttu-id="03085-122">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="03085-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="03085-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="03085-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="03085-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="03085-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="03085-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="03085-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="03085-126">No había suficiente memoria disponible para crear la sección crítica solicitada.</span><span class="sxs-lookup"><span data-stu-id="03085-126">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03085-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="03085-127">Remarks</span></span>  
 <span data-ttu-id="03085-128">Un recuento de rotación se usa solo en un sistema multiprocesador.</span><span class="sxs-lookup"><span data-stu-id="03085-128">A spin count is used only on a multi-processor system.</span></span> <span data-ttu-id="03085-129">El recuento circular especifica el número de veces que un subproceso que realiza la llamada debe girar antes de realizar una operación de espera en un semáforo que está asociado a una sección crítica no está disponible.</span><span class="sxs-lookup"><span data-stu-id="03085-129">The spin count specifies the number of times a calling thread must spin before it performs a wait operation on a semaphore that is associated with an unavailable critical section.</span></span> <span data-ttu-id="03085-130">Si la sección crítica deja de estar disponible durante la operación de giro, el subproceso que realiza la llamada evita la operación de espera.</span><span class="sxs-lookup"><span data-stu-id="03085-130">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span> <span data-ttu-id="03085-131">`CreateCrstWithSpinCount` refleja el Win32 `InitializeCriticalSectionAndSpinCount` función.</span><span class="sxs-lookup"><span data-stu-id="03085-131">`CreateCrstWithSpinCount` mirrors the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03085-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="03085-132">Requirements</span></span>  
 <span data-ttu-id="03085-133">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03085-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03085-134">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="03085-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="03085-135">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="03085-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="03085-136">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03085-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03085-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="03085-137">See also</span></span>

- [<span data-ttu-id="03085-138">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="03085-138">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="03085-139">IHostSemaphore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="03085-139">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="03085-140">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="03085-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
