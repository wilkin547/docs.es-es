---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dff6b245c80050a5e85561b8bba6aa9ba8199ba8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407071"
---
# <a name="clrdebuggingprocessflags-enumeration"></a><span data-ttu-id="d1232-102">CLR_DEBUGGING_PROCESS_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d1232-102">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>
<span data-ttu-id="d1232-103">Proporciona valores que se usan por el [ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="d1232-103">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1232-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d1232-104">Syntax</span></span>  
  
```  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="d1232-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="d1232-105">Members</span></span>  
  
|<span data-ttu-id="d1232-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="d1232-106">Member</span></span>|<span data-ttu-id="d1232-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d1232-107">Description</span></span>|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|<span data-ttu-id="d1232-108">Este tiempo de ejecución tiene un evento de depurador administrado-catch-up para enviar.</span><span class="sxs-lookup"><span data-stu-id="d1232-108">This runtime has a non-catch-up managed debugger event to send.</span></span> <span data-ttu-id="d1232-109">Vea la sección Comentarios para la distinción entre eventos de puesta al día y -catch-up.</span><span class="sxs-lookup"><span data-stu-id="d1232-109">See the Remarks section for the distinction between catch-up and non-catch-up events.</span></span>|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|<span data-ttu-id="d1232-110">Es el evento administrado que está pendiente un <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> solicitud.</span><span class="sxs-lookup"><span data-stu-id="d1232-110">The managed event that is pending is a <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1232-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d1232-111">Remarks</span></span>  
 <span data-ttu-id="d1232-112">Eventos de puesta al día incluyen proceso, dominio de aplicación, ensamblado, módulo y las notificaciones de creación de subproceso que poner al depurador hasta el estado actual después de que ha adjuntado a un proceso.</span><span class="sxs-lookup"><span data-stu-id="d1232-112">Catch-up events include process, application domain, assembly, module, and thread creation notifications that bring the debugger up to the current state after it has attached to a process.</span></span> <span data-ttu-id="d1232-113">Eventos de no-catch-up, que se indican mediante el `CLR_DEBUGGING_MANAGED_EVENT_PENDING` marca, incluir todos los otros eventos del depurador, como las excepciones y administra depuración notificaciones Ayudante (MDA).</span><span class="sxs-lookup"><span data-stu-id="d1232-113">Non-catch-up events, which are indicated by the `CLR_DEBUGGING_MANAGED_EVENT_PENDING` flag, include all other debugger events, such as exceptions and managed debugging assistant (MDA) notifications.</span></span>  
  
 <span data-ttu-id="d1232-114">El `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` marca permite que el tiempo de ejecución diferenciar entre una excepción de terminación y una solicitud para adjuntar un depurador administrado que se puede cancelar.</span><span class="sxs-lookup"><span data-stu-id="d1232-114">The `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` flag enables the runtime to differentiate between a terminating exception and a request to attach a managed debugger that can be canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1232-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d1232-115">Requirements</span></span>  
 <span data-ttu-id="d1232-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1232-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1232-117">**Encabezado:** Metahost.idl, Metahost.h</span><span class="sxs-lookup"><span data-stu-id="d1232-117">**Header:** Metahost.idl, Metahost.h</span></span>  
  
 <span data-ttu-id="d1232-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1232-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1232-119">**Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1232-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1232-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1232-120">See Also</span></span>  
 [<span data-ttu-id="d1232-121">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="d1232-121">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="d1232-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="d1232-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
