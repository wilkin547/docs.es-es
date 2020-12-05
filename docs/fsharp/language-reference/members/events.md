---
title: Events
description: 'Obtenga información sobre cómo los eventos de F # permiten asociar las llamadas de función a las acciones del usuario, que son importantes en la programación de la GUI.'
ms.date: 08/15/2020
ms.openlocfilehash: 17e0cc8840053bf24d5c69694fe94d544c44510d
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740346"
---
# <a name="events"></a><span data-ttu-id="c8405-103">Eventos</span><span class="sxs-lookup"><span data-stu-id="c8405-103">Events</span></span>

<span data-ttu-id="c8405-104">Los eventos permiten asociar las llamadas de función a las acciones del usuario y son importantes para la programación de GUI.</span><span class="sxs-lookup"><span data-stu-id="c8405-104">Events enable you to associate function calls with user actions and are important in GUI programming.</span></span> <span data-ttu-id="c8405-105">Los eventos también los pueden desencadenar las aplicaciones o el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c8405-105">Events can also be triggered by your applications or by the operating system.</span></span>

## <a name="handling-events"></a><span data-ttu-id="c8405-106">Controlar eventos</span><span class="sxs-lookup"><span data-stu-id="c8405-106">Handling Events</span></span>

<span data-ttu-id="c8405-107">Cuando se utiliza una biblioteca de GUI como Windows Forms o Windows Presentation Foundation (WPF), gran parte del código de la aplicación se ejecuta en respuesta a los eventos predefinidos por la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="c8405-107">When you use a GUI library like Windows Forms or Windows Presentation Foundation (WPF), much of the code in your application runs in response to events that are predefined by the library.</span></span> <span data-ttu-id="c8405-108">Estos eventos predefinidos son miembros de clases de GUI, como formularios y controles.</span><span class="sxs-lookup"><span data-stu-id="c8405-108">These predefined events are members of GUI classes such as forms and controls.</span></span> <span data-ttu-id="c8405-109">Se puede agregar comportamiento personalizado a un evento preexistente, como un clic del botón, haciendo referencia al evento con nombre en cuestión (por ejemplo, el evento `Click` de la clase `Form`) e invocando el método `Add`, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="c8405-109">You can add custom behavior to a preexisting event, such as a button click, by referencing the specific named event of interest (for example, the `Click` event of the `Form` class) and invoking the `Add` method, as shown in the following code.</span></span> <span data-ttu-id="c8405-110">Si se ejecuta en F# Interactive, se omitirá la llamada a `System.Windows.Forms.Application.Run(System.Windows.Forms.Form)`.</span><span class="sxs-lookup"><span data-stu-id="c8405-110">If you run this from F# Interactive, omit the call to `System.Windows.Forms.Application.Run(System.Windows.Forms.Form)`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3601.fs)]

<span data-ttu-id="c8405-111">El tipo del método `Add` es `('a -> unit) -> unit`.</span><span class="sxs-lookup"><span data-stu-id="c8405-111">The type of the `Add` method is `('a -> unit) -> unit`.</span></span> <span data-ttu-id="c8405-112">Por consiguiente, el método de control de eventos toma un parámetro, que suele ser los argumentos del evento, y devuelve `unit`.</span><span class="sxs-lookup"><span data-stu-id="c8405-112">Therefore, the event handler method takes one parameter, typically the event arguments, and returns `unit`.</span></span> <span data-ttu-id="c8405-113">En el ejemplo anterior se muestra el controlador de eventos como una expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="c8405-113">The previous example shows the event handler as a lambda expression.</span></span> <span data-ttu-id="c8405-114">El controlador de eventos también puede ser un valor de función, como en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="c8405-114">The event handler can also be a function value, as in the following code example.</span></span> <span data-ttu-id="c8405-115">En el ejemplo de código siguiente también se muestra el uso de los parámetros de controlador de eventos, que proporcionan información específica del tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="c8405-115">The following code example also shows the use of the event handler parameters, which provide information specific to the type of event.</span></span> <span data-ttu-id="c8405-116">Para un evento `MouseMove`, el sistema pasa un objeto `System.Windows.Forms.MouseEventArgs`, que contiene la posición `X` e `Y` del puntero.</span><span class="sxs-lookup"><span data-stu-id="c8405-116">For a `MouseMove` event, the system passes a `System.Windows.Forms.MouseEventArgs` object, which contains the `X` and `Y` position of the pointer.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3602.fs)]

