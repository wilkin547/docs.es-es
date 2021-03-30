---
title: 'Instrucciones de nivel superior: tutorial de C#'
description: En este tutorial se muestra cómo puede usar instrucciones de nivel superior para experimentar y probar conceptos mientras explora ideas propias.
ms.date: 10/28/2020
ms.openlocfilehash: d3cd089c5681e6c06a0c63cbffcc3cf5935fbeef
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104878957"
---
# <a name="tutorial-explore-ideas-using-top-level-statements-to-build-code-as-you-learn"></a><span data-ttu-id="4b774-103">Tutorial: Exploración de ideas mediante instrucciones de nivel superior para compilar código mientras aprende</span><span class="sxs-lookup"><span data-stu-id="4b774-103">Tutorial: Explore ideas using top-level statements to build code as you learn</span></span>

<span data-ttu-id="4b774-104">En este tutorial, aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="4b774-104">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="4b774-105">Obtener información sobre las reglas que rigen el uso de las instrucciones de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="4b774-105">Learn the rules governing your use of top-level statements.</span></span>
> - <span data-ttu-id="4b774-106">Usar instrucciones de nivel superior para explorar algoritmos.</span><span class="sxs-lookup"><span data-stu-id="4b774-106">Use top-level statements to explore algorithms.</span></span>
> - <span data-ttu-id="4b774-107">Refactorizar exploraciones en componentes reutilizables.</span><span class="sxs-lookup"><span data-stu-id="4b774-107">Refactor explorations into reusable components.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4b774-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4b774-108">Prerequisites</span></span>

<span data-ttu-id="4b774-109">Tendrá que configurar el equipo para ejecutar .NET 5, que incluye el compilador de C# 9.</span><span class="sxs-lookup"><span data-stu-id="4b774-109">You'll need to set up your machine to run .NET 5, which includes the C# 9 compiler.</span></span> <span data-ttu-id="4b774-110">El compilador de C# 9 está disponible a partir de [Visual Studio 2019, versión 16.9 Preview 1](https://visualstudio.microsoft.com/vs/preview/) o del [SDK de .NET 5.0](https://dot.net/get-dotnet5).</span><span class="sxs-lookup"><span data-stu-id="4b774-110">The C# 9 compiler is available starting with [Visual Studio 2019 version 16.9 preview 1](https://visualstudio.microsoft.com/vs/preview/) or [.NET 5.0 SDK](https://dot.net/get-dotnet5).</span></span>

<span data-ttu-id="4b774-111">En este tutorial se da por supuesto que está familiarizado con C# y. NET, incluidos Visual Studio o la CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4b774-111">This tutorial assumes you're familiar with C# and .NET, including either Visual Studio or the .NET Core CLI.</span></span>

## <a name="start-exploring"></a><span data-ttu-id="4b774-112">Comienzo de la exploración</span><span class="sxs-lookup"><span data-stu-id="4b774-112">Start exploring</span></span>

<span data-ttu-id="4b774-113">Las instrucciones de nivel superior permiten evitar la ceremonia adicional que requiere colocar el punto de entrada del programa en un método estático en una clase.</span><span class="sxs-lookup"><span data-stu-id="4b774-113">Top-level statements enable you to avoid the extra ceremony required by placing your program's entry point in a static method in a class.</span></span> <span data-ttu-id="4b774-114">El punto de partida típico de una aplicación de consola nueva es similar al código siguiente:</span><span class="sxs-lookup"><span data-stu-id="4b774-114">The typical starting point for a new console application looks like the following code:</span></span>

```csharp
using System;

namespace Application
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

<span data-ttu-id="4b774-115">El código anterior es el resultado de ejecutar el comando `dotnet new console` y crear una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="4b774-115">The preceding code is the result of running the `dotnet new console` command and creating a new console application.</span></span> <span data-ttu-id="4b774-116">Estas 11 líneas solo contienen una línea de código ejecutable.</span><span class="sxs-lookup"><span data-stu-id="4b774-116">Those 11 lines contain only one line of executable code.</span></span> <span data-ttu-id="4b774-117">Puede simplificar ese programa con la nueva característica de instrucciones de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="4b774-117">You can simplify that program with the new top-level statements feature.</span></span> <span data-ttu-id="4b774-118">Esto le permite quitar todas las líneas de este programa menos dos:</span><span class="sxs-lookup"><span data-stu-id="4b774-118">That enables you to remove all but two of the lines in this program:</span></span>

```csharp
using System;

