---
description: 'Más información acerca de: IActionOnCLREvent:: onEvent (método)'
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
ms.openlocfilehash: 163956ab319eb34d58da23d2c4ef2a6b592aab0d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785151"
---
# <a name="iactiononclreventonevent-method"></a><span data-ttu-id="04730-103">IActionOnCLREvent::OnEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="04730-103">IActionOnCLREvent::OnEvent Method</span></span>

<span data-ttu-id="04730-104">Realiza devoluciones de llamada en eventos que se han registrado mediante una llamada al método [ICLROnEventManager:: RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="04730-104">Performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04730-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04730-105">Syntax</span></span>  
  
```cpp  
HRESULT OnEvent (  
    [in] EClrEvent event,  
    [in] PVOID     data  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04730-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="04730-106">Parameters</span></span>  

 `event`  
 <span data-ttu-id="04730-107">de Uno de los valores de [EClrEvent](eclrevent-enumeration.md) , que indica el tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="04730-107">[in] One of the [EClrEvent](eclrevent-enumeration.md) values, which indicates the type of event.</span></span>  
  
 `data`  
 <span data-ttu-id="04730-108">de Un puntero a un objeto que contiene detalles acerca de `event` .</span><span class="sxs-lookup"><span data-stu-id="04730-108">[in] A pointer to an object that contains details about `event`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="04730-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="04730-109">Return Value</span></span>  
  
|<span data-ttu-id="04730-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="04730-110">HRESULT</span></span>|<span data-ttu-id="04730-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="04730-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="04730-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="04730-112">S_OK</span></span>|<span data-ttu-id="04730-113">`OnEvent` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="04730-113">`OnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="04730-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="04730-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="04730-115">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="04730-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="04730-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="04730-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="04730-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="04730-117">The call timed out.</span></span>|  
|<span data-ttu-id="04730-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="04730-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="04730-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="04730-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="04730-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="04730-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="04730-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="04730-121">An event was cancelled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="04730-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="04730-122">E_FAIL</span></span>|<span data-ttu-id="04730-123">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="04730-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="04730-124">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="04730-124">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="04730-125">Las llamadas subsiguientes a cualquier método de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="04730-125">Subsequent calls to any hosting method return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04730-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="04730-126">Remarks</span></span>  

 <span data-ttu-id="04730-127">El `data` parámetro es un puntero a un objeto de tipo no especificado.</span><span class="sxs-lookup"><span data-stu-id="04730-127">The `data` parameter is a pointer to an object of unspecified type.</span></span> <span data-ttu-id="04730-128">Si el `event` parámetro es `Event_DomainUnload` , `data` es el identificador numérico del <xref:System.AppDomain> que se ha descargado.</span><span class="sxs-lookup"><span data-stu-id="04730-128">If the `event` parameter is `Event_DomainUnload`, `data` is the numeric identifier for the <xref:System.AppDomain> that was unloaded.</span></span> <span data-ttu-id="04730-129">El host puede tomar las medidas adecuadas con este identificador como clave.</span><span class="sxs-lookup"><span data-stu-id="04730-129">The host can take appropriate action using this identifier as a key.</span></span>  
  
 <span data-ttu-id="04730-130">Si `event` es `Event_MDAFired` , `data` es un puntero a una instancia de [MDAInfo (](mdainfo-structure.md) que contiene la salida del mensaje de un asistente para la depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="04730-130">If `event` is `Event_MDAFired`, `data` is a pointer to an [MDAInfo](mdainfo-structure.md) instance that contains the message output from a Managed Debugging Assistant (MDA).</span></span> <span data-ttu-id="04730-131">Los MDA son una característica de CLR que ayuda a los desarrolladores a depurar mediante la generación de mensajes XML sobre eventos que, de otro modo, son difíciles de interceptar.</span><span class="sxs-lookup"><span data-stu-id="04730-131">MDAs are a feature of the CLR that help developers with debugging, by generating XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="04730-132">Estos mensajes pueden ser especialmente útiles para depurar las transiciones entre el código administrado y no administrado.</span><span class="sxs-lookup"><span data-stu-id="04730-132">Such messages can be especially useful in debugging transitions between managed and unmanaged code.</span></span> <span data-ttu-id="04730-133">Para obtener más información, vea [diagnosticar errores con asistentes para la depuración administrada](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="04730-133">For more information, see [Diagnosing Errors with Managed Debugging Assistants](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04730-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="04730-134">Requirements</span></span>  

 <span data-ttu-id="04730-135">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04730-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04730-136">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="04730-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="04730-137">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="04730-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="04730-138">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04730-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04730-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="04730-139">See also</span></span>

- [<span data-ttu-id="04730-140">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="04730-140">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="04730-141">EClrEvent (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="04730-141">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="04730-142">IActionOnCLREvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="04730-142">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="04730-143">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="04730-143">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="04730-144">ICLROnEventManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="04730-144">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
- [<span data-ttu-id="04730-145">MDAInfo (Estructura)</span><span class="sxs-lookup"><span data-stu-id="04730-145">MDAInfo Structure</span></span>](mdainfo-structure.md)
