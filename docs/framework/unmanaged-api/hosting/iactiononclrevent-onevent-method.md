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
ms.openlocfilehash: 3bfcb01e30b4cb33ec9276f1d3c6ac2f3bde4b58
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721769"
---
# <a name="iactiononclreventonevent-method"></a><span data-ttu-id="0f526-102">IActionOnCLREvent::OnEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="0f526-102">IActionOnCLREvent::OnEvent Method</span></span>

<span data-ttu-id="0f526-103">Realiza devoluciones de llamada en eventos que se han registrado mediante una llamada al método [ICLROnEventManager:: RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0f526-103">Performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f526-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f526-104">Syntax</span></span>  
  
```cpp  
HRESULT OnEvent (  
    [in] EClrEvent event,  
    [in] PVOID     data  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f526-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0f526-105">Parameters</span></span>  

 `event`  
 <span data-ttu-id="0f526-106">de Uno de los valores de [EClrEvent](eclrevent-enumeration.md) , que indica el tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="0f526-106">[in] One of the [EClrEvent](eclrevent-enumeration.md) values, which indicates the type of event.</span></span>  
  
 `data`  
 <span data-ttu-id="0f526-107">de Un puntero a un objeto que contiene detalles acerca de `event` .</span><span class="sxs-lookup"><span data-stu-id="0f526-107">[in] A pointer to an object that contains details about `event`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f526-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0f526-108">Return Value</span></span>  
  
|<span data-ttu-id="0f526-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0f526-109">HRESULT</span></span>|<span data-ttu-id="0f526-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="0f526-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0f526-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0f526-111">S_OK</span></span>|<span data-ttu-id="0f526-112">`OnEvent` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="0f526-112">`OnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="0f526-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0f526-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0f526-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="0f526-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0f526-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0f526-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0f526-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0f526-116">The call timed out.</span></span>|  
|<span data-ttu-id="0f526-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0f526-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0f526-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="0f526-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0f526-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0f526-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0f526-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="0f526-120">An event was cancelled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0f526-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0f526-121">E_FAIL</span></span>|<span data-ttu-id="0f526-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="0f526-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0f526-123">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="0f526-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0f526-124">Las llamadas subsiguientes a cualquier método de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0f526-124">Subsequent calls to any hosting method return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f526-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0f526-125">Remarks</span></span>  

 <span data-ttu-id="0f526-126">El `data` parámetro es un puntero a un objeto de tipo no especificado.</span><span class="sxs-lookup"><span data-stu-id="0f526-126">The `data` parameter is a pointer to an object of unspecified type.</span></span> <span data-ttu-id="0f526-127">Si el `event` parámetro es `Event_DomainUnload` , `data` es el identificador numérico del <xref:System.AppDomain> que se ha descargado.</span><span class="sxs-lookup"><span data-stu-id="0f526-127">If the `event` parameter is `Event_DomainUnload`, `data` is the numeric identifier for the <xref:System.AppDomain> that was unloaded.</span></span> <span data-ttu-id="0f526-128">El host puede tomar las medidas adecuadas con este identificador como clave.</span><span class="sxs-lookup"><span data-stu-id="0f526-128">The host can take appropriate action using this identifier as a key.</span></span>  
  
 <span data-ttu-id="0f526-129">Si `event` es `Event_MDAFired` , `data` es un puntero a una instancia de [MDAInfo (](mdainfo-structure.md) que contiene la salida del mensaje de un asistente para la depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="0f526-129">If `event` is `Event_MDAFired`, `data` is a pointer to an [MDAInfo](mdainfo-structure.md) instance that contains the message output from a Managed Debugging Assistant (MDA).</span></span> <span data-ttu-id="0f526-130">Los MDA son una característica de CLR que ayuda a los desarrolladores a depurar mediante la generación de mensajes XML sobre eventos que, de otro modo, son difíciles de interceptar.</span><span class="sxs-lookup"><span data-stu-id="0f526-130">MDAs are a feature of the CLR that help developers with debugging, by generating XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="0f526-131">Estos mensajes pueden ser especialmente útiles para depurar las transiciones entre el código administrado y no administrado.</span><span class="sxs-lookup"><span data-stu-id="0f526-131">Such messages can be especially useful in debugging transitions between managed and unmanaged code.</span></span> <span data-ttu-id="0f526-132">Para obtener más información, vea [diagnosticar errores con asistentes para la depuración administrada](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="0f526-132">For more information, see [Diagnosing Errors with Managed Debugging Assistants](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f526-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f526-133">Requirements</span></span>  

 <span data-ttu-id="0f526-134">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f526-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f526-135">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0f526-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0f526-136">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0f526-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0f526-137">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f526-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f526-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0f526-138">See also</span></span>

- [<span data-ttu-id="0f526-139">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="0f526-139">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="0f526-140">EClrEvent (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="0f526-140">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="0f526-141">IActionOnCLREvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f526-141">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="0f526-142">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f526-142">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="0f526-143">ICLROnEventManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f526-143">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
- [<span data-ttu-id="0f526-144">MDAInfo (Estructura)</span><span class="sxs-lookup"><span data-stu-id="0f526-144">MDAInfo Structure</span></span>](mdainfo-structure.md)
