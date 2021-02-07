---
description: 'Más información sobre: IHostSemaphore:: Wait (método)'
title: IHostSemaphore::Wait (Método)
ms.date: 03/30/2017
api_name:
- IHostSemaphore.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore::Wait
helpviewer_keywords:
- IHostSemaphore::Wait method [.NET Framework hosting]
- Wait method, IHostSemaphore interface [.NET Framework hosting]
ms.assetid: 0da962a3-ce55-44dd-ab7a-14ad7105af4a
topic_type:
- apiref
ms.openlocfilehash: 386f9806d6457f30d13e18e7d0d1ab16aafb84ee
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728449"
---
# <a name="ihostsemaphorewait-method"></a><span data-ttu-id="9832b-103">IHostSemaphore::Wait (Método)</span><span class="sxs-lookup"><span data-stu-id="9832b-103">IHostSemaphore::Wait Method</span></span>

<span data-ttu-id="9832b-104">Hace que la instancia actual de [IHostSemaphore](ihostsemaphore-interface.md) espere hasta que sea propiedad o transcurra el período de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="9832b-104">Causes the current [IHostSemaphore](ihostsemaphore-interface.md) instance to wait until it is owned or the specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9832b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9832b-105">Syntax</span></span>  
  
```cpp  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9832b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9832b-106">Parameters</span></span>  

 `dwMilliseconds`  
 <span data-ttu-id="9832b-107">de Número de milisegundos que se va a esperar antes de devolver, si la `IHostSemaphore` instancia actual no es propiedad.</span><span class="sxs-lookup"><span data-stu-id="9832b-107">[in] The number of milliseconds to wait before returning, if the current `IHostSemaphore` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="9832b-108">de Uno de los valores de [WAIT_OPTION](wait-option-enumeration.md) , que especifica qué acción debe realizar el host si esta operación se bloquea.</span><span class="sxs-lookup"><span data-stu-id="9832b-108">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, specifying what action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9832b-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9832b-109">Return Value</span></span>  
  
|<span data-ttu-id="9832b-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9832b-110">HRESULT</span></span>|<span data-ttu-id="9832b-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="9832b-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9832b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="9832b-112">S_OK</span></span>|<span data-ttu-id="9832b-113">`Wait` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="9832b-113">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="9832b-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9832b-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9832b-115">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="9832b-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9832b-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9832b-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9832b-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9832b-117">The call timed out.</span></span>|  
|<span data-ttu-id="9832b-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9832b-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9832b-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="9832b-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9832b-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9832b-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9832b-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="9832b-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9832b-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9832b-122">E_FAIL</span></span>|<span data-ttu-id="9832b-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="9832b-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9832b-124">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="9832b-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9832b-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9832b-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9832b-126">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="9832b-126">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="9832b-127">El host detectó un interbloqueo durante el intervalo de espera y eligió la `IHostSemaphore` instancia actual como sujeto del interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="9832b-127">The host detected a deadlock during the wait interval, and chose the current `IHostSemaphore` instance as a deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9832b-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9832b-128">Requirements</span></span>  

 <span data-ttu-id="9832b-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9832b-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9832b-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9832b-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9832b-131">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9832b-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9832b-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9832b-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9832b-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="9832b-133">See also</span></span>

- [<span data-ttu-id="9832b-134">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9832b-134">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="9832b-135">IHostAutoEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9832b-135">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="9832b-136">IHostManualEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9832b-136">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="9832b-137">IHostSemaphore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9832b-137">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="9832b-138">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9832b-138">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
