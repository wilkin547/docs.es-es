---
title: Eventos de tiempo de ejecución del sistema de tipos
description: Vea eventos de tiempo de ejecución de .NET que recopilan información de diagnóstico específica del sistema de tipos .NET, como TypeLoadStart y TypeLoadStop.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- type system events (CoreCLR)
- ETW, EventPipe, LTTng type system events (CoreCLR)
ms.openlocfilehash: 8eee89cddb0098da2cb449a4be21945adac725e3
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "96594701"
---
# <a name="net-runtime-type-events"></a><span data-ttu-id="ed18c-103">Eventos de tipo en tiempo de ejecución .NET</span><span class="sxs-lookup"><span data-stu-id="ed18c-103">.NET runtime type events</span></span>

<span data-ttu-id="ed18c-104">Estos eventos recopilan información relacionada con la carga de tipos.</span><span class="sxs-lookup"><span data-stu-id="ed18c-104">These events collect information relating to loading types.</span></span> <span data-ttu-id="ed18c-105">Para obtener más información sobre cómo usar estos eventos con fines de diagnóstico, consulte [registro y seguimiento de aplicaciones .net](../../core/diagnostics/logging-tracing.md)</span><span class="sxs-lookup"><span data-stu-id="ed18c-105">For more information about how to use these events for diagnostic purposes, see [logging and tracing .NET applications](../../core/diagnostics/logging-tracing.md)</span></span>

## <a name="typeloadstart-event"></a><span data-ttu-id="ed18c-106">Evento TypeLoadStart</span><span class="sxs-lookup"><span data-stu-id="ed18c-106">TypeLoadStart Event</span></span>

|<span data-ttu-id="ed18c-107">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ed18c-107">Keyword for raising the event</span></span>|<span data-ttu-id="ed18c-108">Evento</span><span class="sxs-lookup"><span data-stu-id="ed18c-108">Event</span></span>|<span data-ttu-id="ed18c-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="ed18c-109">Level</span></span>|  
|-----------------------------------|-----------|-----------|  
|<span data-ttu-id="ed18c-110">`TypeDiagnosticKeyword` (0x8000000000)</span><span class="sxs-lookup"><span data-stu-id="ed18c-110">`TypeDiagnosticKeyword` (0x8000000000)</span></span>|<span data-ttu-id="ed18c-111">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ed18c-111">Informational (4)</span></span>|  

|<span data-ttu-id="ed18c-112">Evento</span><span class="sxs-lookup"><span data-stu-id="ed18c-112">Event</span></span>|<span data-ttu-id="ed18c-113">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ed18c-113">Event ID</span></span>|<span data-ttu-id="ed18c-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed18c-114">Description</span></span>|  
|-----------|--------------|-----------------|  
|`TypeLoadStart`|<span data-ttu-id="ed18c-115">73</span><span class="sxs-lookup"><span data-stu-id="ed18c-115">73</span></span>|<span data-ttu-id="ed18c-116">Se ha iniciado una carga de tipos.</span><span class="sxs-lookup"><span data-stu-id="ed18c-116">A type load has started.</span></span>|

|<span data-ttu-id="ed18c-117">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="ed18c-117">Field name</span></span>|<span data-ttu-id="ed18c-118">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ed18c-118">Data type</span></span>|<span data-ttu-id="ed18c-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed18c-119">Description</span></span>|  
|----------------|---------------|-----------------|  
|`TypeLoadStartID`|`win:UInt32`|<span data-ttu-id="ed18c-120">IDENTIFICADOR de la operación de carga de tipo.</span><span class="sxs-lookup"><span data-stu-id="ed18c-120">ID for the type load operation.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="ed18c-121">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ed18c-121">Unique ID for the instance of CLR or CoreCLR.</span></span>|  

## <a name="typeloadstop-event"></a><span data-ttu-id="ed18c-122">Evento TypeLoadStop</span><span class="sxs-lookup"><span data-stu-id="ed18c-122">TypeLoadStop Event</span></span>

|<span data-ttu-id="ed18c-123">Palabra clave para generar el evento</span><span class="sxs-lookup"><span data-stu-id="ed18c-123">Keyword for raising the event</span></span>|<span data-ttu-id="ed18c-124">Nivel</span><span class="sxs-lookup"><span data-stu-id="ed18c-124">Level</span></span>|  
|-----------------------------------|-----------|-----------|  
|<span data-ttu-id="ed18c-125">`TypeDiagnosticKeyword` (0x8000000000)</span><span class="sxs-lookup"><span data-stu-id="ed18c-125">`TypeDiagnosticKeyword` (0x8000000000)</span></span>|<span data-ttu-id="ed18c-126">Informativo (4)</span><span class="sxs-lookup"><span data-stu-id="ed18c-126">Informational (4)</span></span>|  

|<span data-ttu-id="ed18c-127">Evento</span><span class="sxs-lookup"><span data-stu-id="ed18c-127">Event</span></span>|<span data-ttu-id="ed18c-128">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ed18c-128">Event ID</span></span>|<span data-ttu-id="ed18c-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed18c-129">Description</span></span>|  
|-----------|--------------|-----------------|  
|`TypeLoadStop`|<span data-ttu-id="ed18c-130">74</span><span class="sxs-lookup"><span data-stu-id="ed18c-130">74</span></span>|<span data-ttu-id="ed18c-131">Se ha completado una carga de tipos.</span><span class="sxs-lookup"><span data-stu-id="ed18c-131">A type load is finished.</span></span>|

|<span data-ttu-id="ed18c-132">Nombre del campo</span><span class="sxs-lookup"><span data-stu-id="ed18c-132">Field name</span></span>|<span data-ttu-id="ed18c-133">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ed18c-133">Data type</span></span>|<span data-ttu-id="ed18c-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed18c-134">Description</span></span>|  
|----------------|---------------|-----------------|  
|`TypeLoadStartID`|`win:UInt32`|<span data-ttu-id="ed18c-135">IDENTIFICADOR de la operación de carga de tipo (coincide con el TypeLoadStartID del evento TypeLoadStart correspondiente).</span><span class="sxs-lookup"><span data-stu-id="ed18c-135">ID for the type load operation (matches the corresponding TypeLoadStart event's TypeLoadStartID).</span></span>|
|`LoadLevel`|`win:UInt16`|<span data-ttu-id="ed18c-136">Nivel de carga de tipo.</span><span class="sxs-lookup"><span data-stu-id="ed18c-136">Type load level.</span></span>|
|`TypeID`|`win:UInt64`|<span data-ttu-id="ed18c-137">Puntero al identificador de tipo.</span><span class="sxs-lookup"><span data-stu-id="ed18c-137">Pointer to the type handle.</span></span>|
|`TypeName`|`win:UnicodeString`|<span data-ttu-id="ed18c-138">Nombre del tipo.</span><span class="sxs-lookup"><span data-stu-id="ed18c-138">Name of the type.</span></span>|
|`ClrInstanceID`|`win:UInt16`|<span data-ttu-id="ed18c-139">Identificador único para la instancia de CLR o CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="ed18c-139">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
