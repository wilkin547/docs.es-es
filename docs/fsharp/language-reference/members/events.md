---
title: Eventos (F#)
description: "Obtenga información acerca de cómo los eventos de F # permiten asociar llamadas a funciones a las acciones del usuario, que son importantes en la programación de GUI."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 28b588f2-0c9e-4c0d-babf-901ed934638a
ms.openlocfilehash: 43ff52134093acbd670d48ea83d40f1e9eb377c0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="events"></a><span data-ttu-id="db78b-104">Eventos</span><span class="sxs-lookup"><span data-stu-id="db78b-104">Events</span></span>

> [!NOTE]
<span data-ttu-id="db78b-105">Los vínculos de la referencia de API de este artículo le llevarán a MSDN.</span><span class="sxs-lookup"><span data-stu-id="db78b-105">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="db78b-106">La referencia de API de docs.microsoft.com no está completa.</span><span class="sxs-lookup"><span data-stu-id="db78b-106">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="db78b-107">Los eventos permiten asociar las llamadas de función a las acciones del usuario y son importantes para la programación de GUI.</span><span class="sxs-lookup"><span data-stu-id="db78b-107">Events enable you to associate function calls with user actions and are important in GUI programming.</span></span> <span data-ttu-id="db78b-108">Los eventos también los pueden desencadenar las aplicaciones o el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="db78b-108">Events can also be triggered by your applications or by the operating system.</span></span>

## <a name="handling-events"></a><span data-ttu-id="db78b-109">Controlar eventos</span><span class="sxs-lookup"><span data-stu-id="db78b-109">Handling Events</span></span>
<span data-ttu-id="db78b-110">Cuando se utiliza una biblioteca de GUI como Windows Forms o Windows Presentation Foundation (WPF), gran parte del código de la aplicación se ejecuta en respuesta a los eventos predefinidos por la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="db78b-110">When you use a GUI library like Windows Forms or Windows Presentation Foundation (WPF), much of the code in your application runs in response to events that are predefined by the library.</span></span> <span data-ttu-id="db78b-111">Estos eventos predefinidos son miembros de clases de GUI, como formularios y controles.</span><span class="sxs-lookup"><span data-stu-id="db78b-111">These predefined events are members of GUI classes such as forms and controls.</span></span> <span data-ttu-id="db78b-112">Se puede agregar comportamiento personalizado a un evento preexistente, como un clic del botón, haciendo referencia al evento con nombre en cuestión (por ejemplo, el evento `Click` de la clase `Form`) e invocando el método `Add`, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="db78b-112">You can add custom behavior to a preexisting event, such as a button click, by referencing the specific named event of interest (for example, the `Click` event of the `Form` class) and invoking the `Add` method, as shown in the following code.</span></span> <span data-ttu-id="db78b-113">Si se ejecuta en F# Interactive, se omitirá la llamada a `System.Windows.Forms.Application.Run(System.Windows.Forms.Form)`.</span><span class="sxs-lookup"><span data-stu-id="db78b-113">If you run this from F# Interactive, omit the call to `System.Windows.Forms.Application.Run(System.Windows.Forms.Form)`.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3601.fs)]

<span data-ttu-id="db78b-114">El tipo del método `Add` es `('a -> unit) -> unit`.</span><span class="sxs-lookup"><span data-stu-id="db78b-114">The type of the `Add` method is `('a -> unit) -> unit`.</span></span> <span data-ttu-id="db78b-115">Por consiguiente, el método de control de eventos toma un parámetro, que suele ser los argumentos del evento, y devuelve `unit`.</span><span class="sxs-lookup"><span data-stu-id="db78b-115">Therefore, the event handler method takes one parameter, typically the event arguments, and returns `unit`.</span></span> <span data-ttu-id="db78b-116">En el ejemplo anterior se muestra el controlador de eventos como una expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="db78b-116">The previous example shows the event handler as a lambda expression.</span></span> <span data-ttu-id="db78b-117">El controlador de eventos también puede ser un valor de función, como en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="db78b-117">The event handler can also be a function value, as in the following code example.</span></span> <span data-ttu-id="db78b-118">En el ejemplo de código siguiente también se muestra el uso de los parámetros de controlador de eventos, que proporcionan información específica del tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="db78b-118">The following code example also shows the use of the event handler parameters, which provide information specific to the type of event.</span></span> <span data-ttu-id="db78b-119">Para un evento `MouseMove`, el sistema pasa un objeto `System.Windows.Forms.MouseEventArgs`, que contiene la posición `X` e `Y` del puntero.</span><span class="sxs-lookup"><span data-stu-id="db78b-119">For a `MouseMove` event, the system passes a `System.Windows.Forms.MouseEventArgs` object, which contains the `X` and `Y` position of the pointer.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3602.fs)]
    