Console.WriteLine("Hello World!");
```

<span data-ttu-id="4b774-119">Esta característica simplifica lo que se necesita para comenzar a explorar nuevas ideas.</span><span class="sxs-lookup"><span data-stu-id="4b774-119">This feature simplifies what's needed to begin exploring new ideas.</span></span> <span data-ttu-id="4b774-120">Puede usar las instrucciones de nivel superior para escenarios de scripting o para explorar.</span><span class="sxs-lookup"><span data-stu-id="4b774-120">You can use top-level statements for scripting scenarios, or to explore.</span></span> <span data-ttu-id="4b774-121">Una vez que conozca los aspectos básicos, puede empezar a refactorizar el código y crear métodos, clases u otros ensamblados para los componentes reutilizables que ha compilado.</span><span class="sxs-lookup"><span data-stu-id="4b774-121">Once you've got the basics working, you can start refactoring the code and create methods, classes, or other assemblies for reusable components you've built.</span></span> <span data-ttu-id="4b774-122">Las instrucciones de nivel superior permiten una experimentación rápida y tutoriales para principiantes.</span><span class="sxs-lookup"><span data-stu-id="4b774-122">Top-level statements do enable quick experimentation and beginner tutorials.</span></span> <span data-ttu-id="4b774-123">También proporcionan una ruta fluida desde la experimentación hasta la obtención de programas completos.</span><span class="sxs-lookup"><span data-stu-id="4b774-123">They also provide a smooth path from experimentation to full programs.</span></span>

<span data-ttu-id="4b774-124">Las instrucciones de nivel superior se ejecutan en el orden en el que aparecen en el archivo.</span><span class="sxs-lookup"><span data-stu-id="4b774-124">Top-level statements are executed in the order they appear in the file.</span></span> <span data-ttu-id="4b774-125">Las instrucciones de nivel superior solo se pueden usar en un archivo de código fuente de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b774-125">Top-level statements can only be used in one source file in your application.</span></span> <span data-ttu-id="4b774-126">El compilador genera un error si se usan en más de un archivo.</span><span class="sxs-lookup"><span data-stu-id="4b774-126">The compiler generates an error if you use them in more than one file.</span></span>

## <a name="build-a-magic-net-answer-machine"></a><span data-ttu-id="4b774-127">Creación de un contestador automático de .NET mágico</span><span class="sxs-lookup"><span data-stu-id="4b774-127">Build a magic .NET answer machine</span></span>

<span data-ttu-id="4b774-128">En este tutorial, se creará una aplicación de consola que responde a una pregunta de tipo "sí" o "no" con una respuesta aleatoria.</span><span class="sxs-lookup"><span data-stu-id="4b774-128">For this tutorial, let's build a console application that answers a "yes" or "no" question with a random answer.</span></span> <span data-ttu-id="4b774-129">Compilará la funcionalidad paso a paso.</span><span class="sxs-lookup"><span data-stu-id="4b774-129">You'll build out the functionality step by step.</span></span> <span data-ttu-id="4b774-130">Puede centrarse en la tarea en lugar de la ceremonia necesaria para la estructura de un programa típico.</span><span class="sxs-lookup"><span data-stu-id="4b774-130">You can focus on your task rather than ceremony needed for the structure of a typical program.</span></span> <span data-ttu-id="4b774-131">Después, una vez que esté satisfecho con la funcionalidad, puede refactorizar la aplicación como considere oportuno.</span><span class="sxs-lookup"><span data-stu-id="4b774-131">Then, once you're happy with the functionality, you can refactor the application as you see fit.</span></span>

<span data-ttu-id="4b774-132">Un buen punto de partida es escribir la pregunta de nuevo en la consola.</span><span class="sxs-lookup"><span data-stu-id="4b774-132">A good starting point is to write the question back to the console.</span></span> <span data-ttu-id="4b774-133">Puede empezar por escribir el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="4b774-133">You can start by writing the following code:</span></span>

```csharp
using System;

