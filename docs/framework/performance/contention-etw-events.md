---
title: 'Eventos ETW de contención: .NET'
description: Obtenga detalles sobre los eventos ETW de contención, que se generan cada vez que hay contención para los bloqueos System. Threading. monitor o bloqueos nativos utilizados por el motor en tiempo de ejecución.
ms.date: 03/30/2017
helpviewer_keywords:
- contention events [.NET Framework]
- ETW, contention events (CLR)
ms.assetid: 6933e753-2f2a-425b-ae84-42138c957d76
ms.openlocfilehash: a36b091e0896562fffdb66e895d70049ce0667d7
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309604"
---
# <a name="contention-etw-events"></a><span data-ttu-id="dc7a6-103">Eventos ETW de contención</span><span class="sxs-lookup"><span data-stu-id="dc7a6-103">Contention ETW events</span></span>

<span data-ttu-id="dc7a6-104">Los eventos de contención se generan cuando el tiempo de ejecución usa contención de bloqueos <xref:System.Threading.Monitor?displayProperty=nameWithType> o nativos.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-104">Contention events are raised whenever there is contention for <xref:System.Threading.Monitor?displayProperty=nameWithType> locks or native locks used by the runtime.</span></span> <span data-ttu-id="dc7a6-105">La contención se produce cuando un subproceso espera un bloqueo mientras otro posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-105">Contention occurs when a thread is waiting for a lock while another thread possesses the lock.</span></span>

<span data-ttu-id="dc7a6-106">En la tabla siguiente se muestra la palabra clave bajo la que se generan los eventos de contención y el nivel de los eventos.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-106">The following table shows the keyword under which contention events are raised, and the level of the events.</span></span> <span data-ttu-id="dc7a6-107">Para obtener más información, vea [palabras clave y niveles ETW de CLR](clr-etw-keywords-and-levels.md).</span><span class="sxs-lookup"><span data-stu-id="dc7a6-107">For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).</span></span>

|<span data-ttu-id="dc7a6-108">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="dc7a6-108">Keyword for raising the event</span></span>|<span data-ttu-id="dc7a6-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="dc7a6-109">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="dc7a6-110">`ContentionKeyword` (0x4000)</span><span class="sxs-lookup"><span data-stu-id="dc7a6-110">`ContentionKeyword` (0x4000)</span></span>|<span data-ttu-id="dc7a6-111">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="dc7a6-111">Informational (4)</span></span>|

<span data-ttu-id="dc7a6-112">En la tabla siguiente se muestra la información del evento:</span><span class="sxs-lookup"><span data-stu-id="dc7a6-112">The following table shows event information:</span></span>

|<span data-ttu-id="dc7a6-113">Evento</span><span class="sxs-lookup"><span data-stu-id="dc7a6-113">Event</span></span>|<span data-ttu-id="dc7a6-114">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="dc7a6-114">Event ID</span></span>|<span data-ttu-id="dc7a6-115">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="dc7a6-115">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ContentionStart_V1`|<span data-ttu-id="dc7a6-116">81</span><span class="sxs-lookup"><span data-stu-id="dc7a6-116">81</span></span>|<span data-ttu-id="dc7a6-117">Se inicia la contención.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-117">Contention starts.</span></span> <span data-ttu-id="dc7a6-118">Este evento no incluye la cantidad de tiempo de giro antes de que un subproceso comience a esperar para adquirir un bloqueo; solo se genera cuando el subproceso espera para adquirir un bloqueo.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-118">This event does not include the amount of spinning time before a thread waits to acquire a lock; it is raised only when the thread waits to acquire a lock.</span></span>|
|`ContentionStop`|<span data-ttu-id="dc7a6-119">91</span><span class="sxs-lookup"><span data-stu-id="dc7a6-119">91</span></span>|<span data-ttu-id="dc7a6-120">Finaliza la contención.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-120">Contention ends.</span></span>|

<span data-ttu-id="dc7a6-121">En la tabla siguiente se muestran los datos del evento:</span><span class="sxs-lookup"><span data-stu-id="dc7a6-121">The following table shows event data:</span></span>

|<span data-ttu-id="dc7a6-122">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="dc7a6-122">Field name</span></span>|<span data-ttu-id="dc7a6-123">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="dc7a6-123">Data type</span></span>|<span data-ttu-id="dc7a6-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="dc7a6-124">Description</span></span>|
|----------------|---------------|-----------------|
|<span data-ttu-id="dc7a6-125">Marcas</span><span class="sxs-lookup"><span data-stu-id="dc7a6-125">Flags</span></span>|<span data-ttu-id="dc7a6-126">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="dc7a6-126">win:UInt8</span></span>|<span data-ttu-id="dc7a6-127">0 para administrado; 1 para nativo.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-127">0 for managed; 1 for native.</span></span>|
|<span data-ttu-id="dc7a6-128">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="dc7a6-128">ClrInstanceID</span></span>|<span data-ttu-id="dc7a6-129">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="dc7a6-129">win:UInt16</span></span>|<span data-ttu-id="dc7a6-130">Identificador único para la instancia de CLR.</span><span class="sxs-lookup"><span data-stu-id="dc7a6-130">Unique ID for the instance of CLR.</span></span>|

## <a name="see-also"></a><span data-ttu-id="dc7a6-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dc7a6-131">See also</span></span>

- [<span data-ttu-id="dc7a6-132">CLR ETW Events (Eventos ETW de CLR)</span><span class="sxs-lookup"><span data-stu-id="dc7a6-132">CLR ETW Events</span></span>](clr-etw-events.md)