## <a name="creating-custom-events"></a><span data-ttu-id="db78b-120">Crear eventos personalizados</span><span class="sxs-lookup"><span data-stu-id="db78b-120">Creating Custom Events</span></span>
<span data-ttu-id="db78b-121">Los eventos de F # están representados por F # [eventos](https://msdn.microsoft.com/library/f3b47c8a-4ee5-4ce8-9a72-ad305a17c4b9) de la clase, que implementa el [IEvent](https://msdn.microsoft.com/library/8dbca0df-f8a1-40bd-8d50-aa26f6a8b862) interfaz.</span><span class="sxs-lookup"><span data-stu-id="db78b-121">F# events are represented by the F# [Event](https://msdn.microsoft.com/library/f3b47c8a-4ee5-4ce8-9a72-ad305a17c4b9) class, which implements the [IEvent](https://msdn.microsoft.com/library/8dbca0df-f8a1-40bd-8d50-aa26f6a8b862) interface.</span></span> <span data-ttu-id="db78b-122">`IEvent`es una interfaz que combina la funcionalidad de otras dos interfaces, `System.IObservable<'T>` y [IDelegateEvent](https://msdn.microsoft.com/library/3d849465-6b8e-4fc5-b36c-2941d734268a).</span><span class="sxs-lookup"><span data-stu-id="db78b-122">`IEvent` is itself an interface that combines the functionality of two other interfaces, `System.IObservable<'T>` and [IDelegateEvent](https://msdn.microsoft.com/library/3d849465-6b8e-4fc5-b36c-2941d734268a).</span></span> <span data-ttu-id="db78b-123">Por consiguiente, la clase `Event` tiene una funcionalidad de delegados equivalente a la de otros lenguajes, además de la funcionalidad de `IObservable`, lo que significa que los eventos de F# admiten el filtrado así como el uso de expresiones lambda y funciones de primera clase de F# como controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="db78b-123">Therefore, `Event`s have the equivalent functionality of delegates in other languages, plus the additional functionality from `IObservable`, which means that F# events support event filtering and using F# first-class functions and lambda expressions as event handlers.</span></span> <span data-ttu-id="db78b-124">Esta funcionalidad se proporciona en el [módulo de eventos](https://msdn.microsoft.com/library/8b883baa-a460-4840-9baa-de8260351bc7).</span><span class="sxs-lookup"><span data-stu-id="db78b-124">This functionality is provided in the [Event module](https://msdn.microsoft.com/library/8b883baa-a460-4840-9baa-de8260351bc7).</span></span>