Console.WriteLine(args);
```

<span data-ttu-id="4b774-134">No declare una variable `args`.</span><span class="sxs-lookup"><span data-stu-id="4b774-134">You don't declare an `args` variable.</span></span> <span data-ttu-id="4b774-135">Para el único archivo de código fuente que contiene las instrucciones de nivel superior, el compilador reconoce `args` para indicar los argumentos de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="4b774-135">For the single source file that contains your top-level statements, the compiler recognizes `args` to mean the command-line arguments.</span></span> <span data-ttu-id="4b774-136">El tipo de args es `string[]`, como en todos los programas de C#.</span><span class="sxs-lookup"><span data-stu-id="4b774-136">The type of args is a `string[]`, as in all C# programs.</span></span>

<span data-ttu-id="4b774-137">Puede ejecutar el comando `dotnet run` siguiente para probar el código:</span><span class="sxs-lookup"><span data-stu-id="4b774-137">You can test your code by running the following `dotnet run` command:</span></span>

```dotnetcli
dotnet run -- Should I use top level statements in all my programs?
```

<span data-ttu-id="4b774-138">Los argumentos después de `--` en la línea de comandos se pasan al programa.</span><span class="sxs-lookup"><span data-stu-id="4b774-138">The arguments after the `--` on the command line are passed to the program.</span></span> <span data-ttu-id="4b774-139">Puede ver el tipo de la variable `args`, ya que es lo que se imprime en la consola:</span><span class="sxs-lookup"><span data-stu-id="4b774-139">You can see the type of the `args` variable, because that's what's printed to the console:</span></span>

```console
System.String[]
```

<span data-ttu-id="4b774-140">Para escribir la pregunta en la consola, tendrá que enumerar los argumentos y separarlos con un espacio.</span><span class="sxs-lookup"><span data-stu-id="4b774-140">To write the question to the console, you'll need to enumerate the arguments and separate them with a space.</span></span> <span data-ttu-id="4b774-141">Reemplace la llamada a `WriteLine` por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="4b774-141">Replace the `WriteLine` call with the following code:</span></span>

:::code language="csharp" source="snippets/top-level-statements/ProgramSnippets.cs" ID="EchoInput":::

<span data-ttu-id="4b774-142">Ahora, al ejecutar el programa, mostrará correctamente la pregunta como una cadena de argumentos.</span><span class="sxs-lookup"><span data-stu-id="4b774-142">Now, when you run the program, it will correctly display the question as a string of arguments.</span></span>

## <a name="respond-with-a-random-answer"></a><span data-ttu-id="4b774-143">Respuesta con una respuesta aleatoria</span><span class="sxs-lookup"><span data-stu-id="4b774-143">Respond with a random answer</span></span>

<span data-ttu-id="4b774-144">Después de repetir la pregunta, puede agregar el código para generar la respuesta aleatoria.</span><span class="sxs-lookup"><span data-stu-id="4b774-144">After echoing the question, you can add the code to generate the random answer.</span></span> <span data-ttu-id="4b774-145">Para empezar, agregue una matriz de respuestas posibles:</span><span class="sxs-lookup"><span data-stu-id="4b774-145">Start by adding an array of possible answers:</span></span>

:::code language="csharp" source="snippets/top-level-statements/ProgramSnippets.cs" ID="Answers":::

<span data-ttu-id="4b774-146">Esta matriz tiene 12 respuestas que son afirmativas, 6 inexpresivas y 6 negativas.</span><span class="sxs-lookup"><span data-stu-id="4b774-146">This array has 12 answers that are affirmative, six that are non-committal, and six that are negative.</span></span> <span data-ttu-id="4b774-147">A continuación, agregue el código siguiente para generar y mostrar una respuesta aleatoria de la matriz:</span><span class="sxs-lookup"><span data-stu-id="4b774-147">Next, add the following code to generate and display a random answer from the array:</span></span>

:::code language="csharp" source="snippets/top-level-statements/ProgramSnippets.cs" ID="GenerateAnswer":::

<span data-ttu-id="4b774-148">Puede volver a ejecutar la aplicación para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="4b774-148">You can run the application again to see the results.</span></span> <span data-ttu-id="4b774-149">Debería ver algo parecido a la salida siguiente:</span><span class="sxs-lookup"><span data-stu-id="4b774-149">You should see something like the following output:</span></span>

```dotnetcli
dotnet run -- Should I use top level statements in all my programs?

