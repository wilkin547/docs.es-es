---
title: Eventos ETW de contención - .NET
ms.date: 03/30/2017
helpviewer_keywords:
- contention events [.NET Framework]
- ETW, contention events (CLR)
ms.assetid: 6933e753-2f2a-425b-ae84-42138c957d76
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 95f56a6c8b51c58ed36d5d0de428bf57b728009c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723945"
---
# <a name="contention-etw-events"></a><span data-ttu-id="50e91-102">Eventos ETW de contención</span><span class="sxs-lookup"><span data-stu-id="50e91-102">Contention ETW events</span></span>

<span data-ttu-id="50e91-103">Los eventos de contención se generan cuando el tiempo de ejecución usa contención de bloqueos <xref:System.Threading.Monitor?displayProperty=nameWithType> o nativos.</span><span class="sxs-lookup"><span data-stu-id="50e91-103">Contention events are raised whenever there is contention for <xref:System.Threading.Monitor?displayProperty=nameWithType> locks or native locks used by the runtime.</span></span> <span data-ttu-id="50e91-104">La contención se produce cuando un subproceso espera un bloqueo mientras otro posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="50e91-104">Contention occurs when a thread is waiting for a lock while another thread possesses the lock.</span></span>

<span data-ttu-id="50e91-105">En la tabla siguiente se muestra la palabra clave bajo la que se generan los eventos de contención y el nivel de los eventos.</span><span class="sxs-lookup"><span data-stu-id="50e91-105">The following table shows the keyword under which contention events are raised, and the level of the events.</span></span> <span data-ttu-id="50e91-106">Para obtener más información, consulte [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="50e91-106">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="50e91-107">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="50e91-107">Keyword for raising the event</span></span>|<span data-ttu-id="50e91-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="50e91-108">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="50e91-109">`ContentionKeyword` (0x4000)</span><span class="sxs-lookup"><span data-stu-id="50e91-109">`ContentionKeyword` (0x4000)</span></span>|<span data-ttu-id="50e91-110">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="50e91-110">Informational (4)</span></span>|

<span data-ttu-id="50e91-111">En la tabla siguiente se muestra la información de evento:</span><span class="sxs-lookup"><span data-stu-id="50e91-111">The following table shows event information:</span></span>

|<span data-ttu-id="50e91-112">evento</span><span class="sxs-lookup"><span data-stu-id="50e91-112">Event</span></span>|<span data-ttu-id="50e91-113">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="50e91-113">Event ID</span></span>|<span data-ttu-id="50e91-114">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="50e91-114">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ContentionStart_V1`|<span data-ttu-id="50e91-115">81</span><span class="sxs-lookup"><span data-stu-id="50e91-115">81</span></span>|<span data-ttu-id="50e91-116">Se inicia la contención.</span><span class="sxs-lookup"><span data-stu-id="50e91-116">Contention starts.</span></span> <span data-ttu-id="50e91-117">Este evento no incluye la cantidad de tiempo de giro antes de que un subproceso comience a esperar para adquirir un bloqueo; solo se genera cuando el subproceso espera para adquirir un bloqueo.</span><span class="sxs-lookup"><span data-stu-id="50e91-117">This event does not include the amount of spinning time before a thread waits to acquire a lock; it is raised only when the thread waits to acquire a lock.</span></span>|
|`ContentionStop`|<span data-ttu-id="50e91-118">91</span><span class="sxs-lookup"><span data-stu-id="50e91-118">91</span></span>|<span data-ttu-id="50e91-119">Finaliza la contención.</span><span class="sxs-lookup"><span data-stu-id="50e91-119">Contention ends.</span></span>|

<span data-ttu-id="50e91-120">La siguiente tabla muestra los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="50e91-120">The following table shows event data:</span></span>

|<span data-ttu-id="50e91-121">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="50e91-121">Field name</span></span>|<span data-ttu-id="50e91-122">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="50e91-122">Data type</span></span>|<span data-ttu-id="50e91-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="50e91-123">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="50e91-124">Marcas</span><span class="sxs-lookup"><span data-stu-id="50e91-124">Flags</span></span>|<span data-ttu-id="50e91-125">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="50e91-125">win:UInt8</span></span>|<span data-ttu-id="50e91-126">0 para administrado; 1 para nativo.</span><span class="sxs-lookup"><span data-stu-id="50e91-126">0 for managed; 1 for native.</span></span>|
|<span data-ttu-id="50e91-127">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="50e91-127">ClrInstanceID</span></span>|<span data-ttu-id="50e91-128">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="50e91-128">win:UInt16</span></span>|<span data-ttu-id="50e91-129">Identificador único para la instancia de CLR.</span><span class="sxs-lookup"><span data-stu-id="50e91-129">Unique ID for the instance of CLR.</span></span>|

## <a name="see-also"></a><span data-ttu-id="50e91-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="50e91-130">See also</span></span>

- [<span data-ttu-id="50e91-131">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="50e91-131">CLR ETW Events</span></span>](clr-etw-events.md)
