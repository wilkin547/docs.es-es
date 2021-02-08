---
description: 'Más información sobre: ICLROnEventManager:: Unregisteractiononevent ((método)'
title: ICLROnEventManager::UnregisterActionOnEvent (Método)
ms.date: 03/30/2017
api_name:
- ICLROnEventManager.UnregisterActionOnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager::UnregisterActionOnEvent
helpviewer_keywords:
- UnRegisterActionOnEvent method [.NET Framework hosting]
- ICLROnEventManager::UnRegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: 4c02ec37-cdf0-46b2-890e-235092741236
topic_type:
- apiref
ms.openlocfilehash: 8131c58669ff7be0fdc2b2e063c70d3b370921e8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789819"
---
# <a name="iclroneventmanagerunregisteractiononevent-method"></a><span data-ttu-id="a4a52-103">ICLROnEventManager::UnregisterActionOnEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="a4a52-103">ICLROnEventManager::UnregisterActionOnEvent Method</span></span>

<span data-ttu-id="a4a52-104">Anula el registro de un puntero de devolución de llamada registrado previamente para el evento especificado.</span><span class="sxs-lookup"><span data-stu-id="a4a52-104">Unregisters a previously registered callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4a52-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a4a52-105">Syntax</span></span>  
  
```cpp  
HRESULT UnregisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4a52-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a4a52-106">Parameters</span></span>  

 `event`  
 <span data-ttu-id="a4a52-107">de Uno de los valores de [EClrEvent](eclrevent-enumeration.md) , que indica el evento para el que se va a anular el registro del puntero de devolución de llamada descrito por `pAction` .</span><span class="sxs-lookup"><span data-stu-id="a4a52-107">[in] One of the [EClrEvent](eclrevent-enumeration.md) values, indicating the event for which to unregister the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="a4a52-108">de Un puntero a un objeto [IActionOnCLREvent](iactiononclrevent-interface.md) que se pasó como parámetro al método [RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a4a52-108">[in] A pointer to an [IActionOnCLREvent](iactiononclrevent-interface.md) object that was passed as a parameter to the [RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a4a52-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a4a52-109">Return Value</span></span>  
  
|<span data-ttu-id="a4a52-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a4a52-110">HRESULT</span></span>|<span data-ttu-id="a4a52-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="a4a52-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a4a52-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="a4a52-112">S_OK</span></span>|<span data-ttu-id="a4a52-113">`UnregisterActionOnEvent` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a4a52-113">`UnregisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="a4a52-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a4a52-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a4a52-115">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="a4a52-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a4a52-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a4a52-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a4a52-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a4a52-117">The call timed out.</span></span>|  
|<span data-ttu-id="a4a52-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a4a52-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a4a52-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a4a52-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a4a52-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a4a52-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a4a52-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="a4a52-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a4a52-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a4a52-122">E_FAIL</span></span>|<span data-ttu-id="a4a52-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="a4a52-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a4a52-124">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a4a52-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a4a52-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a4a52-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a4a52-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a4a52-126">Requirements</span></span>  

 <span data-ttu-id="a4a52-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4a52-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4a52-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a4a52-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a4a52-129">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a4a52-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a4a52-130">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4a52-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4a52-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4a52-131">See also</span></span>

- [<span data-ttu-id="a4a52-132">EClrEvent (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="a4a52-132">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="a4a52-133">IActionOnCLREvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a4a52-133">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="a4a52-134">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a4a52-134">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="a4a52-135">ICLROnEventManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a4a52-135">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
