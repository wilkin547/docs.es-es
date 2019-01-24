---
title: 'Eventos: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
  - 'classes [C#], events'
  - 'C# language, events'
  - 'events [C#]'
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
---
# <a name="events-c-programming-guide"></a><span data-ttu-id="05751-102">Eventos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="05751-102">Events (C# Programming Guide)</span></span>
<span data-ttu-id="05751-103">Cuando ocurre algo interesante, los eventos habilitan una [clase](../../../csharp/language-reference/keywords/class.md) u objeto para notificarlo a otras clases u objetos.</span><span class="sxs-lookup"><span data-stu-id="05751-103">Events enable a [class](../../../csharp/language-reference/keywords/class.md) or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="05751-104">La clase que envía (o *genera*) el evento recibe el nombre de *publicador* y las clases que reciben (o *controlan*) el evento se denominan *suscriptores*.</span><span class="sxs-lookup"><span data-stu-id="05751-104">The class that sends (or *raises*) the event is called the *publisher* and the classes that receive (or *handle*) the event are called *subscribers*.</span></span>  
  
 <span data-ttu-id="05751-105">En una aplicación web o una aplicación de Windows Forms en C# típica, se puede suscribir a eventos generados por controles, como botones y cuadros de lista.</span><span class="sxs-lookup"><span data-stu-id="05751-105">In a typical C# Windows Forms or Web application, you subscribe to events raised by controls such as buttons and list boxes.</span></span> <span data-ttu-id="05751-106">Puede usar el entorno de desarrollo integrado (IDE) de Visual C# para examinar los eventos que publica un control y seleccionar los que quiera administrar.</span><span class="sxs-lookup"><span data-stu-id="05751-106">You can use the Visual C# integrated development environment (IDE) to browse the events that a control publishes and select the ones that you want to handle.</span></span> <span data-ttu-id="05751-107">El IDE proporciona una forma sencilla de agregar automáticamente un método de controlador de eventos vacío y el código para suscribirse al evento.</span><span class="sxs-lookup"><span data-stu-id="05751-107">The IDE provides an easy way to automatically add an empty event handler method and the code to subscribe to the event.</span></span> <span data-ttu-id="05751-108">Para obtener más información, vea [Cómo: Suscribir y cancelar la suscripción a eventos](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)</span><span class="sxs-lookup"><span data-stu-id="05751-108">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>  
  
## <a name="events-overview"></a><span data-ttu-id="05751-109">Información general sobre eventos</span><span class="sxs-lookup"><span data-stu-id="05751-109">Events Overview</span></span>  
 <span data-ttu-id="05751-110">Los eventos tienen las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="05751-110">Events have the following properties:</span></span>  
  
-   <span data-ttu-id="05751-111">El publicador determina el momento en el que se genera un evento; los suscriptores determinan la acción que se lleva a cabo en respuesta al evento.</span><span class="sxs-lookup"><span data-stu-id="05751-111">The publisher determines when an event is raised; the subscribers determine what action is taken in response to the event.</span></span>  
  
-   <span data-ttu-id="05751-112">Un evento puede tener varios suscriptores.</span><span class="sxs-lookup"><span data-stu-id="05751-112">An event can have multiple subscribers.</span></span> <span data-ttu-id="05751-113">Un suscriptor puede controlar varios eventos de varios publicadores.</span><span class="sxs-lookup"><span data-stu-id="05751-113">A subscriber can handle multiple events from multiple publishers.</span></span>  
  
-   <span data-ttu-id="05751-114">Nunca se generan eventos que no tienen suscriptores.</span><span class="sxs-lookup"><span data-stu-id="05751-114">Events that have no subscribers are never raised.</span></span>  
  
-   <span data-ttu-id="05751-115">Los eventos se suelen usar para indicar acciones del usuario, como los clics de los botones o las selecciones de menú en las interfaces gráficas de usuario.</span><span class="sxs-lookup"><span data-stu-id="05751-115">Events are typically used to signal user actions such as button clicks or menu selections in graphical user interfaces.</span></span>  
  
