---
title: Eventos (Guía de programación de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
caps.latest.revision: 43
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 72563b9e37c26257a2bf5939f63ece050ec003ab
ms.sourcegitcommit: 75a180acb5d8a2dbd4a52915ce8e980749fb1d05
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2018
---
# <a name="events-c-programming-guide"></a><span data-ttu-id="89096-102">Eventos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="89096-102">Events (C# Programming Guide)</span></span>
<span data-ttu-id="89096-103">Cuando ocurre algo interesante, los eventos habilitan una [clase](../../../csharp/language-reference/keywords/class.md) u objeto para notificarlo a otras clases u objetos.</span><span class="sxs-lookup"><span data-stu-id="89096-103">Events enable a [class](../../../csharp/language-reference/keywords/class.md) or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="89096-104">La clase que envía (o *genera*) el evento recibe el nombre de *publicador* y las clases que reciben (o *controlan*) el evento se denominan *suscriptores*.</span><span class="sxs-lookup"><span data-stu-id="89096-104">The class that sends (or *raises*) the event is called the *publisher* and the classes that receive (or *handle*) the event are called *subscribers*.</span></span>  
  
 <span data-ttu-id="89096-105">En una aplicación web o una aplicación de Windows Forms en C# típica, se puede suscribir a eventos generados por controles, como botones y cuadros de lista.</span><span class="sxs-lookup"><span data-stu-id="89096-105">In a typical C# Windows Forms or Web application, you subscribe to events raised by controls such as buttons and list boxes.</span></span> <span data-ttu-id="89096-106">Puede usar el entorno de desarrollo integrado (IDE) de [!INCLUDE[csprcs](~/includes/csprcs-md.md)] para examinar los eventos que publica un control y seleccionar los que quiera administrar.</span><span class="sxs-lookup"><span data-stu-id="89096-106">You can use the [!INCLUDE[csprcs](~/includes/csprcs-md.md)] integrated development environment (IDE) to browse the events that a control publishes and select the ones that you want to handle.</span></span> <span data-ttu-id="89096-107">El IDE agrega automáticamente un método de controlador de eventos vacío y el código para suscribirse al evento.</span><span class="sxs-lookup"><span data-stu-id="89096-107">The IDE automatically adds an empty event handler method and the code to subscribe to the event.</span></span> <span data-ttu-id="89096-108">Para obtener más información, vea [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md) (Cómo: Suscribir y cancelar la suscripción a eventos [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="89096-108">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>  
  
## <a name="events-overview"></a><span data-ttu-id="89096-109">Información general sobre eventos</span><span class="sxs-lookup"><span data-stu-id="89096-109">Events Overview</span></span>  
 <span data-ttu-id="89096-110">Los eventos tienen las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="89096-110">Events have the following properties:</span></span>  
  
-   <span data-ttu-id="89096-111">El publicador determina el momento en el que se genera un evento; los suscriptores determinan la acción que se lleva a cabo en respuesta al evento.</span><span class="sxs-lookup"><span data-stu-id="89096-111">The publisher determines when an event is raised; the subscribers determine what action is taken in response to the event.</span></span>  
  
-   <span data-ttu-id="89096-112">Un evento puede tener varios suscriptores.</span><span class="sxs-lookup"><span data-stu-id="89096-112">An event can have multiple subscribers.</span></span> <span data-ttu-id="89096-113">Un suscriptor puede controlar varios eventos de varios publicadores.</span><span class="sxs-lookup"><span data-stu-id="89096-113">A subscriber can handle multiple events from multiple publishers.</span></span>  
  
-   <span data-ttu-id="89096-114">Nunca se generan eventos que no tienen suscriptores.</span><span class="sxs-lookup"><span data-stu-id="89096-114">Events that have no subscribers are never raised.</span></span>  
  
-   <span data-ttu-id="89096-115">Los eventos se suelen usar para indicar acciones del usuario, como los clics de los botones o las selecciones de menú en las interfaces gráficas de usuario.</span><span class="sxs-lookup"><span data-stu-id="89096-115">Events are typically used to signal user actions such as button clicks or menu selections in graphical user interfaces.</span></span>  
  
-   <span data-ttu-id="89096-116">Cuando un evento tiene varios suscriptores, los controladores de eventos se invocan sincrónicamente cuando se genera un evento.</span><span class="sxs-lookup"><span data-stu-id="89096-116">When an event has multiple subscribers, the event handlers are invoked synchronously when an event is raised.</span></span> <span data-ttu-id="89096-117">Para invocar eventos de forma asincrónica, consulte [Calling Synchronous Methods Asynchronously](../../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span><span class="sxs-lookup"><span data-stu-id="89096-117">To invoke events asynchronously, see [Calling Synchronous Methods Asynchronously](../../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span></span>  
  
-   <span data-ttu-id="89096-118">En la biblioteca de clases [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] , los eventos se basan en el delegado <xref:System.EventHandler> y en la clase base <xref:System.EventArgs> .</span><span class="sxs-lookup"><span data-stu-id="89096-118">In the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] class library, events are based on the <xref:System.EventHandler> delegate and the <xref:System.EventArgs> base class.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="89096-119">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="89096-119">Related Sections</span></span>  
 <span data-ttu-id="89096-120">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="89096-120">For more information, see:</span></span>  
  
-   [<span data-ttu-id="89096-121">Cómo: Suscribir y cancelar la suscripción a eventos</span><span class="sxs-lookup"><span data-stu-id="89096-121">How to: Subscribe to and Unsubscribe from Events</span></span>](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)  
  
-   [<span data-ttu-id="89096-122">Cómo: Publicar eventos que cumplan las directrices de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="89096-122">How to: Publish Events that Conform to .NET Framework Guidelines</span></span>](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)  
  
-   [<span data-ttu-id="89096-123">Cómo: Producir eventos de una clase base en clases derivadas</span><span class="sxs-lookup"><span data-stu-id="89096-123">How to: Raise Base Class Events in Derived Classes</span></span>](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)  
  
-   [<span data-ttu-id="89096-124">Cómo: Implementar eventos de interfaz</span><span class="sxs-lookup"><span data-stu-id="89096-124">How to:  Implement Interface Events</span></span>](../../../csharp/programming-guide/events/how-to-implement-interface-events.md)  
  
-   [<span data-ttu-id="89096-125">Sincronización de subprocesos</span><span class="sxs-lookup"><span data-stu-id="89096-125">Thread Synchronization</span></span>](../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)  
  
-   [<span data-ttu-id="89096-126">Cómo: Utilizar un diccionario para almacenar instancias de eventos</span><span class="sxs-lookup"><span data-stu-id="89096-126">How to: Use a Dictionary to Store Event Instances</span></span>](../../../csharp/programming-guide/events/how-to-use-a-dictionary-to-store-event-instances.md)  
  
-   [<span data-ttu-id="89096-127">Cómo: Implementar descriptores de acceso de eventos personalizados</span><span class="sxs-lookup"><span data-stu-id="89096-127">How to: Implement Custom Event Accessors</span></span>](../../../csharp/programming-guide/events/how-to-implement-custom-event-accessors.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="89096-128">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="89096-128">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="featured-book-chapters"></a><span data-ttu-id="89096-129">Capítulos destacados del libro</span><span class="sxs-lookup"><span data-stu-id="89096-129">Featured Book Chapters</span></span>  
 <span data-ttu-id="89096-130">[Delegates, Events, and Lambda Expressions](https://msdn.microsoft.com/library/orm-9780596516109-03-09.aspx) (Delegados, eventos y expresiones lambda) en [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://msdn.microsoft.com/library/orm-9780596516109-03.aspx)</span><span class="sxs-lookup"><span data-stu-id="89096-130">[Delegates, Events, and Lambda Expressions](https://msdn.microsoft.com/library/orm-9780596516109-03-09.aspx) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://msdn.microsoft.com/library/orm-9780596516109-03.aspx)</span></span>  
  
 <span data-ttu-id="89096-131">[Delegates and Events](https://msdn.microsoft.com/library/orm-9780596521066-01-17.aspx) (Delegados, eventos y expresiones lambda) en [Learning C# 3.0: Master the fundamentals of C# 3.0](https://msdn.microsoft.com/library/orm-9780596521066-01.aspx)</span><span class="sxs-lookup"><span data-stu-id="89096-131">[Delegates and Events](https://msdn.microsoft.com/library/orm-9780596521066-01-17.aspx) in [Learning C# 3.0: Master the fundamentals of C# 3.0](https://msdn.microsoft.com/library/orm-9780596521066-01.aspx)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89096-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="89096-132">See Also</span></span>  
 <xref:System.EventHandler>  
 [<span data-ttu-id="89096-133">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="89096-133">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="89096-134">Delegados</span><span class="sxs-lookup"><span data-stu-id="89096-134">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
 [<span data-ttu-id="89096-135">Crear controladores de eventos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="89096-135">Creating Event Handlers in Windows Forms</span></span>](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [<span data-ttu-id="89096-136">Programación multiproceso con el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="89096-136">Multithreaded Programming with the Event-based Asynchronous Pattern</span></span>](../../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)
