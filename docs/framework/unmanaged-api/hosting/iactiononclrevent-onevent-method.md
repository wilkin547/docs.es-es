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
ms.openlocfilehash: 28178cca27c257e480a7c5ec87c1925af7de4f78
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436421"
---
# <a name="iactiononclreventonevent-method"></a><span data-ttu-id="72777-102">IActionOnCLREvent::OnEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="72777-102">IActionOnCLREvent::OnEvent Method</span></span>
<span data-ttu-id="72777-103">Realiza las devoluciones de llamada en eventos que se han registrado mediante una llamada a la [ICLROnEventManager:: RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="72777-103">Performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72777-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="72777-104">Syntax</span></span>  
  
```  
HRESULT OnEvent (  
    [in] EClrEvent event,  
    [in] PVOID     data  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="72777-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="72777-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="72777-106">[in] Uno de los [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) valores, lo que indica el tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="72777-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, which indicates the type of event.</span></span>  
  
 `data`  
 <span data-ttu-id="72777-107">[in] Un puntero a un objeto que contiene detalles sobre `event`.</span><span class="sxs-lookup"><span data-stu-id="72777-107">[in] A pointer to an object that contains details about `event`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72777-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="72777-108">Return Value</span></span>  
  
|<span data-ttu-id="72777-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="72777-109">HRESULT</span></span>|<span data-ttu-id="72777-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="72777-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="72777-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="72777-111">S_OK</span></span>|<span data-ttu-id="72777-112">`OnEvent` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="72777-112">`OnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="72777-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="72777-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="72777-114">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="72777-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="72777-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="72777-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="72777-116">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="72777-116">The call timed out.</span></span>|  
|<span data-ttu-id="72777-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="72777-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="72777-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="72777-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="72777-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="72777-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="72777-120">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="72777-120">An event was cancelled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="72777-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="72777-121">E_FAIL</span></span>|<span data-ttu-id="72777-122">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="72777-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="72777-123">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="72777-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="72777-124">Las llamadas subsiguientes a cualquier método de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="72777-124">Subsequent calls to any hosting method return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72777-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="72777-125">Remarks</span></span>  
 <span data-ttu-id="72777-126">El `data` parámetro es un puntero a un objeto de tipo no especificado.</span><span class="sxs-lookup"><span data-stu-id="72777-126">The `data` parameter is a pointer to an object of unspecified type.</span></span> <span data-ttu-id="72777-127">Si el `event` parámetro es `Event_DomainUnload`, `data` es el identificador numérico para el <xref:System.AppDomain> que se ha descargado.</span><span class="sxs-lookup"><span data-stu-id="72777-127">If the `event` parameter is `Event_DomainUnload`, `data` is the numeric identifier for the <xref:System.AppDomain> that was unloaded.</span></span> <span data-ttu-id="72777-128">El host puede realizar las acciones apropiadas utilizando este identificador como una clave.</span><span class="sxs-lookup"><span data-stu-id="72777-128">The host can take appropriate action using this identifier as a key.</span></span>  
  
 <span data-ttu-id="72777-129">Si `event` es `Event_MDAFired`, `data` es un puntero a un [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) instancia que contiene los mensajes de salida de un Asistente para la depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="72777-129">If `event` is `Event_MDAFired`, `data` is a pointer to an [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) instance that contains the message output from a Managed Debugging Assistant (MDA).</span></span> <span data-ttu-id="72777-130">MDA son una característica de CLR que ayuda a los desarrolladores con la depuración, generando mensajes XML sobre eventos que de lo contrario son difíciles de interceptar.</span><span class="sxs-lookup"><span data-stu-id="72777-130">MDAs are a feature of the CLR that help developers with debugging, by generating XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="72777-131">Estos mensajes pueden ser especialmente útiles para depurar las transiciones entre código administrado y no administrado.</span><span class="sxs-lookup"><span data-stu-id="72777-131">Such messages can be especially useful in debugging transitions between managed and unmanaged code.</span></span> <span data-ttu-id="72777-132">Para obtener más información, consulte [diagnóstico de errores con asistentes de depuraciones administradas](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="72777-132">For more information, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72777-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="72777-133">Requirements</span></span>  
 <span data-ttu-id="72777-134">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72777-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72777-135">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="72777-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="72777-136">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="72777-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="72777-137">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72777-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72777-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="72777-138">See Also</span></span>  
 [<span data-ttu-id="72777-139">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="72777-139">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="72777-140">EClrEvent (enumeración)</span><span class="sxs-lookup"><span data-stu-id="72777-140">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [<span data-ttu-id="72777-141">IActionOnCLREvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="72777-141">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [<span data-ttu-id="72777-142">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="72777-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="72777-143">ICLROnEventManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="72777-143">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 [<span data-ttu-id="72777-144">MDAInfo (estructura)</span><span class="sxs-lookup"><span data-stu-id="72777-144">MDAInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)
