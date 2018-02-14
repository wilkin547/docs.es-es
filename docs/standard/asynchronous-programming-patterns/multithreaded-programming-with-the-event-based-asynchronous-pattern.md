---
title: "Programación multiproceso con el modelo asincrónico basado en eventos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: 958d6617-5e70-4b36-b5db-63c16dc35e43
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 557d639cc8a4e7ade2cfbd1f5d7264bca226d273
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="multithreaded-programming-with-the-event-based-asynchronous-pattern"></a><span data-ttu-id="a08e8-102">Programación multiproceso con el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="a08e8-102">Multithreaded Programming with the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="a08e8-103">Hay varias maneras de exponer las características asincrónicas al código de cliente.</span><span class="sxs-lookup"><span data-stu-id="a08e8-103">There are a number of ways to expose asynchronous features to client code.</span></span> <span data-ttu-id="a08e8-104">El modelo asincrónico basado en eventos prescribe la manera recomendada para que las clases presenten comportamiento asincrónico.</span><span class="sxs-lookup"><span data-stu-id="a08e8-104">The Event-based Asynchronous Pattern prescribes the recommended way for classes to present asynchronous behavior.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a08e8-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a08e8-105">In This Section</span></span>  
 [<span data-ttu-id="a08e8-106">Información general sobre el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="a08e8-106">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 <span data-ttu-id="a08e8-107">Describe cómo el Modelo asincrónico basado en evento pone a su disposición las ventajas de las aplicaciones multithreading ocultando muchos de los problemas complejos inherentes al diseño multithreading.</span><span class="sxs-lookup"><span data-stu-id="a08e8-107">Describes how the Event-based Asynchronous Pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>  
  
 [<span data-ttu-id="a08e8-108">Implementación del modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="a08e8-108">Implementing the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="a08e8-109">Describe la manera estándar de empaquetar una clase que tiene características asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="a08e8-109">Describes the standardized way to package a class that has asynchronous features.</span></span>  
  
 [<span data-ttu-id="a08e8-110">Procedimientos recomendados para implementar el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="a08e8-110">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="a08e8-111">Describe los requisitos para exponer las características asincrónicas según el Modelo asincrónico basado en evento.</span><span class="sxs-lookup"><span data-stu-id="a08e8-111">Describes the requirements for exposing asynchronous features according to the Event-based Asynchronous Pattern.</span></span>  
  
 [<span data-ttu-id="a08e8-112">Decisión de cuándo implementar el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="a08e8-112">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="a08e8-113">Describe cómo determinar cuándo se debería decidir implementar el Modelo asincrónico basado en evento en lugar del modelo <xref:System.IAsyncResult>.</span><span class="sxs-lookup"><span data-stu-id="a08e8-113">Describes how to determine when you should choose to implement the Event-based Asynchronous Pattern instead of the <xref:System.IAsyncResult> pattern.</span></span>  
  
 [<span data-ttu-id="a08e8-114">Tutorial: Implementación de un componente que admita el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="a08e8-114">Walkthrough: Implementing a Component That Supports the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="a08e8-115">Explica cómo crear un componente que implementa el Modelo asincrónico basado en evento.</span><span class="sxs-lookup"><span data-stu-id="a08e8-115">Illustrates how to create a component that implements the Event-based Asynchronous Pattern.</span></span> <span data-ttu-id="a08e8-116">Se implementa utilizando las clases auxiliares del espacio de nombres <xref:System.ComponentModel?displayProperty=nameWithType>, que garantiza que el componente funciona correctamente bajo cualquier modelo de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a08e8-116">It is implemented using helper classes from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace, which ensures that the component works correctly under any application model.</span></span>  
  
 [<span data-ttu-id="a08e8-117">Uso de componentes que admitan el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="a08e8-117">How to: Use Components That Support the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="a08e8-118">Describe cómo utilizar un componente que admite el Modelo asincrónico basado en evento.</span><span class="sxs-lookup"><span data-stu-id="a08e8-118">Describes how to use a component that supports the Event-based Asynchronous Pattern.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a08e8-119">Referencia</span><span class="sxs-lookup"><span data-stu-id="a08e8-119">Reference</span></span>  
 <xref:System.ComponentModel.AsyncOperation>  
 <span data-ttu-id="a08e8-120">Describe la clase <xref:System.ComponentModel.AsyncOperation> y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="a08e8-120">Describes the <xref:System.ComponentModel.AsyncOperation> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <span data-ttu-id="a08e8-121">Describe la clase <xref:System.ComponentModel.AsyncOperationManager> y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="a08e8-121">Describes the <xref:System.ComponentModel.AsyncOperationManager> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="a08e8-122">Describe el componente <xref:System.ComponentModel.BackgroundWorker> y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="a08e8-122">Describes the <xref:System.ComponentModel.BackgroundWorker> component and has links to all its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a08e8-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="a08e8-123">See Also</span></span>  
 [<span data-ttu-id="a08e8-124">Procedimientos recomendados para el subprocesamiento administrado</span><span class="sxs-lookup"><span data-stu-id="a08e8-124">Managed Threading Best Practices</span></span>](../../../docs/standard/threading/managed-threading-best-practices.md)  
 [<span data-ttu-id="a08e8-125">Eventos</span><span class="sxs-lookup"><span data-stu-id="a08e8-125">Events</span></span>](../../../docs/standard/events/index.md)  
 [<span data-ttu-id="a08e8-126">Subprocesamiento múltiple en componentes</span><span class="sxs-lookup"><span data-stu-id="a08e8-126">Multithreading in Components</span></span>](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)  
 [<span data-ttu-id="a08e8-127">Modelo asincrónico basado en eventos (EAP)</span><span class="sxs-lookup"><span data-stu-id="a08e8-127">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
