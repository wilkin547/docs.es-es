---
title: Introducción a los eventos
description: Obtenga información sobre los eventos en .NET Core y nuestros objetivos de diseño del lenguaje para los eventos en esta introducción.
ms.date: 06/20/2016
ms.assetid: 9b8d2a00-1584-4a5b-8994-5003d54d8e0c
ms.openlocfilehash: 4da44c151244e8b5de34f550040c271131d9598c
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465239"
---
# <a name="introduction-to-events"></a><span data-ttu-id="c4ca5-103">Introducción a los eventos</span><span class="sxs-lookup"><span data-stu-id="c4ca5-103">Introduction to events</span></span>

[<span data-ttu-id="c4ca5-104">Anterior</span><span class="sxs-lookup"><span data-stu-id="c4ca5-104">Previous</span></span>](delegates-patterns.md)

<span data-ttu-id="c4ca5-105">Los eventos son, como los delegados, un mecanismo de *enlace en tiempo de ejecución*.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-105">Events are, like delegates, a *late binding* mechanism.</span></span> <span data-ttu-id="c4ca5-106">De hecho, los eventos se crean con compatibilidad de lenguaje para los delegados.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-106">In fact, events are built on the language support for delegates.</span></span>

<span data-ttu-id="c4ca5-107">Los eventos son una manera para que un objeto difunda (a todos los componentes interesados del sistema) que algo ha sucedido.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-107">Events are a way for an object to broadcast (to all interested components in the system) that something has happened.</span></span> <span data-ttu-id="c4ca5-108">Cualquier otro componente puede suscribirse al evento, y recibir una notificación cuando se genere uno.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-108">Any other component can subscribe to the event, and be notified when an event is raised.</span></span>

<span data-ttu-id="c4ca5-109">Probablemente ha usado eventos en alguna programación.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-109">You've probably used events in some of your programming.</span></span> <span data-ttu-id="c4ca5-110">Muchos sistemas gráficos tienen un modelo de eventos para notificar la interacción del usuario.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-110">Many graphical systems have an event model to report user interaction.</span></span> <span data-ttu-id="c4ca5-111">Estos eventos notificarán movimiento del mouse, pulsaciones de botón e interacciones similares.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-111">These events would report mouse movement, button presses and similar interactions.</span></span> <span data-ttu-id="c4ca5-112">Ese es uno de los más comunes, pero realmente no es el único escenario donde se usan eventos.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-112">That's one of the most common, but certainly not the only scenario where events are used.</span></span>

<span data-ttu-id="c4ca5-113">Puede definir eventos que deben generarse para las clases.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-113">You can define events that should be raised for your classes.</span></span> <span data-ttu-id="c4ca5-114">Una consideración importante a la hora de trabajar con eventos es que puede que no haya ningún objeto registrado para un evento determinado.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-114">One important consideration when working with events is that there may not be any object registered for a particular event.</span></span> <span data-ttu-id="c4ca5-115">Debe escribir el código de manera que no genere eventos cuando no esté configurado ningún agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-115">You must write your code so that it does not raise events when no listeners are configured.</span></span>

<span data-ttu-id="c4ca5-116">La suscripción a un evento también crea un acoplamiento entre dos objetos (el origen del evento y el receptor del evento).</span><span class="sxs-lookup"><span data-stu-id="c4ca5-116">Subscribing to an event also creates a coupling between two objects (the event source, and the event sink).</span></span> <span data-ttu-id="c4ca5-117">Necesita asegurarse de que el receptor del evento cancela la suscripción del origen del evento cuando ya no está interesado en eventos.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-117">You need to ensure that the event sink unsubscribes from the event source when no longer interested in events.</span></span>

## <a name="design-goals-for-event-support"></a><span data-ttu-id="c4ca5-118">Diseño de objetivos para la compatibilidad con eventos</span><span class="sxs-lookup"><span data-stu-id="c4ca5-118">Design goals for event support</span></span>

