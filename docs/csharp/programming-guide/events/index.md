---
title: 'Eventos: Guía de programación de C#'
description: Obtenga más información sobre los eventos. Cuando ocurre algo interesante, los eventos habilitan una clase u objeto para notificarlo a otras clases u objetos.
ms.date: 07/20/2015
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
ms.openlocfilehash: 86ded81de4b9191c50b993c08b0e87712ff69020
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90545498"
---
# <a name="events-c-programming-guide"></a><span data-ttu-id="ccafd-104">Eventos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="ccafd-104">Events (C# Programming Guide)</span></span>
<span data-ttu-id="ccafd-105">Cuando ocurre algo interesante, los eventos habilitan una [clase](../../language-reference/keywords/class.md) u objeto para notificarlo a otras clases u objetos.</span><span class="sxs-lookup"><span data-stu-id="ccafd-105">Events enable a [class](../../language-reference/keywords/class.md) or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="ccafd-106">La clase que envía (o *genera*) el evento recibe el nombre de *publicador* y las clases que reciben (o *controlan*) el evento se denominan *suscriptores*.</span><span class="sxs-lookup"><span data-stu-id="ccafd-106">The class that sends (or *raises*) the event is called the *publisher* and the classes that receive (or *handle*) the event are called *subscribers*.</span></span>  
  
<span data-ttu-id="ccafd-107">En una aplicación web o una aplicación de Windows Forms en C# típica, se puede suscribir a eventos generados por controles, como botones y cuadros de lista.</span><span class="sxs-lookup"><span data-stu-id="ccafd-107">In a typical C# Windows Forms or Web application, you subscribe to events raised by controls such as buttons and list boxes.</span></span> <span data-ttu-id="ccafd-108">Puede usar el entorno de desarrollo integrado (IDE) de Visual C# para examinar los eventos que publica un control y seleccionar los que quiera administrar.</span><span class="sxs-lookup"><span data-stu-id="ccafd-108">You can use the Visual C# integrated development environment (IDE) to browse the events that a control publishes and select the ones that you want to handle.</span></span> <span data-ttu-id="ccafd-109">El IDE proporciona una forma sencilla de agregar automáticamente un método de controlador de eventos vacío y el código para suscribirse al evento.</span><span class="sxs-lookup"><span data-stu-id="ccafd-109">The IDE provides an easy way to automatically add an empty event handler method and the code to subscribe to the event.</span></span> <span data-ttu-id="ccafd-110">Para obtener más información, vea [Procedimiento para suscribir y cancelar la suscripción a eventos](./how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="ccafd-110">For more information, see [How to subscribe to and unsubscribe from events](./how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>
  
## <a name="events-overview"></a><span data-ttu-id="ccafd-111">Información general sobre eventos</span><span class="sxs-lookup"><span data-stu-id="ccafd-111">Events Overview</span></span>  
 <span data-ttu-id="ccafd-112">Los eventos tienen las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="ccafd-112">Events have the following properties:</span></span>  
  
- <span data-ttu-id="ccafd-113">El publicador determina el momento en el que se genera un evento; los suscriptores determinan la acción que se lleva a cabo en respuesta al evento.</span><span class="sxs-lookup"><span data-stu-id="ccafd-113">The publisher determines when an event is raised; the subscribers determine what action is taken in response to the event.</span></span>  
  
- <span data-ttu-id="ccafd-114">Un evento puede tener varios suscriptores.</span><span class="sxs-lookup"><span data-stu-id="ccafd-114">An event can have multiple subscribers.</span></span> <span data-ttu-id="ccafd-115">Un suscriptor puede controlar varios eventos de varios publicadores.</span><span class="sxs-lookup"><span data-stu-id="ccafd-115">A subscriber can handle multiple events from multiple publishers.</span></span>  
  
- <span data-ttu-id="ccafd-116">Nunca se generan eventos que no tienen suscriptores.</span><span class="sxs-lookup"><span data-stu-id="ccafd-116">Events that have no subscribers are never raised.</span></span>  
  
- <span data-ttu-id="ccafd-117">Los eventos se suelen usar para indicar acciones del usuario, como los clics de los botones o las selecciones de menú en las interfaces gráficas de usuario.</span><span class="sxs-lookup"><span data-stu-id="ccafd-117">Events are typically used to signal user actions such as button clicks or menu selections in graphical user interfaces.</span></span>  
  
