---
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
ms.openlocfilehash: f07958a1a21bb3e93e4ca8202a65407b39188af4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680786"
---
# <a name="ihostautoeventwait-method"></a><span data-ttu-id="fcf2d-102">IHostAutoEvent::Wait (Método)</span><span class="sxs-lookup"><span data-stu-id="fcf2d-102">IHostAutoEvent::Wait Method</span></span>

<span data-ttu-id="fcf2d-103">Hace que la instancia de [IHostAutoEvent](ihostautoevent-interface.md) actual espere hasta que sea propiedad o transcurra un período de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="fcf2d-103">Causes the current [IHostAutoEvent](ihostautoevent-interface.md) instance to wait until it is owned or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcf2d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fcf2d-104">Syntax</span></span>  
  
```cpp  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fcf2d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fcf2d-105">Parameters</span></span>  

 `dwMilliseconds`  
 <span data-ttu-id="fcf2d-106">de Número de milisegundos que `IHostAutoEvent` debe esperar la instancia actual antes de devolver, si ningún subproceso o fibra toma la propiedad.</span><span class="sxs-lookup"><span data-stu-id="fcf2d-106">[in] The number of milliseconds the current `IHostAutoEvent` instance should wait before returning, if no thread or fiber takes ownership.</span></span>  
  
 `option`  
 <span data-ttu-id="fcf2d-107">de Uno de los valores de [WAIT_OPTION](wait-option-enumeration.md) , que especifica la acción que debe realizar el host si esta operación se bloquea.</span><span class="sxs-lookup"><span data-stu-id="fcf2d-107">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, specifying the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fcf2d-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fcf2d-108">Return Value</span></span>  
  
|<span data-ttu-id="fcf2d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fcf2d-109">HRESULT</span></span>|<span data-ttu-id="fcf2d-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="fcf2d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fcf2d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="fcf2d-111">S_OK</span></span>|<span data-ttu-id="fcf2d-112">`Wait` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="fcf2d-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="fcf2d-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fcf2d-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fcf2d-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="fcf2d-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fcf2d-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fcf2d-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fcf2d-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="fcf2d-116">The call timed out.</span></span>|  
|<span data-ttu-id="fcf2d-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fcf2d-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fcf2d-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="fcf2d-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fcf2d-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fcf2d-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fcf2d-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="fcf2d-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fcf2d-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fcf2d-121">E_FAIL</span></span>|<span data-ttu-id="fcf2d-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="fcf2d-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fcf2d-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="fcf2d-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fcf2d-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fcf2d-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fcf2d-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="fcf2d-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="fcf2d-126">El host detectó un interbloqueo durante el intervalo de espera y eligió el evento representado por la `IHostAutoEvent` instancia actual como sujeto del interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="fcf2d-126">The host detected a deadlock during the wait interval, and chose the event represented by the current `IHostAutoEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fcf2d-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fcf2d-127">Requirements</span></span>  

 <span data-ttu-id="fcf2d-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fcf2d-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcf2d-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fcf2d-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fcf2d-130">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fcf2d-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fcf2d-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcf2d-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcf2d-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fcf2d-132">See also</span></span>

- [<span data-ttu-id="fcf2d-133">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fcf2d-133">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="fcf2d-134">IHostAutoEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fcf2d-134">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="fcf2d-135">IHostManualEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fcf2d-135">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="fcf2d-136">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fcf2d-136">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