Should I use top level statements in all my programs?
Better not tell you now.
```

<span data-ttu-id="4b774-150">Este código responde a las preguntas, pero agreguemos una característica más.</span><span class="sxs-lookup"><span data-stu-id="4b774-150">This code answers the questions, but let's add one more feature.</span></span> <span data-ttu-id="4b774-151">Quiere que la aplicación de preguntas simule que se piensa la respuesta.</span><span class="sxs-lookup"><span data-stu-id="4b774-151">You'd like your question app to simulate thinking about the answer.</span></span> <span data-ttu-id="4b774-152">Puede hacerlo si agrega una animación de ASCII y se detiene mientras trabaja.</span><span class="sxs-lookup"><span data-stu-id="4b774-152">You can do that by adding a bit of ASCII animation, and pausing while working.</span></span>  <span data-ttu-id="4b774-153">Agregue el código siguiente después de la línea que reproduce la pregunta:</span><span class="sxs-lookup"><span data-stu-id="4b774-153">Add the following code after the line that echoes the question:</span></span>

:::code language="csharp" source="snippets/top-level-statements/UtilitiesPassOne.cs" ID="AnimationFirstPass":::

<span data-ttu-id="4b774-154">También tendrá que agregar una instrucción `using` a la parte superior del archivo de código fuente:</span><span class="sxs-lookup"><span data-stu-id="4b774-154">You'll also need to add a `using` statement to the top of the source file:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="4b774-155">Las instrucciones `using` deben aparecer antes que cualquier otra del archivo.</span><span class="sxs-lookup"><span data-stu-id="4b774-155">The `using` statements must be before any other statements in the file.</span></span> <span data-ttu-id="4b774-156">De lo contrario, es un error del compilador.</span><span class="sxs-lookup"><span data-stu-id="4b774-156">Otherwise, it's a compiler error.</span></span> <span data-ttu-id="4b774-157">Puede volver a ejecutar el programa y ver la animación.</span><span class="sxs-lookup"><span data-stu-id="4b774-157">You can run the program again and see the animation.</span></span> <span data-ttu-id="4b774-158">Eso mejora la experiencia.</span><span class="sxs-lookup"><span data-stu-id="4b774-158">That makes a better experience.</span></span> <span data-ttu-id="4b774-159">Experimente con la duración del retraso hasta que le guste.</span><span class="sxs-lookup"><span data-stu-id="4b774-159">Experiment with the length of the delay to match your taste.</span></span>

<span data-ttu-id="4b774-160">El código anterior crea un conjunto de líneas giratorias separadas por un espacio.</span><span class="sxs-lookup"><span data-stu-id="4b774-160">The preceding code creates a set of spinning lines separated by a space.</span></span> <span data-ttu-id="4b774-161">Al agregar la palabra clave `await` se le indica al compilador que genere el punto de entrada del programa como un método con el modificador `async` y que devuelva <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4b774-161">Adding the `await` keyword instructs the compiler to generate the program entry point as a method that has the `async` modifier, and returns a <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4b774-162">Este programa no devuelve un valor, por lo que el punto de entrada del programa devuelve `Task`.</span><span class="sxs-lookup"><span data-stu-id="4b774-162">This program does not return a value, so the program entry point returns a `Task`.</span></span> <span data-ttu-id="4b774-163">Si el programa devuelve un valor entero, tendría que agregar una instrucción return al final de las instrucciones de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="4b774-163">If your program returns an integer value, you would add a return statement to the end of your top-level statements.</span></span> <span data-ttu-id="4b774-164">Esa instrucción return especificaría el valor entero que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="4b774-164">That return statement would specify the integer value to return.</span></span> <span data-ttu-id="4b774-165">Si las instrucciones de nivel superior incluyen una expresión `await`, el tipo de valor devuelto se convierte en <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4b774-165">If your top-level statements include an `await` expression, the return type becomes <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType>.</span></span>

## <a name="refactoring-for-the-future"></a><span data-ttu-id="4b774-166">Refactorización para el futuro</span><span class="sxs-lookup"><span data-stu-id="4b774-166">Refactoring for the future</span></span>

<span data-ttu-id="4b774-167">El programa debería ser similar al código siguiente:</span><span class="sxs-lookup"><span data-stu-id="4b774-167">Your program should look like the following code:</span></span>

```csharp
using System;
using System.Threading.Tasks;

