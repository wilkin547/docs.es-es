---
title: Patrones comunes para delegados
description: "Obtenga información sobre los patrones comunes para usar delegados en su código para evitar el acoplamiento seguro entre sus componentes."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 0ff8fdfd-6a11-4327-b061-0f2526f35b43
ms.openlocfilehash: 83214800fb997e9274cacfd1bae85ab07c4515a2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="common-patterns-for-delegates"></a><span data-ttu-id="e4d3b-104">Patrones comunes para delegados</span><span class="sxs-lookup"><span data-stu-id="e4d3b-104">Common Patterns for Delegates</span></span>

[<span data-ttu-id="e4d3b-105">Anterior</span><span class="sxs-lookup"><span data-stu-id="e4d3b-105">Previous</span></span>](delegates-strongly-typed.md)

<span data-ttu-id="e4d3b-106">Los delegados proporcionan un mecanismo que permite que los diseños de software supongan un acoplamiento mínimo entre los componentes.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-106">Delegates provide a mechanism that enables software designs involving minimal coupling between components.</span></span>

<span data-ttu-id="e4d3b-107">Un ejemplo excelente de este tipo de diseño es LINQ.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-107">One excellent example for this kind of design is LINQ.</span></span> <span data-ttu-id="e4d3b-108">El patrón de expresión de consulta LINQ se basa en los delegados para todas sus características.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-108">The LINQ Query Expression Pattern relies on delegates for all of its features.</span></span> <span data-ttu-id="e4d3b-109">Considere este ejemplo sencillo:</span><span class="sxs-lookup"><span data-stu-id="e4d3b-109">Consider this simple example:</span></span>

```csharp
var smallNumbers = numbers.Where(n => n < 10);
```

<span data-ttu-id="e4d3b-110">Se filtra la secuencia solo de los números que son inferiores al valor 10.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-110">This filters the sequence of numbers to only those less than the value 10.</span></span>
<span data-ttu-id="e4d3b-111">El método `Where` usa un delegado que determina qué elementos de una secuencia pasan el filtro.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-111">The `Where` method uses a delegate that determines which elements of a sequence pass the filter.</span></span> <span data-ttu-id="e4d3b-112">Cuando crea una consulta LINQ, proporciona la implementación del delegado para este fin específico.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-112">When you create a LINQ query, you supply the implementation of the delegate for this specific purpose.</span></span>

<span data-ttu-id="e4d3b-113">El prototipo para el método Where es:</span><span class="sxs-lookup"><span data-stu-id="e4d3b-113">The prototype for the Where method is:</span></span>

```csharp
public static IEnumerable<TSource> Where<in TSource> (IEnumerable<TSource> source, Func<TSource, bool> predicate);
```

<span data-ttu-id="e4d3b-114">Este ejemplo se repite con todos los métodos que forman parte de LINQ.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-114">This example is repeated with all the methods that are part of LINQ.</span></span> <span data-ttu-id="e4d3b-115">Todos se basan en delegados para el código que administra la consulta específica.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-115">They all rely on delegates for the code that manages the specific query.</span></span> <span data-ttu-id="e4d3b-116">Este modelo de diseño de API es muy eficaz para obtener información y comprender.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-116">This API design pattern is a very powerful one to learn and understand.</span></span>

<span data-ttu-id="e4d3b-117">En este ejemplo sencillo se ilustra cómo los delegados necesitan muy poco acoplamiento entre componentes.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-117">This simple example illustrates how delegates require very little coupling between components.</span></span> <span data-ttu-id="e4d3b-118">No necesita crear una clase que derive de una clase base determinada.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-118">You don't need to create a class that derives from a particular base class.</span></span> <span data-ttu-id="e4d3b-119">No necesita implementar una interfaz específica.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-119">You don't need to implement a specific interface.</span></span>
<span data-ttu-id="e4d3b-120">El único requisito consiste en proporcionar la implementación de un método que sea fundamental para la tarea que nos ocupa.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-120">The only requirement is to provide the implementation of one method that is fundamental to the task at hand.</span></span>

## <a name="building-your-own-components-with-delegates"></a><span data-ttu-id="e4d3b-121">Crear sus propios componentes con delegados</span><span class="sxs-lookup"><span data-stu-id="e4d3b-121">Building Your Own Components with Delegates</span></span>

<span data-ttu-id="e4d3b-122">Vamos a aprovechar ese ejemplo creando un componente con un diseño que se base en delegados.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-122">Let's build on that example by creating a component using a design that relies on delegates.</span></span>

