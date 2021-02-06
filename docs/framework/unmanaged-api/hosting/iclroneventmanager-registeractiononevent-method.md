---
description: 'Más información acerca de: ICLROnEventManager:: RegisterActionOnEvent (método)'
title: ICLROnEventManager::RegisterActionOnEvent (Método)
ms.date: 03/30/2017
api_name:
- ICLROnEventManager.RegisterActionOnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager::RegisterActionOnEvent
helpviewer_keywords:
- ICLROnEventManager::RegisterActionOnEvent method [.NET Framework hosting]
- RegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: b944cf49-918d-4c4e-993b-77d097a52550
topic_type:
- apiref
ms.openlocfilehash: b13209aed6a169185b42c6b9520f21f59f6be3bb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637435"
---
# <a name="iclroneventmanagerregisteractiononevent-method"></a><span data-ttu-id="3818a-103">ICLROnEventManager::RegisterActionOnEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="3818a-103">ICLROnEventManager::RegisterActionOnEvent Method</span></span>

<span data-ttu-id="3818a-104">Registra un puntero de devolución de llamada para el evento especificado.</span><span class="sxs-lookup"><span data-stu-id="3818a-104">Registers a callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3818a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3818a-105">Syntax</span></span>  
  
```cpp  
HRESULT RegisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3818a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3818a-106">Parameters</span></span>  

 `event`  
 <span data-ttu-id="3818a-107">de Uno de los valores de [EClrEvent](eclrevent-enumeration.md) , que indica el evento para el que se va a registrar el puntero de devolución de llamada descrito por `pAction` .</span><span class="sxs-lookup"><span data-stu-id="3818a-107">[in] One of the [EClrEvent](eclrevent-enumeration.md) values, indicating the event for which to register the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="3818a-108">de Un puntero a un objeto [IActionOnCLREvent](iactiononclrevent-interface.md) al que se llama cuando se activa el evento registrado.</span><span class="sxs-lookup"><span data-stu-id="3818a-108">[in] A pointer to an [IActionOnCLREvent](iactiononclrevent-interface.md) object that is called when the registered event fires.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3818a-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3818a-109">Return Value</span></span>  
  
|<span data-ttu-id="3818a-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3818a-110">HRESULT</span></span>|<span data-ttu-id="3818a-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="3818a-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3818a-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="3818a-112">S_OK</span></span>|<span data-ttu-id="3818a-113">`RegisterActionOnEvent` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3818a-113">`RegisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="3818a-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3818a-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3818a-115">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="3818a-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3818a-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3818a-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3818a-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3818a-117">The call timed out.</span></span>|  
|<span data-ttu-id="3818a-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3818a-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3818a-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="3818a-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3818a-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3818a-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3818a-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="3818a-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3818a-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3818a-122">E_FAIL</span></span>|<span data-ttu-id="3818a-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="3818a-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3818a-124">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="3818a-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3818a-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3818a-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3818a-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3818a-126">Remarks</span></span>  

 <span data-ttu-id="3818a-127">El host puede registrar devoluciones de llamada para uno de los dos tipos de eventos descritos por o ambos `EClrEvent` .</span><span class="sxs-lookup"><span data-stu-id="3818a-127">The host can register callbacks for either or both of the two event types described by `EClrEvent`.</span></span> <span data-ttu-id="3818a-128">El host obtiene la `ICLROnEventManager` interfaz llamando al método [ICLRControl:: GetCLRManager (](iclrcontrol-getclrmanager-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3818a-128">The host gets the `ICLROnEventManager` interface by calling the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3818a-129">Los eventos que `RegisterActionOnEvent` se registran se pueden desencadenar más de una vez y desde distintos subprocesos para indicar una descarga o la deshabilitación de CLR.</span><span class="sxs-lookup"><span data-stu-id="3818a-129">The events that `RegisterActionOnEvent` registers can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3818a-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3818a-130">Requirements</span></span>  

 <span data-ttu-id="3818a-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3818a-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3818a-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3818a-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3818a-133">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3818a-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3818a-134">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3818a-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3818a-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="3818a-135">See also</span></span>

- [<span data-ttu-id="3818a-136">EClrEvent (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="3818a-136">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="3818a-137">IActionOnCLREvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3818a-137">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="3818a-138">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3818a-138">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="3818a-139">ICLROnEventManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3818a-139">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
