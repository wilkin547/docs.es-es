---
title: "Patrón de eventos estándar de .NET"
description: "Obtenga información sobre los patrones de eventos de .NET y cómo crear orígenes de eventos estándar, y suscribir y procesar eventos estándar en su código."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 8a3133d6-4ef2-46f9-9c8d-a8ea8898e4c9
ms.openlocfilehash: ff36438ab02ae6822d7df8425a615aef2ddbf2f2
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="standard-net-event-patterns"></a><span data-ttu-id="4c1f1-104">Patrón de eventos estándar de .NET</span><span class="sxs-lookup"><span data-stu-id="4c1f1-104">Standard .NET event patterns</span></span>

[<span data-ttu-id="4c1f1-105">Anterior</span><span class="sxs-lookup"><span data-stu-id="4c1f1-105">Previous</span></span>](events-overview.md)

<span data-ttu-id="4c1f1-106">Los eventos de .NET generalmente siguen unos patrones conocidos.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-106">.NET events generally follow a few known patterns.</span></span> <span data-ttu-id="4c1f1-107">Estandarizar sobre estos patrones significa que los desarrolladores pueden aprovechar el conocimiento de esos patrones estándar, que se pueden aplicar a cualquier programa de evento de .NET.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-107">Standardizing on these patterns means that developers can leverage knowledge of those standard patterns, which can be applied to any .NET event program.</span></span>

<span data-ttu-id="4c1f1-108">Vamos a analizar los patrones estándar, para que tenga todos los conocimientos necesarios para crear orígenes de eventos estándar y suscribirse y procesar eventos estándar en el código.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-108">Let's go through these standard patterns so you will have all the knowledge you need to create standard event sources, and subscribe and process standard events in your code.</span></span>

## <a name="event-delegate-signatures"></a><span data-ttu-id="4c1f1-109">Firmas de delegado de eventos</span><span class="sxs-lookup"><span data-stu-id="4c1f1-109">Event Delegate Signatures</span></span>

<span data-ttu-id="4c1f1-110">La firma estándar de un delegado de eventos de .NET es:</span><span class="sxs-lookup"><span data-stu-id="4c1f1-110">The standard signature for a .NET event delegate is:</span></span>

```csharp
void OnEventRaised(object sender, EventArgs args);
```

<span data-ttu-id="4c1f1-111">El tipo de valor devuelto es void.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-111">The return type is void.</span></span> <span data-ttu-id="4c1f1-112">Los eventos se basan en delegados y son delegados de multidifusión.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-112">Events are based on delegates and are multicast delegates.</span></span> <span data-ttu-id="4c1f1-113">Eso admite varios suscriptores para cualquier origen de eventos.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-113">That supports multiple subscribers for any event source.</span></span> <span data-ttu-id="4c1f1-114">El único valor devuelto de un método no escala a varios suscriptores de eventos.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-114">The single return value from a method doesn't scale to multiple event subscribers.</span></span> <span data-ttu-id="4c1f1-115">¿Qué valor devuelto ve el origen de evento después de generar un evento?</span><span class="sxs-lookup"><span data-stu-id="4c1f1-115">Which return value does the event source see after raising an event?</span></span> <span data-ttu-id="4c1f1-116">Más adelante en este artículo verá cómo crear protocolos de evento que admiten suscriptores de eventos que notifican información al origen del evento.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-116">Later in this article you'll see how to create event protocols that support event subscribers that report information to the event source.</span></span>

<span data-ttu-id="4c1f1-117">La lista de argumentos contiene dos argumentos: el remitente y los argumentos del evento.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-117">The argument list contains two arguments: the sender, and the event arguments.</span></span> <span data-ttu-id="4c1f1-118">El tipo de tiempo de compilación de `sender` es `System.Object`, aunque probablemente conozca un tipo más derivado que siempre será correcto.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-118">The compile time type of `sender` is `System.Object`, even though you likely know a more derived type that would always be correct.</span></span> <span data-ttu-id="4c1f1-119">Por convención, use `object`.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-119">By convention, use `object`.</span></span>

