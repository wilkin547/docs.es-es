---
title: Patrón asincrónico basado en eventos (EAP)
ms.date: 07/23/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous calls
- asynchronous programming, design patterns
- asynchronous programming
ms.assetid: c6baed9f-2a25-4728-9a9a-53b7b14840cf
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be4935d74affa227386aa6c63dad13e7e2f7d3dd
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44262651"
---
# <a name="event-based-asynchronous-pattern-eap"></a><span data-ttu-id="57183-102">Patrón asincrónico basado en eventos (EAP)</span><span class="sxs-lookup"><span data-stu-id="57183-102">Event-based Asynchronous Pattern (EAP)</span></span>

<span data-ttu-id="57183-103">Hay varias maneras de exponer las características asincrónicas al código de cliente.</span><span class="sxs-lookup"><span data-stu-id="57183-103">There are a number of ways to expose asynchronous features to client code.</span></span> <span data-ttu-id="57183-104">El modelo asincrónico basado en eventos prescribe una manera para que las clases presenten comportamiento asincrónico.</span><span class="sxs-lookup"><span data-stu-id="57183-104">The Event-based Asynchronous Pattern prescribes one way for classes to present asynchronous behavior.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="57183-105">A partir de .NET Framework 4, la biblioteca TPL (Task Parallel Library, biblioteca de procesamiento paralelo basado en tareas) ofrece un nuevo modelo para programación asincrónica y paralela.</span><span class="sxs-lookup"><span data-stu-id="57183-105">Starting with the .NET Framework 4, the Task Parallel Library provides a new model for asynchronous and parallel programming.</span></span> <span data-ttu-id="57183-106">Para obtener más información, vea [Biblioteca de procesamiento paralelo basado en tareas (TPL)](../parallel-programming/task-parallel-library-tpl.md) y [Modelo asincrónico basado en tareas (TAP)](task-based-asynchronous-pattern-tap.md).</span><span class="sxs-lookup"><span data-stu-id="57183-106">For more information, see [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md) and [Task-based Asynchronous Pattern (TAP)](task-based-asynchronous-pattern-tap.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="57183-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="57183-107">In This Section</span></span>

 [<span data-ttu-id="57183-108">Información general sobre el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="57183-108">Event-based Asynchronous Pattern Overview</span></span>](event-based-asynchronous-pattern-overview.md)  
 <span data-ttu-id="57183-109">Describe cómo el Modelo asincrónico basado en evento pone a su disposición las ventajas de las aplicaciones multithreading ocultando muchos de los problemas complejos inherentes al diseño multithreading.</span><span class="sxs-lookup"><span data-stu-id="57183-109">Describes how the Event-based Asynchronous Pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>  
  
 [<span data-ttu-id="57183-110">Implementación del modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="57183-110">Implementing the Event-based Asynchronous Pattern</span></span>](implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="57183-111">Describe la manera estándar de empaquetar una clase que tiene características asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="57183-111">Describes the standardized way to package a class that has asynchronous features.</span></span>  
  
 [<span data-ttu-id="57183-112">Procedimientos recomendados para implementar el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="57183-112">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="57183-113">Describe los requisitos para exponer las características asincrónicas según el Modelo asincrónico basado en evento.</span><span class="sxs-lookup"><span data-stu-id="57183-113">Describes the requirements for exposing asynchronous features according to the Event-based Asynchronous Pattern.</span></span>  
  
 [<span data-ttu-id="57183-114">Decisión de cuándo implementar el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="57183-114">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>](deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="57183-115">En este tema se describe cómo determinar el momento conveniente para implementar el modelo asincrónico basado en eventos en lugar del modelo <xref:System.IAsyncResult>, representado por el [modelo de programación asincrónica (APM)](asynchronous-programming-model-apm.md).</span><span class="sxs-lookup"><span data-stu-id="57183-115">Describes how to determine when you should choose to implement the Event-based Asynchronous Pattern instead of the <xref:System.IAsyncResult> pattern represented by the [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md)</span></span>
  
 [<span data-ttu-id="57183-116">Implementar un componente que admita el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="57183-116">How to: Implement a Component That Supports the Event-based Asynchronous Pattern</span></span>](component-that-supports-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="57183-117">En este tema se describe cómo crear un componente que implemente el modelo asincrónico basado en eventos.</span><span class="sxs-lookup"><span data-stu-id="57183-117">Describes how to create a component that implements the Event-based Asynchronous Pattern.</span></span> <span data-ttu-id="57183-118">Se implementa utilizando las clases auxiliares del espacio de nombres <xref:System.ComponentModel?displayProperty=nameWithType>, que garantiza que el componente funciona correctamente bajo cualquier modelo de aplicación.</span><span class="sxs-lookup"><span data-stu-id="57183-118">It is implemented using helper classes from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace, which ensures that the component works correctly under any application model.</span></span>  

 [<span data-ttu-id="57183-119">Implementar un cliente en un modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="57183-119">How to: Implement a Client of the Event-based Asynchronous Pattern</span></span>](how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="57183-120">En este tema se describe cómo crear un cliente que use un componente que implemente el modelo asincrónico basado en eventos.</span><span class="sxs-lookup"><span data-stu-id="57183-120">Describes how to create a client that uses a component that implements the Event-based Asynchronous Pattern.</span></span>
  
 [<span data-ttu-id="57183-121">Uso de componentes que admitan el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="57183-121">How to: Use Components That Support the Event-based Asynchronous Pattern</span></span>](how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="57183-122">Describe cómo utilizar un componente que admite el Modelo asincrónico basado en evento.</span><span class="sxs-lookup"><span data-stu-id="57183-122">Describes how to use a component that supports the Event-based Asynchronous Pattern.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="57183-123">Referencia</span><span class="sxs-lookup"><span data-stu-id="57183-123">Reference</span></span>

 <xref:System.ComponentModel.AsyncOperation>  
 <span data-ttu-id="57183-124">Describe la clase <xref:System.ComponentModel.AsyncOperation> y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="57183-124">Describes the <xref:System.ComponentModel.AsyncOperation> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <span data-ttu-id="57183-125">Describe la clase <xref:System.ComponentModel.AsyncOperationManager> y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="57183-125">Describes the <xref:System.ComponentModel.AsyncOperationManager> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="57183-126">Describe el componente <xref:System.ComponentModel.BackgroundWorker> y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="57183-126">Describes the <xref:System.ComponentModel.BackgroundWorker> component and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="57183-127">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="57183-127">Related Sections</span></span>

 [<span data-ttu-id="57183-128">Biblioteca TPL</span><span class="sxs-lookup"><span data-stu-id="57183-128">Task Parallel Library (TPL)</span></span>](../parallel-programming/task-parallel-library-tpl.md)  
 <span data-ttu-id="57183-129">Describe un modelo de programación para operaciones asincrónicas y paralelas.</span><span class="sxs-lookup"><span data-stu-id="57183-129">Describes a programming model for asynchronous and parallel operations.</span></span>  
  
 [<span data-ttu-id="57183-130">Subprocesamiento</span><span class="sxs-lookup"><span data-stu-id="57183-130">Threading</span></span>](../../../docs/standard/threading/index.md)  
 <span data-ttu-id="57183-131">En este tema se describen las características de multithreading en .NET.</span><span class="sxs-lookup"><span data-stu-id="57183-131">Describes multithreading features in .NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57183-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="57183-132">See also</span></span>

- [<span data-ttu-id="57183-133">Procedimientos recomendados para el subprocesamiento administrado</span><span class="sxs-lookup"><span data-stu-id="57183-133">Managed Threading Best Practices</span></span>](../threading/managed-threading-best-practices.md)  
- [<span data-ttu-id="57183-134">Eventos</span><span class="sxs-lookup"><span data-stu-id="57183-134">Events</span></span>](../events/index.md)  
- <span data-ttu-id="57183-135">[Asynchronous Programming Design Patterns](index.md) (Patrones de diseño para programación asincrónica)</span><span class="sxs-lookup"><span data-stu-id="57183-135">[Asynchronous Programming Design Patterns](index.md)</span></span>