<span data-ttu-id="c4ca5-119">El diseño del lenguaje para eventos tiene como destino estos objetivos:</span><span class="sxs-lookup"><span data-stu-id="c4ca5-119">The language design for events targets these goals:</span></span>

- <span data-ttu-id="c4ca5-120">Permita un acoplamiento mínimo entre un origen de eventos y un receptor de eventos.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-120">Enable very minimal coupling between an event source and an event sink.</span></span> <span data-ttu-id="c4ca5-121">Estos dos componentes puede que no se hayan escrito por la misma organización e incluso pueden actualizarse en programaciones totalmente diferentes.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-121">These two components may not be written by the same organization, and may even be updated on totally different schedules.</span></span>

- <span data-ttu-id="c4ca5-122">Debe ser muy sencillo suscribirse a un evento y cancelar la suscripción de este.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-122">It should be very simple to subscribe to an event, and to unsubscribe from that same event.</span></span>

- <span data-ttu-id="c4ca5-123">Los orígenes de eventos deben admitir varios suscriptores de eventos.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-123">Event sources should support multiple event subscribers.</span></span> <span data-ttu-id="c4ca5-124">También deben admitir no tener ningún suscriptor de eventos asociado.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-124">It should also support having no event subscribers attached.</span></span>

<span data-ttu-id="c4ca5-125">Puede observar que los objetivos de los eventos son muy similares a los de los delegados.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-125">You can see that the goals for events are very similar to the goals for delegates.</span></span>
<span data-ttu-id="c4ca5-126">Este es el motivo por el que la compatibilidad del lenguaje de eventos se basa en la compatibilidad del lenguaje de delegados.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-126">That's why the event language support is built on the delegate language support.</span></span>

## <a name="language-support-for-events"></a><span data-ttu-id="c4ca5-127">Compatibilidad del lenguaje para eventos</span><span class="sxs-lookup"><span data-stu-id="c4ca5-127">Language support for events</span></span>

<span data-ttu-id="c4ca5-128">La sintaxis para definir eventos, y suscribirse o cancelar la suscripción de eventos, es una extensión de la sintaxis de los delegados.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-128">The syntax for defining events, and subscribing or unsubscribing from events is an extension of the syntax for delegates.</span></span>

<span data-ttu-id="c4ca5-129">Para definir un evento, use la palabra clave `event`:</span><span class="sxs-lookup"><span data-stu-id="c4ca5-129">To define an event you use the `event` keyword:</span></span>

```csharp
public event EventHandler<FileListArgs> Progress;
```

<span data-ttu-id="c4ca5-130">El tipo del evento (`EventHandler<FileListArgs>` en este ejemplo) debe ser un tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-130">The type of the event (`EventHandler<FileListArgs>` in this example) must be a delegate type.</span></span> <span data-ttu-id="c4ca5-131">Existen varias convenciones que debe seguir al declarar un evento.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-131">There are a number of conventions that you should follow when declaring an event.</span></span> <span data-ttu-id="c4ca5-132">Normalmente, el tipo de delegado de eventos tiene un valor devuelto void.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-132">Typically, the event delegate type has a void return.</span></span>
<span data-ttu-id="c4ca5-133">Las declaraciones de eventos deben ser un verbo o una frase verbal.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-133">Event declarations should be a verb, or a verb phrase.</span></span>
<span data-ttu-id="c4ca5-134">Use un tiempo verbal pasado cuando el evento notifique algo que ha ocurrido.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-134">Use past tense when the event reports something that has happened.</span></span> <span data-ttu-id="c4ca5-135">Use un tiempo verbal presente (por ejemplo, `Closing`) para notificar algo que está a punto de suceder.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-135">Use a present tense verb (for example, `Closing`) to report something that is about to happen.</span></span> <span data-ttu-id="c4ca5-136">A menudo, el uso del tiempo presente indica que su clase admite algún tipo de comportamiento de personalización.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-136">Often, using present tense indicates that your class supports some kind of customization behavior.</span></span> <span data-ttu-id="c4ca5-137">Uno de los escenarios más comunes es admitir la cancelación.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-137">One of the most common scenarios is to support cancellation.</span></span> <span data-ttu-id="c4ca5-138">Por ejemplo, un evento `Closing` puede incluir un argumento que indicará si la operación de cierre debe continuar o no.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-138">For example, a `Closing` event may include an argument that would indicate if the close operation should continue, or not.</span></span>  <span data-ttu-id="c4ca5-139">Otros escenarios pueden permitir que los autores de la llamada modifiquen el comportamiento actualizando propiedades de los argumentos de eventos.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-139">Other scenarios may enable callers to modify behavior by updating properties of the event arguments.</span></span> <span data-ttu-id="c4ca5-140">Puede generar un evento para indicar la siguiente acción propuesta que realizará un algoritmo.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-140">You may raise an event to indicate a proposed next action an algorithm will take.</span></span> <span data-ttu-id="c4ca5-141">El controlador de eventos puede exigir una acción diferente modificando las propiedades del argumento de eventos.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-141">The event handler may mandate a different action by modifying  properties of the event argument.</span></span>

