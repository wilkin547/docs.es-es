---
title: Patrón asincrónico basado en eventos (EAP)
ms.date: 07/23/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous calls
- asynchronous programming, design patterns
- asynchronous programming
ms.assetid: c6baed9f-2a25-4728-9a9a-53b7b14840cf
ms.openlocfilehash: ee8c90d63478e444b7d25cb7cbb5c969963d7c63
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73130944"
---
# <a name="event-based-asynchronous-pattern-eap"></a><span data-ttu-id="36a5c-102">Patrón asincrónico basado en eventos (EAP)</span><span class="sxs-lookup"><span data-stu-id="36a5c-102">Event-based Asynchronous Pattern (EAP)</span></span>

<span data-ttu-id="36a5c-103">Hay varias maneras de exponer las características asincrónicas al código de cliente.</span><span class="sxs-lookup"><span data-stu-id="36a5c-103">There are a number of ways to expose asynchronous features to client code.</span></span> <span data-ttu-id="36a5c-104">El modelo asincrónico basado en eventos prescribe una manera para que las clases presenten comportamiento asincrónico.</span><span class="sxs-lookup"><span data-stu-id="36a5c-104">The Event-based Asynchronous Pattern prescribes one way for classes to present asynchronous behavior.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="36a5c-105">A partir de .NET Framework 4, la biblioteca TPL (Task Parallel Library, biblioteca de procesamiento paralelo basado en tareas) ofrece un nuevo modelo para programación asincrónica y paralela.</span><span class="sxs-lookup"><span data-stu-id="36a5c-105">Starting with the .NET Framework 4, the Task Parallel Library provides a new model for asynchronous and parallel programming.</span></span> <span data-ttu-id="36a5c-106">Para obtener más información, vea [Biblioteca de procesamiento paralelo basado en tareas (TPL)](../parallel-programming/task-parallel-library-tpl.md) y [Modelo asincrónico basado en tareas (TAP)](task-based-asynchronous-pattern-tap.md).</span><span class="sxs-lookup"><span data-stu-id="36a5c-106">For more information, see [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md) and [Task-based Asynchronous Pattern (TAP)](task-based-asynchronous-pattern-tap.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="36a5c-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="36a5c-107">In This Section</span></span>

 <span data-ttu-id="36a5c-108">[Event-based Asynchronous Pattern Overview](event-based-asynchronous-pattern-overview.md) (Información general sobre el modelo asincrónico basado en eventos)</span><span class="sxs-lookup"><span data-stu-id="36a5c-108">[Event-based Asynchronous Pattern Overview](event-based-asynchronous-pattern-overview.md)</span></span>  
 <span data-ttu-id="36a5c-109">Describe cómo el Modelo asincrónico basado en evento pone a su disposición las ventajas de las aplicaciones multithreading ocultando muchos de los problemas complejos inherentes al diseño multithreading.</span><span class="sxs-lookup"><span data-stu-id="36a5c-109">Describes how the Event-based Asynchronous Pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>  
  
 [<span data-ttu-id="36a5c-110">Implementación del modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="36a5c-110">Implementing the Event-based Asynchronous Pattern</span></span>](implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="36a5c-111">Describe la manera estándar de empaquetar una clase que tiene características asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="36a5c-111">Describes the standardized way to package a class that has asynchronous features.</span></span>  
  
 [<span data-ttu-id="36a5c-112">Procedimientos recomendados para implementar el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="36a5c-112">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="36a5c-113">Describe los requisitos para exponer las características asincrónicas según el Modelo asincrónico basado en evento.</span><span class="sxs-lookup"><span data-stu-id="36a5c-113">Describes the requirements for exposing asynchronous features according to the Event-based Asynchronous Pattern.</span></span>  
  
 [<span data-ttu-id="36a5c-114">Decisión de cuándo implementar el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="36a5c-114">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>](deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="36a5c-115">En este tema se describe cómo determinar el momento conveniente para implementar el modelo asincrónico basado en eventos en lugar del modelo <xref:System.IAsyncResult>, representado por el [modelo de programación asincrónica (APM)](asynchronous-programming-model-apm.md).</span><span class="sxs-lookup"><span data-stu-id="36a5c-115">Describes how to determine when you should choose to implement the Event-based Asynchronous Pattern instead of the <xref:System.IAsyncResult> pattern represented by the [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md)</span></span>
  
 [<span data-ttu-id="36a5c-116">Implementar un componente que admita el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="36a5c-116">How to: Implement a Component That Supports the Event-based Asynchronous Pattern</span></span>](component-that-supports-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="36a5c-117">En este tema se describe cómo crear un componente que implemente el modelo asincrónico basado en eventos.</span><span class="sxs-lookup"><span data-stu-id="36a5c-117">Describes how to create a component that implements the Event-based Asynchronous Pattern.</span></span> <span data-ttu-id="36a5c-118">Se implementa utilizando las clases del asistente del espacio de nombres <xref:System.ComponentModel?displayProperty=nameWithType>, que garantiza que el componente funciona correctamente bajo cualquier modelo de aplicación.</span><span class="sxs-lookup"><span data-stu-id="36a5c-118">It is implemented using helper classes from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace, which ensures that the component works correctly under any application model.</span></span>  

 [<span data-ttu-id="36a5c-119">Implementar un cliente en un modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="36a5c-119">How to: Implement a Client of the Event-based Asynchronous Pattern</span></span>](how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="36a5c-120">En este tema se describe cómo crear un cliente que use un componente que implemente el modelo asincrónico basado en eventos.</span><span class="sxs-lookup"><span data-stu-id="36a5c-120">Describes how to create a client that uses a component that implements the Event-based Asynchronous Pattern.</span></span>
  
 [<span data-ttu-id="36a5c-121">Uso de componentes que admitan el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="36a5c-121">How to: Use Components That Support the Event-based Asynchronous Pattern</span></span>](how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="36a5c-122">Describe cómo utilizar un componente que admite el Modelo asincrónico basado en evento.</span><span class="sxs-lookup"><span data-stu-id="36a5c-122">Describes how to use a component that supports the Event-based Asynchronous Pattern.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="36a5c-123">Referencia</span><span class="sxs-lookup"><span data-stu-id="36a5c-123">Reference</span></span>

 <xref:System.ComponentModel.AsyncOperation>  
 <span data-ttu-id="36a5c-124">Describe la clase <xref:System.ComponentModel.AsyncOperation> y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="36a5c-124">Describes the <xref:System.ComponentModel.AsyncOperation> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <span data-ttu-id="36a5c-125">Describe la clase <xref:System.ComponentModel.AsyncOperationManager> y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="36a5c-125">Describes the <xref:System.ComponentModel.AsyncOperationManager> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="36a5c-126">Describe el componente <xref:System.ComponentModel.BackgroundWorker> y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="36a5c-126">Describes the <xref:System.ComponentModel.BackgroundWorker> component and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="36a5c-127">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="36a5c-127">Related Sections</span></span>

 [<span data-ttu-id="36a5c-128">Biblioteca TPL</span><span class="sxs-lookup"><span data-stu-id="36a5c-128">Task Parallel Library (TPL)</span></span>](../parallel-programming/task-parallel-library-tpl.md)  
 <span data-ttu-id="36a5c-129">Describe un modelo de programación para operaciones asincrónicas y paralelas.</span><span class="sxs-lookup"><span data-stu-id="36a5c-129">Describes a programming model for asynchronous and parallel operations.</span></span>  
  
 [<span data-ttu-id="36a5c-130">Subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="36a5c-130">Threading</span></span>](../../../docs/standard/threading/index.md)  
 <span data-ttu-id="36a5c-131">En este tema se describen las características de multithreading en .NET.</span><span class="sxs-lookup"><span data-stu-id="36a5c-131">Describes multithreading features in .NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36a5c-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="36a5c-132">See also</span></span>

- [<span data-ttu-id="36a5c-133">Procedimientos recomendados para el subprocesamiento administrado</span><span class="sxs-lookup"><span data-stu-id="36a5c-133">Managed Threading Best Practices</span></span>](../threading/managed-threading-best-practices.md)
- [<span data-ttu-id="36a5c-134">Eventos</span><span class="sxs-lookup"><span data-stu-id="36a5c-134">Events</span></span>](../events/index.md)
- <span data-ttu-id="36a5c-135">[Asynchronous Programming Design Patterns](index.md) (Patrones de diseño para programación asincrónica)</span><span class="sxs-lookup"><span data-stu-id="36a5c-135">[Asynchronous Programming Design Patterns](index.md)</span></span>
