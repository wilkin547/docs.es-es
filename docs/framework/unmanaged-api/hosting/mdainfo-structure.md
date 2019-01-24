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
ms.openlocfilehash: 2d48c3d701b0369ab00150625c26d94f4111b2d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607217"
---
# <a name="mdainfo-structure"></a><span data-ttu-id="86e78-102">MDAInfo (Estructura)</span><span class="sxs-lookup"><span data-stu-id="86e78-102">MDAInfo Structure</span></span>
<span data-ttu-id="86e78-103">Proporciona detalles sobre el `Event_MDAFired` evento que desencadena la creación de un Asistente para depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="86e78-103">Provides details about the `Event_MDAFired` event, which triggers the creation of a managed debugging assistant (MDA).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86e78-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="86e78-104">Syntax</span></span>  
  
```  
typedef struct _MDAInfo {  
    LPCWSTR  lpMDACaption;  
    LPCWSTR  lpMDAMessage  
} MDAInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="86e78-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="86e78-105">Members</span></span>  
  
|<span data-ttu-id="86e78-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="86e78-106">Member</span></span>|<span data-ttu-id="86e78-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="86e78-107">Description</span></span>|  
|------------|-----------------|  
|`lpMDACaption`|<span data-ttu-id="86e78-108">El título del MDA actual.</span><span class="sxs-lookup"><span data-stu-id="86e78-108">The title of the current MDA.</span></span> <span data-ttu-id="86e78-109">El título describe el tipo de error que ha desencadenado la `Event_MDAFired` eventos.</span><span class="sxs-lookup"><span data-stu-id="86e78-109">The title describes the kind of failure that triggered the `Event_MDAFired` event.</span></span>|  
|`lpMDAMessage`|<span data-ttu-id="86e78-110">El mensaje de salida proporcionado por el MDA actual.</span><span class="sxs-lookup"><span data-stu-id="86e78-110">The output message provided by the current MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86e78-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="86e78-111">Remarks</span></span>  
 <span data-ttu-id="86e78-112">Asistentes para la depuración administradas (MDA) son ayudas que funcionan en conjunción con common language runtime (CLR) para realizar tareas como la identificación de las condiciones no válidas para la depuración en el motor de ejecución o el volcado de información adicional sobre el estado de la motor.</span><span class="sxs-lookup"><span data-stu-id="86e78-112">Managed debugging assistants (MDAs) are debugging aids that work in conjunction with the common language runtime (CLR) to perform tasks such as identifying invalid conditions in the runtime execution engine or dumping additional information about the state of the engine.</span></span> <span data-ttu-id="86e78-113">MDA generan mensajes XML sobre eventos que son difíciles de interceptar.</span><span class="sxs-lookup"><span data-stu-id="86e78-113">MDAs generate XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="86e78-114">Son especialmente útiles para depurar las transiciones entre código administrado y no administrado.</span><span class="sxs-lookup"><span data-stu-id="86e78-114">They are especially useful for debugging transitions between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="86e78-115">El tiempo de ejecución realiza los pasos siguientes cuando se desencadena un evento que desencadena la creación de un MDA:</span><span class="sxs-lookup"><span data-stu-id="86e78-115">The runtime takes the following steps when an event that triggers the creation of an MDA is fired:</span></span>  
  
-   <span data-ttu-id="86e78-116">Si el host no ha registrado un [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) instancia mediante una llamada a [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) para recibir una notificación de un `Event_MDAFired` eventos, el tiempo de ejecución continúa con su predeterminada, el comportamiento no hospedado.</span><span class="sxs-lookup"><span data-stu-id="86e78-116">If the host has not registered an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) instance by calling [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) to be notified of an `Event_MDAFired` event, the runtime proceeds with its default, non-hosted behavior.</span></span>  
  
-   <span data-ttu-id="86e78-117">Si el host ha registrado un controlador para este evento, el tiempo de ejecución comprueba si se adjunta un depurador al proceso.</span><span class="sxs-lookup"><span data-stu-id="86e78-117">If the host has registered a handler for this event, the runtime checks to see whether a debugger is attached to the process.</span></span> <span data-ttu-id="86e78-118">Si es así, el tiempo de ejecución se interrumpe el depurador.</span><span class="sxs-lookup"><span data-stu-id="86e78-118">If it is, the runtime breaks into the debugger.</span></span> <span data-ttu-id="86e78-119">Cuando el depurador continúa, llama al host.</span><span class="sxs-lookup"><span data-stu-id="86e78-119">When the debugger continues, it calls into the host.</span></span> <span data-ttu-id="86e78-120">Si no hay ningún depurador está conectado, el runtime llama a `IActionOnCLREvent::OnEvent` y pasa un puntero a un `MDAInfo` la instancia como el `data` parámetro.</span><span class="sxs-lookup"><span data-stu-id="86e78-120">If no debugger is attached, the runtime calls `IActionOnCLREvent::OnEvent` and passes a pointer to an `MDAInfo` instance as the `data` parameter.</span></span>  
  
 <span data-ttu-id="86e78-121">El host puede elegir para activar el MDA y recibir una notificación cuando se activa un MDA.</span><span class="sxs-lookup"><span data-stu-id="86e78-121">The host can choose to activate MDAs and to be notified when an MDA is activated.</span></span> <span data-ttu-id="86e78-122">Esto proporciona al host una oportunidad para invalidar el comportamiento predeterminado y anular el subproceso administrado que provocó el evento, para impedir que se dañe el estado del proceso.</span><span class="sxs-lookup"><span data-stu-id="86e78-122">This gives the host an opportunity to override default behavior and to abort the managed thread that raised the event, to prevent it from corrupting the process state.</span></span> <span data-ttu-id="86e78-123">Para obtener más información sobre el uso de los MDA, consulte [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="86e78-123">For more information about using MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86e78-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="86e78-124">Requirements</span></span>  
 <span data-ttu-id="86e78-125">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86e78-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86e78-126">**Encabezado**: MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="86e78-126">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="86e78-127">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="86e78-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="86e78-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86e78-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86e78-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="86e78-129">See also</span></span>
- [<span data-ttu-id="86e78-130">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="86e78-130">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="86e78-131">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="86e78-131">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
