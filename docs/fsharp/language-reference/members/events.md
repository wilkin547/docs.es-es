---
title: Eventos
description: Obtenga información F# sobre cómo los eventos le permiten asociar las llamadas de función a las acciones del usuario, que son importantes en la programación de la GUI.
ms.date: 05/16/2016
ms.openlocfilehash: ad60aff318832ab3ba5e9f7c43928898e171cea8
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543630"
---
# <a name="events"></a>Eventos

> [!NOTE]
> Los vínculos de la referencia de API de este artículo le llevarán a MSDN.  La referencia de API de docs.microsoft.com no está completa.

Los eventos permiten asociar las llamadas de función a las acciones del usuario y son importantes para la programación de GUI. Los eventos también los pueden desencadenar las aplicaciones o el sistema operativo.

## <a name="handling-events"></a>Controlar eventos

Cuando se utiliza una biblioteca de GUI como Windows Forms o Windows Presentation Foundation (WPF), gran parte del código de la aplicación se ejecuta en respuesta a los eventos predefinidos por la biblioteca. Estos eventos predefinidos son miembros de clases de GUI, como formularios y controles. Se puede agregar comportamiento personalizado a un evento preexistente, como un clic del botón, haciendo referencia al evento con nombre en cuestión (por ejemplo, el evento `Click` de la clase `Form`) e invocando el método `Add`, tal y como se muestra en el código siguiente. Si se ejecuta en F# Interactive, se omitirá la llamada a `System.Windows.Forms.Application.Run(System.Windows.Forms.Form)`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3601.fs)]

El tipo del método `Add` es `('a -> unit) -> unit`. Por consiguiente, el método de control de eventos toma un parámetro, que suele ser los argumentos del evento, y devuelve `unit`. En el ejemplo anterior se muestra el controlador de eventos como una expresión lambda. El controlador de eventos también puede ser un valor de función, como en el ejemplo de código siguiente. En el ejemplo de código siguiente también se muestra el uso de los parámetros de controlador de eventos, que proporcionan información específica del tipo de evento. Para un evento `MouseMove`, el sistema pasa un objeto `System.Windows.Forms.MouseEventArgs`, que contiene la posición `X` e `Y` del puntero.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3602.fs)]

## <a name="creating-custom-events"></a>Crear eventos personalizados

F#los eventos se representan mediante F# la clase de [eventos](https://msdn.microsoft.com/library/f3b47c8a-4ee5-4ce8-9a72-ad305a17c4b9) , que implementa la interfaz [IEvent](https://msdn.microsoft.com/library/8dbca0df-f8a1-40bd-8d50-aa26f6a8b862) . `IEvent` es en sí misma una interfaz que combina la funcionalidad de otras dos interfaces, `System.IObservable<'T>` e [IDelegateEvent](https://msdn.microsoft.com/library/3d849465-6b8e-4fc5-b36c-2941d734268a). Por consiguiente, la clase `Event` tiene una funcionalidad de delegados equivalente a la de otros lenguajes, además de la funcionalidad de `IObservable`, lo que significa que los eventos de F# admiten el filtrado así como el uso de expresiones lambda y funciones de primera clase de F# como controladores de eventos. Esta funcionalidad se proporciona en el [módulo de eventos](https://msdn.microsoft.com/library/8b883baa-a460-4840-9baa-de8260351bc7).