<span data-ttu-id="4c1f1-120">Típicamente, el segundo argumento era un tipo que se derivaba de `System.EventArgs`.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-120">The second argument has typically been a type that is derived from `System.EventArgs`.</span></span> <span data-ttu-id="4c1f1-121">(Verá en la [siguiente sección](modern-events.md) que ya no se aplica esta convención). Si el tipo de evento no necesita ningún argumento adicional, aún tendrá que proporcionar los dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-121">(You'll see in the [next section](modern-events.md) that this convention is no longer enforced.) If your event type does not need any additional arguments, you will still provide both arguments.</span></span>
<span data-ttu-id="4c1f1-122">Hay un valor especial, `EventArgs.Empty`, que debe usarse para indicar que el evento no contiene ninguna información adicional.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-122">There is a special value, `EventArgs.Empty` that you should use to denote that your event does not contain any additional information.</span></span>

<span data-ttu-id="4c1f1-123">Vamos a crear una clase que enumera los archivos en un directorio, o cualquiera de sus subdirectorios que siguen un patrón.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-123">Let's build a class that lists files in a directory, or any of its subdirectories that follow a pattern.</span></span> <span data-ttu-id="4c1f1-124">Este componente genera un evento para cada archivo encontrado que coincida con el modelo.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-124">This component raises an event for each file found that matches the pattern.</span></span>

<span data-ttu-id="4c1f1-125">El uso de un modelo de eventos proporciona algunas ventajas de diseño.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-125">Using an event model provides some design advantages.</span></span> <span data-ttu-id="4c1f1-126">Se pueden crear varios agentes de escucha de eventos que realicen acciones diferentes cuando se encuentre un archivo buscado.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-126">You can create multiple event listeners that perform different actions when a sought file is found.</span></span> <span data-ttu-id="4c1f1-127">La combinación de los distintos agentes de escucha puede crear algoritmos más sólidos.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-127">Combining the different listeners can create more robust algorithms.</span></span>

<span data-ttu-id="4c1f1-128">Esta es la declaración del argumento de evento inicial para buscar un archivo buscado:</span><span class="sxs-lookup"><span data-stu-id="4c1f1-128">Here is the initial event argument declaration for finding a sought file:</span></span> 

```csharp
public class FileFoundArgs : EventArgs
{
    public string FoundFile { get; }

    public FileFoundArgs(string fileName)
    {
        FoundFile = fileName;
    }
}
```

<span data-ttu-id="4c1f1-129">Aunque este tipo parece un tipo pequeño exclusivo para datos, debe seguir la convención y convertirlo en un tipo de referencia (`class`).</span><span class="sxs-lookup"><span data-stu-id="4c1f1-129">Even though this type looks like a small, data-only type, you should follow the convention and make it a reference (`class`) type.</span></span> <span data-ttu-id="4c1f1-130">Esto significa que el objeto de argumento se pasará por referencia y que todos los suscriptores verán las actualizaciones de los datos.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-130">That means the argument object will be passed by reference, and any updates to the data will be viewed by all subscribers.</span></span> <span data-ttu-id="4c1f1-131">La primera versión es un objeto inmutable.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-131">The first version is an immutable object.</span></span> <span data-ttu-id="4c1f1-132">Es preferible hacer que las propiedades en el tipo de argumento de evento sean inmutables.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-132">You should prefer to make the properties in your event argument type immutable.</span></span> <span data-ttu-id="4c1f1-133">De ese modo, un suscriptor no puede cambiar los valores antes de que los vea otro suscriptor.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-133">That way, one subscriber cannot change the values before another subscriber sees them.</span></span> <span data-ttu-id="4c1f1-134">(Hay excepciones, como verá a continuación).</span><span class="sxs-lookup"><span data-stu-id="4c1f1-134">(There are exceptions to this, as you'll see below.)</span></span>  

<span data-ttu-id="4c1f1-135">Después, debemos crear la declaración de evento en la clase FileSearcher.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-135">Next, we need to create the event declaration in the FileSearcher class.</span></span> <span data-ttu-id="4c1f1-136">Aprovechando el tipo `EventHandler<T>`, no es necesario crear otra definición de tipo más.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-136">Leveraging the `EventHandler<T>` type means that you don't need to create yet another type definition.</span></span> <span data-ttu-id="4c1f1-137">Simplemente se puede usar una especialización genérica.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-137">You simply use a generic specialization.</span></span>

<span data-ttu-id="4c1f1-138">Vamos a rellenar la clase FileSearcher para buscar archivos que coincidan con un patrón y generar el evento correcto cuando se detecte una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-138">Let's fill out the FileSearcher class to search for files that match a pattern, and raise the correct event when a match is discovered.</span></span>

```csharp
public class FileSearcher
{
    public event EventHandler<FileFoundArgs> FileFound;

    public void Search(string directory, string searchPattern)
    {
        foreach (var file in Directory.EnumerateFiles(directory, searchPattern))
        {
            FileFound?.Invoke(this, new FileFoundArgs(file));
        }
    }
}
```

## <a name="definining-and-raising-field-like-events"></a><span data-ttu-id="4c1f1-139">Definición y generación de eventos como si fueran campos</span><span class="sxs-lookup"><span data-stu-id="4c1f1-139">Definining and Raising Field-Like Events</span></span>

<span data-ttu-id="4c1f1-140">La manera más sencilla de agregar un evento a la clase es declarar ese evento como un campo público, como en el ejemplo anterior:</span><span class="sxs-lookup"><span data-stu-id="4c1f1-140">The simplest way to add an event to your class is to declare that event as a public field, as in the above example:</span></span>

```csharp
public event EventHandler<FileFoundArgs> FileFound;
```

<span data-ttu-id="4c1f1-141">Parece que se está declarando un campo público, lo que podría parecer una práctica orientada a objetos incorrecta.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-141">This looks like it's declaring a public field, which would appear to be bad object oriented practice.</span></span> <span data-ttu-id="4c1f1-142">Quiere proteger el acceso a los datos a través de propiedades o métodos.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-142">You want to protect data access through properties, or methods.</span></span> <span data-ttu-id="4c1f1-143">Aunque esto pueda parecer una práctica incorrecta, el código generado por el compilador crea contenedores para que solo se pueda tener acceso a los objetos de evento de forma segura.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-143">While this make look like a bad practice, the code generated by the compiler does create wrappers so that the event objects can only be accessed in safe ways.</span></span> <span data-ttu-id="4c1f1-144">Las únicas operaciones disponibles en un evento con aspecto de campo son las de agregar controlador:</span><span class="sxs-lookup"><span data-stu-id="4c1f1-144">The only operations available on a field-like event are add handler:</span></span>

```csharp
EventHandler<FileFoundArgs> onFileFound = (sender, eventArgs) =>
    Console.WriteLine(eventArgs.FoundFile);
lister.FileFound += onFileFound;
```

<span data-ttu-id="4c1f1-145">y quitar controlador:</span><span class="sxs-lookup"><span data-stu-id="4c1f1-145">and remove handler:</span></span>

```csharp
lister.FileFound -= onFileFound;
```

<span data-ttu-id="4c1f1-146">Tenga en cuenta que hay una variable local para el controlador.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-146">Note that there's a local variable for the handler.</span></span> <span data-ttu-id="4c1f1-147">Si usó el cuerpo de la expresión lambda, la eliminación no funcionará correctamente.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-147">If you used the body of the lambda, the remove would not work correctly.</span></span> <span data-ttu-id="4c1f1-148">Sería una instancia diferente del delegado y, en modo silencioso, no se hace nada.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-148">It would be a different instance of the delegate, and silently do nothing.</span></span>

<span data-ttu-id="4c1f1-149">El código fuera de la clase no puede generar el evento, ni puede realizar otras operaciones.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-149">Code outside the class cannot raise the event, nor can it perform any other operations.</span></span>

## <a name="returning-values-from-event-subscribers"></a><span data-ttu-id="4c1f1-150">Devolución de valores desde los suscriptores de eventos</span><span class="sxs-lookup"><span data-stu-id="4c1f1-150">Returning Values from Event Subscribers</span></span>

<span data-ttu-id="4c1f1-151">La versión simple funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-151">Your simple version is working fine.</span></span> <span data-ttu-id="4c1f1-152">Vamos a agregar otra característica: la cancelación.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-152">Let's add another feature: Cancellation.</span></span>

<span data-ttu-id="4c1f1-153">Cuando se genera el evento encontrado, los agentes de escucha deberían ser capaces de detener el procesamiento, si este archivo es el último que se busca.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-153">When you raise the found event, listeners should be able to stop further processing, if this file is that last one sought.</span></span>

<span data-ttu-id="4c1f1-154">Los controladores de eventos no devuelven un valor, por lo que se necesita comunicarlo de otra forma.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-154">The event handlers do not return a value, so you need to communicate that in another way.</span></span> <span data-ttu-id="4c1f1-155">El patrón de eventos estándar usa el objeto EventArgs para incluir campos que los suscriptores de eventos pueden usar para comunicar la cancelación.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-155">The standard event pattern uses the EventArgs object to include fields that event subscribers can use to communicate cancel.</span></span>

<span data-ttu-id="4c1f1-156">Existen dos patrones diferentes que podrían usarse, basándose en la semántica del contrato de cancelación.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-156">There are two different patterns that could be used, based on the semantics of the Cancel contract.</span></span> <span data-ttu-id="4c1f1-157">En ambos casos, se agrega un campo booleano a EventArguments para el evento del archivo encontrado.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-157">In both cases, you'll add a boolean field to the EventArguments for the found file event.</span></span> 

<span data-ttu-id="4c1f1-158">Uno de los patrones permitiría a cualquier suscriptor cancelar la operación.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-158">One pattern would allow any one subscriber to cancel the operation.</span></span>
<span data-ttu-id="4c1f1-159">Para este patrón, el nuevo campo se inicializa en `false`.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-159">For this pattern, the new field is initialized to `false`.</span></span> <span data-ttu-id="4c1f1-160">Los suscriptores pueden cambiarlo a `true`.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-160">Any subscriber can change it to `true`.</span></span> <span data-ttu-id="4c1f1-161">Después de que todos los suscriptores hayan visto el evento generado, el componente FileSearcher examina el valor booleano y toma medidas.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-161">After all subscribers have seen the event raised, the FileSearcher component examines the boolean value and takes action.</span></span>

<span data-ttu-id="4c1f1-162">El segundo patrón solo debería cancelar la operación si todos los suscriptores quieren que se cancele.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-162">The second pattern would only cancel the operation if all subscribers wanted the operation cancelled.</span></span> <span data-ttu-id="4c1f1-163">En este patrón, el nuevo campo se inicializa para indicar que se debe cancelar la operación y cualquier suscriptor puede modificarlo para indicar que la operación debe continuar.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-163">In this pattern, the new field is initialized to indicate the operation should cancel, and any subscriber could change it to indicate the operation should continue.</span></span>
<span data-ttu-id="4c1f1-164">Después de que todos los suscriptores hayan visto el evento generado, el componente FileSearcher examina el valor booleano y toma medidas.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-164">After all subscribers have seen the event raised, the FileSearcher component examines the boolean and takes action.</span></span> <span data-ttu-id="4c1f1-165">Hay un paso adicional en este patrón: el componente necesita saber si los suscriptores vieron el evento.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-165">There is one extra step in this pattern: the component needs to know if any subscribers have seen the event.</span></span> <span data-ttu-id="4c1f1-166">Si no hay ningún suscriptor, el campo indicaría incorrectamente una cancelación.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-166">If there are no subscribers, the field would indicate a cancel incorrectly.</span></span>

<span data-ttu-id="4c1f1-167">Vamos a implementar la primera versión de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-167">Let's implement the first version for this sample.</span></span> <span data-ttu-id="4c1f1-168">Debe agregar un campo booleano al tipo FileFoundEventArgs:</span><span class="sxs-lookup"><span data-stu-id="4c1f1-168">You need to add a boolean field to the FileFoundEventArgs type:</span></span>

```csharp
public class FileFoundArgs : EventArgs
{
    public string FoundFile { get; }
    public bool CancelRequested { get; set; }

    public FileFoundArgs(string fileName)
    {
        FoundFile = fileName;
    }
}
```

<span data-ttu-id="4c1f1-169">Este nuevo campo se debe inicializar en false, por lo que no se cancela por ningún motivo.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-169">This new Field should be initialized to false, so you don't cancel for no reason.</span></span> <span data-ttu-id="4c1f1-170">Es el valor predeterminado para un campo booleano, por lo que sucede automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-170">That is the default value for a boolean field, so that happens automatically.</span></span> <span data-ttu-id="4c1f1-171">El otro cambio en el componente consiste en comprobar el indicador después de generar el evento para ver si alguno de los suscriptores solicitó una cancelación:</span><span class="sxs-lookup"><span data-stu-id="4c1f1-171">The only other change to the component is to check the flag after raising the event to see if any of the subscribers have requested a cancellation:</span></span>

```csharp
public void List(string directory, string searchPattern)
{
    foreach (var file in Directory.EnumerateFiles(directory, searchPattern))
    {
        var args = new FileFoundArgs(file);
        FileFound?.Invoke(this, args);
        if (args.CancelRequested)
            break;
    }
}
```

<span data-ttu-id="4c1f1-172">Una ventaja de este patrón es que no supone un cambio brusco.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-172">One advantage of this pattern is that it isn't a breaking change.</span></span>
<span data-ttu-id="4c1f1-173">Ninguno de los suscriptores solicitó una cancelación antes y siguen sin hacerlo.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-173">None of the subscribers requested a cancel before, and they still are not.</span></span> <span data-ttu-id="4c1f1-174">No debe actualizarse el código de ningún suscriptor a menos que quieran admitir el nuevo protocolo de cancelación.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-174">None of the subscriber code needs updating unless they want to support the new cancel protocol.</span></span> <span data-ttu-id="4c1f1-175">Está acoplado muy holgadamente.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-175">It's very loosely coupled.</span></span>

<span data-ttu-id="4c1f1-176">Vamos a actualizar el suscriptor para que solicite una cancelación una vez que encuentra el primer ejecutable:</span><span class="sxs-lookup"><span data-stu-id="4c1f1-176">Let's update the subscriber so that it requests a cancellation once it finds the first executable:</span></span>

```csharp
EventHandler<FileFoundArgs> onFileFound = (sender, eventArgs) =>
{
    Console.WriteLine(eventArgs.FoundFile);
    eventArgs.CancelRequested = true;
};
```

## <a name="adding-another-event-declaration"></a><span data-ttu-id="4c1f1-177">Agregar otra declaración de evento</span><span class="sxs-lookup"><span data-stu-id="4c1f1-177">Adding Another Event Declaration</span></span>

<span data-ttu-id="4c1f1-178">Vamos a agregar una característica más y demostrar otras expresiones de lenguaje para los eventos.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-178">Let's add one more feature, and demonstrate other language idioms for events.</span></span> <span data-ttu-id="4c1f1-179">Vamos a agregar una sobrecarga del método `Search()` que recorre todos los subdirectorios en busca de archivos.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-179">Let's add an overload of the `Search()` method that traverses all subdirectories in search of files.</span></span>

<span data-ttu-id="4c1f1-180">Podría llegar a ser una operación de larga duración si el directorio tuviese muchos subdirectorios.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-180">This could get to be a lengthy operation in a directory with many sub-directories.</span></span> <span data-ttu-id="4c1f1-181">Vamos a agregar un evento que se genera cuando comienza cada nueva búsqueda en el directorio.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-181">Let's add an event that gets raised when each new directory search begins.</span></span> <span data-ttu-id="4c1f1-182">Esto permite a los suscriptores realizar el seguimiento y actualizar al usuario sobre el progreso.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-182">This enables subscribers to track progress, and update the user as to progress.</span></span> <span data-ttu-id="4c1f1-183">Todos los ejemplos creados hasta ahora son públicos.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-183">All the samples you've created so far are public.</span></span> <span data-ttu-id="4c1f1-184">Convertiremos este evento en un evento interno.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-184">Let's make this one an internal event.</span></span> <span data-ttu-id="4c1f1-185">Eso significa que también se pueden convertir en internos los tipos que se usan para los argumentos.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-185">That means you can also make the types used for the arguments internal as well.</span></span>

<span data-ttu-id="4c1f1-186">Comenzará creando la nueva clase derivada de EventArgs para informar del nuevo directorio y del progreso.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-186">You'll start by creating the new EventArgs derived class for reporting the new directory and progress.</span></span> 

```csharp
internal class SearchDirectoryArgs : EventArgs
{
    internal string CurrentSearchDirectory { get; }
    internal int TotalDirs { get; }
    internal int CompletedDirs { get; }

    internal SearchDirectoryArgs(string dir, int totalDirs, int completedDirs)
    {
        CurrentSearchDirectory = dir;
        TotalDirs = totalDirs;
        CompletedDirs = completedDirs;
    }
}
``` 

<span data-ttu-id="4c1f1-187">De nuevo, puede seguir las recomendaciones para crear un tipo de referencia inmutable para los argumentos de evento.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-187">Again, you can follow the recommendations to make an immutable reference type for the event arguments.</span></span>

<span data-ttu-id="4c1f1-188">Después, defina el evento.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-188">Next, define the event.</span></span> <span data-ttu-id="4c1f1-189">Esta vez, usará una sintaxis diferente.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-189">This time, you'll use a different syntax.</span></span> <span data-ttu-id="4c1f1-190">Además de usar la sintaxis de campos, puede crear explícitamente la propiedad con controladores add y remove.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-190">In addition to using the field syntax, you can explicitly create the property, with add and remove handlers.</span></span> <span data-ttu-id="4c1f1-191">En este ejemplo, no necesitará código adicional en los controladores de este proyecto, pero aquí se muestra cómo se crean.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-191">In this sample, you won't need extra code in those handlers in this project, but this shows how you would create them.</span></span>

```csharp
internal event EventHandler<SearchDirectoryArgs> DirectoryChanged
{
    add { directoryChanged += value; }
    remove { directoryChanged -= value; }
}
private EventHandler<SearchDirectoryArgs> directoryChanged;
```

<span data-ttu-id="4c1f1-192">En muchos aspectos, el código que se escribe aquí refleja el código que genera el compilador para las definiciones de evento de campo que se vieron anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-192">In may ways, the code you write here mirrors the code the compiler generates for the field event definitions you've seen earlier.</span></span> <span data-ttu-id="4c1f1-193">El evento se crea mediante una sintaxis muy similar a la que se usó para las [propiedades](properties.md).</span><span class="sxs-lookup"><span data-stu-id="4c1f1-193">You create the event using syntax very similar to that used for [properties](properties.md).</span></span> <span data-ttu-id="4c1f1-194">Tenga en cuenta que los controladores tienen nombres diferentes: `add` y `remove`.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-194">Notice that the handlers have different names: `add` and `remove`.</span></span> <span data-ttu-id="4c1f1-195">Se llaman para suscribirse al evento o para cancelar la suscripción al evento.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-195">These are called to subscribe to the event, or unsubscribe from the event.</span></span> <span data-ttu-id="4c1f1-196">Tenga en cuenta que también debe declarar un campo de respaldo privado para almacenar la variable de evento.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-196">Notice that you also must declare a private backing field to store the event variable.</span></span> <span data-ttu-id="4c1f1-197">Se inicializa en null.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-197">It is initialized to null.</span></span>

<span data-ttu-id="4c1f1-198">Después, vamos a agregar la sobrecarga del método Search() que recorre los subdirectorios y genera los dos eventos.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-198">Next, let's add the overload of the Search() method that traverses subdirectories and raises both events.</span></span> <span data-ttu-id="4c1f1-199">La manera más fácil de hacerlo consiste en usar un argumento predeterminado para especificar que se quiere buscar en todos los directorios:</span><span class="sxs-lookup"><span data-stu-id="4c1f1-199">The easiest way to accomplish this is to use a default argument to specify that you want to search all directories:</span></span>

```csharp
public void Search(string directory, string searchPattern, bool searchSubDirs = false)
{
    if (searchSubDirs)
    {
        var allDirectories = Directory.GetDirectories(directory, "*.*", SearchOption.AllDirectories);
        var completedDirs = 0;
        var totalDirs = allDirectories.Length + 1;
        foreach (var dir in allDirectories)
        {
            directoryChanged?.Invoke(this,
                new SearchDirectoryArgs(dir, totalDirs, completedDirs++));
            // Recursively search this child directory:
            SearchDirectory(dir, searchPattern);
        }
        // Include the Current Directory:
        directoryChanged?.Invoke(this,
            new SearchDirectoryArgs(directory, totalDirs, completedDirs++));
        SearchDirectory(directory, searchPattern);
    }
    else
    {
        SearchDirectory(directory, searchPattern);
    }
}

private void SearchDirectory(string directory, string searchPattern)
{
    foreach (var file in Directory.EnumerateFiles(directory, searchPattern))
    {
        var args = new FileFoundArgs(file);
        FileFound?.Invoke(this, args);
        if (args.CancelRequested)
            break;
    }
}
```

<span data-ttu-id="4c1f1-200">En este punto, puede ejecutar la aplicación mediante la llamada a la sobrecarga para buscar en todos los subdirectorios.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-200">At this point, you can run the application calling the overload for searching all sub-directories.</span></span> <span data-ttu-id="4c1f1-201">No hay ningún suscriptor en el nuevo evento `ChangeDirectory`, pero al usar el elemento `?.Invoke()` se garantiza que esto funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-201">There are no subscribers on the new `ChangeDirectory` event, but using the `?.Invoke()` idiom ensures that this works correctly.</span></span>

 <span data-ttu-id="4c1f1-202">Vamos a agregar un controlador para escribir una línea que muestre el progreso en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-202">Let's add a handler to write a line that shows the progress in the console window.</span></span> 

```csharp
lister.DirectoryChanged += (sender, eventArgs) =>
{
    Console.Write($"Entering '{eventArgs.CurrentSearchDirectory}'.");
    Console.WriteLine($" {eventArgs.CompletedDirs} of {eventArgs.TotalDirs} completed...");
};
```

<span data-ttu-id="4c1f1-203">Ha visto los patrones que se siguen en todo el ecosistema de. NET.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-203">You've seen patterns that are followed throughout the .NET ecosystem.</span></span>
<span data-ttu-id="4c1f1-204">El aprendizaje de estos patrones y convenciones le permitirá escribir elementos de C# y .NET rápidamente.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-204">By learning these patterns and conventions, you'll be writing idiomatic C# and .NET quickly.</span></span>

<span data-ttu-id="4c1f1-205">Más adelante verá algunos cambios en estos patrones en la versión más reciente de. NET.</span><span class="sxs-lookup"><span data-stu-id="4c1f1-205">Next, you'll see some changes in these patterns in the most recent release of .NET.</span></span>

[<span data-ttu-id="4c1f1-206">Siguiente</span><span class="sxs-lookup"><span data-stu-id="4c1f1-206">Next</span></span>](modern-events.md)