<span data-ttu-id="e4d3b-123">Vamos a definir un componente que pueda usarse para mensajes de registro en un sistema grande.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-123">Let's define a component that could be used for log messages in a large system.</span></span> <span data-ttu-id="e4d3b-124">Los componentes de la biblioteca pueden usarse en muchos entornos diferentes, en varias plataformas diferentes.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-124">The library components could be used in many different environments, on multiple different platforms.</span></span> <span data-ttu-id="e4d3b-125">Existen muchas características comunes en el componente que administra los registros.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-125">There are a lot of common features in the component that manages the logs.</span></span> <span data-ttu-id="e4d3b-126">Necesitará aceptar mensajes de cualquier componente del sistema.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-126">It will need to accept messages from any component in the system.</span></span> <span data-ttu-id="e4d3b-127">Esos mensajes tendrán diferentes prioridades, que el componente principal puede administrar.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-127">Those messages will have different priorities, which the core component can manage.</span></span> <span data-ttu-id="e4d3b-128">Los mensajes deben tener marcas de tiempo en su forma de archivado final.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-128">The messages should have timestamps in their final archived form.</span></span> <span data-ttu-id="e4d3b-129">Para escenarios más avanzados, puede filtrar mensajes por el componente de origen.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-129">For more advanced scenarios, you could filter messages by the source component.</span></span>

<span data-ttu-id="e4d3b-130">Hay un aspecto de la característica que cambiará a menudo: el lugar donde se escriben los mensajes.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-130">There is one aspect of the feature that will change often: where messages are written.</span></span> <span data-ttu-id="e4d3b-131">En algunos entornos, pueden escribirse en la consola de errores.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-131">In some environments, they may be written to the error console.</span></span> <span data-ttu-id="e4d3b-132">En otros, en un archivo.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-132">In others, a file.</span></span> <span data-ttu-id="e4d3b-133">Otras posibilidades incluyen el almacenamiento de bases de datos, los registros de eventos del sistema operativo u otro almacenamiento de documentos.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-133">Other possibilities include database storage, OS event logs, or other document storage.</span></span>

<span data-ttu-id="e4d3b-134">También hay combinaciones de salida que pueden usarse en escenarios diferentes.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-134">There are also combinations of output that might be used in different scenarios.</span></span> <span data-ttu-id="e4d3b-135">Puede que quiera escribir mensajes en la consola y en un archivo.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-135">You may want to write messages to the console and to a file.</span></span>

<span data-ttu-id="e4d3b-136">Un diseño basado en delegados proporcionará una gran flexibilidad y facilitará la compatibilidad de mecanismos de almacenamiento que pueden agregarse en el futuro.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-136">A design based on delegates will provide a great deal of flexibility, and make it easy to support storage mechanisms that may be added in the future.</span></span>

<span data-ttu-id="e4d3b-137">Con este diseño, el componente de registro principal puede ser una clase no virtual, incluso sellada.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-137">Under this design, the primary log component can be a non-virtual, even sealed class.</span></span> <span data-ttu-id="e4d3b-138">Puede conectar cualquier conjunto de delegados para escribir los mensajes en un medio de almacenamiento diferente.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-138">You can plug in any set of delegates to write the messages to different storage media.</span></span> <span data-ttu-id="e4d3b-139">La compatibilidad integrada para los delegados multidifusión facilita la compatibilidad de escenarios donde los mensajes deben escribirse en varias ubicaciones (un archivo y una consola).</span><span class="sxs-lookup"><span data-stu-id="e4d3b-139">The built in support for multicast delegates makes it easy to support scenarios where messages must be written to multiple locations (a file, and a console).</span></span>

## <a name="a-first-implementation"></a><span data-ttu-id="e4d3b-140">Una primera implementación</span><span class="sxs-lookup"><span data-stu-id="e4d3b-140">A First Implementation</span></span>

<span data-ttu-id="e4d3b-141">Comencemos poco a poco: la implementación inicial aceptará mensajes nuevos y los escribirá con cualquier delegado asociado.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-141">Let's start small: the initial implementation will accept new messages, and write them using any attached delegate.</span></span> <span data-ttu-id="e4d3b-142">Puede comenzar con un delegado que escriba mensajes en la consola.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-142">You can start with one delegate that writes messages to the console.</span></span>

```csharp
public static class Logger
{
    public static Action<string> WriteMessage;
    
    public static void LogMessage(string msg)
    {
        WriteMessage(msg);
    }
}
```

