---
title: Evento ETW de pila
ms.date: 03/30/2017
helpviewer_keywords:
- stack event [.NET Framework]
- ETW, stack event (CLR)
ms.assetid: f612fa5b-4b62-4593-a19e-85c9b1018dce
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5dc23f5105b589d5b74c9ea6b7f40b84c2b04e6a
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71046166"
---
# <a name="stack-etw-event"></a><span data-ttu-id="fb501-102">Evento ETW de pila</span><span class="sxs-lookup"><span data-stu-id="fb501-102">Stack ETW Event</span></span>
<span data-ttu-id="fb501-103">El evento de pila se debe usar junto con otros eventos para generar seguimientos de la pila una vez generado un evento.</span><span class="sxs-lookup"><span data-stu-id="fb501-103">The stack event should be used in conjunction with other events to generate stack traces after an event is raised.</span></span> <span data-ttu-id="fb501-104">Se registra cuando se habilita el proveedor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fb501-104">It is logged when the runtime provider is enabled.</span></span> <span data-ttu-id="fb501-105">Se trata de un evento de muy alta frecuencia, porque se genera cada vez que se genera otro evento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fb501-105">This is a very high frequency event, because it is raised whenever another runtime event is raised.</span></span> <span data-ttu-id="fb501-106">Por este motivo, le recomendamos que use este evento con precaución.</span><span class="sxs-lookup"><span data-stu-id="fb501-106">For this reason, we recommend that you use this event with caution.</span></span>  
  
 <span data-ttu-id="fb501-107">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="fb501-107">The following table shows the keyword and level.</span></span> <span data-ttu-id="fb501-108">(Para obtener más información, vea [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)).</span><span class="sxs-lookup"><span data-stu-id="fb501-108">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="fb501-109">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="fb501-109">Keyword for raising the event</span></span>|<span data-ttu-id="fb501-110">Nivel</span><span class="sxs-lookup"><span data-stu-id="fb501-110">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="fb501-111">`StackKeyword` (0x40000000)</span><span class="sxs-lookup"><span data-stu-id="fb501-111">`StackKeyword` (0x40000000)</span></span>|<span data-ttu-id="fb501-112">LogAlways(0)</span><span class="sxs-lookup"><span data-stu-id="fb501-112">LogAlways(0)</span></span>|  
  
 <span data-ttu-id="fb501-113">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="fb501-113">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="fb501-114">Evento</span><span class="sxs-lookup"><span data-stu-id="fb501-114">Event</span></span>|<span data-ttu-id="fb501-115">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="fb501-115">Event ID</span></span>|<span data-ttu-id="fb501-116">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="fb501-116">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`CLRStackWalk`|<span data-ttu-id="fb501-117">82</span><span class="sxs-lookup"><span data-stu-id="fb501-117">82</span></span>|<span data-ttu-id="fb501-118">Junto con otros eventos para generar seguimientos de la pila tras un evento.</span><span class="sxs-lookup"><span data-stu-id="fb501-118">In conjunction with other events to generate stack traces following an event.</span></span>|  
  
 <span data-ttu-id="fb501-119">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="fb501-119">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="fb501-120">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="fb501-120">Field name</span></span>|<span data-ttu-id="fb501-121">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="fb501-121">Data Type</span></span>|<span data-ttu-id="fb501-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="fb501-122">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="fb501-123">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="fb501-123">ClrInstanceID</span></span>|<span data-ttu-id="fb501-124">win:Uint16</span><span class="sxs-lookup"><span data-stu-id="fb501-124">win:Uint16</span></span>|<span data-ttu-id="fb501-125">Identificador único en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fb501-125">Unique runtime identifier.</span></span>|  
|<span data-ttu-id="fb501-126">Reserved1</span><span class="sxs-lookup"><span data-stu-id="fb501-126">Reserved1</span></span>|<span data-ttu-id="fb501-127">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="fb501-127">win:UInt8</span></span>|<span data-ttu-id="fb501-128">Reservado.</span><span class="sxs-lookup"><span data-stu-id="fb501-128">Reserved.</span></span>|  
|<span data-ttu-id="fb501-129">Reserved2</span><span class="sxs-lookup"><span data-stu-id="fb501-129">Reserved2</span></span>|<span data-ttu-id="fb501-130">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="fb501-130">win:UInt8</span></span>|<span data-ttu-id="fb501-131">Reservado.</span><span class="sxs-lookup"><span data-stu-id="fb501-131">Reserved.</span></span>|  
|<span data-ttu-id="fb501-132">FrameCount</span><span class="sxs-lookup"><span data-stu-id="fb501-132">FrameCount</span></span>|<span data-ttu-id="fb501-133">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="fb501-133">win:UInt32</span></span>|<span data-ttu-id="fb501-134">Número de marcos del seguimiento de la pila.</span><span class="sxs-lookup"><span data-stu-id="fb501-134">The number of frames in the stack trace.</span></span>|  
|<span data-ttu-id="fb501-135">Pila</span><span class="sxs-lookup"><span data-stu-id="fb501-135">Stack</span></span>|<span data-ttu-id="fb501-136">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="fb501-136">win:Pointer</span></span>|<span data-ttu-id="fb501-137">Columnas de punteros de instrucción.</span><span class="sxs-lookup"><span data-stu-id="fb501-137">Columns of instruction pointers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fb501-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb501-138">See also</span></span>

- [<span data-ttu-id="fb501-139">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="fb501-139">CLR ETW Events</span></span>](clr-etw-events.md)
