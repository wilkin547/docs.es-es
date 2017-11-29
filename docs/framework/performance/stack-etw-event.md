---
title: Evento ETW de pila
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- stack event [.NET Framework]
- ETW, stack event (CLR)
ms.assetid: f612fa5b-4b62-4593-a19e-85c9b1018dce
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 55219fe755f49b6edbd3b53cc686bf4f9087aa08
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="stack-etw-event"></a><span data-ttu-id="03aa7-102">Evento ETW de pila</span><span class="sxs-lookup"><span data-stu-id="03aa7-102">Stack ETW Event</span></span>
<span data-ttu-id="03aa7-103">El evento de pila se debe usar junto con otros eventos para generar seguimientos de la pila una vez generado un evento.</span><span class="sxs-lookup"><span data-stu-id="03aa7-103">The stack event should be used in conjunction with other events to generate stack traces after an event is raised.</span></span> <span data-ttu-id="03aa7-104">Se registra cuando se habilita el proveedor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="03aa7-104">It is logged when the runtime provider is enabled.</span></span> <span data-ttu-id="03aa7-105">Se trata de un evento de muy alta frecuencia, porque se genera cada vez que se genera otro evento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="03aa7-105">This is a very high frequency event, because it is raised whenever another runtime event is raised.</span></span> <span data-ttu-id="03aa7-106">Por este motivo, le recomendamos que use este evento con precaución.</span><span class="sxs-lookup"><span data-stu-id="03aa7-106">For this reason, we recommend that you use this event with caution.</span></span>  
  
 <span data-ttu-id="03aa7-107">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="03aa7-107">The following table shows the keyword and level.</span></span> <span data-ttu-id="03aa7-108">(Para obtener más información, vea [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)).</span><span class="sxs-lookup"><span data-stu-id="03aa7-108">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="03aa7-109">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="03aa7-109">Keyword for raising the event</span></span>|<span data-ttu-id="03aa7-110">Nivel</span><span class="sxs-lookup"><span data-stu-id="03aa7-110">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="03aa7-111">`StackKeyword` (0x40000000)</span><span class="sxs-lookup"><span data-stu-id="03aa7-111">`StackKeyword` (0x40000000)</span></span>|<span data-ttu-id="03aa7-112">LogAlways(0)</span><span class="sxs-lookup"><span data-stu-id="03aa7-112">LogAlways(0)</span></span>|  
  
 <span data-ttu-id="03aa7-113">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="03aa7-113">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="03aa7-114">Evento</span><span class="sxs-lookup"><span data-stu-id="03aa7-114">Event</span></span>|<span data-ttu-id="03aa7-115">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="03aa7-115">Event ID</span></span>|<span data-ttu-id="03aa7-116">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="03aa7-116">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`CLRStackWalk`|<span data-ttu-id="03aa7-117">82</span><span class="sxs-lookup"><span data-stu-id="03aa7-117">82</span></span>|<span data-ttu-id="03aa7-118">Junto con otros eventos para generar seguimientos de la pila tras un evento.</span><span class="sxs-lookup"><span data-stu-id="03aa7-118">In conjunction with other events to generate stack traces following an event.</span></span>|  
  
 <span data-ttu-id="03aa7-119">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="03aa7-119">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="03aa7-120">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="03aa7-120">Field name</span></span>|<span data-ttu-id="03aa7-121">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="03aa7-121">Data Type</span></span>|<span data-ttu-id="03aa7-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="03aa7-122">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="03aa7-123">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="03aa7-123">ClrInstanceID</span></span>|<span data-ttu-id="03aa7-124">win:Uint16</span><span class="sxs-lookup"><span data-stu-id="03aa7-124">win:Uint16</span></span>|<span data-ttu-id="03aa7-125">Identificador único en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="03aa7-125">Unique runtime identifier.</span></span>|  
|<span data-ttu-id="03aa7-126">Reserved1</span><span class="sxs-lookup"><span data-stu-id="03aa7-126">Reserved1</span></span>|<span data-ttu-id="03aa7-127">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="03aa7-127">win:UInt8</span></span>|<span data-ttu-id="03aa7-128">Reservado.</span><span class="sxs-lookup"><span data-stu-id="03aa7-128">Reserved.</span></span>|  
|<span data-ttu-id="03aa7-129">Reserved2</span><span class="sxs-lookup"><span data-stu-id="03aa7-129">Reserved2</span></span>|<span data-ttu-id="03aa7-130">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="03aa7-130">win:UInt8</span></span>|<span data-ttu-id="03aa7-131">Reservado.</span><span class="sxs-lookup"><span data-stu-id="03aa7-131">Reserved.</span></span>|  
|<span data-ttu-id="03aa7-132">FrameCount</span><span class="sxs-lookup"><span data-stu-id="03aa7-132">FrameCount</span></span>|<span data-ttu-id="03aa7-133">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="03aa7-133">win:UInt32</span></span>|<span data-ttu-id="03aa7-134">Número de marcos del seguimiento de la pila.</span><span class="sxs-lookup"><span data-stu-id="03aa7-134">The number of frames in the stack trace.</span></span>|  
|<span data-ttu-id="03aa7-135">Pila</span><span class="sxs-lookup"><span data-stu-id="03aa7-135">Stack</span></span>|<span data-ttu-id="03aa7-136">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="03aa7-136">win:Pointer</span></span>|<span data-ttu-id="03aa7-137">Columnas de punteros de instrucción.</span><span class="sxs-lookup"><span data-stu-id="03aa7-137">Columns of instruction pointers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="03aa7-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="03aa7-138">See Also</span></span>  
 [<span data-ttu-id="03aa7-139">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="03aa7-139">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