## <a name="creating-custom-events"></a><span data-ttu-id="c8405-117">Crear eventos personalizados</span><span class="sxs-lookup"><span data-stu-id="c8405-117">Creating Custom Events</span></span>

<span data-ttu-id="c8405-118">Los eventos de f # se representan mediante el tipo de [evento](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpevent-1.html) de f #, que implementa la interfaz [IEvent](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-ievent-1.html) .</span><span class="sxs-lookup"><span data-stu-id="c8405-118">F# events are represented by the F# [Event](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpevent-1.html) type, which implements the [IEvent](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-ievent-1.html) interface.</span></span> <span data-ttu-id="c8405-119">`IEvent` es en sí misma una interfaz que combina la funcionalidad de otras dos interfaces `System.IObservable<'T>` e [IDelegateEvent](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-idelegateevent-1.html).</span><span class="sxs-lookup"><span data-stu-id="c8405-119">`IEvent` is itself an interface that combines the functionality of two other interfaces, `System.IObservable<'T>` and [IDelegateEvent](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-idelegateevent-1.html).</span></span> <span data-ttu-id="c8405-120">Por consiguiente, la clase `Event` tiene una funcionalidad de delegados equivalente a la de otros lenguajes, además de la funcionalidad de `IObservable`, lo que significa que los eventos de F# admiten el filtrado así como el uso de expresiones lambda y funciones de primera clase de F# como controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="c8405-120">Therefore, `Event`s have the equivalent functionality of delegates in other languages, plus the additional functionality from `IObservable`, which means that F# events support event filtering and using F# first-class functions and lambda expressions as event handlers.</span></span> <span data-ttu-id="c8405-121">Esta funcionalidad se proporciona en el [módulo de eventos](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-eventmodule.html).</span><span class="sxs-lookup"><span data-stu-id="c8405-121">This functionality is provided in the [Event module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-eventmodule.html).</span></span>