<span data-ttu-id="db78b-125">Para crear en una clase un evento que actúe como cualquier otro evento de .NET Framework, agregue a la clase un enlace `let` que defina un objeto `Event` como un campo de una clase.</span><span class="sxs-lookup"><span data-stu-id="db78b-125">To create an event on a class that acts just like any other .NET Framework event, add to the class a `let` binding that defines an `Event` as a field in a class.</span></span> <span data-ttu-id="db78b-126">Puede especificar el tipo de argumento de evento que desee como tipo de argumento o puede dejarlo en blanco y dejar que el compilador infiera el tipo adecuando.</span><span class="sxs-lookup"><span data-stu-id="db78b-126">You can specify the desired event argument type as the type argument, or leave it blank and have the compiler infer the appropriate type.</span></span> <span data-ttu-id="db78b-127">Además, debe definir un miembro de evento que exponga el evento como un evento de CLI.</span><span class="sxs-lookup"><span data-stu-id="db78b-127">You also must define an event member that exposes the event as a CLI event.</span></span> <span data-ttu-id="db78b-128">Este miembro debe tener la [CLIEvent](https://msdn.microsoft.com/library/d359f1dd-ffa5-42fb-8808-b4c8131a0333) atributo.</span><span class="sxs-lookup"><span data-stu-id="db78b-128">This member should have the [CLIEvent](https://msdn.microsoft.com/library/d359f1dd-ffa5-42fb-8808-b4c8131a0333) attribute.</span></span> <span data-ttu-id="db78b-129">Se declara como una propiedad y su implementación es más que una llamada a la [publicar](https://msdn.microsoft.com/library/b0fdaad5-25e5-43d0-9c0c-ce37c4aeb68e) propiedad del evento.</span><span class="sxs-lookup"><span data-stu-id="db78b-129">It is declared like a property and its implementation is just a call to the [Publish](https://msdn.microsoft.com/library/b0fdaad5-25e5-43d0-9c0c-ce37c4aeb68e) property of the event.</span></span> <span data-ttu-id="db78b-130">Los usuarios de la clase pueden usar el método `Add` del evento publicado para agregar un controlador.</span><span class="sxs-lookup"><span data-stu-id="db78b-130">Users of your class can use the `Add` method of the published event to add a handler.</span></span> <span data-ttu-id="db78b-131">El argumento del método `Add` puede ser una expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="db78b-131">The argument for the `Add` method can be a lambda expression.</span></span> <span data-ttu-id="db78b-132">Puede usar la propiedad `Trigger` del evento para generar el evento pasando los argumentos a la función del controlador.</span><span class="sxs-lookup"><span data-stu-id="db78b-132">You can use the `Trigger` property of the event to raise the event, passing the arguments to the handler function.</span></span> <span data-ttu-id="db78b-133">En el siguiente ejemplo código se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="db78b-133">The following code example illustrates this.</span></span> <span data-ttu-id="db78b-134">En este ejemplo, el argumento de tipo inferido para el evento es una tupla, que representa los argumentos de la expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="db78b-134">In this example, the inferred type argument for the event is a tuple, which represents the arguments for the lambda expression.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3605.fs)]

<span data-ttu-id="db78b-135">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="db78b-135">The output is as follows.</span></span>

```
Event1 occurred! Object data: Hello World!
```

<span data-ttu-id="db78b-136">Aquí se muestra la funcionalidad adicional que proporciona el módulo `Event`.</span><span class="sxs-lookup"><span data-stu-id="db78b-136">The additional functionality provided by the `Event` module is illustrated here.</span></span> <span data-ttu-id="db78b-137">En el siguiente ejemplo de código, se muestra el uso básico de `Event.create` para crear un evento y un método desencadenador, agregar dos controladores de eventos en forma de expresiones lambda y, a continuación, desencadenar el evento para ejecutar ambas expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="db78b-137">The following code example illustrates the basic use of `Event.create` to create an event and a trigger method, add two event handlers in the form of lambda expressions, and then trigger the event to execute both lambda expressions.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3603.fs)]

<span data-ttu-id="db78b-138">La salida del código anterior es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="db78b-138">The output of the previous code is as follows.</span></span>

```
Event occurred.
Given a value: Event occurred.
```

## <a name="processing-event-streams"></a><span data-ttu-id="db78b-139">Procesar secuencias de eventos</span><span class="sxs-lookup"><span data-stu-id="db78b-139">Processing Event Streams</span></span>
<span data-ttu-id="db78b-140">En lugar de limitarse a agregar un controlador de eventos para un evento mediante el uso de la [Event.add](https://msdn.microsoft.com/library/10670d3b-8d47-4f6e-b8df-ebc6f64ef4fd) función, puede usar las funciones de la `Event` módulo para procesar secuencias de eventos de maneras muy personalizadas.</span><span class="sxs-lookup"><span data-stu-id="db78b-140">Instead of just adding an event handler for an event by using the [Event.add](https://msdn.microsoft.com/library/10670d3b-8d47-4f6e-b8df-ebc6f64ef4fd) function, you can use the functions in the `Event` module to process streams of events in highly customized ways.</span></span> <span data-ttu-id="db78b-141">Para ello, se utiliza la canalización hacia delante (`|>`) junto con el evento como primer valor en una serie de llamadas de función, y las funciones del módulo `Event` como llamadas de función subsiguientes.</span><span class="sxs-lookup"><span data-stu-id="db78b-141">To do this, you use the forward pipe (`|>`) together with the event as the first value in a series of function calls, and the `Event` module functions as subsequent function calls.</span></span>

<span data-ttu-id="db78b-142">En el siguiente ejemplo de código, se muestra cómo configurar un evento cuyo controlador se invoca únicamente en determinadas condiciones.</span><span class="sxs-lookup"><span data-stu-id="db78b-142">The following code example shows how to set up an event for which the handler is only called under certain conditions.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3604.fs)]

