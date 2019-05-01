---
title: IActionOnCLREvent::OnEvent (Método)
ms.date: 03/30/2017
api_name:
- IActionOnCLREvent.OnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent::OnEvent
helpviewer_keywords:
- OnEvent method [.NET Framework hosting]
- IActionOnCLREvent::OnEvent method [.NET Framework hosting]
ms.assetid: 0970f10c-4304-4c12-91c0-83e51455afb4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e7045d3b095b6a35be8b55e1066b459e9583c93
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61970240"
---
# <a name="iactiononclreventonevent-method"></a><span data-ttu-id="cdba9-102">IActionOnCLREvent::OnEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="cdba9-102">IActionOnCLREvent::OnEvent Method</span></span>
<span data-ttu-id="cdba9-103">Realiza las devoluciones de llamada en eventos que se han registrado mediante el uso de una llamada a la [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="cdba9-103">Performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdba9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cdba9-104">Syntax</span></span>  
  
```  
HRESULT OnEvent (  
    [in] EClrEvent event,  
    [in] PVOID     data  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cdba9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cdba9-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="cdba9-106">[in] Uno de los [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) valores, que indica el tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="cdba9-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, which indicates the type of event.</span></span>  
  
 `data`  
 <span data-ttu-id="cdba9-107">[in] Un puntero a un objeto que contiene detalles sobre `event`.</span><span class="sxs-lookup"><span data-stu-id="cdba9-107">[in] A pointer to an object that contains details about `event`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cdba9-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cdba9-108">Return Value</span></span>  
  
|<span data-ttu-id="cdba9-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cdba9-109">HRESULT</span></span>|<span data-ttu-id="cdba9-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="cdba9-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cdba9-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="cdba9-111">S_OK</span></span>|<span data-ttu-id="cdba9-112">`OnEvent` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="cdba9-112">`OnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="cdba9-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cdba9-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cdba9-114">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="cdba9-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cdba9-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cdba9-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cdba9-116">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="cdba9-116">The call timed out.</span></span>|  
|<span data-ttu-id="cdba9-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cdba9-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cdba9-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="cdba9-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cdba9-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cdba9-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cdba9-120">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="cdba9-120">An event was cancelled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cdba9-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cdba9-121">E_FAIL</span></span>|<span data-ttu-id="cdba9-122">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="cdba9-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cdba9-123">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="cdba9-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cdba9-124">Las llamadas subsiguientes a cualquier método de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="cdba9-124">Subsequent calls to any hosting method return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cdba9-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cdba9-125">Remarks</span></span>  
 <span data-ttu-id="cdba9-126">El `data` parámetro es un puntero a un objeto de tipo no especificado.</span><span class="sxs-lookup"><span data-stu-id="cdba9-126">The `data` parameter is a pointer to an object of unspecified type.</span></span> <span data-ttu-id="cdba9-127">Si el `event` parámetro es `Event_DomainUnload`, `data` es el identificador numérico para el <xref:System.AppDomain> que se ha descargado.</span><span class="sxs-lookup"><span data-stu-id="cdba9-127">If the `event` parameter is `Event_DomainUnload`, `data` is the numeric identifier for the <xref:System.AppDomain> that was unloaded.</span></span> <span data-ttu-id="cdba9-128">El host pueda tomar medidas apropiadas con este identificador como una clave.</span><span class="sxs-lookup"><span data-stu-id="cdba9-128">The host can take appropriate action using this identifier as a key.</span></span>  
  
 <span data-ttu-id="cdba9-129">Si `event` es `Event_MDAFired`, `data` es un puntero a un [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) instancia que contiene los mensajes de salida de un Asistente para la depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="cdba9-129">If `event` is `Event_MDAFired`, `data` is a pointer to an [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) instance that contains the message output from a Managed Debugging Assistant (MDA).</span></span> <span data-ttu-id="cdba9-130">MDA son una característica de CLR que ayudan a los desarrolladores con la depuración, generando mensajes XML sobre eventos que son difíciles de interceptar.</span><span class="sxs-lookup"><span data-stu-id="cdba9-130">MDAs are a feature of the CLR that help developers with debugging, by generating XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="cdba9-131">Estos mensajes pueden ser especialmente útiles para depurar las transiciones entre código administrado y.</span><span class="sxs-lookup"><span data-stu-id="cdba9-131">Such messages can be especially useful in debugging transitions between managed and unmanaged code.</span></span> <span data-ttu-id="cdba9-132">Para obtener más información, consulte [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="cdba9-132">For more information, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdba9-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cdba9-133">Requirements</span></span>  
 <span data-ttu-id="cdba9-134">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cdba9-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdba9-135">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cdba9-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cdba9-136">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cdba9-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cdba9-137">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdba9-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdba9-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="cdba9-138">See also</span></span>

- [<span data-ttu-id="cdba9-139">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="cdba9-139">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="cdba9-140">EClrEvent (enumeración)</span><span class="sxs-lookup"><span data-stu-id="cdba9-140">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="cdba9-141">IActionOnCLREvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cdba9-141">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="cdba9-142">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cdba9-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="cdba9-143">ICLROnEventManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cdba9-143">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
- [<span data-ttu-id="cdba9-144">MDAInfo (estructura)</span><span class="sxs-lookup"><span data-stu-id="cdba9-144">MDAInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)