<span data-ttu-id="c8405-122">Para crear en una clase un evento que actúe como cualquier otro evento de .NET Framework, agregue a la clase un enlace `let` que defina un objeto `Event` como un campo de una clase.</span><span class="sxs-lookup"><span data-stu-id="c8405-122">To create an event on a class that acts just like any other .NET Framework event, add to the class a `let` binding that defines an `Event` as a field in a class.</span></span> <span data-ttu-id="c8405-123">Puede especificar el tipo de argumento de evento que desee como tipo de argumento o puede dejarlo en blanco y dejar que el compilador infiera el tipo adecuando.</span><span class="sxs-lookup"><span data-stu-id="c8405-123">You can specify the desired event argument type as the type argument, or leave it blank and have the compiler infer the appropriate type.</span></span> <span data-ttu-id="c8405-124">Además, debe definir un miembro de evento que exponga el evento como un evento de CLI.</span><span class="sxs-lookup"><span data-stu-id="c8405-124">You also must define an event member that exposes the event as a CLI event.</span></span> <span data-ttu-id="c8405-125">Este miembro debe tener el atributo [CLIEvent](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-clieventattribute.html) .</span><span class="sxs-lookup"><span data-stu-id="c8405-125">This member should have the [CLIEvent](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-clieventattribute.html) attribute.</span></span> <span data-ttu-id="c8405-126">Se declara como una propiedad y su implementación es simplemente una llamada a la propiedad [Publish](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpevent-1.html#Publish) del evento.</span><span class="sxs-lookup"><span data-stu-id="c8405-126">It is declared like a property and its implementation is just a call to the [Publish](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpevent-1.html#Publish) property of the event.</span></span> <span data-ttu-id="c8405-127">Los usuarios de la clase pueden usar el método `Add` del evento publicado para agregar un controlador.</span><span class="sxs-lookup"><span data-stu-id="c8405-127">Users of your class can use the `Add` method of the published event to add a handler.</span></span> <span data-ttu-id="c8405-128">El argumento del método `Add` puede ser una expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="c8405-128">The argument for the `Add` method can be a lambda expression.</span></span> <span data-ttu-id="c8405-129">Puede usar la propiedad `Trigger` del evento para generar el evento pasando los argumentos a la función del controlador.</span><span class="sxs-lookup"><span data-stu-id="c8405-129">You can use the `Trigger` property of the event to raise the event, passing the arguments to the handler function.</span></span> <span data-ttu-id="c8405-130">En el siguiente ejemplo código se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="c8405-130">The following code example illustrates this.</span></span> <span data-ttu-id="c8405-131">En este ejemplo, el argumento de tipo inferido para el evento es una tupla, que representa los argumentos de la expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="c8405-131">In this example, the inferred type argument for the event is a tuple, which represents the arguments for the lambda expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3605.fs)]

<span data-ttu-id="c8405-132">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="c8405-132">The output is as follows.</span></span>

```console
Event1 occurred! Object data: Hello World!
```

<span data-ttu-id="c8405-133">Aquí se muestra la funcionalidad adicional que proporciona el módulo `Event`.</span><span class="sxs-lookup"><span data-stu-id="c8405-133">The additional functionality provided by the `Event` module is illustrated here.</span></span> <span data-ttu-id="c8405-134">En el siguiente ejemplo de código, se muestra el uso básico de `Event.create` para crear un evento y un método desencadenador, agregar dos controladores de eventos en forma de expresiones lambda y, a continuación, desencadenar el evento para ejecutar ambas expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="c8405-134">The following code example illustrates the basic use of `Event.create` to create an event and a trigger method, add two event handlers in the form of lambda expressions, and then trigger the event to execute both lambda expressions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3603.fs)]

<span data-ttu-id="c8405-135">La salida del código anterior es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="c8405-135">The output of the previous code is as follows.</span></span>

```console
Event occurred.
Given a value: Event occurred.
```

## <a name="processing-event-streams"></a><span data-ttu-id="c8405-136">Procesar secuencias de eventos</span><span class="sxs-lookup"><span data-stu-id="c8405-136">Processing Event Streams</span></span>

<span data-ttu-id="c8405-137">En lugar de agregar simplemente un controlador de eventos para un evento mediante la función [Event. Add](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-eventmodule.html#add) , puede usar las funciones del `Event` módulo para procesar flujos de eventos de maneras muy personalizadas.</span><span class="sxs-lookup"><span data-stu-id="c8405-137">Instead of just adding an event handler for an event by using the [Event.add](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-eventmodule.html#add) function, you can use the functions in the `Event` module to process streams of events in highly customized ways.</span></span> <span data-ttu-id="c8405-138">Para ello, se utiliza la canalización hacia delante (`|>`) junto con el evento como primer valor en una serie de llamadas de función, y las funciones del módulo `Event` como llamadas de función subsiguientes.</span><span class="sxs-lookup"><span data-stu-id="c8405-138">To do this, you use the forward pipe (`|>`) together with the event as the first value in a series of function calls, and the `Event` module functions as subsequent function calls.</span></span>

<span data-ttu-id="c8405-139">En el siguiente ejemplo de código, se muestra cómo configurar un evento cuyo controlador se invoca únicamente en determinadas condiciones.</span><span class="sxs-lookup"><span data-stu-id="c8405-139">The following code example shows how to set up an event for which the handler is only called under certain conditions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3604.fs)]

