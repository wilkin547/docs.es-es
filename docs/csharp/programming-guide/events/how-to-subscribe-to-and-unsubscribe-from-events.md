---
title: 'Procedimiento Suscribir y cancelar la suscripción a eventos: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- event handlers [C#], creating
- Code Editor, event handlers
- events [C#], creating using the IDE
ms.assetid: 6319f39f-282c-4173-8a62-6c4657cf51cd
ms.openlocfilehash: 3df357cb15f7f77cefbf360dd9615ce246afe2ea
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75705332"
---
# <a name="how-to-subscribe-to-and-unsubscribe-from-events-c-programming-guide"></a><span data-ttu-id="54f2a-102">Procedimiento Suscribir y cancelar la suscripción a eventos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="54f2a-102">How to subscribe to and unsubscribe from events (C# Programming Guide)</span></span>
<span data-ttu-id="54f2a-103">La suscripción a un evento publicado por otra clase se realiza cuando quiere escribir código personalizado al que se llama cuando se produce ese evento.</span><span class="sxs-lookup"><span data-stu-id="54f2a-103">You subscribe to an event that is published by another class when you want to write custom code that is called when that event is raised.</span></span> <span data-ttu-id="54f2a-104">Por ejemplo, puede suscribirse al evento `click` de un botón para que la aplicación realice alguna operación cuando el usuario haga clic en el botón.</span><span class="sxs-lookup"><span data-stu-id="54f2a-104">For example, you might subscribe to a button's `click` event in order to make your application do something useful when the user clicks the button.</span></span>  
  
### <a name="to-subscribe-to-events-by-using-the-visual-studio-ide"></a><span data-ttu-id="54f2a-105">Para suscribirse a eventos mediante el IDE de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="54f2a-105">To subscribe to events by using the Visual Studio IDE</span></span>  
  
1. <span data-ttu-id="54f2a-106">Si no puede ver la ventana **Propiedades**, en la vista **Diseño** haga clic con el botón derecho en el formulario o control para el que quiere crear un controlador de eventos y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="54f2a-106">If you cannot see the **Properties** window, in **Design** view, right-click the form or control for which you want to create an event handler, and select **Properties**.</span></span>  
  
2. <span data-ttu-id="54f2a-107">En la parte superior de la ventana **Propiedades**, haga clic en el icono **Eventos**.</span><span class="sxs-lookup"><span data-stu-id="54f2a-107">On top of the **Properties** window, click the **Events** icon.</span></span>  
  
3. <span data-ttu-id="54f2a-108">Haga doble clic en el evento que quiera crear, por ejemplo, el evento `Load`.</span><span class="sxs-lookup"><span data-stu-id="54f2a-108">Double-click the event that you want to create, for example the `Load` event.</span></span>  
  
     <span data-ttu-id="54f2a-109">Visual C# crea un método de controlador de eventos vacío y lo agrega al código.</span><span class="sxs-lookup"><span data-stu-id="54f2a-109">Visual C# creates an empty event handler method and adds it to your code.</span></span> <span data-ttu-id="54f2a-110">También puede agregar manualmente el código en la vista **Código**.</span><span class="sxs-lookup"><span data-stu-id="54f2a-110">Alternatively you can add the code manually in **Code** view.</span></span> <span data-ttu-id="54f2a-111">Por ejemplo, las líneas siguientes de código declaran un método de controlador de eventos al que se llamará cuando la clase `Form` genere el evento `Load`.</span><span class="sxs-lookup"><span data-stu-id="54f2a-111">For example, the following lines of code declare an event handler method that will be called when the `Form` class raises the `Load` event.</span></span>  
  
     [!code-csharp[csProgGuideEvents#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#11)]  
  
     <span data-ttu-id="54f2a-112">La línea de código que es necesaria para suscribirse al evento también se genera automáticamente con el método `InitializeComponent` en el archivo Form1.Designer.cs del proyecto.</span><span class="sxs-lookup"><span data-stu-id="54f2a-112">The line of code that is required to subscribe to the event is also automatically generated in the `InitializeComponent` method in the Form1.Designer.cs file in your project.</span></span> <span data-ttu-id="54f2a-113">Se parece a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="54f2a-113">It resembles this:</span></span>  
  
    ```csharp
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
### <a name="to-subscribe-to-events-programmatically"></a><span data-ttu-id="54f2a-114">Para suscribirse a eventos mediante programación</span><span class="sxs-lookup"><span data-stu-id="54f2a-114">To subscribe to events programmatically</span></span>  
  
1. <span data-ttu-id="54f2a-115">Defina un método de controlador de eventos cuya firma coincida con la firma de delegado del evento.</span><span class="sxs-lookup"><span data-stu-id="54f2a-115">Define an event handler method whose signature matches the delegate signature for the event.</span></span> <span data-ttu-id="54f2a-116">Por ejemplo, si el evento se basa en el tipo de delegado <xref:System.EventHandler>, el siguiente código representa el código auxiliar del método:</span><span class="sxs-lookup"><span data-stu-id="54f2a-116">For example, if the event is based on the <xref:System.EventHandler> delegate type, the following code represents the method stub:</span></span>  
  
    ```csharp
    void HandleCustomEvent(object sender, CustomEventArgs a)  
    {  
       // Do something useful here.  
    }  
    ```  
  
2. <span data-ttu-id="54f2a-117">Use el operador de suma y asignación (`+=`) para asociar el controlador de eventos al evento.</span><span class="sxs-lookup"><span data-stu-id="54f2a-117">Use the addition assignment operator (`+=`) to attach an event handler to the event.</span></span> <span data-ttu-id="54f2a-118">En el ejemplo siguiente, se asume que un objeto denominado `publisher` tiene un evento denominado `RaiseCustomEvent`.</span><span class="sxs-lookup"><span data-stu-id="54f2a-118">In the following example, assume that an object named `publisher` has an event named `RaiseCustomEvent`.</span></span> <span data-ttu-id="54f2a-119">Observe que la clase de suscriptor necesita una referencia a la clase de editor para suscribirse a sus eventos.</span><span class="sxs-lookup"><span data-stu-id="54f2a-119">Note that the subscriber class needs a reference to the publisher class in order to subscribe to its events.</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent += HandleCustomEvent;  
    ```  
  
     <span data-ttu-id="54f2a-120">Observe que la sintaxis anterior es nueva en C# 2.0.</span><span class="sxs-lookup"><span data-stu-id="54f2a-120">Note that the previous syntax is new in C# 2.0.</span></span> <span data-ttu-id="54f2a-121">Al igual que en la sintaxis de C# 1.0, el delegado encapsulador debe crearse explícitamente mediante la palabra clave `new`:</span><span class="sxs-lookup"><span data-stu-id="54f2a-121">It is exactly equivalent to the C# 1.0 syntax in which the encapsulating delegate must be explicitly created by using the `new` keyword:</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent += new CustomEventHandler(HandleCustomEvent);  
    ```  
  
     <span data-ttu-id="54f2a-122">También puede usar una [expresión lambda](../statements-expressions-operators/lambda-expressions.md) para especificar un controlador de eventos:</span><span class="sxs-lookup"><span data-stu-id="54f2a-122">You also can use a [lambda expression](../statements-expressions-operators/lambda-expressions.md) to specify an event handler:</span></span>
  
    ```csharp
    public Form1()  
    {  
        InitializeComponent();  
        this.Click += (s,e) =>
            {
                MessageBox.Show(((MouseEventArgs)e).Location.ToString());
            };
    }  
    ```  
  
### <a name="to-subscribe-to-events-by-using-an-anonymous-method"></a><span data-ttu-id="54f2a-123">Para suscribirse a eventos mediante un método anónimo</span><span class="sxs-lookup"><span data-stu-id="54f2a-123">To subscribe to events by using an anonymous method</span></span>  
  
- <span data-ttu-id="54f2a-124">Si no tiene que cancelar la suscripción a un evento más adelante, puede usar el operador de suma y asignación (`+=`) para asociar un método anónimo al evento.</span><span class="sxs-lookup"><span data-stu-id="54f2a-124">If you will not have to unsubscribe to an event later, you can use the addition assignment operator (`+=`) to attach an anonymous method to the event.</span></span> <span data-ttu-id="54f2a-125">En el ejemplo siguiente, se presupone que un objeto denominado `publisher` tiene un evento denominado `RaiseCustomEvent` y que se ha definido una clase `CustomEventArgs` para proporcionar algún tipo de información específica del evento.</span><span class="sxs-lookup"><span data-stu-id="54f2a-125">In the following example, assume that an object named `publisher` has an event named `RaiseCustomEvent` and that a `CustomEventArgs` class has also been defined to carry some kind of specialized event information.</span></span> <span data-ttu-id="54f2a-126">Observe que la clase de suscriptor necesita una referencia a `publisher` para suscribirse a sus eventos.</span><span class="sxs-lookup"><span data-stu-id="54f2a-126">Note that the subscriber class needs a reference to `publisher` in order to subscribe to its events.</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent += delegate(object o, CustomEventArgs e)  
    {  
      string s = o.ToString() + " " + e.ToString();  
      Console.WriteLine(s);  
    };  
    ```  
  
     <span data-ttu-id="54f2a-127">Es importante tener en cuenta que puede no resultar fácil cancelar la suscripción a un evento si se ha usado una función anónima para suscribirse a él.</span><span class="sxs-lookup"><span data-stu-id="54f2a-127">It is important to notice that you cannot easily unsubscribe from an event if you used an anonymous function to subscribe to it.</span></span> <span data-ttu-id="54f2a-128">Para cancelar la suscripción en esta situación, es necesario regresar al código donde se ha suscrito al evento, almacenar el método anónimo en una variable de delegado y, después, agregar el delegado al evento.</span><span class="sxs-lookup"><span data-stu-id="54f2a-128">To unsubscribe in this scenario, it is necessary to go back to the code where you subscribe to the event, store the anonymous method in a delegate variable, and then add the delegate to the event.</span></span> <span data-ttu-id="54f2a-129">En general, se recomienda que no use funciones anónimas para suscribirse a eventos si va a tener que cancelar la suscripción al evento en el código más adelante.</span><span class="sxs-lookup"><span data-stu-id="54f2a-129">In general, we recommend that you do not use anonymous functions to subscribe to events if you will have to unsubscribe from the event at some later point in your code.</span></span> <span data-ttu-id="54f2a-130">Para obtener más información sobre las funciones anónimas, vea [Funciones anónimas](../statements-expressions-operators/anonymous-functions.md).</span><span class="sxs-lookup"><span data-stu-id="54f2a-130">For more information about anonymous functions, see [Anonymous Functions](../statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="unsubscribing"></a><span data-ttu-id="54f2a-131">Cancelar una suscripción</span><span class="sxs-lookup"><span data-stu-id="54f2a-131">Unsubscribing</span></span>  
 <span data-ttu-id="54f2a-132">Para impedir que se invoque el controlador de eventos cuando se produce el evento, puede cancelar la suscripción al evento.</span><span class="sxs-lookup"><span data-stu-id="54f2a-132">To prevent your event handler from being invoked when the event is raised, unsubscribe from the event.</span></span> <span data-ttu-id="54f2a-133">Para evitar que se pierdan recursos, debe cancelar la suscripción a los eventos antes de eliminar un objeto suscriptor.</span><span class="sxs-lookup"><span data-stu-id="54f2a-133">In order to prevent resource leaks, you should unsubscribe from events before you dispose of a subscriber object.</span></span> <span data-ttu-id="54f2a-134">Hasta que se cancela la suscripción a un evento, el delegado multidifusión subyacente al evento en el objeto de publicación tiene una referencia al delegado que encapsula el controlador de eventos del suscriptor.</span><span class="sxs-lookup"><span data-stu-id="54f2a-134">Until you unsubscribe from an event, the multicast delegate that underlies the event in the publishing object has a reference to the delegate that encapsulates the subscriber's event handler.</span></span> <span data-ttu-id="54f2a-135">Mientras el objeto de publicación mantenga esa referencia, la recolección de elementos no utilizados no eliminará el objeto suscriptor.</span><span class="sxs-lookup"><span data-stu-id="54f2a-135">As long as the publishing object holds that reference, garbage collection will not delete your subscriber object.</span></span>  
  
#### <a name="to-unsubscribe-from-an-event"></a><span data-ttu-id="54f2a-136">Para cancelar la suscripción a un evento</span><span class="sxs-lookup"><span data-stu-id="54f2a-136">To unsubscribe from an event</span></span>  
  
- <span data-ttu-id="54f2a-137">Use el operador de resta y asignación (`-=`) para cancelar la suscripción a un evento:</span><span class="sxs-lookup"><span data-stu-id="54f2a-137">Use the subtraction assignment operator (`-=`) to unsubscribe from an event:</span></span>  
  
    ```csharp
    publisher.RaiseCustomEvent -= HandleCustomEvent;  
    ```  
  
     <span data-ttu-id="54f2a-138">Cuando se haya cancelado la suscripción a un evento de todos los suscriptores, la instancia del evento en la clase de editor se establecerá en `null`.</span><span class="sxs-lookup"><span data-stu-id="54f2a-138">When all subscribers have unsubscribed from an event, the event instance in the publisher class is set to `null`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54f2a-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="54f2a-139">See also</span></span>

- [<span data-ttu-id="54f2a-140">Eventos</span><span class="sxs-lookup"><span data-stu-id="54f2a-140">Events</span></span>](./index.md)
- [<span data-ttu-id="54f2a-141">event</span><span class="sxs-lookup"><span data-stu-id="54f2a-141">event</span></span>](../../language-reference/keywords/event.md)
- [<span data-ttu-id="54f2a-142">Procedimiento para publicar eventos que cumplan las instrucciones de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="54f2a-142">How to publish events that conform to .NET Framework Guidelines</span></span>](./how-to-publish-events-that-conform-to-net-framework-guidelines.md)
- [<span data-ttu-id="54f2a-143">Operadores - y -=</span><span class="sxs-lookup"><span data-stu-id="54f2a-143">- and -= operators</span></span>](../../language-reference/operators/subtraction-operator.md)
- [<span data-ttu-id="54f2a-144">Operadores + y += </span><span class="sxs-lookup"><span data-stu-id="54f2a-144">+ and += operators</span></span>](../../language-reference/operators/addition-operator.md)
