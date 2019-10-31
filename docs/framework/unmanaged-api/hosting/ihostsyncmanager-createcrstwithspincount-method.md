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
ms.openlocfilehash: 632b8d43ed459d489825dc796d39864e2ed15ec3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139414"
---
# <a name="ihostsyncmanagercreatecrstwithspincount-method"></a><span data-ttu-id="5d40d-102">IHostSyncManager::CreateCrstWithSpinCount (Método)</span><span class="sxs-lookup"><span data-stu-id="5d40d-102">IHostSyncManager::CreateCrstWithSpinCount Method</span></span>
<span data-ttu-id="5d40d-103">Crea un objeto de sección crítica con el recuento de giros para la sincronización.</span><span class="sxs-lookup"><span data-stu-id="5d40d-103">Creates a critical section object with spin count for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d40d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d40d-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCrstWithSpinCount (  
    [in]  DWORD dwSpinCount,  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d40d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5d40d-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="5d40d-106">de Especifica el recuento de giros para el objeto de sección crítica.</span><span class="sxs-lookup"><span data-stu-id="5d40d-106">[in] Specifies the spin count for the critical section object.</span></span>  
  
 `ppCrst`  
 <span data-ttu-id="5d40d-107">enuncia Un puntero a la dirección de una instancia de [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) o null si no se pudo crear la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="5d40d-107">[out] A pointer to the address of an [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d40d-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5d40d-108">Return Value</span></span>  
  
|<span data-ttu-id="5d40d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5d40d-109">HRESULT</span></span>|<span data-ttu-id="5d40d-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d40d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5d40d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5d40d-111">S_OK</span></span>|<span data-ttu-id="5d40d-112">`CreateCrstWithSpinCount` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="5d40d-112">`CreateCrstWithSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="5d40d-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5d40d-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5d40d-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="5d40d-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5d40d-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5d40d-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5d40d-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5d40d-116">The call timed out.</span></span>|  
|<span data-ttu-id="5d40d-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5d40d-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5d40d-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="5d40d-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5d40d-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5d40d-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5d40d-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="5d40d-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5d40d-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5d40d-121">E_FAIL</span></span>|<span data-ttu-id="5d40d-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="5d40d-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5d40d-123">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="5d40d-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5d40d-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5d40d-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5d40d-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="5d40d-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="5d40d-126">No había suficiente memoria disponible para crear la sección crítica solicitada.</span><span class="sxs-lookup"><span data-stu-id="5d40d-126">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d40d-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5d40d-127">Remarks</span></span>  
 <span data-ttu-id="5d40d-128">Un recuento de giros solo se utiliza en un sistema de varios procesadores.</span><span class="sxs-lookup"><span data-stu-id="5d40d-128">A spin count is used only on a multi-processor system.</span></span> <span data-ttu-id="5d40d-129">El recuento de giros especifica el número de veces que un subproceso de llamada debe girar antes de realizar una operación de espera en un semáforo que está asociado a una sección crítica no disponible.</span><span class="sxs-lookup"><span data-stu-id="5d40d-129">The spin count specifies the number of times a calling thread must spin before it performs a wait operation on a semaphore that is associated with an unavailable critical section.</span></span> <span data-ttu-id="5d40d-130">Si la sección crítica se vuelve gratuita durante la operación de giro, el subproceso que realiza la llamada evita la operación de espera.</span><span class="sxs-lookup"><span data-stu-id="5d40d-130">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span> <span data-ttu-id="5d40d-131">`CreateCrstWithSpinCount` refleja la función de `InitializeCriticalSectionAndSpinCount` de Win32.</span><span class="sxs-lookup"><span data-stu-id="5d40d-131">`CreateCrstWithSpinCount` mirrors the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d40d-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5d40d-132">Requirements</span></span>  
 <span data-ttu-id="5d40d-133">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d40d-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d40d-134">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5d40d-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5d40d-135">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5d40d-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d40d-136">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d40d-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d40d-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d40d-137">See also</span></span>

- [<span data-ttu-id="5d40d-138">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5d40d-138">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="5d40d-139">IHostSemaphore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5d40d-139">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="5d40d-140">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5d40d-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