<span data-ttu-id="e4d3b-143">La clase estática anterior es lo más sencillo que puede funcionar.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-143">The static class above is the simplest thing that can work.</span></span> <span data-ttu-id="e4d3b-144">Necesitamos escribir solo la implementación para el método que escribe mensajes en la consola:</span><span class="sxs-lookup"><span data-stu-id="e4d3b-144">We need to write the single implementation for the method that writes messages to the console:</span></span> 

```csharp
public static void LogToConsole(string message)
{
    Console.Error.WriteLine(message);
}
```

<span data-ttu-id="e4d3b-145">Por último, necesita conectar el delegado asociándolo al delegado WriteMessage que se declara en el registrador:</span><span class="sxs-lookup"><span data-stu-id="e4d3b-145">Finally, you need to hook up the delegate by attaching it to the WriteMessage delegate declared in the logger:</span></span>

```csharp
Logger.WriteMessage += LogToConsole;
```

## <a name="practices"></a><span data-ttu-id="e4d3b-146">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="e4d3b-146">Practices</span></span>

<span data-ttu-id="e4d3b-147">Hasta ahora nuestro ejemplo es bastante sencillo, pero sigue mostrando algunas instrucciones importantes para los diseños que involucran a los delegados.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-147">Our sample so far is fairly simple, but it still demonstrates some of the important guidelines for designs involving delegates.</span></span>

<span data-ttu-id="e4d3b-148">Con los tipos de delegado definidos en Core Framework es más sencillo para los usuarios trabajar con los delegados.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-148">Using the delegate types defined in the Core Framework makes it easier for users to work with the delegates.</span></span> <span data-ttu-id="e4d3b-149">No necesita definir tipos nuevos, y los desarrolladores que usen su biblioteca no necesitan aprender nuevos tipos de delegado especializados.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-149">You don't need to define new types, and developers using your library do not need to learn new, specialized delegate types.</span></span>

<span data-ttu-id="e4d3b-150">Las interfaces que se han usado son tan mínimas y flexibles como es posible: para crear un registrador de salida nuevo, debe crear un método.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-150">The interfaces used are as minimal and as flexible as possible: To create a new output logger, you must create one method.</span></span> <span data-ttu-id="e4d3b-151">Ese método puede ser un método estático o un método de instancia.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-151">That method may be a static method, or an instance method.</span></span> <span data-ttu-id="e4d3b-152">Puede tener cualquier acceso.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-152">It may have any access.</span></span>

## <a name="formatting-output"></a><span data-ttu-id="e4d3b-153">Resultados con formato</span><span class="sxs-lookup"><span data-stu-id="e4d3b-153">Formatting Output</span></span>

<span data-ttu-id="e4d3b-154">Vamos a hacer esta primera versión un poco más sólida y, después, empezaremos a crear otros mecanismos de registro.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-154">Let's make this first version a bit more robust, and then start creating other logging mechanisms.</span></span>

<span data-ttu-id="e4d3b-155">Después, vamos a agregar algunos argumentos al método `LogMessage()` de manera que su clase de registro cree más mensajes estructurados:</span><span class="sxs-lookup"><span data-stu-id="e4d3b-155">Next, let's add a few arguments to the `LogMessage()` method so that your log class creates more structured messages:</span></span>

```csharp
// Logger implementation two
public enum Severity
{
    Verbose,
    Trace,
    Information,
    Warning,
    Error,
    Critical
}

public static class Logger
{
    public static Action<string> WriteMessage;
    
    public static void LogMessage(Severity s, string component, string msg)
    {
        var outputMsg = $"{DateTime.Now}\t{s}\t{component}\t{msg}";
        WriteMessage(outputMsg);
    }
}
```

<span data-ttu-id="e4d3b-156">A continuación, vamos a usar ese argumento `Severity` para filtrar los mensajes que se envían a la salida del registro.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-156">Next, let's make use of that `Severity` argument to filter the messages that are sent to the log's output.</span></span> 

```csharp
public static class Logger
{
    public static Action<string> WriteMessage;
    
    public static Severity LogLevel {get;set;} = Severity.Warning;
    
    public static void LogMessage(Severity s, string component, string msg)
    {
        if (s < LogLevel)
            return;
            
        var outputMsg = $"{DateTime.Now}\t{s}\t{component}\t{msg}";
        WriteMessage(outputMsg);
    }
}
```
## <a name="practices"></a><span data-ttu-id="e4d3b-157">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="e4d3b-157">Practices</span></span>

