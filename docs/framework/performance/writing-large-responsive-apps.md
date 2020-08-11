---
title: Escribir aplicaciones grandes de .NET Framework que respondan
description: Escriba aplicaciones .NET grandes, con capacidad de respuesta o aplicaciones que procesan una gran cantidad de datos, como archivos o bases de datos.
ms.date: 03/30/2017
ms.assetid: 123457ac-4223-4273-bb58-3bc0e4957e9d
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4a9f5d50ad78b2b0bef0ece3c4fce47d2925aca5
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063762"
---
# <a name="writing-large-responsive-net-framework-apps"></a><span data-ttu-id="5532f-103">Escribir aplicaciones grandes de .NET Framework que respondan</span><span class="sxs-lookup"><span data-stu-id="5532f-103">Writing Large, Responsive .NET Framework Apps</span></span>

<span data-ttu-id="5532f-104">En este artículo se ofrecen varias sugerencias para mejorar el rendimiento de las aplicaciones .NET Framework de gran tamaño o de aquellas aplicaciones que procesan una gran cantidad de datos, como archivos o bases de datos.</span><span class="sxs-lookup"><span data-stu-id="5532f-104">This article provides tips for improving the performance of large .NET Framework apps, or apps that process a large amount of data such as files or databases.</span></span> <span data-ttu-id="5532f-105">Estas sugerencias proceden de reescribir los compiladores de C# y Visual Basic en código administrado; además, el artículo incluye varios ejemplos reales del compilador de C#.</span><span class="sxs-lookup"><span data-stu-id="5532f-105">These tips come from rewriting the C# and Visual Basic compilers in managed code, and this article includes several real examples from the C# compiler.</span></span>
  
<span data-ttu-id="5532f-106">.NET Framework es muy productivo en la compilación de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="5532f-106">The .NET Framework is highly productive for building apps.</span></span> <span data-ttu-id="5532f-107">Gracias a unos lenguajes potentes y seguros, así como a una amplia colección de bibliotecas, la compilación de aplicaciones resulta muy fructífera.</span><span class="sxs-lookup"><span data-stu-id="5532f-107">Powerful and safe languages and a rich collection of libraries make app building highly fruitful.</span></span> <span data-ttu-id="5532f-108">Sin embargo, una gran productividad conlleva responsabilidad.</span><span class="sxs-lookup"><span data-stu-id="5532f-108">However, with great productivity comes responsibility.</span></span> <span data-ttu-id="5532f-109">Use todas las posibilidades de .NET Framework, pero prepárese para ajustar el rendimiento del código cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="5532f-109">You should use all the power of the .NET Framework, but be prepared to tune your code’s performance when needed.</span></span>
  
## <a name="why-the-new-compiler-performance-applies-to-your-app"></a><span data-ttu-id="5532f-110">Por qué el rendimiento del nuevo compilador afecta a su aplicación</span><span class="sxs-lookup"><span data-stu-id="5532f-110">Why the new compiler performance applies to your app</span></span>  
 <span data-ttu-id="5532f-111">El equipo .NET Compiler Platform («Roslyn») ha reescrito los compiladores de C# y Visual Basic en código administrado con el objetivo de proporcionar nuevas API para el modelado y análisis de código, la compilación de herramientas y la habilitación de experiencias, y también para permitir una experiencia mucho más enriquecedora en cuanto a código en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5532f-111">The .NET Compiler Platform ("Roslyn") team rewrote the C# and Visual Basic compilers in managed code to provide new APIs for modeling and analyzing code, building tools, and enabling much richer, code-aware experiences in Visual Studio.</span></span> <span data-ttu-id="5532f-112">La reescritura de los compiladores y la compilación de experiencias de Visual Studio en los nuevos compiladores ha revelado información útil sobre el rendimiento que se puede emplear en cualquier aplicación de .NET Framework de gran tamaño o en cualquier aplicación que procese una gran cantidad de datos.</span><span class="sxs-lookup"><span data-stu-id="5532f-112">Rewriting the compilers and building Visual Studio experiences on the new compilers revealed useful performance insights that are applicable to any large .NET Framework app or any app that processes a lot of data.</span></span> <span data-ttu-id="5532f-113">No es necesario tener conocimientos sobre compiladores para beneficiarse de la información y los ejemplos del compilador de C#.</span><span class="sxs-lookup"><span data-stu-id="5532f-113">You don't need to know about compilers to take advantage of the insights and examples from the C# compiler.</span></span>
  
 <span data-ttu-id="5532f-114">Visual Studio usa las API de compilador para crear todas aquellas características de IntelliSense que adoran los usuarios: coloración de identificadores y palabras clave, listas de finalización de sintaxis, líneas en zigzag de errores, sugerencias sobre parámetros, emisión de código y acciones de código.</span><span class="sxs-lookup"><span data-stu-id="5532f-114">Visual Studio uses the compiler APIs to build all the IntelliSense features that users love, such as colorization of identifiers and keywords, syntax completion lists, squiggles for errors, parameter tips, code issues, and code actions.</span></span> <span data-ttu-id="5532f-115">Visual Studio proporciona esta ayuda mientras los desarrolladores escriben y modifican su código; Visual Studio debe responder en todo momento mientras el compilador modela continuamente el código que editan los desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="5532f-115">Visual Studio provides this help while developers are typing and changing their code, and Visual Studio must remain responsive while the compiler continually models the code developers edit.</span></span>
  
 <span data-ttu-id="5532f-116">Cuando los usuarios finales interactúan con la aplicación, esperan una capacidad de respuesta adecuada.</span><span class="sxs-lookup"><span data-stu-id="5532f-116">When your end users interact with your app, they expect it to be responsive.</span></span> <span data-ttu-id="5532f-117">La escritura o la gestión de comandos nunca debe bloquearse.</span><span class="sxs-lookup"><span data-stu-id="5532f-117">Typing or command handling should never be blocked.</span></span> <span data-ttu-id="5532f-118">La ayuda debe aparecer rápidamente o desaparecer si el usuario continúa escribiendo.</span><span class="sxs-lookup"><span data-stu-id="5532f-118">Help should pop up quickly or give up if the user continues typing.</span></span> <span data-ttu-id="5532f-119">La aplicación debe evitar bloquear el subproceso de la interfaz de usuario con largos cálculos que ralenticen la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5532f-119">Your app should avoid blocking the UI thread with long computations that make the app feel sluggish.</span></span>
  
 <span data-ttu-id="5532f-120">Para obtener más información sobre los compiladores de Roslyn, vea [el SDK de .net Compiler Platform](../../csharp/roslyn-sdk/index.md).</span><span class="sxs-lookup"><span data-stu-id="5532f-120">For more information about Roslyn compilers, see [The .NET Compiler Platform SDK](../../csharp/roslyn-sdk/index.md).</span></span>
  
## <a name="just-the-facts"></a><span data-ttu-id="5532f-121">Solo los hechos</span><span class="sxs-lookup"><span data-stu-id="5532f-121">Just the Facts</span></span>  
 <span data-ttu-id="5532f-122">Tenga en cuenta lo siguiente cuando ajuste el rendimiento y cree aplicaciones de .NET Framework con capacidad de respuesta.</span><span class="sxs-lookup"><span data-stu-id="5532f-122">Consider these facts when tuning performance and creating responsive .NET Framework apps.</span></span>
  
### <a name="fact-1-dont-prematurely-optimize"></a><span data-ttu-id="5532f-123">Hecho 1: No optimice prematuramente</span><span class="sxs-lookup"><span data-stu-id="5532f-123">Fact 1: Don’t prematurely optimize</span></span>  
 <span data-ttu-id="5532f-124">Escribir código más complejo de lo necesario conlleva costes de mantenimiento, depuración y pulido.</span><span class="sxs-lookup"><span data-stu-id="5532f-124">Writing code that is more complex than it needs to be incurs maintenance, debugging, and polishing costs.</span></span> <span data-ttu-id="5532f-125">Los programadores experimentados saben intuitivamente cómo resolver problemas de código y cómo escribir un código más eficaz.</span><span class="sxs-lookup"><span data-stu-id="5532f-125">Experienced programmers have an intuitive grasp of how to solve coding problems and write more efficient code.</span></span> <span data-ttu-id="5532f-126">Sin embargo, a veces optimizan el código de forma prematura.</span><span class="sxs-lookup"><span data-stu-id="5532f-126">However, they sometimes prematurely optimize their code.</span></span> <span data-ttu-id="5532f-127">Por ejemplo, usan una tabla hash cuando con una simple matriz bastaría, o utilizan un almacenamiento en caché complicado que puede consumir memoria en vez de simplemente recalcular los valores.</span><span class="sxs-lookup"><span data-stu-id="5532f-127">For example, they use a hash table when a simple array would suffice, or use complicated caching that may leak memory instead of simply recomputing values.</span></span> <span data-ttu-id="5532f-128">Incluso los programadores experimentados deben probar el rendimiento y analizar el código cuando se detectan problemas.</span><span class="sxs-lookup"><span data-stu-id="5532f-128">Even if you’re an experience programmer, you should test for performance and analyze your code when you find issues.</span></span>
  