Console.WriteLine();
foreach(var s in args)
{
    Console.Write(s);
    Console.Write(' ');
}
Console.WriteLine();

for (int i = 0; i < 20; i++)
{
    Console.Write("| -");
    await Task.Delay(50);
    Console.Write("\b\b\b");
    Console.Write("/ \\");
    await Task.Delay(50);
    Console.Write("\b\b\b");
    Console.Write("- |");
    await Task.Delay(50);
    Console.Write("\b\b\b");
    Console.Write("\\ /");
    await Task.Delay(50);
    Console.Write("\b\b\b");
}
Console.WriteLine();

string[] answers =
{
    "It is certain.",       "Reply hazy, try again.",     "Don't count on it.",
    "It is decidedly so.",  "Ask again later.",           "My reply is no.",
    "Without a doubt.",     "Better not tell you now.",   "My sources say no.",
    "Yes – definitely.",    "Cannot predict now.",        "Outlook not so good.",
    "You may rely on it.",  "Concentrate and ask again.", "Very doubtful.",
    "As I see it, yes.",
    "Most likely.",
    "Outlook good.",
    "Yes.",
    "Signs point to yes.",
};

var index = new Random().Next(answers.Length - 1);
Console.WriteLine(answers[index]);
```

<span data-ttu-id="4b774-168">En el código anterior es razonable.</span><span class="sxs-lookup"><span data-stu-id="4b774-168">The preceding code is reasonable.</span></span> <span data-ttu-id="4b774-169">Funciona.</span><span class="sxs-lookup"><span data-stu-id="4b774-169">It works.</span></span> <span data-ttu-id="4b774-170">Pero no es reutilizable.</span><span class="sxs-lookup"><span data-stu-id="4b774-170">But it isn't reusable.</span></span> <span data-ttu-id="4b774-171">Ahora que ya tiene la aplicación en funcionamiento, es momento de extraer los elementos reutilizables.</span><span class="sxs-lookup"><span data-stu-id="4b774-171">Now that you have the application working, it's time to pull out reusable parts.</span></span>

<span data-ttu-id="4b774-172">Un candidato es el código que muestra la animación en espera.</span><span class="sxs-lookup"><span data-stu-id="4b774-172">One candidate is the code that displays the waiting animation.</span></span> <span data-ttu-id="4b774-173">Ese fragmento de código se puede convertir en un método:</span><span class="sxs-lookup"><span data-stu-id="4b774-173">That snippet can become a method:</span></span>

<span data-ttu-id="4b774-174">Puede empezar por crear una función local en el archivo.</span><span class="sxs-lookup"><span data-stu-id="4b774-174">You can start by creating a local function in your file.</span></span> <span data-ttu-id="4b774-175">Reemplace la animación actual por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="4b774-175">Replace the current animation with the following code:</span></span>

```csharp
await ShowConsoleAnimation();

