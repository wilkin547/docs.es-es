---
title: Patrón asincrónico basado en eventos (EAP)
description: Vea vínculos a artículos sobre el modelo asincrónico basado en eventos (EAP) en .NET, como la implementación, los procedimientos recomendados y la implementación de un cliente EAP, entre otros.
ms.date: 07/23/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous calls
- asynchronous programming, design patterns
- asynchronous programming
ms.assetid: c6baed9f-2a25-4728-9a9a-53b7b14840cf
ms.openlocfilehash: 03b4d914d72b96b882c774565654c022b145b5f2
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768877"
---
# <a name="event-based-asynchronous-pattern-eap"></a><span data-ttu-id="117fc-103">Patrón asincrónico basado en eventos (EAP)</span><span class="sxs-lookup"><span data-stu-id="117fc-103">Event-based Asynchronous Pattern (EAP)</span></span>

<span data-ttu-id="117fc-104">Hay varias maneras de exponer las características asincrónicas al código de cliente.</span><span class="sxs-lookup"><span data-stu-id="117fc-104">There are a number of ways to expose asynchronous features to client code.</span></span> <span data-ttu-id="117fc-105">El modelo asincrónico basado en eventos prescribe una manera para que las clases presenten comportamiento asincrónico.</span><span class="sxs-lookup"><span data-stu-id="117fc-105">The Event-based Asynchronous Pattern prescribes one way for classes to present asynchronous behavior.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="117fc-106">A partir de .NET Framework 4, la biblioteca TPL (Task Parallel Library, biblioteca de procesamiento paralelo basado en tareas) ofrece un nuevo modelo para programación asincrónica y paralela.</span><span class="sxs-lookup"><span data-stu-id="117fc-106">Starting with the .NET Framework 4, the Task Parallel Library provides a new model for asynchronous and parallel programming.</span></span> <span data-ttu-id="117fc-107">Para obtener más información, vea [Biblioteca de procesamiento paralelo basado en tareas (TPL)](../parallel-programming/task-parallel-library-tpl.md) y [Modelo asincrónico basado en tareas (TAP)](task-based-asynchronous-pattern-tap.md).</span><span class="sxs-lookup"><span data-stu-id="117fc-107">For more information, see [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md) and [Task-based Asynchronous Pattern (TAP)](task-based-asynchronous-pattern-tap.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="117fc-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="117fc-108">In This Section</span></span>

 [<span data-ttu-id="117fc-109">Información general sobre el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="117fc-109">Event-based Asynchronous Pattern Overview</span></span>](event-based-asynchronous-pattern-overview.md)  
 <span data-ttu-id="117fc-110">Describe cómo el Modelo asincrónico basado en evento pone a su disposición las ventajas de las aplicaciones multithreading ocultando muchos de los problemas complejos inherentes al diseño multithreading.</span><span class="sxs-lookup"><span data-stu-id="117fc-110">Describes how the Event-based Asynchronous Pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>  
  
 [<span data-ttu-id="117fc-111">Implementación del modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="117fc-111">Implementing the Event-based Asynchronous Pattern</span></span>](implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="117fc-112">Describe la manera estándar de empaquetar una clase que tiene características asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="117fc-112">Describes the standardized way to package a class that has asynchronous features.</span></span>  
  
 [<span data-ttu-id="117fc-113">Procedimientos recomendados para implementar el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="117fc-113">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="117fc-114">Describe los requisitos para exponer las características asincrónicas según el Modelo asincrónico basado en evento.</span><span class="sxs-lookup"><span data-stu-id="117fc-114">Describes the requirements for exposing asynchronous features according to the Event-based Asynchronous Pattern.</span></span>  
  
 [<span data-ttu-id="117fc-115">Decisión de cuándo implementar el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="117fc-115">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>](deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="117fc-116">En este tema se describe cómo determinar el momento conveniente para implementar el modelo asincrónico basado en eventos en lugar del modelo <xref:System.IAsyncResult>, representado por el [modelo de programación asincrónica (APM)](asynchronous-programming-model-apm.md).</span><span class="sxs-lookup"><span data-stu-id="117fc-116">Describes how to determine when you should choose to implement the Event-based Asynchronous Pattern instead of the <xref:System.IAsyncResult> pattern represented by the [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md)</span></span>
  
 [<span data-ttu-id="117fc-117">Cómo: Implementación de un componente que admita el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="117fc-117">How to: Implement a Component That Supports the Event-based Asynchronous Pattern</span></span>](component-that-supports-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="117fc-118">En este tema se describe cómo crear un componente que implemente el modelo asincrónico basado en eventos.</span><span class="sxs-lookup"><span data-stu-id="117fc-118">Describes how to create a component that implements the Event-based Asynchronous Pattern.</span></span> <span data-ttu-id="117fc-119">Se implementa utilizando las clases del asistente del espacio de nombres <xref:System.ComponentModel?displayProperty=nameWithType>, que garantiza que el componente funciona correctamente bajo cualquier modelo de aplicación.</span><span class="sxs-lookup"><span data-stu-id="117fc-119">It is implemented using helper classes from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace, which ensures that the component works correctly under any application model.</span></span>  

 [<span data-ttu-id="117fc-120">Cómo: Implementar un cliente en un modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="117fc-120">How to: Implement a Client of the Event-based Asynchronous Pattern</span></span>](how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="117fc-121">En este tema se describe cómo crear un cliente que use un componente que implemente el modelo asincrónico basado en eventos.</span><span class="sxs-lookup"><span data-stu-id="117fc-121">Describes how to create a client that uses a component that implements the Event-based Asynchronous Pattern.</span></span>
  
 [<span data-ttu-id="117fc-122">Cómo: Uso de componentes que admitan el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="117fc-122">How to: Use Components That Support the Event-based Asynchronous Pattern</span></span>](how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="117fc-123">Describe cómo utilizar un componente que admite el Modelo asincrónico basado en evento.</span><span class="sxs-lookup"><span data-stu-id="117fc-123">Describes how to use a component that supports the Event-based Asynchronous Pattern.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="117fc-124">Referencia</span><span class="sxs-lookup"><span data-stu-id="117fc-124">Reference</span></span>

 <xref:System.ComponentModel.AsyncOperation>  
 <span data-ttu-id="117fc-125">Describe la clase <xref:System.ComponentModel.AsyncOperation> y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="117fc-125">Describes the <xref:System.ComponentModel.AsyncOperation> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <span data-ttu-id="117fc-126">Describe la clase <xref:System.ComponentModel.AsyncOperationManager> y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="117fc-126">Describes the <xref:System.ComponentModel.AsyncOperationManager> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="117fc-127">Describe el componente <xref:System.ComponentModel.BackgroundWorker> y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="117fc-127">Describes the <xref:System.ComponentModel.BackgroundWorker> component and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="117fc-128">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="117fc-128">Related Sections</span></span>

 [<span data-ttu-id="117fc-129">Biblioteca TPL</span><span class="sxs-lookup"><span data-stu-id="117fc-129">Task Parallel Library (TPL)</span></span>](../parallel-programming/task-parallel-library-tpl.md)  
 <span data-ttu-id="117fc-130">Describe un modelo de programación para operaciones asincrónicas y paralelas.</span><span class="sxs-lookup"><span data-stu-id="117fc-130">Describes a programming model for asynchronous and parallel operations.</span></span>  
  
 [<span data-ttu-id="117fc-131">Subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="117fc-131">Threading</span></span>](../threading/index.md)  
 <span data-ttu-id="117fc-132">En este tema se describen las características de multithreading en .NET.</span><span class="sxs-lookup"><span data-stu-id="117fc-132">Describes multithreading features in .NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="117fc-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="117fc-133">See also</span></span>

- [<span data-ttu-id="117fc-134">Procedimientos recomendados para el subprocesamiento administrado</span><span class="sxs-lookup"><span data-stu-id="117fc-134">Managed Threading Best Practices</span></span>](../threading/managed-threading-best-practices.md)
- [<span data-ttu-id="117fc-135">Eventos</span><span class="sxs-lookup"><span data-stu-id="117fc-135">Events</span></span>](../events/index.md)
- [<span data-ttu-id="117fc-136">Patrones para la programación asincrónica</span><span class="sxs-lookup"><span data-stu-id="117fc-136">Asynchronous Programming Design Patterns</span></span>](index.md)
