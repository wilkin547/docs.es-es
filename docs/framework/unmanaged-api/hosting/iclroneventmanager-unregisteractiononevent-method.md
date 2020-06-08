---
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
ms.openlocfilehash: a3018d8477d5abd7d03ad8675503624d2e44e8f4
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504139"
---
# <a name="iclroneventmanagerunregisteractiononevent-method"></a><span data-ttu-id="a1fc0-102">ICLROnEventManager::UnregisterActionOnEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="a1fc0-102">ICLROnEventManager::UnregisterActionOnEvent Method</span></span>
<span data-ttu-id="a1fc0-103">Anula el registro de un puntero de devolución de llamada registrado previamente para el evento especificado.</span><span class="sxs-lookup"><span data-stu-id="a1fc0-103">Unregisters a previously registered callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1fc0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1fc0-104">Syntax</span></span>  
  
```cpp  
HRESULT UnregisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1fc0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a1fc0-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="a1fc0-106">de Uno de los valores de [EClrEvent](eclrevent-enumeration.md) , que indica el evento para el que se va a anular el registro del puntero de devolución de llamada descrito por `pAction` .</span><span class="sxs-lookup"><span data-stu-id="a1fc0-106">[in] One of the [EClrEvent](eclrevent-enumeration.md) values, indicating the event for which to unregister the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="a1fc0-107">de Un puntero a un objeto [IActionOnCLREvent](iactiononclrevent-interface.md) que se pasó como parámetro al método [RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a1fc0-107">[in] A pointer to an [IActionOnCLREvent](iactiononclrevent-interface.md) object that was passed as a parameter to the [RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1fc0-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a1fc0-108">Return Value</span></span>  
  
|<span data-ttu-id="a1fc0-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a1fc0-109">HRESULT</span></span>|<span data-ttu-id="a1fc0-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1fc0-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a1fc0-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a1fc0-111">S_OK</span></span>|<span data-ttu-id="a1fc0-112">`UnregisterActionOnEvent`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a1fc0-112">`UnregisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="a1fc0-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a1fc0-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a1fc0-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="a1fc0-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a1fc0-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a1fc0-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a1fc0-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a1fc0-116">The call timed out.</span></span>|  
|<span data-ttu-id="a1fc0-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a1fc0-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a1fc0-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a1fc0-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a1fc0-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a1fc0-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a1fc0-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="a1fc0-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a1fc0-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a1fc0-121">E_FAIL</span></span>|<span data-ttu-id="a1fc0-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="a1fc0-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a1fc0-123">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a1fc0-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a1fc0-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a1fc0-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a1fc0-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a1fc0-125">Requirements</span></span>  
 <span data-ttu-id="a1fc0-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1fc0-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1fc0-127">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a1fc0-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a1fc0-128">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a1fc0-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a1fc0-129">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1fc0-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1fc0-130">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="a1fc0-130">See also</span></span>

- [<span data-ttu-id="a1fc0-131">EClrEvent (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="a1fc0-131">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="a1fc0-132">IActionOnCLREvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a1fc0-132">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="a1fc0-133">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a1fc0-133">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="a1fc0-134">ICLROnEventManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a1fc0-134">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