- <span data-ttu-id="ccafd-118">Cuando un evento tiene varios suscriptores, los controladores de eventos se invocan sincrónicamente cuando se genera un evento.</span><span class="sxs-lookup"><span data-stu-id="ccafd-118">When an event has multiple subscribers, the event handlers are invoked synchronously when an event is raised.</span></span> <span data-ttu-id="ccafd-119">Para invocar eventos de forma asincrónica, consulte [Llamar a métodos sincrónicos de forma asincrónica](../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span><span class="sxs-lookup"><span data-stu-id="ccafd-119">To invoke events asynchronously, see [Calling Synchronous Methods Asynchronously](../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span></span>  
  
- <span data-ttu-id="ccafd-120">En la biblioteca de clases de .NET, los eventos se basan en el delegado <xref:System.EventHandler> y en la clase base <xref:System.EventArgs>.</span><span class="sxs-lookup"><span data-stu-id="ccafd-120">In the .NET class library, events are based on the <xref:System.EventHandler> delegate and the <xref:System.EventArgs> base class.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ccafd-121">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="ccafd-121">Related Sections</span></span>  
 <span data-ttu-id="ccafd-122">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="ccafd-122">For more information, see:</span></span>  
  
- [<span data-ttu-id="ccafd-123">Procedimiento para suscribir y cancelar la suscripción a eventos</span><span class="sxs-lookup"><span data-stu-id="ccafd-123">How to subscribe to and unsubscribe from events</span></span>](./how-to-subscribe-to-and-unsubscribe-from-events.md)

- [<span data-ttu-id="ccafd-124">Procedimiento para publicar eventos que cumplan las instrucciones de .NET</span><span class="sxs-lookup"><span data-stu-id="ccafd-124">How to publish events that conform to .NET Guidelines</span></span>](./how-to-publish-events-that-conform-to-net-framework-guidelines.md)

- [<span data-ttu-id="ccafd-125">Procedimiento para generar eventos de una clase base en clases derivadas</span><span class="sxs-lookup"><span data-stu-id="ccafd-125">How to raise base class events in derived classes</span></span>](./how-to-raise-base-class-events-in-derived-classes.md)

- [<span data-ttu-id="ccafd-126">Procedimiento para implementar eventos de interfaz</span><span class="sxs-lookup"><span data-stu-id="ccafd-126">How to implement interface events</span></span>](./how-to-implement-interface-events.md)

- [<span data-ttu-id="ccafd-127">Procedimiento para implementar descriptores de acceso de eventos personalizados</span><span class="sxs-lookup"><span data-stu-id="ccafd-127">How to implement custom event accessors</span></span>](./how-to-implement-custom-event-accessors.md)

## <a name="c-language-specification"></a><span data-ttu-id="ccafd-128">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="ccafd-128">C# Language Specification</span></span>  

<span data-ttu-id="ccafd-129">Para obtener más información, consulte la sección [Eventos](~/_csharplang/spec/classes.md#events) de [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="ccafd-129">For more information, see [Events](~/_csharplang/spec/classes.md#events) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="ccafd-130">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="ccafd-130">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="featured-book-chapters"></a><span data-ttu-id="ccafd-131">Capítulos destacados del libro</span><span class="sxs-lookup"><span data-stu-id="ccafd-131">Featured Book Chapters</span></span>  
 <span data-ttu-id="ccafd-132">[Delegates, Events, and Lambda Expressions](/previous-versions/visualstudio/visual-studio-2008/ff518994(v=orm.10)) (Delegados, eventos y expresiones lambda) en [C# 3.0 Cookbook, Tercera edición: More than 250 solutions for C# 3.0 programmers](/previous-versions/visualstudio/visual-studio-2008/ff518995(v=orm.10)) (Más de 250 soluciones para programadores de C# 3.0)</span><span class="sxs-lookup"><span data-stu-id="ccafd-132">[Delegates, Events, and Lambda Expressions](/previous-versions/visualstudio/visual-studio-2008/ff518994(v=orm.10)) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](/previous-versions/visualstudio/visual-studio-2008/ff518995(v=orm.10))</span></span>  
  
 <span data-ttu-id="ccafd-133">[Delegates and Events](/previous-versions/visualstudio/visual-studio-2008/ff652490(v=orm.10)) (Delegados y eventos) en [Learning C# 3.0: Master the fundamentals of C# 3.0](/previous-versions/visualstudio/visual-studio-2008/ff652493(v=orm.10))</span><span class="sxs-lookup"><span data-stu-id="ccafd-133">[Delegates and Events](/previous-versions/visualstudio/visual-studio-2008/ff652490(v=orm.10)) in [Learning C# 3.0: Master the fundamentals of C# 3.0](/previous-versions/visualstudio/visual-studio-2008/ff652493(v=orm.10))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccafd-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="ccafd-134">See also</span></span>

- <xref:System.EventHandler>
- [<span data-ttu-id="ccafd-135">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="ccafd-135">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ccafd-136">Delegados</span><span class="sxs-lookup"><span data-stu-id="ccafd-136">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="ccafd-137">Crear controladores de eventos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ccafd-137">Creating Event Handlers in Windows Forms</span></span>](/dotnet/desktop/winforms/creating-event-handlers-in-windows-forms)