static async Task ShowConsoleAnimation()
{
    for (int i = 0; i < 20; i++)
    {
        Console.Write("| -");
        await Task.Delay(50);
        Console.Write("\b\b\b");
        Console.Write("/ \\");
        await Task.Delay(50);
        Console.Write("\b\b\b");
        Console.Write("- |");
        await Task.Delay(50);
        Console.Write("\b\b\b");
        Console.Write("\\ /");
        await Task.Delay(50);
        Console.Write("\b\b\b");
    }
    Console.WriteLine();
}
```

<span data-ttu-id="4b774-176">En el código anterior se crea una función local dentro del método Main.</span><span class="sxs-lookup"><span data-stu-id="4b774-176">The preceding code creates a local function inside your main method.</span></span> <span data-ttu-id="4b774-177">Todavía no es reutilizable.</span><span class="sxs-lookup"><span data-stu-id="4b774-177">That's still not reusable.</span></span> <span data-ttu-id="4b774-178">Por tanto, extraiga ese código en una clase.</span><span class="sxs-lookup"><span data-stu-id="4b774-178">So, extract that code into a class.</span></span> <span data-ttu-id="4b774-179">Cree un archivo con el nombre *utilities.cs* y agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="4b774-179">Create a new file named *utilities.cs* and add the following code:</span></span>

:::code language="csharp" source="snippets/top-level-statements/UtilitiesPassOne.cs" ID="SnippetUtilities":::

<span data-ttu-id="4b774-180">Un archivo que tiene instrucciones de nivel superior también puede contener espacios de nombres y tipos al final del archivo, después de las instrucciones de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="4b774-180">A file that has top-level statements can also contain namespaces and types at the end of the file, after the top-level statements.</span></span> <span data-ttu-id="4b774-181">Pero para este tutorial, coloque el método de animación en un archivo independiente para que sea más fácil de usar.</span><span class="sxs-lookup"><span data-stu-id="4b774-181">But for this tutorial you put the animation method in a separate file to make it more readily reusable.</span></span>

<span data-ttu-id="4b774-182">Por último, puede limpiar el código de animación para quitar duplicaciones:</span><span class="sxs-lookup"><span data-stu-id="4b774-182">Finally, you can clean the animation code to remove some duplication:</span></span>

:::code language="csharp" source="snippets/top-level-statements/Utilities.cs" ID="Animation":::

<span data-ttu-id="4b774-183">Ahora tiene una aplicación completa y ha refactorizado los elementos reutilizables para su uso posterior.</span><span class="sxs-lookup"><span data-stu-id="4b774-183">Now you have a complete application, and you've refactored the reusable parts for later use.</span></span> <span data-ttu-id="4b774-184">Puede llamar al nuevo método de utilidad desde las instrucciones de nivel superior, tal como se muestra a continuación en la versión finalizada del programa principal:</span><span class="sxs-lookup"><span data-stu-id="4b774-184">You can call the new utility method from your top-level statements, as shown below in the finished version of the main program:</span></span>

:::code language="csharp" source="snippets/top-level-statements/Program.cs":::

<span data-ttu-id="4b774-185">Esto agrega la llamada a `Utilities.ShowConsoleAnimation` y agrega una instrucción `using` adicional.</span><span class="sxs-lookup"><span data-stu-id="4b774-185">This adds the call to `Utilities.ShowConsoleAnimation`, and adds an additional `using` statement.</span></span>

## <a name="summary"></a><span data-ttu-id="4b774-186">Resumen</span><span class="sxs-lookup"><span data-stu-id="4b774-186">Summary</span></span>

<span data-ttu-id="4b774-187">Las instrucciones de nivel superior facilitan la creación de programas sencillos para explorar nuevos algoritmos.</span><span class="sxs-lookup"><span data-stu-id="4b774-187">Top-level statements make it easier to create simple programs for use to explore new algorithms.</span></span> <span data-ttu-id="4b774-188">Puede experimentar con algoritmos si prueba otros fragmentos de código.</span><span class="sxs-lookup"><span data-stu-id="4b774-188">You can experiment with algorithms by trying different snippets of code.</span></span> <span data-ttu-id="4b774-189">Una vez que haya aprendido lo que funciona, puede refactorizar el código para que sea más fácil de mantener.</span><span class="sxs-lookup"><span data-stu-id="4b774-189">Once you've learned what works, you can refactor the code to be more maintainable.</span></span>

<span data-ttu-id="4b774-190">Las instrucciones de nivel superior simplifican los programas basados en aplicaciones de consola.</span><span class="sxs-lookup"><span data-stu-id="4b774-190">Top-level statements simplify programs that are based on console applications.</span></span> <span data-ttu-id="4b774-191">Esto incluye Azure Functions, las acciones de GitHub y otras utilidades pequeñas.</span><span class="sxs-lookup"><span data-stu-id="4b774-191">These include Azure functions, GitHub actions, and other small utilities.</span></span> <span data-ttu-id="4b774-192">Para obtener más información, vea [Instrucciones de nivel superior (Guía de programación de C#)](../../programming-guide/main-and-command-args/top-level-statements.md).</span><span class="sxs-lookup"><span data-stu-id="4b774-192">For more information, see [Top-level statements (C# Programming Guide)](../../programming-guide/main-and-command-args/top-level-statements.md).</span></span>