<span data-ttu-id="e4d3b-158">Ha agregado características nuevas a la infraestructura de registro.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-158">You've added new features to the logging infrastructure.</span></span> <span data-ttu-id="e4d3b-159">Como el componente del registrador se acopla débilmente a cualquier mecanismo de salida, estas características nuevas pueden agregarse sin afectar a ningún código que implementa el delegado del registrador.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-159">Because the logger component is very loosely coupled to any output mechanism, these new features can be added with no impact on any of the code implementing the logger delegate.</span></span>

<span data-ttu-id="e4d3b-160">A medida que siga creando esto, verá más ejemplos de cómo este acoplamiento débil permite una mayor flexibilidad en la actualización de las partes del sitio sin que haya cambios en otras ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-160">As you keep building this, you'll see more examples of how this loose coupling enables greater flexibility in updating parts of the site without any changes to other locations.</span></span> <span data-ttu-id="e4d3b-161">De hecho, en una aplicación más grande, las clases de salida del registrador pueden estar en un ensamblado diferente, y ni siquiera necesitan volver a crearse.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-161">In fact, in a larger application, the logger output classes might be in a different assembly, and not even need to be rebuilt.</span></span>

## <a name="building-a-second-output-engine"></a><span data-ttu-id="e4d3b-162">Crear un segundo motor de salida</span><span class="sxs-lookup"><span data-stu-id="e4d3b-162">Building a Second Output Engine</span></span>

<span data-ttu-id="e4d3b-163">El componente de registro se está desarrollando correctamente.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-163">The Log component is coming along well.</span></span> <span data-ttu-id="e4d3b-164">Vamos a agregar un motor de salida más que registre mensajes en un archivo.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-164">Let's add one more output engine that logs messages to a file.</span></span> <span data-ttu-id="e4d3b-165">Este será un motor de salida ligeramente más involucrado.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-165">This will be a slightly more involved output engine.</span></span> <span data-ttu-id="e4d3b-166">Será una clase que encapsule las operaciones de archivo y garantice que el archivo esté siempre cerrado después de cada escritura.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-166">It will be a class that encapsulates the file operations, and ensures that the file is always closed after each write.</span></span> <span data-ttu-id="e4d3b-167">Eso garantiza que todos los datos se vacíen en el disco después de que se genere cada mensaje.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-167">That ensures that all the data is flushed to disk after each message is generated.</span></span>

<span data-ttu-id="e4d3b-168">Aquí se muestra ese registrador basado en archivos:</span><span class="sxs-lookup"><span data-stu-id="e4d3b-168">Here is that file based logger:</span></span>

```csharp
public class FileLogger
{
    private readonly string logPath;
    public FileLogger(string path)
    {
        logPath = path;
        Logger.WriteMessage += LogMessage;
    }
    
    public void DetachLog() => Logger.WriteMessage -= LogMessage;

    // make sure this can't throw.
    private void LogMessage(string msg)
    {
        try {
            using (var log = File.AppendText(logPath))
            {
                log.WriteLine(msg);
                log.Flush();
            }
        } catch (Exception e)
        {
            // Hmm. Not sure what to do.
            // Logging is failing...
        }
    }
}
```

<span data-ttu-id="e4d3b-169">Una vez que haya creado esta clase, puede inicializarla y esta asocia su método LogMessage al componente de registrador:</span><span class="sxs-lookup"><span data-stu-id="e4d3b-169">Once you've created this class, you can instantiate it and it attaches its LogMessage method to the Logger component:</span></span>

```csharp
var file = new FileLogger("log.txt");
```

<span data-ttu-id="e4d3b-170">Estos dos no son mutuamente exclusivos.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-170">These two are not mutually exclusive.</span></span> <span data-ttu-id="e4d3b-171">Puede asociar ambos métodos de registro y generar mensajes en la consola y en un archivo:</span><span class="sxs-lookup"><span data-stu-id="e4d3b-171">You could attach both log methods and generate messages to the console and a file:</span></span>

```csharp
var fileOutput = new FileLogger("log.txt");
Logger.WriteMessage += LogToConsole;
```

<span data-ttu-id="e4d3b-172">Después, incluso en la misma aplicación, puede quitar uno de los delegados sin ocasionar ningún otro problema en el sistema:</span><span class="sxs-lookup"><span data-stu-id="e4d3b-172">Later, even in the same application, you can remove one of the delegates without any other issues to the system:</span></span>

```csharp
Logger.WriteMessage -= LogToConsole;
```