<span data-ttu-id="c8405-140">El [módulo observable](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-observablemodule.html) contiene funciones similares que operan en objetos observables.</span><span class="sxs-lookup"><span data-stu-id="c8405-140">The [Observable module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-observablemodule.html) contains similar functions that operate on observable objects.</span></span> <span data-ttu-id="c8405-141">Los objetos observables son similares a los eventos pero solo se suscriben activamente a los eventos si ellos mismos son objeto de una suscripción.</span><span class="sxs-lookup"><span data-stu-id="c8405-141">Observable objects are similar to events but only actively subscribe to events if they themselves are being subscribed to.</span></span>

## <a name="implementing-an-interface-event"></a><span data-ttu-id="c8405-142">Implementar un evento de interfaz</span><span class="sxs-lookup"><span data-stu-id="c8405-142">Implementing an Interface Event</span></span>

<span data-ttu-id="c8405-143">Cuando se desarrollan componentes de interfaz de usuario, suele empezarse por crear un nuevo formulario o control que herede de un formulario o control ya existente.</span><span class="sxs-lookup"><span data-stu-id="c8405-143">As you develop UI components, you often start by creating a new form or a new control that inherits from an existing form or control.</span></span> <span data-ttu-id="c8405-144">A menudo los eventos se definen en una interfaz y, en ese caso, debe implementar la interfaz para implementar el evento.</span><span class="sxs-lookup"><span data-stu-id="c8405-144">Events are frequently defined on an interface, and, in that case, you must implement the interface to implement the event.</span></span> <span data-ttu-id="c8405-145">La interfaz `System.ComponentModel.INotifyPropertyChanged` define un único evento `System.ComponentModel.INotifyPropertyChanged.PropertyChanged`.</span><span class="sxs-lookup"><span data-stu-id="c8405-145">The `System.ComponentModel.INotifyPropertyChanged` interface defines a single `System.ComponentModel.INotifyPropertyChanged.PropertyChanged` event.</span></span> <span data-ttu-id="c8405-146">En el código siguiente se muestra cómo implementar el evento definido por esta interfaz heredada:</span><span class="sxs-lookup"><span data-stu-id="c8405-146">The following code illustrates how to implement the event that this inherited interface defined:</span></span>

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
        this.Click |> Event.add(fun evArgs ->
            this.Property1 <- "text2"
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
        printfn "Property {args.PropertyName} changed its value to {newValue}"

// Create a form, hook up the event handler, and start the application.
let appForm = new AppForm()
let inpc = appForm :> INotifyPropertyChanged
inpc.PropertyChanged.Add(appForm.OnPropertyChanged)
Application.Run(appForm)
```

<span data-ttu-id="c8405-147">Si desea enlazar el evento en el constructor, el código es algo más complejo porque el enlace del evento debe estar en un bloque `then` de un constructor adicional, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c8405-147">If you want to hook up the event in the constructor, the code is a bit more complicated because the event hookup must be in a `then` block in an additional constructor, as in the following example:</span></span>

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
        this.Click |> Event.add(fun evArgs ->
            this.Property1 <- "text2"
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
        printfn "Property {args.PropertyName} changed its value to {newValue}"

    new() as this =
        new AppForm(0)
        then
            let inpc = this :> INotifyPropertyChanged
            inpc.PropertyChanged.Add(this.OnPropertyChanged)

// Create a form, hook up the event handler, and start the application.
let appForm = new AppForm()
Application.Run(appForm)
```

## <a name="see-also"></a><span data-ttu-id="c8405-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c8405-148">See also</span></span>

- [<span data-ttu-id="c8405-149">Miembros</span><span class="sxs-lookup"><span data-stu-id="c8405-149">Members</span></span>](index.md)
- [<span data-ttu-id="c8405-150">Controlar y provocar eventos</span><span class="sxs-lookup"><span data-stu-id="c8405-150">Handling and Raising Events</span></span>](../../../standard/events/index.md)
- [<span data-ttu-id="c8405-151">Expresiones lambda: `fun` palabra clave</span><span class="sxs-lookup"><span data-stu-id="c8405-151">Lambda Expressions: The `fun` Keyword</span></span>](../functions/lambda-expressions-the-fun-keyword.md)