<span data-ttu-id="c4ca5-142">Cuando quiera generar el evento, llame a los controladores de eventos mediante la sintaxis de invocación del delegado:</span><span class="sxs-lookup"><span data-stu-id="c4ca5-142">When you want to raise the event, you call the event handlers using the delegate invocation syntax:</span></span>

```csharp
Progress?.Invoke(this, new FileListArgs(file));
```

<span data-ttu-id="c4ca5-143">Como se ha tratado en la sección sobre [delegados](delegates-patterns.md), el operador ?.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-143">As discussed in the section on [delegates](delegates-patterns.md), the ?.</span></span>
<span data-ttu-id="c4ca5-144">hace que se garantice más fácilmente que no intenta generar el evento cuando no existen suscriptores en este.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-144">operator makes it easy to ensure that you do not attempt to raise the event when there are no subscribers to that event.</span></span>

<span data-ttu-id="c4ca5-145">Se suscribe a un evento con el operador `+=`:</span><span class="sxs-lookup"><span data-stu-id="c4ca5-145">You subscribe to an event by using the `+=` operator:</span></span>

```csharp
EventHandler<FileListArgs> onProgress = (sender, eventArgs) =>
    Console.WriteLine(eventArgs.FoundFile);

fileLister.Progress += onProgress;
```

<span data-ttu-id="c4ca5-146">El método de controlador normalmente tiene el prefijo "On" seguido del nombre del evento, como se ha mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-146">The handler method typically has the prefix 'On' followed by the event name, as shown above.</span></span>

<span data-ttu-id="c4ca5-147">Cancela la suscripción con el operador `-=`:</span><span class="sxs-lookup"><span data-stu-id="c4ca5-147">You unsubscribe using the `-=` operator:</span></span>

```csharp
fileLister.Progress -= onProgress;
```

<span data-ttu-id="c4ca5-148">Es importante que declare una variable local para la expresión que representa el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-148">It's important that you declare a local variable for the expression that represents the event handler.</span></span> <span data-ttu-id="c4ca5-149">Eso garantiza que la cancelación de la suscripción quita el controlador.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-149">That ensures the unsubscribe removes the handler.</span></span>
<span data-ttu-id="c4ca5-150">Si, en su lugar, ha usado el cuerpo de la expresión lambda, está intentando quitar un controlador que nunca ha estado asociado, lo que no produce ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-150">If, instead, you used the body of the lambda expression, you are attempting to remove a handler that has never been attached, which does nothing.</span></span>

<span data-ttu-id="c4ca5-151">En el artículo siguiente, obtendrá más información sobre los modelos de eventos típicos y las diferentes variaciones de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c4ca5-151">In the next article, you'll learn more about typical event patterns, and different variations on this example.</span></span>

[<span data-ttu-id="c4ca5-152">Siguiente</span><span class="sxs-lookup"><span data-stu-id="c4ca5-152">Next</span></span>](event-pattern.md)
