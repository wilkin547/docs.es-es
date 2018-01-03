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
ms.workload: dotnet
ms.openlocfilehash: 1107c6608fe5136eb6159b1d4f0a438e95c4dabb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="stack-etw-event"></a><span data-ttu-id="369ec-102">Evento ETW de pila</span><span class="sxs-lookup"><span data-stu-id="369ec-102">Stack ETW Event</span></span>
<span data-ttu-id="369ec-103">El evento de pila se debe usar junto con otros eventos para generar seguimientos de la pila una vez generado un evento.</span><span class="sxs-lookup"><span data-stu-id="369ec-103">The stack event should be used in conjunction with other events to generate stack traces after an event is raised.</span></span> <span data-ttu-id="369ec-104">Se registra cuando se habilita el proveedor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="369ec-104">It is logged when the runtime provider is enabled.</span></span> <span data-ttu-id="369ec-105">Se trata de un evento de muy alta frecuencia, porque se genera cada vez que se genera otro evento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="369ec-105">This is a very high frequency event, because it is raised whenever another runtime event is raised.</span></span> <span data-ttu-id="369ec-106">Por este motivo, le recomendamos que use este evento con precaución.</span><span class="sxs-lookup"><span data-stu-id="369ec-106">For this reason, we recommend that you use this event with caution.</span></span>  
  
 <span data-ttu-id="369ec-107">En la tabla siguiente se muestra la palabra clave y el nivel.</span><span class="sxs-lookup"><span data-stu-id="369ec-107">The following table shows the keyword and level.</span></span> <span data-ttu-id="369ec-108">(Para obtener más información, vea [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)).</span><span class="sxs-lookup"><span data-stu-id="369ec-108">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="369ec-109">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="369ec-109">Keyword for raising the event</span></span>|<span data-ttu-id="369ec-110">Nivel</span><span class="sxs-lookup"><span data-stu-id="369ec-110">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="369ec-111">`StackKeyword` (0x40000000)</span><span class="sxs-lookup"><span data-stu-id="369ec-111">`StackKeyword` (0x40000000)</span></span>|<span data-ttu-id="369ec-112">LogAlways(0)</span><span class="sxs-lookup"><span data-stu-id="369ec-112">LogAlways(0)</span></span>|  
  
 <span data-ttu-id="369ec-113">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="369ec-113">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="369ec-114">Evento</span><span class="sxs-lookup"><span data-stu-id="369ec-114">Event</span></span>|<span data-ttu-id="369ec-115">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="369ec-115">Event ID</span></span>|<span data-ttu-id="369ec-116">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="369ec-116">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`CLRStackWalk`|<span data-ttu-id="369ec-117">82</span><span class="sxs-lookup"><span data-stu-id="369ec-117">82</span></span>|<span data-ttu-id="369ec-118">Junto con otros eventos para generar seguimientos de la pila tras un evento.</span><span class="sxs-lookup"><span data-stu-id="369ec-118">In conjunction with other events to generate stack traces following an event.</span></span>|  
  
 <span data-ttu-id="369ec-119">En la siguiente tabla se muestran los datos del evento.</span><span class="sxs-lookup"><span data-stu-id="369ec-119">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="369ec-120">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="369ec-120">Field name</span></span>|<span data-ttu-id="369ec-121">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="369ec-121">Data Type</span></span>|<span data-ttu-id="369ec-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="369ec-122">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="369ec-123">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="369ec-123">ClrInstanceID</span></span>|<span data-ttu-id="369ec-124">win:Uint16</span><span class="sxs-lookup"><span data-stu-id="369ec-124">win:Uint16</span></span>|<span data-ttu-id="369ec-125">Identificador único en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="369ec-125">Unique runtime identifier.</span></span>|  
|<span data-ttu-id="369ec-126">Reserved1</span><span class="sxs-lookup"><span data-stu-id="369ec-126">Reserved1</span></span>|<span data-ttu-id="369ec-127">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="369ec-127">win:UInt8</span></span>|<span data-ttu-id="369ec-128">Reservado.</span><span class="sxs-lookup"><span data-stu-id="369ec-128">Reserved.</span></span>|  
|<span data-ttu-id="369ec-129">Reserved2</span><span class="sxs-lookup"><span data-stu-id="369ec-129">Reserved2</span></span>|<span data-ttu-id="369ec-130">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="369ec-130">win:UInt8</span></span>|<span data-ttu-id="369ec-131">Reservado.</span><span class="sxs-lookup"><span data-stu-id="369ec-131">Reserved.</span></span>|  
|<span data-ttu-id="369ec-132">FrameCount</span><span class="sxs-lookup"><span data-stu-id="369ec-132">FrameCount</span></span>|<span data-ttu-id="369ec-133">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="369ec-133">win:UInt32</span></span>|<span data-ttu-id="369ec-134">Número de marcos del seguimiento de la pila.</span><span class="sxs-lookup"><span data-stu-id="369ec-134">The number of frames in the stack trace.</span></span>|  
|<span data-ttu-id="369ec-135">Pila</span><span class="sxs-lookup"><span data-stu-id="369ec-135">Stack</span></span>|<span data-ttu-id="369ec-136">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="369ec-136">win:Pointer</span></span>|<span data-ttu-id="369ec-137">Columnas de punteros de instrucción.</span><span class="sxs-lookup"><span data-stu-id="369ec-137">Columns of instruction pointers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="369ec-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="369ec-138">See Also</span></span>  
 [<span data-ttu-id="369ec-139">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="369ec-139">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
