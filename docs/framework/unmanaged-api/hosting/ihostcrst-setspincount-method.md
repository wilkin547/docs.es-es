---
title: IHostCrst::SetSpinCount (Método)
ms.date: 03/30/2017
api_name:
- IHostCrst.SetSpinCount
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::SetSpinCount
helpviewer_keywords:
- IHostCrst::SetSpinCount method [.NET Framework hosting]
- SetSpinCount method [.NET Framework hosting]
ms.assetid: 863fc8ce-9b8a-477e-8dd8-75c8544bb43a
topic_type:
- apiref
ms.openlocfilehash: 2436809f35d5c46416f48987cc92feb51d291a6a
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804883"
---
# <a name="ihostcrstsetspincount-method"></a><span data-ttu-id="2c7b6-102">IHostCrst::SetSpinCount (Método)</span><span class="sxs-lookup"><span data-stu-id="2c7b6-102">IHostCrst::SetSpinCount Method</span></span>
<span data-ttu-id="2c7b6-103">Establece el número de giros de la instancia de [IHostCrst](ihostcrst-interface.md) actual.</span><span class="sxs-lookup"><span data-stu-id="2c7b6-103">Sets the spin count for the current [IHostCrst](ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c7b6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2c7b6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c7b6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2c7b6-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="2c7b6-106">de Nuevo número de giros de la `IHostCrst` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="2c7b6-106">[in] The new spin count for the current `IHostCrst` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c7b6-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2c7b6-107">Return Value</span></span>  
  
|<span data-ttu-id="2c7b6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2c7b6-108">HRESULT</span></span>|<span data-ttu-id="2c7b6-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="2c7b6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2c7b6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2c7b6-110">S_OK</span></span>|<span data-ttu-id="2c7b6-111">`SetSpinCount`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="2c7b6-111">`SetSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="2c7b6-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2c7b6-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2c7b6-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="2c7b6-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2c7b6-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2c7b6-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2c7b6-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2c7b6-115">The call timed out.</span></span>|  
|<span data-ttu-id="2c7b6-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2c7b6-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2c7b6-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="2c7b6-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2c7b6-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2c7b6-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2c7b6-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="2c7b6-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2c7b6-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2c7b6-120">E_FAIL</span></span>|<span data-ttu-id="2c7b6-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="2c7b6-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2c7b6-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="2c7b6-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2c7b6-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2c7b6-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c7b6-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2c7b6-124">Remarks</span></span>  
 <span data-ttu-id="2c7b6-125">En sistemas de varios procesadores, si la sección crítica representada por la `IHostCrst` instancia actual no está disponible, un subproceso de llamada gira los `dwSpinCount` tiempos antes de llamar a [IHostSemaphore:: wait](ihostsemaphore-wait-method.md) en un semáforo asociado a la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="2c7b6-125">On multi-processor systems, if the critical section represented by the current `IHostCrst` instance is unavailable, a calling thread spins `dwSpinCount` times before calling [IHostSemaphore::Wait](ihostsemaphore-wait-method.md) on a semaphore associated with the critical section.</span></span> <span data-ttu-id="2c7b6-126">Si la sección crítica se vuelve gratuita durante la operación de giro, el subproceso que realiza la llamada evita la operación de espera.</span><span class="sxs-lookup"><span data-stu-id="2c7b6-126">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span>  
  
 <span data-ttu-id="2c7b6-127">El uso de `dwSpinCount` es idéntico al uso del parámetro con el mismo nombre en la función de Win32 `InitializeCriticalSectionAndSpinCount` .</span><span class="sxs-lookup"><span data-stu-id="2c7b6-127">The usage of `dwSpinCount` is identical to the usage of the parameter of the same name in the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c7b6-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2c7b6-128">Requirements</span></span>  
 <span data-ttu-id="2c7b6-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c7b6-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c7b6-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2c7b6-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2c7b6-131">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2c7b6-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2c7b6-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c7b6-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c7b6-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2c7b6-133">See also</span></span>

- [<span data-ttu-id="2c7b6-134">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2c7b6-134">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="2c7b6-135">IHostCrst (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2c7b6-135">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="2c7b6-136">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2c7b6-136">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