## <a name="practices"></a><span data-ttu-id="e4d3b-173">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="e4d3b-173">Practices</span></span>

<span data-ttu-id="e4d3b-174">Ahora, ha agregado un segundo controlador de salida para el subsistema de registro.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-174">Now, you've added a second output handler for the logging sub-system.</span></span>
<span data-ttu-id="e4d3b-175">Este necesita un poco más de infraestructura para admitir correctamente el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-175">This one needs a bit more infrastructure to correctly support the file system.</span></span> <span data-ttu-id="e4d3b-176">El delegado es un método de instancia.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-176">The delegate is an instance method.</span></span> <span data-ttu-id="e4d3b-177">También es un método privado.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-177">It's also a private method.</span></span>
<span data-ttu-id="e4d3b-178">No existe ninguna necesidad de una mayor accesibilidad porque la infraestructura de delegado puede conectarse a los delegados.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-178">There's no need for greater accessibility because the delegate infrastructure can connect the delegates.</span></span>

<span data-ttu-id="e4d3b-179">En segundo lugar, el diseño basado en delegados permite varios métodos de salida sin ningún código adicional.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-179">Second, the delegate-based design enables multiple output methods without any extra code.</span></span> <span data-ttu-id="e4d3b-180">No necesita crear ninguna infraestructura adicional para admitir varios métodos de salida.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-180">You don't need to build any additional infrastructure to support multiple output methods.</span></span> <span data-ttu-id="e4d3b-181">Simplemente se convierten en otro método en la lista de invocación.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-181">They simply become another method on the invocation list.</span></span>

<span data-ttu-id="e4d3b-182">Preste una atención especial al código del método de salida de registro de archivo.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-182">Pay special attention to the code in the file logging output method.</span></span> <span data-ttu-id="e4d3b-183">Se codifica para garantizar que no produce ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-183">It is coded to ensure that it does not throw any exceptions.</span></span> <span data-ttu-id="e4d3b-184">Aunque esto no siempre es estrictamente necesario, a menudo es un buen procedimiento.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-184">While this isn't always strictly necessary, it's often a good practice.</span></span> <span data-ttu-id="e4d3b-185">Si cualquiera de los métodos de delegado produce una excepción, los delegados restantes que se encuentran en la invocación no se invocarán.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-185">If either of the delegate methods throws an exception, the remaining delegates that are on the invocation won't be invoked.</span></span>

<span data-ttu-id="e4d3b-186">Como última observación, el registrador de archivos debe administrar sus recursos abriendo y cerrando el archivo en cada mensaje de registro.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-186">As a last note, the file logger must manage its resources by opening and closing the file on each log message.</span></span> <span data-ttu-id="e4d3b-187">Puede optar por mantener el archivo abierto e implementar IDisposable para cerrar el archivo cuando termine.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-187">You could choose to keep the file open and implement IDisposable to close the file when you are completed.</span></span>
<span data-ttu-id="e4d3b-188">Cualquier método tiene sus ventajas e inconvenientes.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-188">Either method has its advantages and disadvantages.</span></span> <span data-ttu-id="e4d3b-189">Ambos crean un poco más de acoplamiento entre las clases.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-189">Both do create a bit more coupling between the classes.</span></span>

<span data-ttu-id="e4d3b-190">Ningún código de la clase de registrador necesitará actualizarse para admitir cualquier escenario.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-190">None of the code in the Logger class would need to be updated in order to support either scenario.</span></span>

## <a name="handling-null-delegates"></a><span data-ttu-id="e4d3b-191">Control de delegados NULL</span><span class="sxs-lookup"><span data-stu-id="e4d3b-191">Handling Null Delegates</span></span>

<span data-ttu-id="e4d3b-192">Por último, vamos a actualizar el método LogMessage de manera que sea sólido para esos casos en los que no se selecciona ningún mecanismo de salida.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-192">Finally, let's update the LogMessage method so that it is robust for those cases when no output mechanism is selected.</span></span> <span data-ttu-id="e4d3b-193">La implementación actual producirá `NullReferenceException` cuando el delegado `WriteMessage` no tenga una lista de invocación asociada.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-193">The current implementation will throw a `NullReferenceException` when the `WriteMessage` delegate does not have an invocation list attached.</span></span>
<span data-ttu-id="e4d3b-194">Puede que prefiera un diseño que continúe silenciosamente cuando no se haya asociado ningún método.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-194">You may prefer a design that silently continues when no methods have been attached.</span></span> <span data-ttu-id="e4d3b-195">Esto es sencillo con el operador condicional NULL, combinado con el método `Delegate.Invoke()`:</span><span class="sxs-lookup"><span data-stu-id="e4d3b-195">This is easy using the null conditional operator, combined with the `Delegate.Invoke()` method:</span></span>

