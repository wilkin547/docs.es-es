---
title: Evento ETW de pila
description: Obtenga información sobre el evento ETW de pila, que se debe usar junto con otros eventos para generar seguimientos de pila después de que se produzca un evento.
ms.date: 03/30/2017
helpviewer_keywords:
- stack event [.NET Framework]
- ETW, stack event (CLR)
ms.assetid: f612fa5b-4b62-4593-a19e-85c9b1018dce
ms.openlocfilehash: cab496615c4ef17831895b72c8987917e3c06e77
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474142"
---
# <a name="stack-etw-event"></a><span data-ttu-id="2ead8-103">Evento ETW de pila</span><span class="sxs-lookup"><span data-stu-id="2ead8-103">Stack ETW Event</span></span>
<span data-ttu-id="2ead8-104">El evento de pila se debe usar junto con otros eventos para generar seguimientos de la pila una vez generado un evento.</span><span class="sxs-lookup"><span data-stu-id="2ead8-104">The stack event should be used in conjunction with other events to generate stack traces after an event is raised.</span></span> <span data-ttu-id="2ead8-105">Se registra cuando se habilita el proveedor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2ead8-105">It is logged when the runtime provider is enabled.</span></span> <span data-ttu-id="2ead8-106">Se trata de un evento de muy alta frecuencia, porque se genera cada vez que se genera otro evento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2ead8-106">This is a very high frequency event, because it is raised whenever another runtime event is raised.</span></span> <span data-ttu-id="2ead8-107">Por este motivo, le recomendamos que use este evento con precaución.</span><span class="sxs-lookup"><span data-stu-id="2ead8-107">For this reason, we recommend that you use this event with caution.</span></span>  
  
 <span data-ttu-id="2ead8-108">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="2ead8-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="2ead8-109">(Para obtener más información, vea [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)).</span><span class="sxs-lookup"><span data-stu-id="2ead8-109">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="2ead8-110">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="2ead8-110">Keyword for raising the event</span></span>|<span data-ttu-id="2ead8-111">Nivel</span><span class="sxs-lookup"><span data-stu-id="2ead8-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="2ead8-112">`StackKeyword` (0x40000000)</span><span class="sxs-lookup"><span data-stu-id="2ead8-112">`StackKeyword` (0x40000000)</span></span>|<span data-ttu-id="2ead8-113">LogAlways(0)</span><span class="sxs-lookup"><span data-stu-id="2ead8-113">LogAlways(0)</span></span>|  
  
 <span data-ttu-id="2ead8-114">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="2ead8-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2ead8-115">Evento</span><span class="sxs-lookup"><span data-stu-id="2ead8-115">Event</span></span>|<span data-ttu-id="2ead8-116">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="2ead8-116">Event ID</span></span>|<span data-ttu-id="2ead8-117">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="2ead8-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`CLRStackWalk`|<span data-ttu-id="2ead8-118">82</span><span class="sxs-lookup"><span data-stu-id="2ead8-118">82</span></span>|<span data-ttu-id="2ead8-119">Junto con otros eventos para generar seguimientos de la pila tras un evento.</span><span class="sxs-lookup"><span data-stu-id="2ead8-119">In conjunction with other events to generate stack traces following an event.</span></span>|  
  
 <span data-ttu-id="2ead8-120">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="2ead8-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="2ead8-121">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="2ead8-121">Field name</span></span>|<span data-ttu-id="2ead8-122">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2ead8-122">Data Type</span></span>|<span data-ttu-id="2ead8-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="2ead8-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2ead8-124">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2ead8-124">ClrInstanceID</span></span>|<span data-ttu-id="2ead8-125">win:Uint16</span><span class="sxs-lookup"><span data-stu-id="2ead8-125">win:Uint16</span></span>|<span data-ttu-id="2ead8-126">Identificador único en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2ead8-126">Unique runtime identifier.</span></span>|  
|<span data-ttu-id="2ead8-127">Reserved1</span><span class="sxs-lookup"><span data-stu-id="2ead8-127">Reserved1</span></span>|<span data-ttu-id="2ead8-128">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="2ead8-128">win:UInt8</span></span>|<span data-ttu-id="2ead8-129">Reservado.</span><span class="sxs-lookup"><span data-stu-id="2ead8-129">Reserved.</span></span>|  
|<span data-ttu-id="2ead8-130">Reserved2</span><span class="sxs-lookup"><span data-stu-id="2ead8-130">Reserved2</span></span>|<span data-ttu-id="2ead8-131">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="2ead8-131">win:UInt8</span></span>|<span data-ttu-id="2ead8-132">Reservado.</span><span class="sxs-lookup"><span data-stu-id="2ead8-132">Reserved.</span></span>|  
|<span data-ttu-id="2ead8-133">FrameCount</span><span class="sxs-lookup"><span data-stu-id="2ead8-133">FrameCount</span></span>|<span data-ttu-id="2ead8-134">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2ead8-134">win:UInt32</span></span>|<span data-ttu-id="2ead8-135">Número de marcos del seguimiento de la pila.</span><span class="sxs-lookup"><span data-stu-id="2ead8-135">The number of frames in the stack trace.</span></span>|  
|<span data-ttu-id="2ead8-136">Pila</span><span class="sxs-lookup"><span data-stu-id="2ead8-136">Stack</span></span>|<span data-ttu-id="2ead8-137">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="2ead8-137">win:Pointer</span></span>|<span data-ttu-id="2ead8-138">Columnas de punteros de instrucción.</span><span class="sxs-lookup"><span data-stu-id="2ead8-138">Columns of instruction pointers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2ead8-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2ead8-139">See also</span></span>

- [<span data-ttu-id="2ead8-140">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="2ead8-140">CLR ETW Events</span></span>](clr-etw-events.md)
