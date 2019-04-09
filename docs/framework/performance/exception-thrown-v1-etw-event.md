---
title: Evento ETW de excepción Thrown_V1
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dd322d25d91bb277a4c817594c968c28a6d61d68
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136141"
---
# <a name="exception-thrownv1-etw-event"></a><span data-ttu-id="347d2-102">Evento ETW de excepción Thrown_V1</span><span class="sxs-lookup"><span data-stu-id="347d2-102">Exception Thrown_V1 ETW Event</span></span>
<span data-ttu-id="347d2-103">Este evento captura información sobre las excepciones que se generan.</span><span class="sxs-lookup"><span data-stu-id="347d2-103">This event captures information about the exceptions that are thrown.</span></span>  
  
 <span data-ttu-id="347d2-104">En la tabla siguiente se muestra la palabra clave bajo la que se genera el evento, y el nivel del evento.</span><span class="sxs-lookup"><span data-stu-id="347d2-104">The following table shows the keyword under which the event is raised, and the level of the event.</span></span> <span data-ttu-id="347d2-105">(Para obtener más información, vea [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)).</span><span class="sxs-lookup"><span data-stu-id="347d2-105">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="347d2-106">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="347d2-106">Keyword for raising the event</span></span>|<span data-ttu-id="347d2-107">Nivel</span><span class="sxs-lookup"><span data-stu-id="347d2-107">Level</span></span>|  
|-----------------------------------|-----------|  
|`ExceptionKeyword` <span data-ttu-id="347d2-108">(0x8000)</span><span class="sxs-lookup"><span data-stu-id="347d2-108">(0x8000)</span></span>|<span data-ttu-id="347d2-109">Advertencia (2)</span><span class="sxs-lookup"><span data-stu-id="347d2-109">Warning (2)</span></span>|  
  
 <span data-ttu-id="347d2-110">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="347d2-110">The following table shows event information.</span></span>  
  
|<span data-ttu-id="347d2-111">evento</span><span class="sxs-lookup"><span data-stu-id="347d2-111">Event</span></span>|<span data-ttu-id="347d2-112">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="347d2-112">Event ID</span></span>|<span data-ttu-id="347d2-113">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="347d2-113">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|<span data-ttu-id="347d2-114">80</span><span class="sxs-lookup"><span data-stu-id="347d2-114">80</span></span>|<span data-ttu-id="347d2-115">Se genera una excepción administrada.</span><span class="sxs-lookup"><span data-stu-id="347d2-115">A managed exception is thrown.</span></span>|  
  
 <span data-ttu-id="347d2-116">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="347d2-116">The following table shows event data.</span></span>  
  
|<span data-ttu-id="347d2-117">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="347d2-117">Field name</span></span>|<span data-ttu-id="347d2-118">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="347d2-118">Data type</span></span>|<span data-ttu-id="347d2-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="347d2-119">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="347d2-120">Tipo de excepción</span><span class="sxs-lookup"><span data-stu-id="347d2-120">Exception Type</span></span>|<span data-ttu-id="347d2-121">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="347d2-121">win:UnicodeString</span></span>|<span data-ttu-id="347d2-122">Tipo de la excepción; por ejemplo, `System.NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="347d2-122">Type of the exception; for example, `System.NullReferenceException`.</span></span>|  
|<span data-ttu-id="347d2-123">Mensaje de la excepción</span><span class="sxs-lookup"><span data-stu-id="347d2-123">Exception Message</span></span>|<span data-ttu-id="347d2-124">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="347d2-124">win:UnicodeString</span></span>|<span data-ttu-id="347d2-125">Mensaje actual de la excepción.</span><span class="sxs-lookup"><span data-stu-id="347d2-125">Actual exception message.</span></span>|  
|<span data-ttu-id="347d2-126">EIPCodeThrow</span><span class="sxs-lookup"><span data-stu-id="347d2-126">EIPCodeThrow</span></span>|<span data-ttu-id="347d2-127">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="347d2-127">win:Pointer</span></span>|<span data-ttu-id="347d2-128">Puntero de instrucción donde se ha producido la excepción.</span><span class="sxs-lookup"><span data-stu-id="347d2-128">Instruction pointer where exception occurred.</span></span>|  
|<span data-ttu-id="347d2-129">ExceptionHR</span><span class="sxs-lookup"><span data-stu-id="347d2-129">ExceptionHR</span></span>|<span data-ttu-id="347d2-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="347d2-130">win:UInt32</span></span>|<span data-ttu-id="347d2-131">Excepción [HRESULT](https://go.microsoft.com/fwlink/?LinkId=179679).</span><span class="sxs-lookup"><span data-stu-id="347d2-131">Exception [HRESULT](https://go.microsoft.com/fwlink/?LinkId=179679).</span></span>|  
|<span data-ttu-id="347d2-132">ExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="347d2-132">ExceptionFlags</span></span>|<span data-ttu-id="347d2-133">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="347d2-133">win:UInt16</span></span>|<span data-ttu-id="347d2-134">0x01: HasInnerException (vea [eventos ETW de CLR](../../../docs/framework/performance/clr-etw-events.md) en la documentación de Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="347d2-134">0x01: HasInnerException (see [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md) in the Visual Basic documentation).</span></span><br /><br /> <span data-ttu-id="347d2-135">0x02: IsNestedException.</span><span class="sxs-lookup"><span data-stu-id="347d2-135">0x02: IsNestedException.</span></span><br /><br /> <span data-ttu-id="347d2-136">0x04: IsRethrownException.</span><span class="sxs-lookup"><span data-stu-id="347d2-136">0x04: IsRethrownException.</span></span><br /><br /> <span data-ttu-id="347d2-137">0x08: IsCorruptedStateException (indica que el estado del proceso está dañado; vea [Handling Corrupted State Exceptions](https://go.microsoft.com/fwlink/?LinkId=179681) en MSDN).</span><span class="sxs-lookup"><span data-stu-id="347d2-137">0x08: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](https://go.microsoft.com/fwlink/?LinkId=179681) on MSDN).</span></span><br /><br /> <span data-ttu-id="347d2-138">0x10: IsCLSCompliant (una excepción que se deriva de <xref:System.Exception> es conforme a CLS; en caso contrario, no es conforme a CLS).</span><span class="sxs-lookup"><span data-stu-id="347d2-138">0x10: IsCLSCompliant (an exception that derives from <xref:System.Exception> is CLS-compliant; otherwise, it is not CLS-compliant).</span></span>|  
|<span data-ttu-id="347d2-139">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="347d2-139">ClrInstanceID</span></span>|<span data-ttu-id="347d2-140">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="347d2-140">win:UInt16</span></span>|<span data-ttu-id="347d2-141">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="347d2-141">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="347d2-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="347d2-142">See also</span></span>

- [<span data-ttu-id="347d2-143">Eventos ETW de CLR</span><span class="sxs-lookup"><span data-stu-id="347d2-143">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