```csharp
public static void LogMessage(string msg)
{
    WriteMessage?.Invoke(msg);
}
```

<span data-ttu-id="e4d3b-196">El operador condicional NULL (`?.`) crea un cortocircuito cuando el operando izquierdo (`WriteMessage` en este caso) es NULL, lo que significa que no se realiza ningún intento para registrar un mensaje.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-196">The null conditional operator (`?.`) short-circuits when the left operand (`WriteMessage` in this case) is null, which means no attempt is made to log a message.</span></span>

<span data-ttu-id="e4d3b-197">No encontrará el método `Invoke()` en la documentación de `System.Delegate` o `System.MulticastDelegate`.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-197">You won't find the `Invoke()` method listed in the documentation for `System.Delegate` or `System.MulticastDelegate`.</span></span> <span data-ttu-id="e4d3b-198">El compilador genera un método `Invoke` con seguridad de tipos para cualquier tipo de delegado declarado.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-198">The compiler generates a type safe `Invoke` method for any delegate type declared.</span></span> <span data-ttu-id="e4d3b-199">En este ejemplo, eso significa que `Invoke` toma un solo argumento `string` y tiene un tipo de valor devuelto void.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-199">In this example, that means `Invoke` takes a single `string` argument, and has a void return type.</span></span>

## <a name="summary-of-practices"></a><span data-ttu-id="e4d3b-200">Resumen de procedimientos</span><span class="sxs-lookup"><span data-stu-id="e4d3b-200">Summary of Practices</span></span>

<span data-ttu-id="e4d3b-201">Ha observado los comienzos de un componente de registro que puede expandirse con otros sistemas de escritura y otras características.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-201">You've seen the beginnings of a log component that could be expanded with other writers, and other features.</span></span> <span data-ttu-id="e4d3b-202">Con el uso de delegados en el diseño, estos componentes diferentes están acoplados muy débilmente.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-202">By using delegates in the design these different components are very loosely coupled.</span></span> <span data-ttu-id="e4d3b-203">Esto ofrece varias ventajas.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-203">This provides several advantages.</span></span> <span data-ttu-id="e4d3b-204">Es muy sencillo crear mecanismos de salida nuevos y asociarlos al sistema.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-204">It's very easy to create new output mechanisms and attach them to the system.</span></span> <span data-ttu-id="e4d3b-205">Estos otros mecanismos solo necesitan un método: el método que escribe el mensaje de registro.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-205">These other mechanisms only need one method: the method that writes the log message.</span></span> <span data-ttu-id="e4d3b-206">Es un diseño que es muy resistente cuando se agregan características nuevas.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-206">It's a design that is very resilient when new features are added.</span></span> <span data-ttu-id="e4d3b-207">El contrato que se necesita para cualquier sistema de escritura es implementar un método.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-207">The contract required for any writer is to implement one method.</span></span> <span data-ttu-id="e4d3b-208">Ese método puede ser un método estático o de instancia.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-208">That method could be a static or instance method.</span></span> <span data-ttu-id="e4d3b-209">Puede ser público, privado o de cualquier otro acceso legal.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-209">It could be public, private, or any other legal access.</span></span>

<span data-ttu-id="e4d3b-210">La clase de registrador puede realizar cualquier número de cambios o mejoras sin producir cambios importantes.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-210">The Logger class can make any number of enhancements or changes without introducing breaking changes.</span></span> <span data-ttu-id="e4d3b-211">Como cualquier clase, no puede modificar la API pública sin el riesgo de que se produzcan cambios importantes.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-211">Like any class, you cannot modify the public API without the risk of breaking changes.</span></span> <span data-ttu-id="e4d3b-212">Pero, como el acoplamiento entre el registrador y cualquier motor de salida se realiza solo mediante el delegado, ningún otro tipo (como interfaces o clases base) está involucrado.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-212">But, because the coupling between the logger and any output engines is only through the delegate, no other types (like interfaces or base classes) are involved.</span></span> <span data-ttu-id="e4d3b-213">El acoplamiento es lo más pequeño posible.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-213">The coupling is as small as possible.</span></span>

[<span data-ttu-id="e4d3b-214">Siguiente</span><span class="sxs-lookup"><span data-stu-id="e4d3b-214">Next</span></span>](events-overview.md)
