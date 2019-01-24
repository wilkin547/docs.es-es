---
title: EClrEvent (Enumeración)
ms.date: 03/30/2017
api_name:
- EClrEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrEvent
helpviewer_keywords:
- EClrEvent enumeration [.NET Framework hosting]
ms.assetid: 7c36a7c2-75a2-4971-bc23-abf54c812154
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d66e010340d186eed2222ae2ba8cfb24b8e8d7b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658577"
---
# <a name="eclrevent-enumeration"></a><span data-ttu-id="cd869-102">EClrEvent (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="cd869-102">EClrEvent Enumeration</span></span>
<span data-ttu-id="cd869-103">Describe los eventos de common language runtime (CLR) para que el host puede registrar devoluciones de llamada.</span><span class="sxs-lookup"><span data-stu-id="cd869-103">Describes the common language runtime (CLR) events for which the host can register callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd869-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cd869-104">Syntax</span></span>  
  
```  
typedef enum {  
    Event_ClrDisabled,  
    Event_DomainUnload,  
    Event_MDAFired,  
    Event_StackOverflow  
} EClrEvent;  
```  
  
## <a name="members"></a><span data-ttu-id="cd869-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="cd869-105">Members</span></span>  
  
|<span data-ttu-id="cd869-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="cd869-106">Member</span></span>|<span data-ttu-id="cd869-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="cd869-107">Description</span></span>|  
|------------|-----------------|  
|`Event_ClrDisabled`|<span data-ttu-id="cd869-108">Especifica un error grave de CLR.</span><span class="sxs-lookup"><span data-stu-id="cd869-108">Specifies a fatal CLR error.</span></span>|  
|`Event_DomainUnload`|<span data-ttu-id="cd869-109">Especifica la descarga de un determinado <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="cd869-109">Specifies the unloading of a particular <xref:System.AppDomain>.</span></span>|  
|`Event_MDAFired`|<span data-ttu-id="cd869-110">Especifica que se ha generado un mensaje del Asistente para la depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="cd869-110">Specifies that a Managed Debugging Assistant (MDA) message has been generated.</span></span>|  
|`Event_StackOverflow`|<span data-ttu-id="cd869-111">Especifica que se ha producido un error de desbordamiento de pila.</span><span class="sxs-lookup"><span data-stu-id="cd869-111">Specifies that a stack overflow error has occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd869-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cd869-112">Remarks</span></span>  
 <span data-ttu-id="cd869-113">El host puede registrar devoluciones de llamada para cualquiera de los tipos de eventos descritos por `EClrEvent` llamando a métodos de la [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="cd869-113">The host can register callbacks for any of the event types described by `EClrEvent` by calling methods of the [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) interface.</span></span> <span data-ttu-id="cd869-114">El host obtiene un puntero a esta interfaz mediante una llamada a la [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="cd869-114">The host gets a pointer to this interface by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
 <span data-ttu-id="cd869-115">El `Event_CLRDisabled` y `Event_DomainUnload` se pueden generar eventos más de una vez y desde diferentes subprocesos para indicar una descarga o la deshabilitación de CLR.</span><span class="sxs-lookup"><span data-stu-id="cd869-115">The `Event_CLRDisabled` and `Event_DomainUnload` events can be raised more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
 <span data-ttu-id="cd869-116">El `Event_MDAFired` evento provoca la creación de un [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) instancia que contiene los detalles del mensaje MDA.</span><span class="sxs-lookup"><span data-stu-id="cd869-116">The `Event_MDAFired` event raises the creation of an [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) instance that contains the details of the MDA message.</span></span> <span data-ttu-id="cd869-117">Para obtener más información sobre los MDA, consulte [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="cd869-117">For more information about MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd869-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cd869-118">Requirements</span></span>  
 <span data-ttu-id="cd869-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd869-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd869-120">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cd869-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cd869-121">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cd869-121">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cd869-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd869-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd869-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd869-123">See also</span></span>
- [<span data-ttu-id="cd869-124">IActionOnCLREvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cd869-124">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="cd869-125">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cd869-125">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="cd869-126">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="cd869-126">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
