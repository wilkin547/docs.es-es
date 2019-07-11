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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 00ad48dfe57d388653a9151393dd7b91a28a9615
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770028"
---
# <a name="iclroneventmanagerunregisteractiononevent-method"></a><span data-ttu-id="5426f-102">ICLROnEventManager::UnregisterActionOnEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="5426f-102">ICLROnEventManager::UnregisterActionOnEvent Method</span></span>
<span data-ttu-id="5426f-103">Anula el registro de un puntero de devolución de llamada registrada anteriormente para el evento especificado.</span><span class="sxs-lookup"><span data-stu-id="5426f-103">Unregisters a previously registered callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5426f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5426f-104">Syntax</span></span>  
  
```cpp  
HRESULT UnregisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5426f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5426f-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="5426f-106">[in] Uno de los [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) valores, que indica el evento para el que se va a anular el puntero de devolución de llamada descrito por `pAction`.</span><span class="sxs-lookup"><span data-stu-id="5426f-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, indicating the event for which to unregister the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="5426f-107">[in] Un puntero a un [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) objeto que se pasó como un parámetro a la [RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="5426f-107">[in] A pointer to an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) object that was passed as a parameter to the [RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5426f-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5426f-108">Return Value</span></span>  
  
|<span data-ttu-id="5426f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5426f-109">HRESULT</span></span>|<span data-ttu-id="5426f-110">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5426f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5426f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5426f-111">S_OK</span></span>|<span data-ttu-id="5426f-112">`UnregisterActionOnEvent` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="5426f-112">`UnregisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="5426f-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5426f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5426f-114">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="5426f-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5426f-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5426f-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5426f-116">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="5426f-116">The call timed out.</span></span>|  
|<span data-ttu-id="5426f-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5426f-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5426f-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="5426f-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5426f-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5426f-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5426f-120">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="5426f-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5426f-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5426f-121">E_FAIL</span></span>|<span data-ttu-id="5426f-122">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="5426f-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5426f-123">Después de un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="5426f-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5426f-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5426f-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5426f-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5426f-125">Requirements</span></span>  
 <span data-ttu-id="5426f-126">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5426f-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5426f-127">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5426f-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5426f-128">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5426f-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5426f-129">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5426f-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5426f-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="5426f-130">See also</span></span>

- [<span data-ttu-id="5426f-131">EClrEvent (enumeración)</span><span class="sxs-lookup"><span data-stu-id="5426f-131">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="5426f-132">IActionOnCLREvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5426f-132">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="5426f-133">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5426f-133">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="5426f-134">ICLROnEventManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5426f-134">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