<span data-ttu-id="db78b-143">El [Observable (módulo)](https://msdn.microsoft.com/library/16b8610b-b30a-4df7-aa99-d9d352276227) contiene funciones similares que se usan con objetos observables.</span><span class="sxs-lookup"><span data-stu-id="db78b-143">The [Observable module](https://msdn.microsoft.com/library/16b8610b-b30a-4df7-aa99-d9d352276227) contains similar functions that operate on observable objects.</span></span> <span data-ttu-id="db78b-144">Los objetos observables son similares a los eventos pero solo se suscriben activamente a los eventos si ellos mismos son objeto de una suscripción.</span><span class="sxs-lookup"><span data-stu-id="db78b-144">Observable objects are similar to events but only actively subscribe to events if they themselves are being subscribed to.</span></span>


## <a name="implementing-an-interface-event"></a><span data-ttu-id="db78b-145">Implementar un evento de interfaz</span><span class="sxs-lookup"><span data-stu-id="db78b-145">Implementing an Interface Event</span></span>
<span data-ttu-id="db78b-146">Cuando se desarrollan componentes de interfaz de usuario, suele empezarse por crear un nuevo formulario o control que herede de un formulario o control ya existente.</span><span class="sxs-lookup"><span data-stu-id="db78b-146">As you develop UI components, you often start by creating a new form or a new control that inherits from an existing form or control.</span></span> <span data-ttu-id="db78b-147">A menudo los eventos se definen en una interfaz y, en ese caso, debe implementar la interfaz para implementar el evento.</span><span class="sxs-lookup"><span data-stu-id="db78b-147">Events are frequently defined on an interface, and, in that case, you must implement the interface to implement the event.</span></span> <span data-ttu-id="db78b-148">La interfaz `System.ComponentModel.INotifyPropertyChanged` define un único evento `System.ComponentModel.INotifyPropertyChanged.PropertyChanged`.</span><span class="sxs-lookup"><span data-stu-id="db78b-148">The `System.ComponentModel.INotifyPropertyChanged` interface defines a single `System.ComponentModel.INotifyPropertyChanged.PropertyChanged` event.</span></span> <span data-ttu-id="db78b-149">En el código siguiente se muestra cómo implementar el evento definido por esta interfaz heredada:</span><span class="sxs-lookup"><span data-stu-id="db78b-149">The following code illustrates how to implement the event that this inherited interface defined:</span></span>

```fsharp
module CustomForm

open System.Windows.Forms
open System.ComponentModel

type AppForm() as this =
    inherit Form()

    // Define the propertyChanged event.
    let propertyChanged = Event<PropertyChangedEventHandler, PropertyChangedEventArgs>()
    let mutable underlyingValue = "text0"

    // Set up a click event to change the properties.
    do
        this.Click |> Event.add(fun evArgs -> this.Property1 <- "text2"
        this.Property2 <- "text3")

    // This property does not have the property-changed event set.
    member val Property1 : string = "text" with get, set

    // This property has the property-changed event set.
    member this.Property2
        with get() = underlyingValue
        and set(newValue) =
            underlyingValue <- newValue
            propertyChanged.Trigger(this, new PropertyChangedEventArgs("Property2"))

    // Expose the PropertyChanged event as a first class .NET event.
    [<CLIEvent>]
    member this.PropertyChanged = propertyChanged.Publish


    // Define the add and remove methods to implement this interface.
    interface INotifyPropertyChanged with
        member this.add_PropertyChanged(handler) = propertyChanged.Publish.AddHandler(handler)
        member this.remove_PropertyChanged(handler) = propertyChanged.Publish.RemoveHandler(handler)

    // This is the event-handler method.
    member this.OnPropertyChanged(args : PropertyChangedEventArgs) =
        let newProperty = this.GetType().GetProperty(args.PropertyName)
        let newValue = newProperty.GetValue(this :> obj) :?> string
        printfn "Property %s changed its value to %s" args.PropertyName newValue

// Create a form, hook up the event handler, and start the application.
let appForm = new AppForm()
let inpc = appForm :> INotifyPropertyChanged
inpc.PropertyChanged.Add(appForm.OnPropertyChanged)
Application.Run(appForm)
```

<span data-ttu-id="db78b-150">Si desea enlazar el evento en el constructor, el código es algo más complejo porque el enlace del evento debe estar en un bloque `then` de un constructor adicional, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="db78b-150">If you want to hook up the event in the constructor, the code is a bit more complicated because the event hookup must be in a `then` block in an additional constructor, as in the following example:</span></span>

```fsharp
module CustomForm

open System.Windows.Forms
open System.ComponentModel

// Create a private constructor with a dummy argument so that the public
// constructor can have no arguments.
type AppForm private (dummy) as this =
    inherit Form()

    // Define the propertyChanged event.
    let propertyChanged = Event<PropertyChangedEventHandler, PropertyChangedEventArgs>()
    let mutable underlyingValue = "text0"

    // Set up a click event to change the properties.
    do
        this.Click |> Event.add(fun evArgs -> this.Property1 <- "text2"
        this.Property2 <- "text3")


    // This property does not have the property changed event set.
    member val Property1 : string = "text" with get, set

    // This property has the property changed event set.
    member this.Property2
        with get() = underlyingValue
        and set(newValue) =
            underlyingValue <- newValue
            propertyChanged.Trigger(this, new PropertyChangedEventArgs("Property2"))

    [<CLIEvent>]
    member this.PropertyChanged = propertyChanged.Publish

    // Define the add and remove methods to implement this interface.
    interface INotifyPropertyChanged with
        member this.add_PropertyChanged(handler) = this.PropertyChanged.AddHandler(handler)
        member this.remove_PropertyChanged(handler) = this.PropertyChanged.RemoveHandler(handler)

    // This is the event handler method.
    member this.OnPropertyChanged(args : PropertyChangedEventArgs) =
        let newProperty = this.GetType().GetProperty(args.PropertyName)
        let newValue = newProperty.GetValue(this :> obj) :?> string
        printfn "Property %s changed its value to %s" args.PropertyName newValue

    new() as this =
        new AppForm(0)
        then
            let inpc = this :> INotifyPropertyChanged
            inpc.PropertyChanged.Add(this.OnPropertyChanged)


// Create a form, hook up the event handler, and start the application.
let appForm = new AppForm()
Application.Run(appForm)
```

## <a name="see-also"></a><span data-ttu-id="db78b-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="db78b-151">See Also</span></span>
[<span data-ttu-id="db78b-152">Miembros</span><span class="sxs-lookup"><span data-stu-id="db78b-152">Members</span></span>](index.md)

[<span data-ttu-id="db78b-153">Controlar y provocar eventos</span><span class="sxs-lookup"><span data-stu-id="db78b-153">Handling and Raising Events</span></span>](https://msdn.microsoft.com/library/edzehd2t.aspx)

[<span data-ttu-id="db78b-154">Expresiones lambda: La `fun` (palabra clave)</span><span class="sxs-lookup"><span data-stu-id="db78b-154">Lambda Expressions: The `fun` Keyword</span></span>](../functions/lambda-expressions-the-fun-keyword.md)

[<span data-ttu-id="db78b-155">Control.Event módulo</span><span class="sxs-lookup"><span data-stu-id="db78b-155">Control.Event Module</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.event-module-%5bfsharp%5d)

[<span data-ttu-id="db78b-156">Control.Event &#60;' T &#62; Clase</span><span class="sxs-lookup"><span data-stu-id="db78b-156">Control.Event&#60;'T&#62; Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.event%5b%27t%5d-class-%5bfsharp%5d)

[<span data-ttu-id="db78b-157">Control.Event &#60;' Delegado,'Args &#62; Clase</span><span class="sxs-lookup"><span data-stu-id="db78b-157">Control.Event&#60;'Delegate,'Args&#62; Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.event%5b%27delegate%2c%27args%5d-class-%5bfsharp%5d)
