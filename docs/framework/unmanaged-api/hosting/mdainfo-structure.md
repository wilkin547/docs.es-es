---
description: 'Más información acerca de: estructura MDAInfo ('
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
ms.openlocfilehash: 5c42537a68d38e6cff3d70dcb796cd733ce64a1e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679763"
---
# <a name="mdainfo-structure"></a><span data-ttu-id="57977-103">MDAInfo (Estructura)</span><span class="sxs-lookup"><span data-stu-id="57977-103">MDAInfo Structure</span></span>

<span data-ttu-id="57977-104">Proporciona detalles sobre el `Event_MDAFired` evento, que desencadena la creación de un asistente para la depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="57977-104">Provides details about the `Event_MDAFired` event, which triggers the creation of a managed debugging assistant (MDA).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57977-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="57977-105">Syntax</span></span>  
  
```cpp  
typedef struct _MDAInfo {  
    LPCWSTR  lpMDACaption;  
    LPCWSTR  lpMDAMessage  
} MDAInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="57977-106">Members</span><span class="sxs-lookup"><span data-stu-id="57977-106">Members</span></span>  
  
|<span data-ttu-id="57977-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="57977-107">Member</span></span>|<span data-ttu-id="57977-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="57977-108">Description</span></span>|  
|------------|-----------------|  
|`lpMDACaption`|<span data-ttu-id="57977-109">Título del MDA actual.</span><span class="sxs-lookup"><span data-stu-id="57977-109">The title of the current MDA.</span></span> <span data-ttu-id="57977-110">El título describe el tipo de error que desencadenó el `Event_MDAFired` evento.</span><span class="sxs-lookup"><span data-stu-id="57977-110">The title describes the kind of failure that triggered the `Event_MDAFired` event.</span></span>|  
|`lpMDAMessage`|<span data-ttu-id="57977-111">Mensaje de salida proporcionado por el MDA actual.</span><span class="sxs-lookup"><span data-stu-id="57977-111">The output message provided by the current MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57977-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="57977-112">Remarks</span></span>  

 <span data-ttu-id="57977-113">Los asistentes para la depuración administrada (MDA) son ayudas para la depuración que funcionan junto con el Common Language Runtime (CLR) para realizar tareas como la identificación de condiciones no válidas en el motor de ejecución en tiempo de ejecución o el volcado de información adicional sobre el estado del motor.</span><span class="sxs-lookup"><span data-stu-id="57977-113">Managed debugging assistants (MDAs) are debugging aids that work in conjunction with the common language runtime (CLR) to perform tasks such as identifying invalid conditions in the runtime execution engine or dumping additional information about the state of the engine.</span></span> <span data-ttu-id="57977-114">Los MDA generan mensajes XML sobre eventos que, de otro modo, son difíciles de interceptar.</span><span class="sxs-lookup"><span data-stu-id="57977-114">MDAs generate XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="57977-115">Son especialmente útiles para depurar las transiciones entre el código administrado y no administrado.</span><span class="sxs-lookup"><span data-stu-id="57977-115">They are especially useful for debugging transitions between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="57977-116">El tiempo de ejecución sigue los pasos siguientes cuando se activa un evento que desencadena la creación de un MDA:</span><span class="sxs-lookup"><span data-stu-id="57977-116">The runtime takes the following steps when an event that triggers the creation of an MDA is fired:</span></span>  
  
- <span data-ttu-id="57977-117">Si el host no ha registrado una instancia de [IActionOnCLREvent](iactiononclrevent-interface.md) llamando a [ICLROnEventManager:: RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) para recibir una notificación de un `Event_MDAFired` evento, el tiempo de ejecución continúa con su comportamiento predeterminado no hospedado.</span><span class="sxs-lookup"><span data-stu-id="57977-117">If the host has not registered an [IActionOnCLREvent](iactiononclrevent-interface.md) instance by calling [ICLROnEventManager::RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) to be notified of an `Event_MDAFired` event, the runtime proceeds with its default, non-hosted behavior.</span></span>  
  
- <span data-ttu-id="57977-118">Si el host ha registrado un controlador para este evento, el tiempo de ejecución comprueba si hay un depurador asociado al proceso.</span><span class="sxs-lookup"><span data-stu-id="57977-118">If the host has registered a handler for this event, the runtime checks to see whether a debugger is attached to the process.</span></span> <span data-ttu-id="57977-119">Si es así, el Runtime se interrumpe en el depurador.</span><span class="sxs-lookup"><span data-stu-id="57977-119">If it is, the runtime breaks into the debugger.</span></span> <span data-ttu-id="57977-120">Cuando el depurador continúa, llama al host.</span><span class="sxs-lookup"><span data-stu-id="57977-120">When the debugger continues, it calls into the host.</span></span> <span data-ttu-id="57977-121">Si no hay ningún depurador asociado, el Runtime llama a `IActionOnCLREvent::OnEvent` y pasa un puntero a una `MDAInfo` instancia de como `data` parámetro.</span><span class="sxs-lookup"><span data-stu-id="57977-121">If no debugger is attached, the runtime calls `IActionOnCLREvent::OnEvent` and passes a pointer to an `MDAInfo` instance as the `data` parameter.</span></span>  
  
 <span data-ttu-id="57977-122">El host puede optar por activar los MDA y recibir una notificación cuando se activa un MDA.</span><span class="sxs-lookup"><span data-stu-id="57977-122">The host can choose to activate MDAs and to be notified when an MDA is activated.</span></span> <span data-ttu-id="57977-123">Esto proporciona al host una oportunidad para invalidar el comportamiento predeterminado y anular el subproceso administrado que provocó el evento, para evitar que dañe el estado del proceso.</span><span class="sxs-lookup"><span data-stu-id="57977-123">This gives the host an opportunity to override default behavior and to abort the managed thread that raised the event, to prevent it from corrupting the process state.</span></span> <span data-ttu-id="57977-124">Para obtener más información sobre el uso de MDA, vea [diagnosticar errores con asistentes para la depuración administrada](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="57977-124">For more information about using MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57977-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="57977-125">Requirements</span></span>  

 <span data-ttu-id="57977-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57977-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57977-127">**Encabezado:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="57977-127">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="57977-128">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="57977-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="57977-129">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57977-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57977-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="57977-130">See also</span></span>

- [<span data-ttu-id="57977-131">Estructuras de hospedaje</span><span class="sxs-lookup"><span data-stu-id="57977-131">Hosting Structures</span></span>](hosting-structures.md)
- [<span data-ttu-id="57977-132">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="57977-132">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