Para crear en una clase un evento que actúe como cualquier otro evento de .NET Framework, agregue a la clase un enlace `let` que defina un objeto `Event` como un campo de una clase. Puede especificar el tipo de argumento de evento que desee como tipo de argumento o puede dejarlo en blanco y dejar que el compilador infiera el tipo adecuando. Además, debe definir un miembro de evento que exponga el evento como un evento de CLI. Este miembro debe tener el atributo [CLIEvent](https://msdn.microsoft.com/library/d359f1dd-ffa5-42fb-8808-b4c8131a0333) . Se declara como una propiedad y su implementación es simplemente una llamada a la propiedad [Publish](https://msdn.microsoft.com/library/b0fdaad5-25e5-43d0-9c0c-ce37c4aeb68e) del evento. Los usuarios de la clase pueden usar el método `Add` del evento publicado para agregar un controlador. El argumento del método `Add` puede ser una expresión lambda. Puede usar la propiedad `Trigger` del evento para generar el evento pasando los argumentos a la función del controlador. En el siguiente ejemplo código se muestra cómo hacerlo. En este ejemplo, el argumento de tipo inferido para el evento es una tupla, que representa los argumentos de la expresión lambda.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3605.fs)]

La salida es la siguiente.

```console
Event1 occurred! Object data: Hello World!
```

Aquí se muestra la funcionalidad adicional que proporciona el módulo `Event`. En el siguiente ejemplo de código, se muestra el uso básico de `Event.create` para crear un evento y un método desencadenador, agregar dos controladores de eventos en forma de expresiones lambda y, a continuación, desencadenar el evento para ejecutar ambas expresiones lambda.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3603.fs)]

La salida del código anterior es la siguiente.

```console
Event occurred.
Given a value: Event occurred.
```

## <a name="processing-event-streams"></a>Procesar secuencias de eventos

En lugar de agregar simplemente un controlador de eventos para un evento mediante la función [Event. Add](https://msdn.microsoft.com/library/10670d3b-8d47-4f6e-b8df-ebc6f64ef4fd) , puede usar las funciones del módulo `Event` para procesar secuencias de eventos de maneras muy personalizadas. Para ello, se utiliza la canalización hacia delante (`|>`) junto con el evento como primer valor en una serie de llamadas de función, y las funciones del módulo `Event` como llamadas de función subsiguientes.

En el siguiente ejemplo de código, se muestra cómo configurar un evento cuyo controlador se invoca únicamente en determinadas condiciones.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3604.fs)]

El [módulo observable](https://msdn.microsoft.com/library/16b8610b-b30a-4df7-aa99-d9d352276227) contiene funciones similares que operan en objetos observables. Los objetos observables son similares a los eventos pero solo se suscriben activamente a los eventos si ellos mismos son objeto de una suscripción.

## <a name="implementing-an-interface-event"></a>Implementar un evento de interfaz

Cuando se desarrollan componentes de interfaz de usuario, suele empezarse por crear un nuevo formulario o control que herede de un formulario o control ya existente. A menudo los eventos se definen en una interfaz y, en ese caso, debe implementar la interfaz para implementar el evento. La interfaz `System.ComponentModel.INotifyPropertyChanged` define un único evento `System.ComponentModel.INotifyPropertyChanged.PropertyChanged`. En el código siguiente se muestra cómo implementar el evento definido por esta interfaz heredada:

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
        printfn "Property %s changed its value to %s" args.PropertyName newValue

// Create a form, hook up the event handler, and start the application.
let appForm = new AppForm()
let inpc = appForm :> INotifyPropertyChanged
inpc.PropertyChanged.Add(appForm.OnPropertyChanged)
Application.Run(appForm)
```

Si desea enlazar el evento en el constructor, el código es algo más complejo porque el enlace del evento debe estar en un bloque `then` de un constructor adicional, como en el ejemplo siguiente:

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

## <a name="see-also"></a>Consulte también

- [Miembros](index.md)
- [Control y generación de eventos](../../../standard/events/index.md)
- [Expresiones lambda: palabra clave `fun`](../functions/lambda-expressions-the-fun-keyword.md)
- [Control. event (módulo)](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.event-module-%5bfsharp%5d)
- [Control. event&#60;(&#62; clase)](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.event%5b%27t%5d-class-%5bfsharp%5d)
- [Control. event&#60;' Delegate, '&#62; args (clase)](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.event%5b%27delegate%2c%27args%5d-class-%5bfsharp%5d)
