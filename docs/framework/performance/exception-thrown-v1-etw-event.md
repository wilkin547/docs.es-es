---
title: Evento ETW de excepción Thrown_V1
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3f0e968053c87319bf90bf3de0f21d750ec899ab
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447633"
---
# <a name="exception-thrown_v1-etw-event"></a><span data-ttu-id="fb198-102">Evento ETW de excepción Thrown_V1</span><span class="sxs-lookup"><span data-stu-id="fb198-102">Exception Thrown_V1 ETW Event</span></span>
<span data-ttu-id="fb198-103">Este evento captura información sobre las excepciones que se generan.</span><span class="sxs-lookup"><span data-stu-id="fb198-103">This event captures information about the exceptions that are thrown.</span></span>  
  
 <span data-ttu-id="fb198-104">En la tabla siguiente se muestra la palabra clave bajo la que se genera el evento, y el nivel del evento.</span><span class="sxs-lookup"><span data-stu-id="fb198-104">The following table shows the keyword under which the event is raised, and the level of the event.</span></span> <span data-ttu-id="fb198-105">(Para obtener más información, vea [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)).</span><span class="sxs-lookup"><span data-stu-id="fb198-105">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="fb198-106">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="fb198-106">Keyword for raising the event</span></span>|<span data-ttu-id="fb198-107">Nivel</span><span class="sxs-lookup"><span data-stu-id="fb198-107">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="fb198-108">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="fb198-108">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="fb198-109">Advertencia (2)</span><span class="sxs-lookup"><span data-stu-id="fb198-109">Warning (2)</span></span>|  
  
 <span data-ttu-id="fb198-110">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="fb198-110">The following table shows event information.</span></span>  
  
|<span data-ttu-id="fb198-111">evento</span><span class="sxs-lookup"><span data-stu-id="fb198-111">Event</span></span>|<span data-ttu-id="fb198-112">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="fb198-112">Event ID</span></span>|<span data-ttu-id="fb198-113">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="fb198-113">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|<span data-ttu-id="fb198-114">80</span><span class="sxs-lookup"><span data-stu-id="fb198-114">80</span></span>|<span data-ttu-id="fb198-115">Se genera una excepción administrada.</span><span class="sxs-lookup"><span data-stu-id="fb198-115">A managed exception is thrown.</span></span>|  
  
 <span data-ttu-id="fb198-116">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="fb198-116">The following table shows event data.</span></span>  
  
|<span data-ttu-id="fb198-117">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="fb198-117">Field name</span></span>|<span data-ttu-id="fb198-118">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="fb198-118">Data type</span></span>|<span data-ttu-id="fb198-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="fb198-119">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="fb198-120">Tipo de excepción</span><span class="sxs-lookup"><span data-stu-id="fb198-120">Exception Type</span></span>|<span data-ttu-id="fb198-121">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="fb198-121">win:UnicodeString</span></span>|<span data-ttu-id="fb198-122">Tipo de la excepción; por ejemplo, `System.NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="fb198-122">Type of the exception; for example, `System.NullReferenceException`.</span></span>|  
|<span data-ttu-id="fb198-123">Mensaje de la excepción</span><span class="sxs-lookup"><span data-stu-id="fb198-123">Exception Message</span></span>|<span data-ttu-id="fb198-124">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="fb198-124">win:UnicodeString</span></span>|<span data-ttu-id="fb198-125">Mensaje actual de la excepción.</span><span class="sxs-lookup"><span data-stu-id="fb198-125">Actual exception message.</span></span>|  
|<span data-ttu-id="fb198-126">EIPCodeThrow</span><span class="sxs-lookup"><span data-stu-id="fb198-126">EIPCodeThrow</span></span>|<span data-ttu-id="fb198-127">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="fb198-127">win:Pointer</span></span>|<span data-ttu-id="fb198-128">Puntero de instrucción donde se ha producido la excepción.</span><span class="sxs-lookup"><span data-stu-id="fb198-128">Instruction pointer where exception occurred.</span></span>|  
|<span data-ttu-id="fb198-129">ExceptionHR</span><span class="sxs-lookup"><span data-stu-id="fb198-129">ExceptionHR</span></span>|<span data-ttu-id="fb198-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="fb198-130">win:UInt32</span></span>|<span data-ttu-id="fb198-131">Excepción [HRESULT](https://docs.microsoft.com/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).</span><span class="sxs-lookup"><span data-stu-id="fb198-131">Exception [HRESULT](https://docs.microsoft.com/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).</span></span>|  
|<span data-ttu-id="fb198-132">ExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="fb198-132">ExceptionFlags</span></span>|<span data-ttu-id="fb198-133">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="fb198-133">win:UInt16</span></span>|<span data-ttu-id="fb198-134">0x01: HasInnerException (vea [Eventos ETW de CLR](clr-etw-events.md) en la documentación de Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="fb198-134">0x01: HasInnerException (see [CLR ETW Events](clr-etw-events.md) in the Visual Basic documentation).</span></span><br /><br /> <span data-ttu-id="fb198-135">0x02: IsNestedException.</span><span class="sxs-lookup"><span data-stu-id="fb198-135">0x02: IsNestedException.</span></span><br /><br /> <span data-ttu-id="fb198-136">0x04: IsRethrownException.</span><span class="sxs-lookup"><span data-stu-id="fb198-136">0x04: IsRethrownException.</span></span><br /><br /> <span data-ttu-id="fb198-137">0x08: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](https://docs.microsoft.com/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).</span><span class="sxs-lookup"><span data-stu-id="fb198-137">0x08: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](https://docs.microsoft.com/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).</span></span><br /><br /> <span data-ttu-id="fb198-138">0x10: IsCLSCompliant (una excepción que deriva de <xref:System.Exception> es conforme a CLS; de lo contrario, no es conforme a CLS).</span><span class="sxs-lookup"><span data-stu-id="fb198-138">0x10: IsCLSCompliant (an exception that derives from <xref:System.Exception> is CLS-compliant; otherwise, it is not CLS-compliant).</span></span>|  
|<span data-ttu-id="fb198-139">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="fb198-139">ClrInstanceID</span></span>|<span data-ttu-id="fb198-140">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="fb198-140">win:UInt16</span></span>|<span data-ttu-id="fb198-141">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="fb198-141">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fb198-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb198-142">See also</span></span>

- [<span data-ttu-id="fb198-143">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="fb198-143">CLR ETW Events</span></span>](clr-etw-events.md)
