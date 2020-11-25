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
ms.openlocfilehash: 22274759f931da614a234efe0a6f6eb3aade027c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729569"
---
# <a name="ihostcrstsetspincount-method"></a><span data-ttu-id="85ff4-102">IHostCrst::SetSpinCount (Método)</span><span class="sxs-lookup"><span data-stu-id="85ff4-102">IHostCrst::SetSpinCount Method</span></span>

<span data-ttu-id="85ff4-103">Establece el número de giros de la instancia de [IHostCrst](ihostcrst-interface.md) actual.</span><span class="sxs-lookup"><span data-stu-id="85ff4-103">Sets the spin count for the current [IHostCrst](ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85ff4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85ff4-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85ff4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="85ff4-105">Parameters</span></span>  

 `dwSpinCount`  
 <span data-ttu-id="85ff4-106">de Nuevo número de giros de la `IHostCrst` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="85ff4-106">[in] The new spin count for the current `IHostCrst` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="85ff4-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="85ff4-107">Return Value</span></span>  
  
|<span data-ttu-id="85ff4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="85ff4-108">HRESULT</span></span>|<span data-ttu-id="85ff4-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="85ff4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="85ff4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="85ff4-110">S_OK</span></span>|<span data-ttu-id="85ff4-111">`SetSpinCount` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="85ff4-111">`SetSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="85ff4-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="85ff4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="85ff4-113">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="85ff4-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="85ff4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="85ff4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="85ff4-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="85ff4-115">The call timed out.</span></span>|  
|<span data-ttu-id="85ff4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="85ff4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="85ff4-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="85ff4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="85ff4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="85ff4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="85ff4-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="85ff4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="85ff4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="85ff4-120">E_FAIL</span></span>|<span data-ttu-id="85ff4-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="85ff4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="85ff4-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="85ff4-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="85ff4-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="85ff4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85ff4-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="85ff4-124">Remarks</span></span>  

 <span data-ttu-id="85ff4-125">En sistemas de varios procesadores, si la sección crítica representada por la `IHostCrst` instancia actual no está disponible, un subproceso de llamada gira los `dwSpinCount` tiempos antes de llamar a [IHostSemaphore:: wait](ihostsemaphore-wait-method.md) en un semáforo asociado a la sección crítica.</span><span class="sxs-lookup"><span data-stu-id="85ff4-125">On multi-processor systems, if the critical section represented by the current `IHostCrst` instance is unavailable, a calling thread spins `dwSpinCount` times before calling [IHostSemaphore::Wait](ihostsemaphore-wait-method.md) on a semaphore associated with the critical section.</span></span> <span data-ttu-id="85ff4-126">Si la sección crítica se vuelve gratuita durante la operación de giro, el subproceso que realiza la llamada evita la operación de espera.</span><span class="sxs-lookup"><span data-stu-id="85ff4-126">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span>  
  
 <span data-ttu-id="85ff4-127">El uso de `dwSpinCount` es idéntico al uso del parámetro con el mismo nombre en la función de Win32 `InitializeCriticalSectionAndSpinCount` .</span><span class="sxs-lookup"><span data-stu-id="85ff4-127">The usage of `dwSpinCount` is identical to the usage of the parameter of the same name in the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85ff4-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="85ff4-128">Requirements</span></span>  

 <span data-ttu-id="85ff4-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85ff4-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85ff4-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="85ff4-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="85ff4-131">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="85ff4-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="85ff4-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85ff4-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85ff4-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="85ff4-133">See also</span></span>

- [<span data-ttu-id="85ff4-134">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="85ff4-134">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="85ff4-135">IHostCrst (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="85ff4-135">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="85ff4-136">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="85ff4-136">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
