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
ms.openlocfilehash: 86bc320c28a5fbf122d234a4a1f15b674628c0b5
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803397"
---
# <a name="ihostsyncmanagercreatecrstwithspincount-method"></a><span data-ttu-id="a38ac-102">IHostSyncManager::CreateCrstWithSpinCount (Método)</span><span class="sxs-lookup"><span data-stu-id="a38ac-102">IHostSyncManager::CreateCrstWithSpinCount Method</span></span>
<span data-ttu-id="a38ac-103">Crea un objeto de sección crítica con el recuento de giros para la sincronización.</span><span class="sxs-lookup"><span data-stu-id="a38ac-103">Creates a critical section object with spin count for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a38ac-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a38ac-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCrstWithSpinCount (  
    [in]  DWORD dwSpinCount,  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a38ac-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a38ac-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="a38ac-106">de Especifica el recuento de giros para el objeto de sección crítica.</span><span class="sxs-lookup"><span data-stu-id="a38ac-106">[in] Specifies the spin count for the critical section object.</span></span>  
  
 `ppCrst`  
 <span data-ttu-id="a38ac-107">enuncia Un puntero a la dirección de una instancia de [IHostCrst](ihostcrst-interface.md) o null si no se pudo crear la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="a38ac-107">[out] A pointer to the address of an [IHostCrst](ihostcrst-interface.md) instance, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a38ac-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a38ac-108">Return Value</span></span>  
  
|<span data-ttu-id="a38ac-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a38ac-109">HRESULT</span></span>|<span data-ttu-id="a38ac-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="a38ac-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a38ac-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a38ac-111">S_OK</span></span>|<span data-ttu-id="a38ac-112">`CreateCrstWithSpinCount`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a38ac-112">`CreateCrstWithSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="a38ac-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a38ac-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a38ac-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="a38ac-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a38ac-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a38ac-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a38ac-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a38ac-116">The call timed out.</span></span>|  
|<span data-ttu-id="a38ac-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a38ac-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a38ac-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a38ac-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a38ac-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a38ac-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a38ac-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="a38ac-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a38ac-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a38ac-121">E_FAIL</span></span>|<span data-ttu-id="a38ac-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="a38ac-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a38ac-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a38ac-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a38ac-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a38ac-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a38ac-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a38ac-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="a38ac-126">No había suficiente memoria disponible para crear la sección crítica solicitada.</span><span class="sxs-lookup"><span data-stu-id="a38ac-126">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a38ac-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a38ac-127">Remarks</span></span>  
 <span data-ttu-id="a38ac-128">Un recuento de giros solo se utiliza en un sistema de varios procesadores.</span><span class="sxs-lookup"><span data-stu-id="a38ac-128">A spin count is used only on a multi-processor system.</span></span> <span data-ttu-id="a38ac-129">El recuento de giros especifica el número de veces que un subproceso de llamada debe girar antes de realizar una operación de espera en un semáforo que está asociado a una sección crítica no disponible.</span><span class="sxs-lookup"><span data-stu-id="a38ac-129">The spin count specifies the number of times a calling thread must spin before it performs a wait operation on a semaphore that is associated with an unavailable critical section.</span></span> <span data-ttu-id="a38ac-130">Si la sección crítica se vuelve gratuita durante la operación de giro, el subproceso que realiza la llamada evita la operación de espera.</span><span class="sxs-lookup"><span data-stu-id="a38ac-130">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span> <span data-ttu-id="a38ac-131">`CreateCrstWithSpinCount`refleja la función de Win32 `InitializeCriticalSectionAndSpinCount` .</span><span class="sxs-lookup"><span data-stu-id="a38ac-131">`CreateCrstWithSpinCount` mirrors the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a38ac-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a38ac-132">Requirements</span></span>  
 <span data-ttu-id="a38ac-133">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a38ac-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a38ac-134">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a38ac-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a38ac-135">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a38ac-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a38ac-136">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a38ac-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a38ac-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a38ac-137">See also</span></span>

- [<span data-ttu-id="a38ac-138">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a38ac-138">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="a38ac-139">IHostSemaphore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a38ac-139">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="a38ac-140">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a38ac-140">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
