---
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
ms.openlocfilehash: 7f0770585e977f5299a40517c28dfb776b2ab898
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725617"
---
# <a name="iclroneventmanagerregisteractiononevent-method"></a><span data-ttu-id="9218d-102">ICLROnEventManager::RegisterActionOnEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="9218d-102">ICLROnEventManager::RegisterActionOnEvent Method</span></span>

<span data-ttu-id="9218d-103">Registra un puntero de devolución de llamada para el evento especificado.</span><span class="sxs-lookup"><span data-stu-id="9218d-103">Registers a callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9218d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9218d-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9218d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9218d-105">Parameters</span></span>  

 `event`  
 <span data-ttu-id="9218d-106">de Uno de los valores de [EClrEvent](eclrevent-enumeration.md) , que indica el evento para el que se va a registrar el puntero de devolución de llamada descrito por `pAction` .</span><span class="sxs-lookup"><span data-stu-id="9218d-106">[in] One of the [EClrEvent](eclrevent-enumeration.md) values, indicating the event for which to register the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="9218d-107">de Un puntero a un objeto [IActionOnCLREvent](iactiononclrevent-interface.md) al que se llama cuando se activa el evento registrado.</span><span class="sxs-lookup"><span data-stu-id="9218d-107">[in] A pointer to an [IActionOnCLREvent](iactiononclrevent-interface.md) object that is called when the registered event fires.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9218d-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9218d-108">Return Value</span></span>  
  
|<span data-ttu-id="9218d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9218d-109">HRESULT</span></span>|<span data-ttu-id="9218d-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="9218d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9218d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9218d-111">S_OK</span></span>|<span data-ttu-id="9218d-112">`RegisterActionOnEvent` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="9218d-112">`RegisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="9218d-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9218d-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9218d-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="9218d-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9218d-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9218d-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9218d-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9218d-116">The call timed out.</span></span>|  
|<span data-ttu-id="9218d-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9218d-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9218d-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="9218d-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9218d-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9218d-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9218d-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="9218d-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9218d-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9218d-121">E_FAIL</span></span>|<span data-ttu-id="9218d-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="9218d-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9218d-123">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="9218d-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9218d-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9218d-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9218d-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9218d-125">Remarks</span></span>  

 <span data-ttu-id="9218d-126">El host puede registrar devoluciones de llamada para uno de los dos tipos de eventos descritos por o ambos `EClrEvent` .</span><span class="sxs-lookup"><span data-stu-id="9218d-126">The host can register callbacks for either or both of the two event types described by `EClrEvent`.</span></span> <span data-ttu-id="9218d-127">El host obtiene la `ICLROnEventManager` interfaz llamando al método [ICLRControl:: GetCLRManager (](iclrcontrol-getclrmanager-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9218d-127">The host gets the `ICLROnEventManager` interface by calling the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9218d-128">Los eventos que `RegisterActionOnEvent` se registran se pueden desencadenar más de una vez y desde distintos subprocesos para indicar una descarga o la deshabilitación de CLR.</span><span class="sxs-lookup"><span data-stu-id="9218d-128">The events that `RegisterActionOnEvent` registers can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9218d-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9218d-129">Requirements</span></span>  

 <span data-ttu-id="9218d-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9218d-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9218d-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9218d-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9218d-132">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9218d-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9218d-133">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9218d-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9218d-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9218d-134">See also</span></span>

- [<span data-ttu-id="9218d-135">EClrEvent (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="9218d-135">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="9218d-136">IActionOnCLREvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9218d-136">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="9218d-137">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9218d-137">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="9218d-138">ICLROnEventManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9218d-138">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
