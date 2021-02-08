---
description: 'Más información acerca de: IHostAutoEvent:: Wait (método)'
title: IHostAutoEvent::Wait (Método)
ms.date: 03/30/2017
api_name:
- IHostAutoEvent.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent::Wait
helpviewer_keywords:
- Wait method, IHostAutoEvent interface [.NET Framework hosting]
- IHostAutoEvent::Wait method [.NET Framework hosting]
ms.assetid: 535d51c5-9112-401b-8c36-85f35d7ee609
topic_type:
- apiref
ms.openlocfilehash: 0b75b44075dda46a3d84850cebd6b8f3851b055c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789482"
---
# <a name="ihostautoeventwait-method"></a><span data-ttu-id="bce63-103">IHostAutoEvent::Wait (Método)</span><span class="sxs-lookup"><span data-stu-id="bce63-103">IHostAutoEvent::Wait Method</span></span>

<span data-ttu-id="bce63-104">Hace que la instancia de [IHostAutoEvent](ihostautoevent-interface.md) actual espere hasta que sea propiedad o transcurra un período de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="bce63-104">Causes the current [IHostAutoEvent](ihostautoevent-interface.md) instance to wait until it is owned or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bce63-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bce63-105">Syntax</span></span>  
  
```cpp  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bce63-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bce63-106">Parameters</span></span>  

 `dwMilliseconds`  
 <span data-ttu-id="bce63-107">de Número de milisegundos que `IHostAutoEvent` debe esperar la instancia actual antes de devolver, si ningún subproceso o fibra toma la propiedad.</span><span class="sxs-lookup"><span data-stu-id="bce63-107">[in] The number of milliseconds the current `IHostAutoEvent` instance should wait before returning, if no thread or fiber takes ownership.</span></span>  
  
 `option`  
 <span data-ttu-id="bce63-108">de Uno de los valores de [WAIT_OPTION](wait-option-enumeration.md) , que especifica la acción que debe realizar el host si esta operación se bloquea.</span><span class="sxs-lookup"><span data-stu-id="bce63-108">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, specifying the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bce63-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bce63-109">Return Value</span></span>  
  
|<span data-ttu-id="bce63-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bce63-110">HRESULT</span></span>|<span data-ttu-id="bce63-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="bce63-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bce63-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="bce63-112">S_OK</span></span>|<span data-ttu-id="bce63-113">`Wait` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="bce63-113">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="bce63-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bce63-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bce63-115">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="bce63-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bce63-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bce63-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bce63-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="bce63-117">The call timed out.</span></span>|  
|<span data-ttu-id="bce63-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bce63-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bce63-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="bce63-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bce63-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bce63-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bce63-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="bce63-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bce63-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bce63-122">E_FAIL</span></span>|<span data-ttu-id="bce63-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="bce63-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bce63-124">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="bce63-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bce63-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="bce63-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="bce63-126">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="bce63-126">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="bce63-127">El host detectó un interbloqueo durante el intervalo de espera y eligió el evento representado por la `IHostAutoEvent` instancia actual como sujeto del interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="bce63-127">The host detected a deadlock during the wait interval, and chose the event represented by the current `IHostAutoEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bce63-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bce63-128">Requirements</span></span>  

 <span data-ttu-id="bce63-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bce63-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bce63-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="bce63-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bce63-131">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bce63-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bce63-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bce63-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bce63-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="bce63-133">See also</span></span>

- [<span data-ttu-id="bce63-134">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bce63-134">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="bce63-135">IHostAutoEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bce63-135">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="bce63-136">IHostManualEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bce63-136">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="bce63-137">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bce63-137">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
