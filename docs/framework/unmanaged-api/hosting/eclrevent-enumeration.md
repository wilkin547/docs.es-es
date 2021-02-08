---
description: 'Más información acerca de: EClrEvent (enumeración)'
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
ms.openlocfilehash: 7c2365d1a2fb0109bab9159c3af4e2da3a46de6f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785606"
---
# <a name="eclrevent-enumeration"></a><span data-ttu-id="aacff-103">EClrEvent (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="aacff-103">EClrEvent Enumeration</span></span>

<span data-ttu-id="aacff-104">Describe los eventos de Common Language Runtime (CLR) para los que el host puede registrar devoluciones de llamada.</span><span class="sxs-lookup"><span data-stu-id="aacff-104">Describes the common language runtime (CLR) events for which the host can register callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aacff-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aacff-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    Event_ClrDisabled,  
    Event_DomainUnload,  
    Event_MDAFired,  
    Event_StackOverflow  
} EClrEvent;  
```  
  
## <a name="members"></a><span data-ttu-id="aacff-106">Members</span><span class="sxs-lookup"><span data-stu-id="aacff-106">Members</span></span>  
  
|<span data-ttu-id="aacff-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="aacff-107">Member</span></span>|<span data-ttu-id="aacff-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="aacff-108">Description</span></span>|  
|------------|-----------------|  
|`Event_ClrDisabled`|<span data-ttu-id="aacff-109">Especifica un error grave de CLR.</span><span class="sxs-lookup"><span data-stu-id="aacff-109">Specifies a fatal CLR error.</span></span>|  
|`Event_DomainUnload`|<span data-ttu-id="aacff-110">Especifica la descarga de un determinado <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="aacff-110">Specifies the unloading of a particular <xref:System.AppDomain>.</span></span>|  
|`Event_MDAFired`|<span data-ttu-id="aacff-111">Especifica que se ha generado un mensaje del Asistente para la depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="aacff-111">Specifies that a Managed Debugging Assistant (MDA) message has been generated.</span></span>|  
|`Event_StackOverflow`|<span data-ttu-id="aacff-112">Especifica que se ha producido un error de desbordamiento de pila.</span><span class="sxs-lookup"><span data-stu-id="aacff-112">Specifies that a stack overflow error has occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aacff-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="aacff-113">Remarks</span></span>  

 <span data-ttu-id="aacff-114">El host puede registrar devoluciones de llamada para cualquiera de los tipos de evento descritos por `EClrEvent` llamando a métodos de la interfaz [ICLROnEventManager](iclroneventmanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="aacff-114">The host can register callbacks for any of the event types described by `EClrEvent` by calling methods of the [ICLROnEventManager](iclroneventmanager-interface.md) interface.</span></span> <span data-ttu-id="aacff-115">El host obtiene un puntero a esta interfaz llamando al método [ICLRControl:: GetCLRManager (](iclrcontrol-getclrmanager-method.md) .</span><span class="sxs-lookup"><span data-stu-id="aacff-115">The host gets a pointer to this interface by calling the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
 <span data-ttu-id="aacff-116">Los `Event_CLRDisabled` `Event_DomainUnload` eventos y se pueden generar más de una vez y desde distintos subprocesos para indicar una descarga o la deshabilitación de CLR.</span><span class="sxs-lookup"><span data-stu-id="aacff-116">The `Event_CLRDisabled` and `Event_DomainUnload` events can be raised more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
 <span data-ttu-id="aacff-117">El `Event_MDAFired` evento genera la creación de una instancia de [MDAInfo (](mdainfo-structure.md) que contiene los detalles del mensaje de MDA.</span><span class="sxs-lookup"><span data-stu-id="aacff-117">The `Event_MDAFired` event raises the creation of an [MDAInfo](mdainfo-structure.md) instance that contains the details of the MDA message.</span></span> <span data-ttu-id="aacff-118">Para obtener más información acerca de los MDA, vea [diagnosticar errores con asistentes para la depuración administrada](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="aacff-118">For more information about MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aacff-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aacff-119">Requirements</span></span>  

 <span data-ttu-id="aacff-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aacff-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aacff-121">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="aacff-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aacff-122">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aacff-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aacff-123">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aacff-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aacff-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="aacff-124">See also</span></span>

- [<span data-ttu-id="aacff-125">IActionOnCLREvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="aacff-125">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="aacff-126">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="aacff-126">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="aacff-127">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="aacff-127">Hosting Enumerations</span></span>](hosting-enumerations.md)
