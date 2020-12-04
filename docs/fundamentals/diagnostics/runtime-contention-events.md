---
title: Supervisar eventos de tiempo de ejecución de contención de bloqueo
description: Vea eventos ETW que recopilan información específica de las contenciones de bloqueo del monitor.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- monitor lock contention events (CoreCLR)
- ETW, EventPipe, LTTng contention events (CoreCLR)
ms.openlocfilehash: 38e5f493d4b223b4839dbd6f814cf656722189b2
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "96594706"
---
# <a name="net-runtime-contention-events"></a><span data-ttu-id="f8948-103">Eventos de contención en tiempo de ejecución de .NET</span><span class="sxs-lookup"><span data-stu-id="f8948-103">.NET runtime contention events</span></span>

<span data-ttu-id="f8948-104">Estos eventos en tiempo de ejecución capturan información sobre las contenciones de bloqueo de monitor como con `Monitor.Enter` o la palabra clave Lock de C#.</span><span class="sxs-lookup"><span data-stu-id="f8948-104">These runtime events capture information about monitor lock contentions such as with `Monitor.Enter` or the C# lock keyword.</span></span> <span data-ttu-id="f8948-105">Para obtener más información sobre cómo usar estos eventos con fines de diagnóstico, consulte [registro y seguimiento de aplicaciones .net](../../core/diagnostics/logging-tracing.md)</span><span class="sxs-lookup"><span data-stu-id="f8948-105">For more information about how to use these events for diagnostic purposes, see [logging and tracing .NET applications](../../core/diagnostics/logging-tracing.md)</span></span>

## <a name="contentionstart_v1-event"></a><span data-ttu-id="f8948-106">Evento ContentionStart_V1</span><span class="sxs-lookup"><span data-stu-id="f8948-106">ContentionStart_V1 event</span></span>

<span data-ttu-id="f8948-107">Este evento se genera al inicio de una contención de bloqueo de monitor.</span><span class="sxs-lookup"><span data-stu-id="f8948-107">This event is emitted at the start of a monitor lock contention.</span></span>

|<span data-ttu-id="f8948-108">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="f8948-108">Keyword for raising the event</span></span>|<span data-ttu-id="f8948-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="f8948-109">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="f8948-110">`ContentionKeyword` (0x4000)</span><span class="sxs-lookup"><span data-stu-id="f8948-110">`ContentionKeyword` (0x4000)</span></span>|<span data-ttu-id="f8948-111">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="f8948-111">Informational (4)</span></span>|

 <span data-ttu-id="f8948-112">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="f8948-112">The following table shows event information.</span></span>

|<span data-ttu-id="f8948-113">Evento</span><span class="sxs-lookup"><span data-stu-id="f8948-113">Event</span></span>|<span data-ttu-id="f8948-114">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="f8948-114">Event ID</span></span>|<span data-ttu-id="f8948-115">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="f8948-115">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ContentionStart_V1`|<span data-ttu-id="f8948-116">81</span><span class="sxs-lookup"><span data-stu-id="f8948-116">81</span></span>|<span data-ttu-id="f8948-117">Se inicia una contención de bloqueo de monitor.</span><span class="sxs-lookup"><span data-stu-id="f8948-117">A monitor lock contention starts.</span></span>|

|<span data-ttu-id="f8948-118">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="f8948-118">Field name</span></span>|<span data-ttu-id="f8948-119">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="f8948-119">Data type</span></span>|<span data-ttu-id="f8948-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8948-120">Description</span></span>|
|----------------|---------------|-----------------|
|`Flags`|`win:UInt8`|<span data-ttu-id="f8948-121">`0` para administrado; `1` para nativo.</span><span class="sxs-lookup"><span data-stu-id="f8948-121">`0` for managed; `1` for native.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="f8948-122">IDENTIFICADOR único de la instancia de CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="f8948-122">Unique ID for the instance of CoreCLR.</span></span>|

## <a name="contentionstop_v1-event"></a><span data-ttu-id="f8948-123">Evento ContentionStop_V1</span><span class="sxs-lookup"><span data-stu-id="f8948-123">ContentionStop_V1 event</span></span>

<span data-ttu-id="f8948-124">Este evento se emite al final de una contención de bloqueo de monitor.</span><span class="sxs-lookup"><span data-stu-id="f8948-124">This event is emitted at the end of a monitor lock contention.</span></span>

|<span data-ttu-id="f8948-125">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="f8948-125">Keyword for raising the event</span></span>|<span data-ttu-id="f8948-126">Nivel</span><span class="sxs-lookup"><span data-stu-id="f8948-126">Level</span></span>|
|-----------------------------------|-----------|
|<span data-ttu-id="f8948-127">`ContentionKeyword` (0x4000)</span><span class="sxs-lookup"><span data-stu-id="f8948-127">`ContentionKeyword` (0x4000)</span></span>|<span data-ttu-id="f8948-128">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="f8948-128">Informational (4)</span></span>|

 <span data-ttu-id="f8948-129">En la siguiente tabla se muestra la información del evento.</span><span class="sxs-lookup"><span data-stu-id="f8948-129">The following table shows event information.</span></span>

|<span data-ttu-id="f8948-130">Evento</span><span class="sxs-lookup"><span data-stu-id="f8948-130">Event</span></span>|<span data-ttu-id="f8948-131">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="f8948-131">Event ID</span></span>|<span data-ttu-id="f8948-132">Se genera cuando</span><span class="sxs-lookup"><span data-stu-id="f8948-132">Raised when</span></span>|
|-----------|--------------|-----------------|
|`ContentionStop_V1`|<span data-ttu-id="f8948-133">91</span><span class="sxs-lookup"><span data-stu-id="f8948-133">91</span></span>|<span data-ttu-id="f8948-134">Finaliza una contención de bloqueo de monitor.</span><span class="sxs-lookup"><span data-stu-id="f8948-134">A monitor lock contention ends.</span></span>|

|<span data-ttu-id="f8948-135">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="f8948-135">Field name</span></span>|<span data-ttu-id="f8948-136">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="f8948-136">Data type</span></span>|<span data-ttu-id="f8948-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8948-137">Description</span></span>|
|----------------|---------------|-----------------|
|`Flags`|`win:UInt8`|<span data-ttu-id="f8948-138">`0` para administrado; `1` para nativo.</span><span class="sxs-lookup"><span data-stu-id="f8948-138">`0` for managed; `1` for native.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="f8948-139">IDENTIFICADOR único de la instancia de CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="f8948-139">Unique ID for the instance of CoreCLR.</span></span>|
|`DurationNs`|`win:Double`|<span data-ttu-id="f8948-140">Duración de la contención en nanosegundos.</span><span class="sxs-lookup"><span data-stu-id="f8948-140">Duration of the contention in nanoseconds.</span></span>|
