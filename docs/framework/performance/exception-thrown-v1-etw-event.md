---
title: Evento ETW de excepción Thrown_V1
description: Vea información detallada sobre el evento ETW ExceptionThrown_V1. Los datos de eventos, como los nombres de campo, los tipos de datos y las descripciones, se proporcionan para las excepciones producidas.
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
ms.openlocfilehash: c1ba994b291bd278a95e34beb0b02ed6581786e8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263482"
---
# <a name="exception-thrown_v1-etw-event"></a><span data-ttu-id="cc6d4-104">Evento ETW de excepción Thrown_V1</span><span class="sxs-lookup"><span data-stu-id="cc6d4-104">Exception Thrown_V1 ETW Event</span></span>

<span data-ttu-id="cc6d4-105">Este evento captura información sobre las excepciones que se generan.</span><span class="sxs-lookup"><span data-stu-id="cc6d4-105">This event captures information about the exceptions that are thrown.</span></span>  
  
 <span data-ttu-id="cc6d4-106">En la tabla siguiente se muestra la palabra clave bajo la que se genera el evento, y el nivel del evento.</span><span class="sxs-lookup"><span data-stu-id="cc6d4-106">The following table shows the keyword under which the event is raised, and the level of the event.</span></span> <span data-ttu-id="cc6d4-107">(Para obtener más información, vea [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)).</span><span class="sxs-lookup"><span data-stu-id="cc6d4-107">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="cc6d4-108">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="cc6d4-108">Keyword for raising the event</span></span>|<span data-ttu-id="cc6d4-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="cc6d4-109">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="cc6d4-110">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="cc6d4-110">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="cc6d4-111">Advertencia (2)</span><span class="sxs-lookup"><span data-stu-id="cc6d4-111">Warning (2)</span></span>|  
  
 <span data-ttu-id="cc6d4-112">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="cc6d4-112">The following table shows event information.</span></span>  
  
|<span data-ttu-id="cc6d4-113">Evento</span><span class="sxs-lookup"><span data-stu-id="cc6d4-113">Event</span></span>|<span data-ttu-id="cc6d4-114">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="cc6d4-114">Event ID</span></span>|<span data-ttu-id="cc6d4-115">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="cc6d4-115">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|<span data-ttu-id="cc6d4-116">80</span><span class="sxs-lookup"><span data-stu-id="cc6d4-116">80</span></span>|<span data-ttu-id="cc6d4-117">Se genera una excepción administrada.</span><span class="sxs-lookup"><span data-stu-id="cc6d4-117">A managed exception is thrown.</span></span>|  
  
 <span data-ttu-id="cc6d4-118">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="cc6d4-118">The following table shows event data.</span></span>  
  
|<span data-ttu-id="cc6d4-119">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="cc6d4-119">Field name</span></span>|<span data-ttu-id="cc6d4-120">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="cc6d4-120">Data type</span></span>|<span data-ttu-id="cc6d4-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc6d4-121">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="cc6d4-122">Tipo de excepción</span><span class="sxs-lookup"><span data-stu-id="cc6d4-122">Exception Type</span></span>|<span data-ttu-id="cc6d4-123">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="cc6d4-123">win:UnicodeString</span></span>|<span data-ttu-id="cc6d4-124">Tipo de la excepción; por ejemplo, `System.NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="cc6d4-124">Type of the exception; for example, `System.NullReferenceException`.</span></span>|  
|<span data-ttu-id="cc6d4-125">Mensaje de la excepción</span><span class="sxs-lookup"><span data-stu-id="cc6d4-125">Exception Message</span></span>|<span data-ttu-id="cc6d4-126">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="cc6d4-126">win:UnicodeString</span></span>|<span data-ttu-id="cc6d4-127">Mensaje actual de la excepción.</span><span class="sxs-lookup"><span data-stu-id="cc6d4-127">Actual exception message.</span></span>|  
|<span data-ttu-id="cc6d4-128">EIPCodeThrow</span><span class="sxs-lookup"><span data-stu-id="cc6d4-128">EIPCodeThrow</span></span>|<span data-ttu-id="cc6d4-129">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="cc6d4-129">win:Pointer</span></span>|<span data-ttu-id="cc6d4-130">Puntero de instrucción donde se ha producido la excepción.</span><span class="sxs-lookup"><span data-stu-id="cc6d4-130">Instruction pointer where exception occurred.</span></span>|  
|<span data-ttu-id="cc6d4-131">ExceptionHR</span><span class="sxs-lookup"><span data-stu-id="cc6d4-131">ExceptionHR</span></span>|<span data-ttu-id="cc6d4-132">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="cc6d4-132">win:UInt32</span></span>|<span data-ttu-id="cc6d4-133">Excepción [HRESULT](/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).</span><span class="sxs-lookup"><span data-stu-id="cc6d4-133">Exception [HRESULT](/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).</span></span>|  
|<span data-ttu-id="cc6d4-134">ExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="cc6d4-134">ExceptionFlags</span></span>|<span data-ttu-id="cc6d4-135">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="cc6d4-135">win:UInt16</span></span>|<span data-ttu-id="cc6d4-136">0x01: HasInnerException (vea [Eventos ETW de CLR](clr-etw-events.md) en la documentación de Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="cc6d4-136">0x01: HasInnerException (see [CLR ETW Events](clr-etw-events.md) in the Visual Basic documentation).</span></span><br /><br /> <span data-ttu-id="cc6d4-137">0x02: IsNestedException.</span><span class="sxs-lookup"><span data-stu-id="cc6d4-137">0x02: IsNestedException.</span></span><br /><br /> <span data-ttu-id="cc6d4-138">0x04: IsRethrownException.</span><span class="sxs-lookup"><span data-stu-id="cc6d4-138">0x04: IsRethrownException.</span></span><br /><br /> <span data-ttu-id="cc6d4-139">0x08: IsCorruptedStateException (indica que el estado del proceso está dañado; consulte [control de excepciones de estado dañadas](/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).</span><span class="sxs-lookup"><span data-stu-id="cc6d4-139">0x08: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).</span></span><br /><br /> <span data-ttu-id="cc6d4-140">0x10: IsCLSCompliant (una excepción que deriva de <xref:System.Exception> es conforme a CLS; de lo contrario, no es conforme a CLS).</span><span class="sxs-lookup"><span data-stu-id="cc6d4-140">0x10: IsCLSCompliant (an exception that derives from <xref:System.Exception> is CLS-compliant; otherwise, it is not CLS-compliant).</span></span>|  
|<span data-ttu-id="cc6d4-141">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="cc6d4-141">ClrInstanceID</span></span>|<span data-ttu-id="cc6d4-142">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="cc6d4-142">win:UInt16</span></span>|<span data-ttu-id="cc6d4-143">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="cc6d4-143">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cc6d4-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc6d4-144">See also</span></span>

- [<span data-ttu-id="cc6d4-145">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="cc6d4-145">CLR ETW Events</span></span>](clr-etw-events.md)