### <a name="fact-2-if-youre-not-measuring-youre-guessing"></a><span data-ttu-id="5532f-129">Hecho 2: Si no realiza mediciones, solo tiene conjeturas</span><span class="sxs-lookup"><span data-stu-id="5532f-129">Fact 2: If you’re not measuring, you’re guessing</span></span>  
 <span data-ttu-id="5532f-130">Los perfiles y las medidas no mienten.</span><span class="sxs-lookup"><span data-stu-id="5532f-130">Profiles and measurements don’t lie.</span></span> <span data-ttu-id="5532f-131">Los perfiles muestran si la CPU está totalmente cargada o si hay un bloqueo en E/S de disco.</span><span class="sxs-lookup"><span data-stu-id="5532f-131">Profiles show you whether the CPU is fully loaded or whether you’re blocked on disk I/O.</span></span> <span data-ttu-id="5532f-132">Los perfiles indican el tipo y la cantidad de memoria que se está asignando y si la CPU emplea mucho tiempo en la [recolección de elementos no utilizados](../../standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="5532f-132">Profiles tell you what kind and how much memory you’re allocating and whether your CPU is spending a lot of time in [garbage collection](../../standard/garbage-collection/index.md) (GC).</span></span>
  
 <span data-ttu-id="5532f-133">Establezca objetivos de rendimiento para los escenarios o las experiencias de cliente claves de la aplicación y escriba pruebas para medir el rendimiento. </span><span class="sxs-lookup"><span data-stu-id="5532f-133">You should set performance goals for key customer experiences or scenarios in your app and write tests to measure performance.</span></span> <span data-ttu-id="5532f-134">Investigue los errores de las pruebas mediante el método científico: use perfiles como guía, cree hipótesis sobre el origen del problema y pruebe esas hipótesis con un experimento o cambio de código.</span><span class="sxs-lookup"><span data-stu-id="5532f-134">Investigate failing tests by applying the scientific method: use profiles to guide you, hypothesize what the issue might be, and test your hypothesis with an experiment or code change.</span></span> <span data-ttu-id="5532f-135">Establezca una línea base de medidas de rendimiento a lo largo del tiempo con pruebas periódicas para así aislar los cambios que causan regresiones en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="5532f-135">Establish baseline performance measurements over time with regular testing, so you can isolate changes that cause regressions in performance.</span></span> <span data-ttu-id="5532f-136">Si enfoca de manera rigurosa el trabajo de rendimiento, evitará perder el tiempo con actualizaciones de código que no necesita.</span><span class="sxs-lookup"><span data-stu-id="5532f-136">By approaching performance work in a rigorous way, you’ll avoid wasting time with code updates you don’t need.</span></span>
  
### <a name="fact-3-good-tools-make-all-the-difference"></a><span data-ttu-id="5532f-137">Hecho 3: Las herramientas de calidad marcan la diferencia</span><span class="sxs-lookup"><span data-stu-id="5532f-137">Fact 3: Good tools make all the difference</span></span>  
 <span data-ttu-id="5532f-138">Unas herramientas de calidad permiten profundizar rápidamente en los problemas de rendimiento más importantes (CPU, memoria o disco) y sirven para localizar el código que provoca esos cuellos de botella.</span><span class="sxs-lookup"><span data-stu-id="5532f-138">Good tools let you drill quickly into the biggest performance issues (CPU, memory, or disk) and help you locate the code that causes those bottlenecks.</span></span> <span data-ttu-id="5532f-139">Microsoft incluye una variedad de herramientas de rendimiento como [Visual Studio Profiler](/visualstudio/profiling/beginners-guide-to-performance-profiling) y [PerfView](https://www.microsoft.com/download/details.aspx?id=28567).</span><span class="sxs-lookup"><span data-stu-id="5532f-139">Microsoft ships a variety of performance tools such as [Visual Studio Profiler](/visualstudio/profiling/beginners-guide-to-performance-profiling) and [PerfView](https://www.microsoft.com/download/details.aspx?id=28567).</span></span>
  
 <span data-ttu-id="5532f-140">PerfView es una herramienta gratuita muy potente que sirve para centrarse en los problemas con raíces profundas como, por ejemplo, E/S de disco, eventos de GC y memoria.</span><span class="sxs-lookup"><span data-stu-id="5532f-140">PerfView is a free and amazingly powerful tool that helps you focus on deep issues such as disk I/O, GC events, and memory.</span></span> <span data-ttu-id="5532f-141">Puede capturar eventos de [Seguimiento de eventos para Windows](../wcf/samples/etw-tracing.md) (ETW) relacionados con el rendimiento y ver fácilmente información por aplicación, por proceso, por pila y por subproceso.</span><span class="sxs-lookup"><span data-stu-id="5532f-141">You can capture performance-related [Event Tracing for Windows](../wcf/samples/etw-tracing.md) (ETW) events and view easily per app, per process, per stack, and per thread information.</span></span> <span data-ttu-id="5532f-142">PerfView muestra la cantidad y el tipo de memoria que asigna la aplicación, así como las funciones o pilas de llamadas que contribuyen en determinada medida a las asignaciones de memoria.</span><span class="sxs-lookup"><span data-stu-id="5532f-142">PerfView shows you how much and what kind of memory your app allocates, and which functions or call stacks contribute how much to the memory allocations.</span></span> <span data-ttu-id="5532f-143">Para más información, vea los completos artículos de ayuda, las demostraciones y los vídeos que se incluyen con la herramienta (como los [tutoriales de PerfView](https://channel9.msdn.com/Series/PerfView-Tutorial) de Channel 9).</span><span class="sxs-lookup"><span data-stu-id="5532f-143">For details, see the rich help topics, demos, and videos included with the tool (such as the [PerfView tutorials](https://channel9.msdn.com/Series/PerfView-Tutorial) on Channel 9).</span></span>
  
### <a name="fact-4-its-all-about-allocations"></a><span data-ttu-id="5532f-144">Hecho 4: La clave está en las asignaciones</span><span class="sxs-lookup"><span data-stu-id="5532f-144">Fact 4: It’s all about allocations</span></span>  
 <span data-ttu-id="5532f-145">Podría pensarse que la compilación de una aplicación de .NET Framework que muestre una buena capacidad de respuesta depende de la utilización de los algoritmos —como usar una ordenación rápida en vez de una de burbuja—, pero no es así.</span><span class="sxs-lookup"><span data-stu-id="5532f-145">You might think that building a responsive .NET Framework app is all about algorithms, such as using quick sort instead of bubble sort, but that's not the case.</span></span> <span data-ttu-id="5532f-146">El factor de mayor peso a la hora de compilar una aplicación diligente es la asignación de memoria, sobre todo cuando la aplicación es muy grande o procesa grandes cantidades de datos.</span><span class="sxs-lookup"><span data-stu-id="5532f-146">The biggest factor in building a responsive app is allocating memory, especially when your app is very large or processes large amounts of data.</span></span>
  
 <span data-ttu-id="5532f-147">Casi todo el trabajo de compilar las experiencias de IDE con las nuevas API de compilador se invirtió en evitar las asignaciones y administrar las estrategias de almacenamiento en caché.</span><span class="sxs-lookup"><span data-stu-id="5532f-147">Almost all the work to build responsive IDE experiences with the new compiler APIs involved avoiding allocations and managing caching strategies.</span></span> <span data-ttu-id="5532f-148">El seguimiento de PerfView muestra que el rendimiento de los nuevos compiladores de C# y Visual Basic rara vez está asociado a la CPU.</span><span class="sxs-lookup"><span data-stu-id="5532f-148">PerfView traces show that the performance of the new C# and Visual Basic compilers is rarely CPU bound.</span></span> <span data-ttu-id="5532f-149">Los compiladores pueden estar asociados a E/S al leer miles o millones de líneas de código, al leer metadatos o al emitir código generado.</span><span class="sxs-lookup"><span data-stu-id="5532f-149">The compilers can be I/O bound when reading hundreds of thousands or millions of lines of code, reading metadata, or emitting generated code.</span></span> <span data-ttu-id="5532f-150">Los retrasos del subproceso de la interfaz de usuario se deben prácticamente todos a la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="5532f-150">The UI thread delays are nearly all due to garbage collection.</span></span> <span data-ttu-id="5532f-151">La GC de .NET Framework está ajustada para optimizar el rendimiento y una gran parte de su trabajo se realiza mientras se ejecuta el código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5532f-151">The .NET Framework GC is highly tuned for performance and does much of its work concurrently while app code executes.</span></span> <span data-ttu-id="5532f-152">Pero una única asignación puede desencadenar una costosa recolección [gen2](../../standard/garbage-collection/fundamentals.md) y detener todos los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="5532f-152">However, a single allocation can trigger an expensive [gen2](../../standard/garbage-collection/fundamentals.md) collection, stopping all threads.</span></span>
  
## <a name="common-allocations-and-examples"></a><span data-ttu-id="5532f-153">Asignaciones comunes y ejemplos</span><span class="sxs-lookup"><span data-stu-id="5532f-153">Common allocations and examples</span></span>  
 <span data-ttu-id="5532f-154">Las expresiones de ejemplo que se incluyen en esta sección tiene asignaciones que parecen pequeñas.</span><span class="sxs-lookup"><span data-stu-id="5532f-154">The example expressions in this section have hidden allocations that appear small.</span></span> <span data-ttu-id="5532f-155">Aun así, si una aplicación grande ejecuta las expresiones un número de veces suficiente, pueden producirse cientos de megabytes, e incluso gigabytes, de asignaciones.</span><span class="sxs-lookup"><span data-stu-id="5532f-155">However, if a large app executes the expressions enough times, they can causes hundreds of megabytes, even gigabytes, of allocations.</span></span> <span data-ttu-id="5532f-156">Por ejemplo, durante las pruebas de un minuto en las que se simulaba la escritura de un desarrollador en el editor se asignaron gigabytes de memoria, y esto hizo que el equipo de rendimiento se centrase en los escenarios de escritura.</span><span class="sxs-lookup"><span data-stu-id="5532f-156">For example, one-minute tests that simulated a developer’s typing in the editor allocated gigabytes of memory and led the performance team to focus on typing scenarios.</span></span>
  
### <a name="boxing"></a><span data-ttu-id="5532f-157">Boxing</span><span class="sxs-lookup"><span data-stu-id="5532f-157">Boxing</span></span>  
 <span data-ttu-id="5532f-158">La [conversión boxing](../../csharp/programming-guide/types/boxing-and-unboxing.md) se produce cuando se ajustan en un objeto tipos de valores que normalmente residen en la pila o en estructuras de datos.</span><span class="sxs-lookup"><span data-stu-id="5532f-158">[Boxing](../../csharp/programming-guide/types/boxing-and-unboxing.md) occurs when value types that normally live on the stack or in data structures are wrapped in an object.</span></span> <span data-ttu-id="5532f-159">Es decir, se asigna un objeto para contener los datos y luego se devuelve un puntero al objeto.</span><span class="sxs-lookup"><span data-stu-id="5532f-159">That is, you allocate an object to hold the data, and then return a pointer to the object.</span></span> <span data-ttu-id="5532f-160">.NET Framework a veces realiza una conversión boxing de valores debido a la signatura de un método o al tipo de la ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="5532f-160">The .NET Framework sometimes boxes values due to the signature of a method or the type of a storage location.</span></span> <span data-ttu-id="5532f-161">El encapsulamiento de un tipo de valor en un objeto obliga a asignar memoria.</span><span class="sxs-lookup"><span data-stu-id="5532f-161">Wrapping a value type in an object causes memory allocation.</span></span> <span data-ttu-id="5532f-162">Muchas operaciones de conversión boxing puede sumar megabytes o gigabytes de asignaciones a la aplicación, lo que significa que esta provocará más GC.</span><span class="sxs-lookup"><span data-stu-id="5532f-162">Many boxing operations can contribute megabytes or gigabytes of allocations to your app, which means that your app will cause more GCs.</span></span> <span data-ttu-id="5532f-163">.NET Framework y los compiladores de lenguaje evitan la conversión boxing siempre que pueden, pero a veces se produce en el momento menos esperado.</span><span class="sxs-lookup"><span data-stu-id="5532f-163">The .NET Framework and the language compilers avoid boxing when possible, but sometimes it happens when you least expect it.</span></span>
  
 <span data-ttu-id="5532f-164">Para ver la conversión boxing en PerfView, inicie un seguimiento y mire GC Heap Alloc Stacks bajo el nombre de proceso de su aplicación (recuerde, PerfView informa de todos los procesos).</span><span class="sxs-lookup"><span data-stu-id="5532f-164">To see boxing in PerfView, open a trace and look at GC Heap Alloc Stacks under your app’s process name (remember, PerfView reports on all processes).</span></span> <span data-ttu-id="5532f-165">Si ve tipos como <xref:System.Int32?displayProperty=nameWithType> y <xref:System.Char?displayProperty=nameWithType> en las asignaciones, significa que está realizando una conversión boxing de tipos de valores.</span><span class="sxs-lookup"><span data-stu-id="5532f-165">If you see types like <xref:System.Int32?displayProperty=nameWithType> and <xref:System.Char?displayProperty=nameWithType> under allocations, you are boxing value types.</span></span> <span data-ttu-id="5532f-166">Si se elige uno de estos tipos, se mostrarán las pilas y las funciones en las que se han convertido.</span><span class="sxs-lookup"><span data-stu-id="5532f-166">Choosing one of these types will show the stacks and functions in which they are boxed.</span></span>
  
 <span data-ttu-id="5532f-167">**Ejemplo 1: métodos de cadena y argumentos de tipo de valor**</span><span class="sxs-lookup"><span data-stu-id="5532f-167">**Example 1: string methods and value type arguments**</span></span>  
  
 <span data-ttu-id="5532f-168">En este código de ejemplo se muestra una potencial conversión boxing innecesaria y excesiva:</span><span class="sxs-lookup"><span data-stu-id="5532f-168">This sample code illustrates potentially unnecessary and excessive boxing:</span></span>  
  
```csharp  
public class Logger  
{  
    public static void WriteLine(string s) { /*...*/ }  
}  
  
public class BoxingExample  
{  
    public void Log(int id, int size)  
    {  
        var s = string.Format("{0}:{1}", id, size);  
        Logger.WriteLine(s);  
    }  
}  
```  
  
 <span data-ttu-id="5532f-169">El código proporciona funcionalidad de registro, por lo que la aplicación puede llamar a la función `Log` frecuentemente, quizá millones de veces.</span><span class="sxs-lookup"><span data-stu-id="5532f-169">This code provides logging functionality, so an app may call the `Log` function frequently, maybe millions of times.</span></span> <span data-ttu-id="5532f-170">El problema es que la llamada a `string.Format` se resuelve a la sobrecarga <xref:System.String.Format%28System.String%2CSystem.Object%2CSystem.Object%29>.</span><span class="sxs-lookup"><span data-stu-id="5532f-170">The problem is that the call to `string.Format` resolves to the <xref:System.String.Format%28System.String%2CSystem.Object%2CSystem.Object%29> overload.</span></span>
  
 <span data-ttu-id="5532f-171">Esta sobrecarga necesita que .NET Framework realice una conversión boxing de los valores `int` para transformarlos en objetos y pasarlos a esta llamada al método.</span><span class="sxs-lookup"><span data-stu-id="5532f-171">This overload requires the .NET Framework to box the `int` values into objects to pass them to this method call.</span></span> <span data-ttu-id="5532f-172">Una solución parcial es llamar a `id.ToString()` y `size.ToString()`, y pasar todas las cadenas (que son objetos) a la llamada `string.Format`.</span><span class="sxs-lookup"><span data-stu-id="5532f-172">A partial fix is to call `id.ToString()` and `size.ToString()` and pass all strings (which are objects) to the `string.Format` call.</span></span> <span data-ttu-id="5532f-173">La llamada a `ToString()` no asigna una cadena, pero esa asignación se producirá de todos modos en `string.Format`.</span><span class="sxs-lookup"><span data-stu-id="5532f-173">Calling `ToString()` does allocate a string, but that allocation will happen anyway inside `string.Format`.</span></span>
  
 <span data-ttu-id="5532f-174">Puede considerar que esta llamada básica a `string.Format` es simplemente concatenación de cadenas, por lo que puede escribir este código en su lugar:</span><span class="sxs-lookup"><span data-stu-id="5532f-174">You might consider that this basic call to `string.Format` is just string concatenation, so you might write this code instead:</span></span>  
  
```csharp  
var s = id.ToString() + ':' + size.ToString();  
```  
  
 <span data-ttu-id="5532f-175">No obstante, esa línea de código introduce una asignación boxing porque se compila en <xref:System.String.Concat%28System.Object%2CSystem.Object%2CSystem.Object%29>.</span><span class="sxs-lookup"><span data-stu-id="5532f-175">However, that line of code introduces a boxing allocation because it compiles to <xref:System.String.Concat%28System.Object%2CSystem.Object%2CSystem.Object%29>.</span></span> <span data-ttu-id="5532f-176">.NET Framework debe realizar una conversión boxing del literal de carácter para invocar a `Concat`.</span><span class="sxs-lookup"><span data-stu-id="5532f-176">The .NET Framework must box the character literal to invoke `Concat`</span></span>  
  
 <span data-ttu-id="5532f-177">**Corrección para el ejemplo 1**</span><span class="sxs-lookup"><span data-stu-id="5532f-177">**Fix for example 1**</span></span>  
  
 <span data-ttu-id="5532f-178">La solución es sencilla.</span><span class="sxs-lookup"><span data-stu-id="5532f-178">The complete fix is simple.</span></span> <span data-ttu-id="5532f-179">Simplemente reemplace el literal de carácter por un literal de cadena; este no provoca conversión boxing porque las cadenas ya son objetos:</span><span class="sxs-lookup"><span data-stu-id="5532f-179">Just replace the character literal with a string literal, which incurs no boxing because strings are already objects:</span></span>  
  
```csharp  
var s = id.ToString() + ":" + size.ToString();  
```  
  
 <span data-ttu-id="5532f-180">**Ejemplo 2: conversión boxing de enum**</span><span class="sxs-lookup"><span data-stu-id="5532f-180">**Example 2: enum boxing**</span></span>  
  
 <span data-ttu-id="5532f-181">Este ejemplo fue el causante de una cantidad enorme de asignación en los nuevos compiladores de C# y Visual Basic debido al uso frecuente de tipos de enumeración, especialmente en operaciones de búsqueda en diccionarios.</span><span class="sxs-lookup"><span data-stu-id="5532f-181">This example was responsible for a huge amount of allocation in the new C# and Visual Basic compilers due to frequent use of enumeration types, especially in dictionary lookup operations.</span></span>
  
```csharp  
public enum Color  
{  
    Red, Green, Blue  
}  
  
public class BoxingExample  
{  
    private string name;  
    private Color color;  
    public override int GetHashCode()  
    {  
        return name.GetHashCode() ^ color.GetHashCode();  
    }  
}  
```  
  
 <span data-ttu-id="5532f-182">Este problema es muy sutil.</span><span class="sxs-lookup"><span data-stu-id="5532f-182">This problem is very subtle.</span></span> <span data-ttu-id="5532f-183">PerfView consideraba esto como una conversión boxing de <xref:System.Enum.GetHashCode>, ya que, por motivos de implementación, el método realiza una conversión boxing de la representación subyacente del tipo de enumeración.</span><span class="sxs-lookup"><span data-stu-id="5532f-183">PerfView would report this as <xref:System.Enum.GetHashCode> boxing because the method boxes the underlying representation of the enumeration type, for implementation reasons.</span></span> <span data-ttu-id="5532f-184">Si observa detenidamente en PerfView, puede ver dos asignaciones de conversión boxing para cada llamada a <xref:System.Enum.GetHashCode>.</span><span class="sxs-lookup"><span data-stu-id="5532f-184">If you look closely in PerfView, you may see two boxing allocations for each call to <xref:System.Enum.GetHashCode>.</span></span> <span data-ttu-id="5532f-185">El compilador inserta una y .NET Framework inserta la otra.</span><span class="sxs-lookup"><span data-stu-id="5532f-185">The compiler inserts one, and the .NET Framework inserts the other.</span></span>
  
 <span data-ttu-id="5532f-186">**Corrección para el ejemplo 2**</span><span class="sxs-lookup"><span data-stu-id="5532f-186">**Fix for example 2**</span></span>  
  
 <span data-ttu-id="5532f-187">Es muy fácil evitar ambas asignaciones si se convierte a la representación subyacente antes de llamar a <xref:System.Enum.GetHashCode>:</span><span class="sxs-lookup"><span data-stu-id="5532f-187">You can easily avoid both allocations by casting to the underlying representation before calling <xref:System.Enum.GetHashCode>:</span></span>  
  
```csharp  
((int)color).GetHashCode()  
```  
  
 <span data-ttu-id="5532f-188">Otra fuente común de conversión boxing en tipos de enumeración es el método <xref:System.Enum.HasFlag%28System.Enum%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5532f-188">Another common source of boxing on enumeration types is the <xref:System.Enum.HasFlag%28System.Enum%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="5532f-189">Es necesario realizar una conversión boxing del argumento pasado a <xref:System.Enum.HasFlag%28System.Enum%29>.</span><span class="sxs-lookup"><span data-stu-id="5532f-189">The argument passed to <xref:System.Enum.HasFlag%28System.Enum%29> has to be boxed.</span></span> <span data-ttu-id="5532f-190">En la mayoría de los casos, el reemplazo de llamadas a <xref:System.Enum.HasFlag%28System.Enum%29?displayProperty=nameWithType> con una prueba bit a bit es más sencilla y sin asignaciones.</span><span class="sxs-lookup"><span data-stu-id="5532f-190">In most cases, replacing calls to <xref:System.Enum.HasFlag%28System.Enum%29?displayProperty=nameWithType> with a bitwise test is simpler and allocation-free.</span></span>
  
 <span data-ttu-id="5532f-191">No olvide el primer hecho de rendimiento (no optimice prematuramente) y no empiece a reescribir todo su código de este modo.</span><span class="sxs-lookup"><span data-stu-id="5532f-191">Keep the first performance fact in mind (that is, don’t prematurely optimize) and don’t start rewriting all your code in this way.</span></span> <span data-ttu-id="5532f-192">Tenga en cuenta los costes de la conversión boxing, pero, antes de cambiar el código, perfile su aplicación y busque los puntos conflictivos.</span><span class="sxs-lookup"><span data-stu-id="5532f-192">Be aware of these boxing costs, but change your code only after profiling your app and finding the hot spots.</span></span>
  
### <a name="strings"></a><span data-ttu-id="5532f-193">Cadenas</span><span class="sxs-lookup"><span data-stu-id="5532f-193">Strings</span></span>  
 <span data-ttu-id="5532f-194">La manipulación de cadenas es uno de los mayores causantes de las asignaciones y con frecuencia aparece entre el top cinco de las asignaciones en PerfView.</span><span class="sxs-lookup"><span data-stu-id="5532f-194">String manipulations are some of the biggest culprits for allocations, and they often show up in PerfView in the top five allocations.</span></span> <span data-ttu-id="5532f-195">Los programas usan cadenas para serialización, JSON y API REST.</span><span class="sxs-lookup"><span data-stu-id="5532f-195">Programs use strings for serialization, JSON, and REST APIs.</span></span> <span data-ttu-id="5532f-196">Las cadenas se pueden usar como constantes de programación para interoperar con sistemas cuando no se pueden usar tipos de enumeración.</span><span class="sxs-lookup"><span data-stu-id="5532f-196">You can use strings as programmatic constants for interoperating with systems when you can’t use enumeration types.</span></span> <span data-ttu-id="5532f-197">Cuando la generación de perfiles muestra que las cadenas están afectando enormemente al rendimiento, busque llamadas a métodos <xref:System.String> como <xref:System.String.Format%2A>, <xref:System.String.Concat%2A>, <xref:System.String.Split%2A>, <xref:System.String.Join%2A>, <xref:System.String.Substring%2A>, etc.</span><span class="sxs-lookup"><span data-stu-id="5532f-197">When your profiling shows that strings are highly affecting performance, look for calls to <xref:System.String> methods such as <xref:System.String.Format%2A>, <xref:System.String.Concat%2A>, <xref:System.String.Split%2A>, <xref:System.String.Join%2A>, <xref:System.String.Substring%2A>, and so on.</span></span> <span data-ttu-id="5532f-198">El uso de <xref:System.Text.StringBuilder> para evitar el crear una cadena a partir de muchos fragmentos sirve de ayuda, pero incluso asignando el objeto <xref:System.Text.StringBuilder> puede originar un cuello de botella que es necesario administrar.</span><span class="sxs-lookup"><span data-stu-id="5532f-198">Using <xref:System.Text.StringBuilder> to avoid the cost of creating one string from many pieces helps, but even allocating the <xref:System.Text.StringBuilder> object might become a bottleneck that you need to manage.</span></span>
  
 <span data-ttu-id="5532f-199">**Ejemplo 3: operaciones de cadena**</span><span class="sxs-lookup"><span data-stu-id="5532f-199">**Example 3: string operations**</span></span>  
  
 <span data-ttu-id="5532f-200">El compilador de C# tenía este código que escribe el texto de un comentario de documento XML con formato:</span><span class="sxs-lookup"><span data-stu-id="5532f-200">The C# compiler had this code that writes the text of a formatted XML doc comment:</span></span>  
  
```csharp  
public void WriteFormattedDocComment(string text)  
{  
    string[] lines = text.Split(new[] { "\r\n", "\r", "\n" },  
                                StringSplitOptions.None);  
    int numLines = lines.Length;  
    bool skipSpace = true;  
    if (lines[0].TrimStart().StartsWith("///"))  
    {  
        for (int i = 0; i < numLines; i++)  
        {  
            string trimmed = lines[i].TrimStart();  
            if (trimmed.Length < 4 || !char.IsWhiteSpace(trimmed[3]))  
            {  
                skipSpace = false;  
                break;  
            }  
        }  
        int substringStart = skipSpace ? 4 : 3;  
        for (int i = 0; i < numLines; i++)  
            WriteLine(lines[i].TrimStart().Substring(substringStart));  
    }  
    else { /* ... */ }  
```  
  
 <span data-ttu-id="5532f-201">Como se puede ver, en este código hay mucha manipulación de cadenas.</span><span class="sxs-lookup"><span data-stu-id="5532f-201">You can see that this code does a lot of string manipulation.</span></span> <span data-ttu-id="5532f-202">El código usa métodos de biblioteca para dividir líneas en cadenas independientes, para reducir espacio en blanco, para comprobar si el argumento `text` es un comentario de documentación XML y para extraer subcadenas de las líneas.</span><span class="sxs-lookup"><span data-stu-id="5532f-202">The code uses library methods to split lines into separate strings, to trim white space, to check whether the argument `text` is an XML documentation comment, and to extract substrings from lines.</span></span>
  
 <span data-ttu-id="5532f-203">En la primera línea dentro de `WriteFormattedDocComment`, la llamada `text.Split` asigna una nueva matriz de tres elementos como argumento cada vez que se llama.</span><span class="sxs-lookup"><span data-stu-id="5532f-203">On the first line inside `WriteFormattedDocComment`, the `text.Split` call allocates a new three-element array as the argument every time it’s called.</span></span> <span data-ttu-id="5532f-204">El compilador tiene que emitir código para asignar esta matriz en cada ocasión.</span><span class="sxs-lookup"><span data-stu-id="5532f-204">The compiler has to emit code to allocate this array each time.</span></span> <span data-ttu-id="5532f-205">Eso se debe a que el compilador no sabe si <xref:System.String.Split%2A> almacena la matriz en algún lugar donde pueda ser modificada por otro código, lo que afectaría a las llamadas posteriores a `WriteFormattedDocComment`.</span><span class="sxs-lookup"><span data-stu-id="5532f-205">That’s because the compiler doesn’t know if <xref:System.String.Split%2A> stores the array somewhere where the array might be modified by other code, which would affect later calls to `WriteFormattedDocComment`.</span></span> <span data-ttu-id="5532f-206">La llamada a <xref:System.String.Split%2A> también asigna una cadena para cada línea en `text` y asigna otra memoria para realizar la operación.</span><span class="sxs-lookup"><span data-stu-id="5532f-206">The call to <xref:System.String.Split%2A> also allocates a string for every line in `text` and allocates other memory to perform the operation.</span></span>
  
 <span data-ttu-id="5532f-207">`WriteFormattedDocComment` tiene tres llamadas al método <xref:System.String.TrimStart%2A>.</span><span class="sxs-lookup"><span data-stu-id="5532f-207">`WriteFormattedDocComment` has three calls to the <xref:System.String.TrimStart%2A> method.</span></span> <span data-ttu-id="5532f-208">Dos están en bucles internos que duplican el trabajo y las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="5532f-208">Two are in inner loops that duplicate work and allocations.</span></span> <span data-ttu-id="5532f-209">Para empeorar las cosas, la llamada al método <xref:System.String.TrimStart%2A> sin argumentos asigna una matriz vacía (para el parámetro `params`) además del resultado de la cadena.</span><span class="sxs-lookup"><span data-stu-id="5532f-209">To make matters worse, calling the <xref:System.String.TrimStart%2A> method with no arguments allocates an empty array (for the `params` parameter) in addition to the string result.</span></span>
  
 <span data-ttu-id="5532f-210">Por último, hay una llamada al método <xref:System.String.Substring%2A>, que normalmente asigna una cadena nueva.</span><span class="sxs-lookup"><span data-stu-id="5532f-210">Lastly, there is a call to the <xref:System.String.Substring%2A> method, which usually allocates a new string.</span></span>
  
 <span data-ttu-id="5532f-211">**Corrección para el ejemplo 3**</span><span class="sxs-lookup"><span data-stu-id="5532f-211">**Fix for example 3**</span></span>  
  
 <span data-ttu-id="5532f-212">A diferencia de los ejemplos anteriores, estas asignaciones no se resuelven con pequeñas asignaciones.</span><span class="sxs-lookup"><span data-stu-id="5532f-212">Unlike the earlier examples, small edits cannot fix these allocations.</span></span> <span data-ttu-id="5532f-213">Es necesario dar un paso atrás, observar el problema y enfocarlo de manera diferente.</span><span class="sxs-lookup"><span data-stu-id="5532f-213">You need to step back, look at the problem, and approach it differently.</span></span> <span data-ttu-id="5532f-214">Por ejemplo, observará que el argumento para `WriteFormattedDocComment()` es una cadena que tiene toda la información que necesita el método, por lo que el código podría hacer más labores de indización en vez de asignar muchas cadenas parciales.</span><span class="sxs-lookup"><span data-stu-id="5532f-214">For example, you'll notice that the argument to `WriteFormattedDocComment()` is a string that has all the information that the method needs, so the code could do more indexing instead of allocating many partial strings.</span></span>
  
 <span data-ttu-id="5532f-215">El equipo de rendimiento del compilador abordó estas asignaciones con un código como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="5532f-215">The compiler’s performance team tackled all these allocations with code like this:</span></span>  
  
```csharp  
private int IndexOfFirstNonWhiteSpaceChar(string text, int start) {  
    while (start < text.Length && char.IsWhiteSpace(text[start])) start++;  
    return start;  
}  
  
private bool TrimmedStringStartsWith(string text, int start, string prefix) {  
    start = IndexOfFirstNonWhiteSpaceChar(text, start);  
    int len = text.Length - start;  
    if (len < prefix.Length) return false;  
    for (int i = 0; i < len; i++)  
    {  
        if (prefix[i] != text[start + i]) return false;  
    }  
    return true;  
}  
  
// etc...
```  
  
 <span data-ttu-id="5532f-216">La primera versión de `WriteFormattedDocComment()` asignaba una matriz, varias subcadenas y una subcadena recortada junto con una matriz `params` vacía.</span><span class="sxs-lookup"><span data-stu-id="5532f-216">The first version of `WriteFormattedDocComment()` allocated an array, several substrings, and a trimmed substring along with an empty `params` array.</span></span> <span data-ttu-id="5532f-217">También se ha comprobado "///".</span><span class="sxs-lookup"><span data-stu-id="5532f-217">It also checked for "///".</span></span> <span data-ttu-id="5532f-218">El código revisado solo usa la indización y no realiza ninguna asignación.</span><span class="sxs-lookup"><span data-stu-id="5532f-218">The revised code uses only indexing and allocates nothing.</span></span> <span data-ttu-id="5532f-219">Busca el primer carácter que no sea un espacio en blanco y, a continuación, comprueba el carácter carácter a carácter para ver si la cadena comienza con "///".</span><span class="sxs-lookup"><span data-stu-id="5532f-219">It finds the first character that is not white space, and then checks character by character to see if the string starts with "///".</span></span> <span data-ttu-id="5532f-220">El nuevo código usa en `IndexOfFirstNonWhiteSpaceChar` lugar de <xref:System.String.TrimStart%2A> para devolver el primer índice (después de un índice de inicio especificado) en el que se produce un carácter que no es un espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="5532f-220">The new code uses `IndexOfFirstNonWhiteSpaceChar` instead of <xref:System.String.TrimStart%2A> to return the first index (after a specified start index) where a non-white-space character occurs.</span></span> <span data-ttu-id="5532f-221">La corrección no está completa, pero sirve para comprobar cómo se aplican correcciones similares para obtener una solución completa.</span><span class="sxs-lookup"><span data-stu-id="5532f-221">The fix is not complete, but you can see how to apply similar fixes for a complete solution.</span></span> <span data-ttu-id="5532f-222">Al aplicar este enfoque en todo el código, se pueden quitar todas las asignaciones en `WriteFormattedDocComment()`.</span><span class="sxs-lookup"><span data-stu-id="5532f-222">By applying this approach throughout the code, you can remove all allocations in `WriteFormattedDocComment()`.</span></span>
  
 <span data-ttu-id="5532f-223">**Ejemplo 4: StringBuilder**</span><span class="sxs-lookup"><span data-stu-id="5532f-223">**Example 4: StringBuilder**</span></span>  
  
 <span data-ttu-id="5532f-224">En este ejemplo se usa un objeto <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="5532f-224">This example uses a <xref:System.Text.StringBuilder> object.</span></span> <span data-ttu-id="5532f-225">La función siguiente genera un nombre de tipo completo para tipos genéricos:</span><span class="sxs-lookup"><span data-stu-id="5532f-225">The following function generates a full type name for generic types:</span></span>  
  
```csharp  
public class Example  
{  
    // Constructs a name like "SomeType<T1, T2, T3>"  
    public string GenerateFullTypeName(string name, int arity)  
    {  
        StringBuilder sb = new StringBuilder();  
  
        sb.Append(name);  
        if (arity != 0)  
        {  
            sb.Append("<");  
            for (int i = 1; i < arity; i++)  
            {  
                sb.Append("T"); sb.Append(i.ToString()); sb.Append(", ");  
            }  
            sb.Append("T"); sb.Append(i.ToString()); sb.Append(">");  
        }  
  
        return sb.ToString();  
    }  
}  
```  
  
 <span data-ttu-id="5532f-226">El foco está en la línea que crea una nueva instancia <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="5532f-226">The focus is on the line that creates a new <xref:System.Text.StringBuilder> instance.</span></span> <span data-ttu-id="5532f-227">El código causa una asignación para `sb.ToString()` y asignaciones internas dentro de la implementación <xref:System.Text.StringBuilder>, pero esas asignaciones no se pueden controlar si se desea el resultado de la cadena.</span><span class="sxs-lookup"><span data-stu-id="5532f-227">The code causes an allocation for `sb.ToString()` and internal allocations within the <xref:System.Text.StringBuilder> implementation, but you cannot control those allocations if you want the string result.</span></span>
  
 <span data-ttu-id="5532f-228">**Corrección para el ejemplo 4**</span><span class="sxs-lookup"><span data-stu-id="5532f-228">**Fix for example 4**</span></span>  
  
 <span data-ttu-id="5532f-229">Para corregir la asignación del objeto `StringBuilder`, almacene el objeto en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="5532f-229">To fix the `StringBuilder` object allocation, cache the  object.</span></span> <span data-ttu-id="5532f-230">El almacenamiento en caché de una única instancia que podría desecharse puede mejorar el rendimiento de manera significativa.</span><span class="sxs-lookup"><span data-stu-id="5532f-230">Even caching a single instance that might get thrown away can improve performance significantly.</span></span> <span data-ttu-id="5532f-231">Esta es la nueva implementación de la función, que omite todo el código excepto las nuevas líneas primera y última:</span><span class="sxs-lookup"><span data-stu-id="5532f-231">This is the function’s new implementation, omitting all the code except for the new first and last lines:</span></span>  
  
```csharp  
// Constructs a name like "MyType<T1, T2, T3>"  
public string GenerateFullTypeName(string name, int arity)  
{  
    StringBuilder sb = AcquireBuilder();  
    /* Use sb as before */  
    return GetStringAndReleaseBuilder(sb);  
}  
```  
  
 <span data-ttu-id="5532f-232">Las partes clave son las nuevas funciones `AcquireBuilder()` y `GetStringAndReleaseBuilder()`:</span><span class="sxs-lookup"><span data-stu-id="5532f-232">The key parts are the new `AcquireBuilder()` and `GetStringAndReleaseBuilder()` functions:</span></span>  
  
```csharp  
[ThreadStatic]  
private static StringBuilder cachedStringBuilder;  
  
private static StringBuilder AcquireBuilder()  
{  
    StringBuilder result = cachedStringBuilder;  
    if (result == null)  
    {  
        return new StringBuilder();  
    }  
    result.Clear();  
    cachedStringBuilder = null;  
    return result;  
}  
  
private static string GetStringAndReleaseBuilder(StringBuilder sb)  
{  
    string result = sb.ToString();  
    cachedStringBuilder = sb;  
    return result;  
}  
```  
  
 <span data-ttu-id="5532f-233">Dado que los nuevos compiladores usan subprocesos, estas implementaciones utilizan un campo estático de subproceso (atributo <xref:System.ThreadStaticAttribute>) para almacenar en la caché el <xref:System.Text.StringBuilder>, con lo que probablemente se pueda renunciar a la declaración `ThreadStatic`.</span><span class="sxs-lookup"><span data-stu-id="5532f-233">Because the new compilers use threading, these implementations use a thread-static field (<xref:System.ThreadStaticAttribute> attribute) to cache the <xref:System.Text.StringBuilder>, and you likely can forgo the `ThreadStatic` declaration.</span></span> <span data-ttu-id="5532f-234">El campo estático de subproceso contiene un valor único para cada subproceso que ejecuta este código.</span><span class="sxs-lookup"><span data-stu-id="5532f-234">The thread-static field holds a unique value for each thread that executes this code.</span></span>
  
 <span data-ttu-id="5532f-235">`AcquireBuilder()` devuelve la instancia <xref:System.Text.StringBuilder> almacenada en la caché (si la hay) después de borrarla y establecer el campo o la caché en null.</span><span class="sxs-lookup"><span data-stu-id="5532f-235">`AcquireBuilder()` returns the cached <xref:System.Text.StringBuilder> instance if there is one, after clearing it and setting the field or cache to null.</span></span> <span data-ttu-id="5532f-236">De lo contrario, `AcquireBuilder()` crea una instancia nueva y la devuelve, dejando el campo o la caché establecidos en null.</span><span class="sxs-lookup"><span data-stu-id="5532f-236">Otherwise, `AcquireBuilder()` creates a new instance and returns it, leaving the field or cache set to null.</span></span>
  
 <span data-ttu-id="5532f-237">Cuando haya acabado con <xref:System.Text.StringBuilder>, llame a `GetStringAndReleaseBuilder()` para obtener el resultado de la cadena, guarde la instancia <xref:System.Text.StringBuilder> en el campo o en la caché, y después devuelva el resultado.</span><span class="sxs-lookup"><span data-stu-id="5532f-237">When you’re done with <xref:System.Text.StringBuilder> , you call `GetStringAndReleaseBuilder()` to get the string result, save the <xref:System.Text.StringBuilder> instance in the field or cache, and then return the result.</span></span> <span data-ttu-id="5532f-238">Es posible que en la ejecución se vuelva a introducir este código y se creen varios objetos <xref:System.Text.StringBuilder> (aunque rara vez ocurre).</span><span class="sxs-lookup"><span data-stu-id="5532f-238">It is possible for execution to re-enter this code and to create multiple <xref:System.Text.StringBuilder> objects (although that rarely happens).</span></span> <span data-ttu-id="5532f-239">El código solo guarda la última instancia <xref:System.Text.StringBuilder> liberada para su uso posterior.</span><span class="sxs-lookup"><span data-stu-id="5532f-239">The code saves only the last released <xref:System.Text.StringBuilder> instance for later use.</span></span> <span data-ttu-id="5532f-240">Esa sencilla estrategia de almacenamiento en caché redujo significativamente las asignaciones en los nuevos compiladores.</span><span class="sxs-lookup"><span data-stu-id="5532f-240">This simple caching strategy significantly reduced allocations in the new compilers.</span></span> <span data-ttu-id="5532f-241">Hay partes de .NET Framework y MSBuild ("MSBuild") que usan una técnica similar para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="5532f-241">Parts of the .NET Framework and MSBuild ("MSBuild") use a similar technique to improve performance.</span></span>
  
 <span data-ttu-id="5532f-242">Esta estrategia simple de almacenamiento en caché respeta el buen diseño de caché porque tiene un límite de tamaño.</span><span class="sxs-lookup"><span data-stu-id="5532f-242">This simple caching strategy adheres to good cache design because it has a size cap.</span></span> <span data-ttu-id="5532f-243">No obstante, hay más código ahora que en el original, lo que significa un mayor coste de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="5532f-243">However, there is more code now than in the original, which means more maintenance costs.</span></span> <span data-ttu-id="5532f-244">Únicamente debe adoptar la estrategia de almacenamiento en caché si se ha encontrado con un problema de rendimiento y PerfView muestra que las asignaciones de <xref:System.Text.StringBuilder> suponen una contribución significativa.</span><span class="sxs-lookup"><span data-stu-id="5532f-244">You should adopt the caching strategy only if you’ve found a performance problem, and PerfView has shown that <xref:System.Text.StringBuilder> allocations are a significant contributor.</span></span>
  
### <a name="linq-and-lambdas"></a><span data-ttu-id="5532f-245">LINQ y lambdas</span><span class="sxs-lookup"><span data-stu-id="5532f-245">LINQ and lambdas</span></span>  
<span data-ttu-id="5532f-246">Language-Integrated Query (LINQ), junto con las expresiones lambda, es un ejemplo de una característica de productividad.</span><span class="sxs-lookup"><span data-stu-id="5532f-246">Language-Integrated Query (LINQ), in conjunction with lambda expressions, is an example of a productivity feature.</span></span> <span data-ttu-id="5532f-247">Sin embargo, su uso puede tener un impacto significativo en el rendimiento a lo largo del tiempo, y es posible que tenga que volver a escribir el código.</span><span class="sxs-lookup"><span data-stu-id="5532f-247">However, its use may have a significant impact on performance over time, and you might find you need to rewrite your code.</span></span>
  
 <span data-ttu-id="5532f-248">**Ejemplo 5: lambdas, List \<T> e IEnumerable\<T>**</span><span class="sxs-lookup"><span data-stu-id="5532f-248">**Example 5: Lambdas, List\<T>, and IEnumerable\<T>**</span></span>  
  
 <span data-ttu-id="5532f-249">En este ejemplo se usa [LINQ y código de estilo funcional](https://docs.microsoft.com/archive/blogs/charlie/anders-hejlsberg-on-linq-and-functional-programming) para buscar un símbolo en el modelo del compilador, dada una cadena de nombre:</span><span class="sxs-lookup"><span data-stu-id="5532f-249">This example uses [LINQ and functional style code](https://docs.microsoft.com/archive/blogs/charlie/anders-hejlsberg-on-linq-and-functional-programming) to find a symbol in the compiler’s model, given a name string:</span></span>  
  
```csharp  
class Symbol {  
    public string Name { get; private set; }  
    /*...*/  
}  
  
class Compiler {  
    private List<Symbol> symbols;  
    public Symbol FindMatchingSymbol(string name)  
    {  
        return symbols.FirstOrDefault(s => s.Name == name);  
    }  
}  
```  
  
 <span data-ttu-id="5532f-250">El nuevo compilador y las experiencias de IDE creadas en él llaman a `FindMatchingSymbol()` con mucha frecuencia, y hay varias asignaciones ocultas en la única línea de código de esta función.</span><span class="sxs-lookup"><span data-stu-id="5532f-250">The new compiler and the IDE experiences built on it call `FindMatchingSymbol()` very frequently, and there are several hidden allocations in this function’s single line of code.</span></span> <span data-ttu-id="5532f-251">Para examinar estas asignaciones, primero divida la única línea de código de la función en dos líneas:</span><span class="sxs-lookup"><span data-stu-id="5532f-251">To examine those allocations, first split the function’s single line of code into two lines:</span></span>  
  
```csharp  
Func<Symbol, bool> predicate = s => s.Name == name;  
     return symbols.FirstOrDefault(predicate);  
```  
  
 <span data-ttu-id="5532f-252">En la primera línea, la [expresión lambda](../../csharp/language-reference/operators/lambda-expressions.md) `s => s.Name == name` [cierra](https://docs.microsoft.com/archive/blogs/ericlippert/what-are-closures) la variable local `name`.</span><span class="sxs-lookup"><span data-stu-id="5532f-252">In the first line, the [lambda expression](../../csharp/language-reference/operators/lambda-expressions.md) `s => s.Name == name` [closes over](https://docs.microsoft.com/archive/blogs/ericlippert/what-are-closures) the local variable `name`.</span></span> <span data-ttu-id="5532f-253">Esto significa que, además de asignar un objeto para el [delegado](../../csharp/language-reference/builtin-types/reference-types.md#the-delegate-type) que contiene `predicate`, el código asigna una clase estática para contener el entorno que captura el valor de `name`.</span><span class="sxs-lookup"><span data-stu-id="5532f-253">This means that in addition to allocating an object for the [delegate](../../csharp/language-reference/builtin-types/reference-types.md#the-delegate-type) that `predicate` holds, the code allocates a static class to hold the environment that captures the value of `name`.</span></span> <span data-ttu-id="5532f-254">El compilador genera código como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="5532f-254">The compiler generates code like the following:</span></span>  
  
```csharp  
// Compiler-generated class to hold environment state for lambda  
private class Lambda1Environment  
{  
    public string capturedName;  
    public bool Evaluate(Symbol s)  
    {  
        return s.Name == this.capturedName;  
    }  
}  
  
// Expanded Func<Symbol, bool> predicate = s => s.Name == name;  
Lambda1Environment l = new Lambda1Environment() { capturedName = name };  
var predicate = new Func<Symbol, bool>(l.Evaluate);  
```  
  
 <span data-ttu-id="5532f-255">Las dos asignaciones `new` (una para la clase de entorno y la otra para el delegado) son ahora explícitas.</span><span class="sxs-lookup"><span data-stu-id="5532f-255">The two `new` allocations (one for the environment class and one for the delegate) are explicit now.</span></span>
  
 <span data-ttu-id="5532f-256">Ahora observe la llamada a `FirstOrDefault`.</span><span class="sxs-lookup"><span data-stu-id="5532f-256">Now look at the call to `FirstOrDefault`.</span></span> <span data-ttu-id="5532f-257">Este método de extensión en el tipo <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> también crea una asignación.</span><span class="sxs-lookup"><span data-stu-id="5532f-257">This extension method on the <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> type incurs an allocation too.</span></span> <span data-ttu-id="5532f-258">Dado que `FirstOrDefault` toma un objeto <xref:System.Collections.Generic.IEnumerable%601> como primer argumento, se puede expandir la llamada al código siguiente (un poco simplificado para el análisis):</span><span class="sxs-lookup"><span data-stu-id="5532f-258">Because `FirstOrDefault` takes an <xref:System.Collections.Generic.IEnumerable%601> object as its first argument, you can expand the call to the following code (simplified a bit for discussion):</span></span>  
  
```csharp  
// Expanded return symbols.FirstOrDefault(predicate) ...
     IEnumerable<Symbol> enumerable = symbols;  
     IEnumerator<Symbol> enumerator = enumerable.GetEnumerator();  
     while(enumerator.MoveNext())  
     {  
         if (predicate(enumerator.Current))  
             return enumerator.Current;  
     }  
     return default(Symbol);  
```  
  
 <span data-ttu-id="5532f-259">La variable `symbols` tiene el tipo <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="5532f-259">The `symbols` variable has type <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="5532f-260">El tipo de colección <xref:System.Collections.Generic.List%601> implementa <xref:System.Collections.Generic.IEnumerable%601> y define inteligentemente un enumerador (interfaz <xref:System.Collections.Generic.IEnumerator%601>) que <xref:System.Collections.Generic.List%601> implementa con una `struct`.</span><span class="sxs-lookup"><span data-stu-id="5532f-260">The <xref:System.Collections.Generic.List%601> collection type implements <xref:System.Collections.Generic.IEnumerable%601> and cleverly defines an enumerator (<xref:System.Collections.Generic.IEnumerator%601> interface) that <xref:System.Collections.Generic.List%601> implements with a `struct`.</span></span> <span data-ttu-id="5532f-261">Usar una estructura en vez de una clase significa que normalmente se evitan asignaciones del montón, lo que, a su vez, puede afectar al rendimiento de la recolección de elementos no utilizados. </span><span class="sxs-lookup"><span data-stu-id="5532f-261">Using a structure instead of a class means that you usually avoid any heap allocations, which, in turn, can affect garbage collection performance.</span></span> <span data-ttu-id="5532f-262">Por lo general, los enumeradores se usan con el bucle `foreach` del lenguaje, que utiliza la estructura de enumerador tal como se devuelve en la pila de llamadas.</span><span class="sxs-lookup"><span data-stu-id="5532f-262">Enumerators are typically used with the language’s `foreach` loop, which uses the enumerator structure as it is returned on the call stack.</span></span> <span data-ttu-id="5532f-263">El incremento del puntero de la pila de llamadas para dejar sitio a un objeto no afecta a GC del modo que lo hace una asignación del montón.</span><span class="sxs-lookup"><span data-stu-id="5532f-263">Incrementing the call stack pointer to make room for an object does not affect GC the way a heap allocation does.</span></span>
  
 <span data-ttu-id="5532f-264">En el caso de la llamada `FirstOrDefault` expandida, el código necesita llamar a `GetEnumerator()` en una interfaz <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="5532f-264">In the case of the expanded `FirstOrDefault` call, the code needs to call `GetEnumerator()` on an <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="5532f-265">Con la asignación de `symbols` a la variable `enumerable` de tipo `IEnumerable<Symbol>`, se pierde la información de que el objeto real es una lista <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="5532f-265">Assigning `symbols` to the `enumerable` variable of type `IEnumerable<Symbol>` loses the information that the actual object is a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="5532f-266">Esto significa que cuando el código captura al enumerador con `enumerable.GetEnumerator()`, .NET Framework tiene que realizar una conversión boxing de la estructura devuelta para asignarla a la variable `enumerator`.</span><span class="sxs-lookup"><span data-stu-id="5532f-266">This means that when the code fetches the enumerator with `enumerable.GetEnumerator()`, the .NET Framework has to box the returned structure to assign it to the `enumerator` variable.</span></span>
  
 <span data-ttu-id="5532f-267">**Corrección para el ejemplo 5**</span><span class="sxs-lookup"><span data-stu-id="5532f-267">**Fix for example 5**</span></span>  
  
 <span data-ttu-id="5532f-268">En esta corrección, `FindMatchingSymbol` se reescribe para reemplazar la única línea de código con seis líneas de código que siguen siendo concisas, fáciles de leer y entender, y sencillas de mantener:</span><span class="sxs-lookup"><span data-stu-id="5532f-268">The fix is to rewrite `FindMatchingSymbol` as follows, replacing its single line of code with six lines of code that are still concise, easy to read and understand, and easy to maintain:</span></span>  
  
```csharp  
public Symbol FindMatchingSymbol(string name)  
    {  
        foreach (Symbol s in symbols)  
        {  
            if (s.Name == name)  
                return s;  
        }  
        return null;  
    }  
```  
  
 <span data-ttu-id="5532f-269">El código no utiliza métodos de extensión LINQ, lambdas ni enumeradores, y no crea asignaciones.</span><span class="sxs-lookup"><span data-stu-id="5532f-269">This code doesn’t use LINQ extension methods, lambdas, or enumerators, and it incurs no allocations.</span></span> <span data-ttu-id="5532f-270">No hay asignaciones porque el compilador puede ver que la colección `symbols` es una <xref:System.Collections.Generic.List%601> y puede vincular el enumerador resultante (una estructura) a una variable local con el tipo correcto para evitar la conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="5532f-270">There are no allocations because the compiler can see that the `symbols` collection is a <xref:System.Collections.Generic.List%601> and can bind the resulting enumerator (a structure) to a local variable with the right type to avoid boxing.</span></span> <span data-ttu-id="5532f-271">La versión original de esta función es un gran ejemplo del poder expresivo de C# y de la productividad .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5532f-271">The original version of this function was a great example of the expressive power of C# and the productivity of the .NET Framework.</span></span> <span data-ttu-id="5532f-272">Esta nueva y más eficaz versión conserva esas cualidades sin agregar ningún código complejo que haya que mantener.</span><span class="sxs-lookup"><span data-stu-id="5532f-272">This new and more efficient version preserves those qualities without adding any complex code to maintain.</span></span>
  
### <a name="async-method-caching"></a><span data-ttu-id="5532f-273">Almacenamiento en caché del método asincrónico</span><span class="sxs-lookup"><span data-stu-id="5532f-273">Async method caching</span></span>  

<span data-ttu-id="5532f-274">En el ejemplo siguiente se muestra un problema común al intentar usar resultados de la caché en un método [async](../../csharp/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="5532f-274">The next example shows a common problem when you try to use cached results in an [async](../../csharp/programming-guide/concepts/async/index.md) method.</span></span>
  
 <span data-ttu-id="5532f-275">**Ejemplo 6: almacenamiento en caché en métodos asincrónicos**</span><span class="sxs-lookup"><span data-stu-id="5532f-275">**Example 6: caching in async methods**</span></span>  
  
 <span data-ttu-id="5532f-276">Las características del IDE de Visual Studio incorporadas a los nuevos compiladores de C# y Visual Basic suelen capturar árboles de sintaxis y, cuando eso sucede, los compiladores usan asincronía para que Visual Studio siga respondiendo.</span><span class="sxs-lookup"><span data-stu-id="5532f-276">The Visual Studio IDE features built on the new C# and Visual Basic compilers frequently fetch syntax trees, and the compilers use async when doing so to keep Visual Studio responsive.</span></span> <span data-ttu-id="5532f-277">Esta es la primera versión del código que puede escribir para obtener un árbol de sintaxis:</span><span class="sxs-lookup"><span data-stu-id="5532f-277">Here’s the first version of the code you might write to get a syntax tree:</span></span>  
  
```csharp  
class SyntaxTree { /*...*/ }  
  
class Parser { /*...*/  
    public SyntaxTree Syntax { get; }  
    public Task ParseSourceCode() { /*...*/ }  
}  
  
class Compilation { /*...*/  
    public async Task<SyntaxTree> GetSyntaxTreeAsync()  
    {  
        var parser = new Parser(); // allocation  
        await parser.ParseSourceCode(); // expensive  
        return parser.Syntax;  
    }  
}  
```  
  
 <span data-ttu-id="5532f-278">Como se puede ver, la llamada a `GetSyntaxTreeAsync()` crea una instancia de `Parser`, analiza el código y luego devuelve un objeto <xref:System.Threading.Tasks.Task>, `Task<SyntaxTree>`.</span><span class="sxs-lookup"><span data-stu-id="5532f-278">You can see that calling `GetSyntaxTreeAsync()` instantiates a `Parser`, parses the code, and then returns a <xref:System.Threading.Tasks.Task> object, `Task<SyntaxTree>`.</span></span> <span data-ttu-id="5532f-279">La parte costosa es asignar la instancia `Parser` y analizar el código.</span><span class="sxs-lookup"><span data-stu-id="5532f-279">The expensive part is allocating the `Parser` instance and parsing the code.</span></span> <span data-ttu-id="5532f-280">La función devuelve <xref:System.Threading.Tasks.Task>, de modo que los autores de llamadas pueden esperar al trabajo de análisis y liberar el subproceso de la interfaz de usuario para que responda a la entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="5532f-280">The function returns a <xref:System.Threading.Tasks.Task> so that callers can await the parsing work and free the UI thread to be responsive to user input.</span></span>
  
 <span data-ttu-id="5532f-281">Hay varias características de Visual Studio que pueden intentar obtener el mismo árbol de sintaxis; por tanto, se puede escribir el código siguiente para almacenar en caché el resultado del análisis a fin de ahorrar tiempo y asignaciones.</span><span class="sxs-lookup"><span data-stu-id="5532f-281">Several Visual Studio features might try to get the same syntax tree, so you might write the following code to cache the parsing result to save time and allocations.</span></span> <span data-ttu-id="5532f-282">No obstante, este código crea una asignación:</span><span class="sxs-lookup"><span data-stu-id="5532f-282">However, this code incurs an allocation:</span></span>  
  
```csharp  
class Compilation { /*...*/  
  
    private SyntaxTree cachedResult;  
  
    public async Task<SyntaxTree> GetSyntaxTreeAsync()  
    {  
        if (this.cachedResult == null)  
        {  
            var parser = new Parser(); // allocation  
            await parser.ParseSourceCode(); // expensive  
            this.cachedResult = parser.Syntax;  
        }  
        return this.cachedResult;  
    }  
}  
```  
  
 <span data-ttu-id="5532f-283">Como puede ver, el nuevo código con almacenamiento en caché tiene un campo `SyntaxTree` denominado `cachedResult`.</span><span class="sxs-lookup"><span data-stu-id="5532f-283">You see that the new code with caching has a `SyntaxTree` field named `cachedResult`.</span></span> <span data-ttu-id="5532f-284">Cuando este campo es null, `GetSyntaxTreeAsync()` hace el trabajo y guarda el resultado en la caché.</span><span class="sxs-lookup"><span data-stu-id="5532f-284">When this field is null, `GetSyntaxTreeAsync()` does the work and saves the result in the cache.</span></span> <span data-ttu-id="5532f-285">`GetSyntaxTreeAsync()` devuelve el objeto `SyntaxTree`.</span><span class="sxs-lookup"><span data-stu-id="5532f-285">`GetSyntaxTreeAsync()` returns the `SyntaxTree` object.</span></span> <span data-ttu-id="5532f-286">El problema es que cuando se tiene una función `async` de tipo `Task<SyntaxTree>`, y se devuelve un valor de tipo `SyntaxTree`, el compilador emite código para asignar una tarea que contenga el resultado (mediante `Task<SyntaxTree>.FromResult()`).</span><span class="sxs-lookup"><span data-stu-id="5532f-286">The problem is that when you have an `async` function of type `Task<SyntaxTree>`, and you return a value of type `SyntaxTree`, the compiler emits code to allocate a Task to hold the result (by using `Task<SyntaxTree>.FromResult()`).</span></span> <span data-ttu-id="5532f-287">La tarea se marca como completada y el resultado está disponible de inmediato.</span><span class="sxs-lookup"><span data-stu-id="5532f-287">The Task is marked as completed, and the result is immediately available.</span></span> <span data-ttu-id="5532f-288">En el código de los nuevos compiladores, la aparición de objetos <xref:System.Threading.Tasks.Task> que ya se habían completado se producía tan a menudo que corregir estas asignaciones mejoró sensiblemente la respuesta.</span><span class="sxs-lookup"><span data-stu-id="5532f-288">In the code for the new compilers, <xref:System.Threading.Tasks.Task> objects that were already completed occurred so often that fixing these allocations improved responsiveness noticeably.</span></span>
  
 <span data-ttu-id="5532f-289">**Corrección para el ejemplo 6**</span><span class="sxs-lookup"><span data-stu-id="5532f-289">**Fix for example 6**</span></span>  
  
 <span data-ttu-id="5532f-290">Para quitar la asignación completada <xref:System.Threading.Tasks.Task> , puede almacenar en caché el objeto de tarea con el resultado completado:</span><span class="sxs-lookup"><span data-stu-id="5532f-290">To remove the completed <xref:System.Threading.Tasks.Task> allocation, you can cache the Task object with the completed result:</span></span>  
  
```csharp  
class Compilation { /*...*/  
  
    private Task<SyntaxTree> cachedResult;  
  
    public Task<SyntaxTree> GetSyntaxTreeAsync()  
    {  
        return this.cachedResult ??
               (this.cachedResult = GetSyntaxTreeUncachedAsync());  
    }  
  
    private async Task<SyntaxTree> GetSyntaxTreeUncachedAsync()  
    {  
        var parser = new Parser(); // allocation  
        await parser.ParseSourceCode(); // expensive  
        return parser.Syntax;  
    }  
}  
```  
  
 <span data-ttu-id="5532f-291">Este código cambia el tipo de `cachedResult` a `Task<SyntaxTree>` y emplea una función del asistente `async` que contiene el código original de `GetSyntaxTreeAsync()`.</span><span class="sxs-lookup"><span data-stu-id="5532f-291">This code changes the type of `cachedResult` to `Task<SyntaxTree>` and employs an `async` helper function that holds the original code from `GetSyntaxTreeAsync()`.</span></span> <span data-ttu-id="5532f-292">`GetSyntaxTreeAsync()` ahora usa el [operador de uso combinado de NULL](../../csharp/language-reference/operators/null-coalescing-operator.md) para devolver `cachedResult` si no es null.</span><span class="sxs-lookup"><span data-stu-id="5532f-292">`GetSyntaxTreeAsync()` now uses the [null coalescing operator](../../csharp/language-reference/operators/null-coalescing-operator.md) to return `cachedResult` if it isn't null.</span></span> <span data-ttu-id="5532f-293">Si `cachedResult` es null, entonces `GetSyntaxTreeAsync()` llama a `GetSyntaxTreeUncachedAsync()` y almacena el resultado en la caché.</span><span class="sxs-lookup"><span data-stu-id="5532f-293">If `cachedResult` is null, then `GetSyntaxTreeAsync()` calls `GetSyntaxTreeUncachedAsync()` and caches the result.</span></span> <span data-ttu-id="5532f-294">Observe que `GetSyntaxTreeAsync()` no aguarda por la llamada a `GetSyntaxTreeUncachedAsync()`, como haría el código normalmente.</span><span class="sxs-lookup"><span data-stu-id="5532f-294">Notice that `GetSyntaxTreeAsync()` doesn’t await the call to `GetSyntaxTreeUncachedAsync()` as the code would normally.</span></span> <span data-ttu-id="5532f-295">No usar await significa que cuando `GetSyntaxTreeUncachedAsync()` devuelve su objeto <xref:System.Threading.Tasks.Task>, `GetSyntaxTreeAsync()` devuelve inmediatamente <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="5532f-295">Not using await means that when `GetSyntaxTreeUncachedAsync()` returns its <xref:System.Threading.Tasks.Task> object, `GetSyntaxTreeAsync()` immediately returns the <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="5532f-296">Ahora, el resultado almacenado en la caché es <xref:System.Threading.Tasks.Task>, por lo que no hay asignaciones que devolver el resultado almacenado en la caché.</span><span class="sxs-lookup"><span data-stu-id="5532f-296">Now, the cached result is a <xref:System.Threading.Tasks.Task>, so there are no allocations to return the cached result.</span></span>
  
### <a name="additional-considerations"></a><span data-ttu-id="5532f-297">Consideraciones adicionales</span><span class="sxs-lookup"><span data-stu-id="5532f-297">Additional considerations</span></span>  
 <span data-ttu-id="5532f-298">A continuación se señalan otras cuestiones sobre aplicaciones grandes o que procesan una gran cantidad de datos.</span><span class="sxs-lookup"><span data-stu-id="5532f-298">Here are a few more points about potential problems in large apps or apps that process a lot of data.</span></span>
  
 <span data-ttu-id="5532f-299">**Diccionarios**</span><span class="sxs-lookup"><span data-stu-id="5532f-299">**Dictionaries**</span></span>  
  
 <span data-ttu-id="5532f-300">Los diccionarios son omnipresentes en muchos programas: resultan muy prácticos y son eficaces de manera inherente.</span><span class="sxs-lookup"><span data-stu-id="5532f-300">Dictionaries are used ubiquitously in many programs, and though dictionaries are very convenient and inherently efficient.</span></span> <span data-ttu-id="5532f-301">Sin embargo, a menudo se usa de forma inapropiada.</span><span class="sxs-lookup"><span data-stu-id="5532f-301">However, they’re often used inappropriately.</span></span> <span data-ttu-id="5532f-302">En Visual Studio y los nuevos compiladores, el análisis muestra que muchos de los diccionarios de los diccionarios contienen un único elemento o están vacíos.</span><span class="sxs-lookup"><span data-stu-id="5532f-302">In Visual Studio and the new compilers, analysis shows that many of the dictionaries contained a single element or were empty.</span></span> <span data-ttu-id="5532f-303">Un <xref:System.Collections.Generic.Dictionary%602> vacío tiene diez campos y ocupa 48 bytes en el montón de una máquina x86.</span><span class="sxs-lookup"><span data-stu-id="5532f-303">An empty <xref:System.Collections.Generic.Dictionary%602> has ten fields and occupies 48 bytes on the heap on an x86 machine.</span></span> <span data-ttu-id="5532f-304">Los diccionarios son estupendos cuando se necesita una asignación o una estructura de datos asociativa con una búsqueda constante.</span><span class="sxs-lookup"><span data-stu-id="5532f-304">Dictionaries are great when you need a mapping or associative data structure with constant-time lookup.</span></span> <span data-ttu-id="5532f-305">No obstante, cuando solo se tienen unos pocos elementos, el usar un diccionario es una pérdida de espacio.</span><span class="sxs-lookup"><span data-stu-id="5532f-305">However, when you have only a few elements, you waste a lot of space by using a dictionary.</span></span> <span data-ttu-id="5532f-306">En su lugar, por ejemplo, se puede realizar una búsqueda iterativa por un `List<KeyValuePair\<K,V>>` sin perder velocidad.</span><span class="sxs-lookup"><span data-stu-id="5532f-306">Instead, for example, you could iteratively look through a `List<KeyValuePair\<K,V>>`, just as fast.</span></span> <span data-ttu-id="5532f-307">Si usa un diccionario solo para cargarlo con datos y luego leerlos (un modelo muy común), usar una matriz ordenada con una búsqueda N(log(N)) puede resultar casi tan rápido, en función del número de elementos que se use.</span><span class="sxs-lookup"><span data-stu-id="5532f-307">If you use a dictionary only to load it with data and then read from it (a very common pattern), using a sorted array with an N(log(N)) lookup might be nearly as fast, depending on the number of elements you're using.</span></span>
  
 <span data-ttu-id="5532f-308">**Clases frente a estructuras**</span><span class="sxs-lookup"><span data-stu-id="5532f-308">**Classes vs. structures**</span></span>  
  
 <span data-ttu-id="5532f-309">En cierto modo, las clases y las estructuras ofrecen la clásica contrapartida entre espacio y tiempo a la hora de para ajustar las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="5532f-309">In a way, classes and structures provide a classic space/time tradeoff for tuning your apps.</span></span> <span data-ttu-id="5532f-310">Las clases generan 12 bytes de sobrecarga en una máquina x86 aunque no tengan campos, pero pasarlas no resulta costoso ya que solo se necesita un puntero para hacer referencia a una instancia de clase.</span><span class="sxs-lookup"><span data-stu-id="5532f-310">Classes incur 12 bytes of overhead on an x86 machine even if they have no fields, but they are inexpensive to pass around because it only takes a pointer to refer to a class instance.</span></span> <span data-ttu-id="5532f-311">Las estructuras no crean asignaciones del montón si no se les aplica una conversión boxing, pero cuando se pasan estructuras grandes como argumentos de función o valores devueltos, se consume tiempo de CPU para copiar atómicamente todos los miembros de datos de las estructuras.</span><span class="sxs-lookup"><span data-stu-id="5532f-311">Structures incur no heap allocations if they aren’t boxed, but when you pass large structures as function arguments or return values, it takes CPU time to atomically copy all the data members of the structures.</span></span> <span data-ttu-id="5532f-312">Controle las llamadas repetidas a propiedades que devuelvan estructuras y almacene en la caché el valor de la propiedad en una variable local para evitar el exceso de copia de datos.</span><span class="sxs-lookup"><span data-stu-id="5532f-312">Watch out for repeated calls to properties that return structures, and cache the property’s value in a local variable to avoid excessive data copying.</span></span>
  
 <span data-ttu-id="5532f-313">**Cachés**</span><span class="sxs-lookup"><span data-stu-id="5532f-313">**Caches**</span></span>  
  
 <span data-ttu-id="5532f-314">Un truco de rendimiento muy habitual es almacenar los resultados en la caché.</span><span class="sxs-lookup"><span data-stu-id="5532f-314">A common performance trick is to cache results.</span></span> <span data-ttu-id="5532f-315">Sin embargo, una caché sin un límite de tamaño o una directiva de retirada puede conllevar la pérdida de memoria.</span><span class="sxs-lookup"><span data-stu-id="5532f-315">However, a cache without a size cap or disposal policy can be a memory leak.</span></span> <span data-ttu-id="5532f-316">Si para procesar grandes cantidades de datos usa mucha memoria en las cachés, puede causar que la recolección de elementos no utilizados anule los beneficios de las búsquedas de la caché.</span><span class="sxs-lookup"><span data-stu-id="5532f-316">When processing large amounts of data, if you hold on to a lot of memory in caches, you can cause garbage collection to override the benefits of your cached lookups.</span></span>
  
 <span data-ttu-id="5532f-317">En este artículo se ha explicado cómo deben tenerse en cuenta los síntomas de cuello de botella de rendimiento que pueden afectar a la respuesta de su aplicación, especialmente en sistemas grandes o sistemas que procesan una gran cantidad de datos.</span><span class="sxs-lookup"><span data-stu-id="5532f-317">In this article, we discussed how you should be aware of performance bottleneck symptoms that can affect your app's responsiveness, especially for large systems or systems that process a large amount of data.</span></span> <span data-ttu-id="5532f-318">Los causantes más habituales son la conversión boxing, las manipulaciones de cadenas, LINQ y lambda, el almacenamiento en caché en métodos asincrónicos, el uso de la memoria caché sin un límite de tamaño o directiva de retirada, la utilización inadecuada de diccionarios y el pase de estructuras.es.</span><span class="sxs-lookup"><span data-stu-id="5532f-318">Common culprits include boxing, string manipulations, LINQ and lambda, caching in async methods, caching without a size limit or disposal policy, inappropriate use of dictionaries, and passing around structures.</span></span> <span data-ttu-id="5532f-319">No olvide los cuatro hechos sobre el ajuste de las aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="5532f-319">Keep in mind the four facts for tuning your apps:</span></span>  
  
- <span data-ttu-id="5532f-320">No optimice prematuramente: sea productivo y ajuste la aplicación cuando detecte problemas.</span><span class="sxs-lookup"><span data-stu-id="5532f-320">Don’t prematurely optimize – be productive and tune your app when you spot problems.</span></span>
  
- <span data-ttu-id="5532f-321">Los perfiles no mienten: si no mide, conjetura.</span><span class="sxs-lookup"><span data-stu-id="5532f-321">Profiles don’t lie – you’re guessing if you’re not measuring.</span></span>
  
- <span data-ttu-id="5532f-322">Unas herramientas buenas marcan la diferencia: descargue PerfView y pruébelo.</span><span class="sxs-lookup"><span data-stu-id="5532f-322">Good tools make all the difference – download PerfView and try it out.</span></span>
  
- <span data-ttu-id="5532f-323">La clave son las asignaciones: es donde el equipo de la plataforma de compiladores invirtió más tiempo en mejorar el rendimiento de los nuevos compiladores.</span><span class="sxs-lookup"><span data-stu-id="5532f-323">It's all about allocations – that is where the compiler platform team spent most of their time improving the performance of the new compilers.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5532f-324">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="5532f-324">See also</span></span>

- [<span data-ttu-id="5532f-325">Vídeo de presentación de este tema</span><span class="sxs-lookup"><span data-stu-id="5532f-325">Video of presentation of this topic</span></span>](https://channel9.msdn.com/Events/TechEd/NorthAmerica/2013/DEV-B333)
- [<span data-ttu-id="5532f-326">Guía básica para la generación de perfiles de rendimiento</span><span class="sxs-lookup"><span data-stu-id="5532f-326">Beginners Guide to Performance Profiling</span></span>](/visualstudio/profiling/beginners-guide-to-performance-profiling)
- [<span data-ttu-id="5532f-327">Rendimiento</span><span class="sxs-lookup"><span data-stu-id="5532f-327">Performance</span></span>](index.md)
- <span data-ttu-id="5532f-328">[.NET Performance Tips (Sugerencias de rendimiento de .NET)](https://docs.microsoft.com/previous-versions/dotnet/articles/ms973839(v%3dmsdn.10))</span><span class="sxs-lookup"><span data-stu-id="5532f-328">[.NET Performance Tips](https://docs.microsoft.com/previous-versions/dotnet/articles/ms973839(v%3dmsdn.10))</span></span>
- [<span data-ttu-id="5532f-329">Tutoriales de PerfView de Channel 9</span><span class="sxs-lookup"><span data-stu-id="5532f-329">Channel 9 PerfView tutorials</span></span>](https://channel9.msdn.com/Series/PerfView-Tutorial)
- [<span data-ttu-id="5532f-330">SDK de .NET Compiler Platform</span><span class="sxs-lookup"><span data-stu-id="5532f-330">The .NET Compiler Platform SDK</span></span>](../../csharp/roslyn-sdk/index.md)
- [<span data-ttu-id="5532f-331">repositorio dotnet/Roslyn en GitHub</span><span class="sxs-lookup"><span data-stu-id="5532f-331">dotnet/roslyn repo on GitHub</span></span>](https://github.com/dotnet/roslyn)
