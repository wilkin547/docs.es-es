---
description: 'Más información acerca de: enumeración CLR_DEBUGGING_PROCESS_FLAGS'
title: CLR_DEBUGGING_PROCESS_FLAGS (Enumeración)
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_PROCESS_FLAGS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_PROCESS_FLAG
helpviewer_keywords:
- CLR_DEBUGGING_PROCESS_FLAGS enumeration [.NET Framework debugging]
ms.assetid: 85b85fde-1f87-490b-ba8d-d604670959c3
topic_type:
- apiref
ms.openlocfilehash: 81510bde123ef9a8adefaec5b0708086dacbbf2d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772814"
---
# <a name="clr_debugging_process_flags-enumeration"></a><span data-ttu-id="95bfe-103">CLR_DEBUGGING_PROCESS_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="95bfe-103">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>

<span data-ttu-id="95bfe-104">Proporciona valores que usa el método [ICLRDebugging:: openvirtualprocess (](iclrdebugging-openvirtualprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="95bfe-104">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95bfe-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="95bfe-105">Syntax</span></span>  
  
```cpp  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="95bfe-106">Members</span><span class="sxs-lookup"><span data-stu-id="95bfe-106">Members</span></span>  
  
|<span data-ttu-id="95bfe-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="95bfe-107">Member</span></span>|<span data-ttu-id="95bfe-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="95bfe-108">Description</span></span>|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|<span data-ttu-id="95bfe-109">Este Runtime tiene un evento de depurador administrado que no es de puesta en marcha para enviar.</span><span class="sxs-lookup"><span data-stu-id="95bfe-109">This runtime has a non-catch-up managed debugger event to send.</span></span> <span data-ttu-id="95bfe-110">Vea la sección Comentarios para ver la distinción entre eventos de puesta al día y de no puesta al día.</span><span class="sxs-lookup"><span data-stu-id="95bfe-110">See the Remarks section for the distinction between catch-up and non-catch-up events.</span></span>|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|<span data-ttu-id="95bfe-111">El evento administrado que está pendiente es una <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> solicitud.</span><span class="sxs-lookup"><span data-stu-id="95bfe-111">The managed event that is pending is a <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95bfe-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="95bfe-112">Remarks</span></span>  

 <span data-ttu-id="95bfe-113">Los eventos de puesta al día incluyen notificaciones de creación de procesos, dominios de aplicación, ensamblados, módulos y subprocesos que ponen el depurador al estado actual una vez que se ha adjuntado a un proceso.</span><span class="sxs-lookup"><span data-stu-id="95bfe-113">Catch-up events include process, application domain, assembly, module, and thread creation notifications that bring the debugger up to the current state after it has attached to a process.</span></span> <span data-ttu-id="95bfe-114">Los eventos que no son de puesta al día, que se indican mediante la `CLR_DEBUGGING_MANAGED_EVENT_PENDING` marca, incluyen todos los demás eventos del depurador, como las excepciones y las notificaciones del Asistente para la depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="95bfe-114">Non-catch-up events, which are indicated by the `CLR_DEBUGGING_MANAGED_EVENT_PENDING` flag, include all other debugger events, such as exceptions and managed debugging assistant (MDA) notifications.</span></span>  
  
 <span data-ttu-id="95bfe-115">La `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` marca permite al motor en tiempo de ejecución diferenciar entre una excepción de terminación y una solicitud para asociar un depurador administrado que se puede cancelar.</span><span class="sxs-lookup"><span data-stu-id="95bfe-115">The `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` flag enables the runtime to differentiate between a terminating exception and a request to attach a managed debugger that can be canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95bfe-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="95bfe-116">Requirements</span></span>  

 <span data-ttu-id="95bfe-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95bfe-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95bfe-118">**Encabezado:** Metahost. idl, Metahost. h</span><span class="sxs-lookup"><span data-stu-id="95bfe-118">**Header:** Metahost.idl, Metahost.h</span></span>  
  
 <span data-ttu-id="95bfe-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95bfe-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95bfe-120">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95bfe-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95bfe-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="95bfe-121">See also</span></span>

- [<span data-ttu-id="95bfe-122">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="95bfe-122">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="95bfe-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="95bfe-123">Debugging</span></span>](index.md)
