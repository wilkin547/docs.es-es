---
description: 'Más información sobre: IHostCrst:: Setspincount ((método)'
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
ms.openlocfilehash: f04281d2649f210e64fc4c0585eb7d52be3e8ec5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721234"
---
# <a name="ihostcrstsetspincount-method"></a><span data-ttu-id="73766-103">IHostCrst::SetSpinCount (Método)</span><span class="sxs-lookup"><span data-stu-id="73766-103">IHostCrst::SetSpinCount Method</span></span>

<span data-ttu-id="73766-104">Establece el número de giros de la instancia de [IHostCrst](ihostcrst-interface.md) actual.</span><span class="sxs-lookup"><span data-stu-id="73766-104">Sets the spin count for the current [IHostCrst](ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73766-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73766-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73766-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="73766-106">Parameters</span></span>  

 `dwSpinCount`  
 <span data-ttu-id="73766-107">de Nuevo número de giros de la `IHostCrst` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="73766-107">[in] The new spin count for the current `IHostCrst` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="73766-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="73766-108">Return Value</span></span>  
  
|<span data-ttu-id="73766-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="73766-109">HRESULT</span></span>|<span data-ttu-id="73766-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="73766-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="73766-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="73766-111">S_OK</span></span>|<span data-ttu-id="73766-112">`SetSpinCount` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="73766-112">`SetSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="73766-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="73766-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="73766-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="73766-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="73766-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="73766-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="73766-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="73766-116">The call timed out.</span></span>|  
|<span data-ttu-id="73766-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="73766-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="73766-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="73766-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="73766-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="73766-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="73766-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="73766-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="73766-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="73766-121">E_FAIL</span></span>|<span data-ttu-id="73766-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="73766-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="73766-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="73766-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="73766-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="73766-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73766-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="73766-125">Remarks</span></span>  

 <span data-ttu-id="73766-126">En sistemas de varios procesadores, si la sección crítica representada por la `IHostCrst` instancia actual no está disponible, un subproceso de llamada gira los `dwSpinCount` tiempos antes de llamar a [IHostSemaphore:: wait](ihostsemaphore-wait-method.md) en un semáforo asociado a la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="73766-126">On multi-processor systems, if the critical section represented by the current `IHostCrst` instance is unavailable, a calling thread spins `dwSpinCount` times before calling [IHostSemaphore::Wait](ihostsemaphore-wait-method.md) on a semaphore associated with the critical section.</span></span> <span data-ttu-id="73766-127">Si la sección crítica se vuelve gratuita durante la operación de giro, el subproceso que realiza la llamada evita la operación de espera.</span><span class="sxs-lookup"><span data-stu-id="73766-127">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span>  
  
 <span data-ttu-id="73766-128">El uso de `dwSpinCount` es idéntico al uso del parámetro con el mismo nombre en la función de Win32 `InitializeCriticalSectionAndSpinCount` .</span><span class="sxs-lookup"><span data-stu-id="73766-128">The usage of `dwSpinCount` is identical to the usage of the parameter of the same name in the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73766-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="73766-129">Requirements</span></span>  

 <span data-ttu-id="73766-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73766-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73766-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="73766-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="73766-132">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="73766-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="73766-133">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73766-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73766-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="73766-134">See also</span></span>

- [<span data-ttu-id="73766-135">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="73766-135">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="73766-136">IHostCrst (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="73766-136">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="73766-137">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="73766-137">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
