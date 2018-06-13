---
title: MDAInfo (Estructura)
ms.date: 03/30/2017
api_name:
- MDAInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- MDAInfo
helpviewer_keywords:
- MDAInfo structure [.NET Framework hosting]
ms.assetid: fb8c14f7-d461-43d1-8b47-adb6723b9b93
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5164e85ecc97de99dcc493c2ba5efa8fc3468471
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443185"
---
# <a name="mdainfo-structure"></a><span data-ttu-id="acd31-102">MDAInfo (Estructura)</span><span class="sxs-lookup"><span data-stu-id="acd31-102">MDAInfo Structure</span></span>
<span data-ttu-id="acd31-103">Proporciona detalles sobre la `Event_MDAFired` eventos, lo que desencadena la creación de un Asistente para depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="acd31-103">Provides details about the `Event_MDAFired` event, which triggers the creation of a managed debugging assistant (MDA).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acd31-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="acd31-104">Syntax</span></span>  
  
```  
typedef struct _MDAInfo {  
    LPCWSTR  lpMDACaption;  
    LPCWSTR  lpMDAMessage  
} MDAInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="acd31-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="acd31-105">Members</span></span>  
  
|<span data-ttu-id="acd31-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="acd31-106">Member</span></span>|<span data-ttu-id="acd31-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="acd31-107">Description</span></span>|  
|------------|-----------------|  
|`lpMDACaption`|<span data-ttu-id="acd31-108">El título del MDA actual.</span><span class="sxs-lookup"><span data-stu-id="acd31-108">The title of the current MDA.</span></span> <span data-ttu-id="acd31-109">El título describe el tipo de error que ha desencadenado la `Event_MDAFired` eventos.</span><span class="sxs-lookup"><span data-stu-id="acd31-109">The title describes the kind of failure that triggered the `Event_MDAFired` event.</span></span>|  
|`lpMDAMessage`|<span data-ttu-id="acd31-110">El mensaje de salida proporcionado por el MDA actual.</span><span class="sxs-lookup"><span data-stu-id="acd31-110">The output message provided by the current MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="acd31-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="acd31-111">Remarks</span></span>  
 <span data-ttu-id="acd31-112">Asistentes para la depuración administradas (MDA) son ayudas que funcionan en conjunción con common language runtime (CLR) para realizar tareas, como la identificación de las condiciones no válidas para la depuración en el motor de ejecución en tiempo de ejecución o para volcar información adicional sobre el estado de la motor de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="acd31-112">Managed debugging assistants (MDAs) are debugging aids that work in conjunction with the common language runtime (CLR) to perform tasks such as identifying invalid conditions in the runtime execution engine or dumping additional information about the state of the engine.</span></span> <span data-ttu-id="acd31-113">MDA generan mensajes XML sobre eventos que son difíciles de interceptar.</span><span class="sxs-lookup"><span data-stu-id="acd31-113">MDAs generate XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="acd31-114">Son especialmente útiles para depurar las transiciones entre código administrado y no administrado.</span><span class="sxs-lookup"><span data-stu-id="acd31-114">They are especially useful for debugging transitions between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="acd31-115">El tiempo de ejecución realiza los pasos siguientes cuando se desencadena un evento que desencadena la creación de un MDA:</span><span class="sxs-lookup"><span data-stu-id="acd31-115">The runtime takes the following steps when an event that triggers the creation of an MDA is fired:</span></span>  
  
-   <span data-ttu-id="acd31-116">Si el host no ha registrado un [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) instancia mediante una llamada a [ICLROnEventManager:: RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) recibir una notificación de un `Event_MDAFired` eventos, el tiempo de ejecución continúa con su valor predeterminado, comportamiento no hospedado.</span><span class="sxs-lookup"><span data-stu-id="acd31-116">If the host has not registered an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) instance by calling [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) to be notified of an `Event_MDAFired` event, the runtime proceeds with its default, non-hosted behavior.</span></span>  
  
-   <span data-ttu-id="acd31-117">Si el host ha registrado un controlador para este evento, el tiempo de ejecución comprueba si hay un depurador asociado al proceso.</span><span class="sxs-lookup"><span data-stu-id="acd31-117">If the host has registered a handler for this event, the runtime checks to see whether a debugger is attached to the process.</span></span> <span data-ttu-id="acd31-118">Si es así, el tiempo de ejecución se interrumpe el depurador.</span><span class="sxs-lookup"><span data-stu-id="acd31-118">If it is, the runtime breaks into the debugger.</span></span> <span data-ttu-id="acd31-119">Cuando el depurador continúa, llama al host.</span><span class="sxs-lookup"><span data-stu-id="acd31-119">When the debugger continues, it calls into the host.</span></span> <span data-ttu-id="acd31-120">Si se ha asociado ningún depurador, el runtime llama a `IActionOnCLREvent::OnEvent` y pasa un puntero a un `MDAInfo` instancia como el `data` parámetro.</span><span class="sxs-lookup"><span data-stu-id="acd31-120">If no debugger is attached, the runtime calls `IActionOnCLREvent::OnEvent` and passes a pointer to an `MDAInfo` instance as the `data` parameter.</span></span>  
  
 <span data-ttu-id="acd31-121">El host puede elegir que se va a activar el MDA como recibir una notificación cuando se active un MDA.</span><span class="sxs-lookup"><span data-stu-id="acd31-121">The host can choose to activate MDAs and to be notified when an MDA is activated.</span></span> <span data-ttu-id="acd31-122">Esto impide al host una oportunidad para invalidar el comportamiento predeterminado y anular el subproceso administrado que desencadena el evento para evitar que se dañe el estado del proceso.</span><span class="sxs-lookup"><span data-stu-id="acd31-122">This gives the host an opportunity to override default behavior and to abort the managed thread that raised the event, to prevent it from corrupting the process state.</span></span> <span data-ttu-id="acd31-123">Para obtener más información acerca del uso de MDA, consulte [diagnóstico de errores con asistentes de depuraciones administradas](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="acd31-123">For more information about using MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acd31-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="acd31-124">Requirements</span></span>  
 <span data-ttu-id="acd31-125">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acd31-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acd31-126">**Encabezado:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="acd31-126">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="acd31-127">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="acd31-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="acd31-128">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acd31-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acd31-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="acd31-129">See Also</span></span>  
 [<span data-ttu-id="acd31-130">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="acd31-130">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [<span data-ttu-id="acd31-131">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="acd31-131">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