-   <span data-ttu-id="05751-116">Cuando un evento tiene varios suscriptores, los controladores de eventos se invocan sincrónicamente cuando se genera un evento.</span><span class="sxs-lookup"><span data-stu-id="05751-116">When an event has multiple subscribers, the event handlers are invoked synchronously when an event is raised.</span></span> <span data-ttu-id="05751-117">Para invocar eventos de forma asincrónica, consulte [Calling Synchronous Methods Asynchronously](../../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span><span class="sxs-lookup"><span data-stu-id="05751-117">To invoke events asynchronously, see [Calling Synchronous Methods Asynchronously](../../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span></span>  
  
-   <span data-ttu-id="05751-118">En la biblioteca de clases [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] , los eventos se basan en el delegado <xref:System.EventHandler> y en la clase base <xref:System.EventArgs> .</span><span class="sxs-lookup"><span data-stu-id="05751-118">In the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] class library, events are based on the <xref:System.EventHandler> delegate and the <xref:System.EventArgs> base class.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="05751-119">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="05751-119">Related Sections</span></span>  
 <span data-ttu-id="05751-120">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="05751-120">For more information, see:</span></span>  
  
-   [<span data-ttu-id="05751-121">Cómo: Suscribir y cancelar la suscripción a eventos</span><span class="sxs-lookup"><span data-stu-id="05751-121">How to: Subscribe to and Unsubscribe from Events</span></span>](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)  
  
-   [<span data-ttu-id="05751-122">Cómo: Publicar eventos que cumplan las directrices de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="05751-122">How to: Publish Events that Conform to .NET Framework Guidelines</span></span>](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)  
  
-   [<span data-ttu-id="05751-123">Cómo: Producir eventos de una clase base en clases derivadas</span><span class="sxs-lookup"><span data-stu-id="05751-123">How to: Raise Base Class Events in Derived Classes</span></span>](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)  
  
-   [<span data-ttu-id="05751-124">Cómo:  Implementar eventos de interfaz</span><span class="sxs-lookup"><span data-stu-id="05751-124">How to:  Implement Interface Events</span></span>](../../../csharp/programming-guide/events/how-to-implement-interface-events.md)  
  
-   [<span data-ttu-id="05751-125">Cómo: Utilizar un diccionario para almacenar instancias de eventos</span><span class="sxs-lookup"><span data-stu-id="05751-125">How to: Use a Dictionary to Store Event Instances</span></span>](../../../csharp/programming-guide/events/how-to-use-a-dictionary-to-store-event-instances.md)  
  
-   <span data-ttu-id="05751-126">[Cómo: Implementar descriptores de acceso de eventos personalizados](../../../csharp/programming-guide/events/how-to-implement-custom-event-accessors.md).</span><span class="sxs-lookup"><span data-stu-id="05751-126">[How to: Implement Custom Event Accessors](../../../csharp/programming-guide/events/how-to-implement-custom-event-accessors.md)</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="05751-127">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="05751-127">C# Language Specification</span></span>  

<span data-ttu-id="05751-128">Para obtener más información, consulte la sección [Eventos](~/_csharplang/spec/classes.md#events) de [Especificación del lenguaje C#](../../language-reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="05751-128">For more information, see [Events](~/_csharplang/spec/classes.md#events) in the [C# Language Specification](../../language-reference/language-specification/index.md).</span></span> <span data-ttu-id="05751-129">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="05751-129">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="featured-book-chapters"></a><span data-ttu-id="05751-130">Capítulos destacados del libro</span><span class="sxs-lookup"><span data-stu-id="05751-130">Featured Book Chapters</span></span>  
 <span data-ttu-id="05751-131">[Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) (Delegados, eventos y expresiones lambda) en [C# 3.0 Cookbook, Tercera edición: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29) (Más de 250 soluciones para programadores de C# 3.0)</span><span class="sxs-lookup"><span data-stu-id="05751-131">[Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)</span></span>  
  
 <span data-ttu-id="05751-132">[Delegates and Events](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652490%28v=orm.10%29) (Delegados y eventos) en [Learning C# 3.0: Master the fundamentals of C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v=orm.10%29)</span><span class="sxs-lookup"><span data-stu-id="05751-132">[Delegates and Events](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652490%28v=orm.10%29) in [Learning C# 3.0: Master the fundamentals of C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v=orm.10%29)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05751-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="05751-133">See also</span></span>

- <xref:System.EventHandler>
- [<span data-ttu-id="05751-134">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="05751-134">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="05751-135">Delegados</span><span class="sxs-lookup"><span data-stu-id="05751-135">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
- [<span data-ttu-id="05751-136">Crear controladores de eventos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="05751-136">Creating Event Handlers in Windows Forms</span></span>](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)
