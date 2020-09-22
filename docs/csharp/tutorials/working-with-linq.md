---
title: Trabajar con LINQ
description: En este tutorial se enseña cómo generar secuencias con LINQ, escribir métodos para su uso en consultas LINQ y distinguir entre la evaluación diligente y diferida.
ms.date: 10/29/2018
ms.technology: csharp-linq
ms.assetid: 0db12548-82cb-4903-ac88-13103d70aa77
ms.openlocfilehash: 59e86d6412e16728fb03d05f7f4e221a26ec1bb1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536241"
---
# <a name="work-with-language-integrated-query-linq"></a><span data-ttu-id="ec259-103">Uso de Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="ec259-103">Work with Language-Integrated Query (LINQ)</span></span>

## <a name="introduction"></a><span data-ttu-id="ec259-104">Introducción</span><span class="sxs-lookup"><span data-stu-id="ec259-104">Introduction</span></span>

<span data-ttu-id="ec259-105">En este tutorial aprenderá varias características de .NET Core y el lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="ec259-105">This tutorial teaches you features in .NET Core and the C# language.</span></span> <span data-ttu-id="ec259-106">Aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="ec259-106">You’ll learn how to:</span></span>

- <span data-ttu-id="ec259-107">Generar secuencias con LINQ.</span><span class="sxs-lookup"><span data-stu-id="ec259-107">Generate sequences with LINQ.</span></span>
- <span data-ttu-id="ec259-108">Escribir métodos que puedan usarse fácilmente en las consultas LINQ.</span><span class="sxs-lookup"><span data-stu-id="ec259-108">Write methods that can be easily used in LINQ queries.</span></span>
- <span data-ttu-id="ec259-109">Distinguir entre evaluación diligente y diferida.</span><span class="sxs-lookup"><span data-stu-id="ec259-109">Distinguish between eager and lazy evaluation.</span></span>

<span data-ttu-id="ec259-110">Aprenderá estas técnicas mediante la creación de una aplicación que muestra uno de los conocimientos básicos de cualquier mago: el [orden aleatorio faro](https://en.wikipedia.org/wiki/Faro_shuffle).</span><span class="sxs-lookup"><span data-stu-id="ec259-110">You'll learn these techniques by building an application that demonstrates one of the basic skills of any magician: the [faro shuffle](https://en.wikipedia.org/wiki/Faro_shuffle).</span></span> <span data-ttu-id="ec259-111">En resumen, el orden aleatorio faro es una técnica basada en dividir la baraja exactamente por la mitad; a continuación, el orden aleatorio intercala cada carta de cada mitad de la baraja hasta volver a crear la original.</span><span class="sxs-lookup"><span data-stu-id="ec259-111">Briefly, a faro shuffle is a technique where you split a card deck exactly in half, then the shuffle interleaves each one card from each half to rebuild the original deck.</span></span>

<span data-ttu-id="ec259-112">Los magos usan esta técnica porque cada carta está en una ubicación conocida después de cada orden aleatorio, y el orden sigue un patrón de repetición.</span><span class="sxs-lookup"><span data-stu-id="ec259-112">Magicians use this technique because every card is in a known location after each shuffle, and the order is a repeating pattern.</span></span>

<span data-ttu-id="ec259-113">Para el propósito sobre el que trata este artículo, resulta divertido ocuparnos de la manipulación de secuencias de datos.</span><span class="sxs-lookup"><span data-stu-id="ec259-113">For your purposes, it is a light hearted look at manipulating sequences of data.</span></span> <span data-ttu-id="ec259-114">La aplicación que se va a crear compilará una baraja de cartas y después realizará una secuencia de órdenes aleatorios, que escribirá cada vez la secuencia completa.</span><span class="sxs-lookup"><span data-stu-id="ec259-114">The application you'll build constructs a card deck and then performs a sequence of shuffles, writing the sequence out each time.</span></span> <span data-ttu-id="ec259-115">También podrá comparar el orden actualizado con el original.</span><span class="sxs-lookup"><span data-stu-id="ec259-115">You'll also compare the updated order to the original order.</span></span>

<span data-ttu-id="ec259-116">Este tutorial consta de varios pasos.</span><span class="sxs-lookup"><span data-stu-id="ec259-116">This tutorial has multiple steps.</span></span> <span data-ttu-id="ec259-117">Después de cada paso, puede ejecutar la aplicación y ver el progreso.</span><span class="sxs-lookup"><span data-stu-id="ec259-117">After each step, you can run the application and see the progress.</span></span> <span data-ttu-id="ec259-118">También puede ver el [ejemplo completo](https://github.com/dotnet/samples/blob/master/csharp/getting-started/console-linq) en el repositorio dotnet/samples de GitHub.</span><span class="sxs-lookup"><span data-stu-id="ec259-118">You can also see the [completed sample](https://github.com/dotnet/samples/blob/master/csharp/getting-started/console-linq) in the dotnet/samples GitHub repository.</span></span> <span data-ttu-id="ec259-119">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#view-and-download-samples).</span><span class="sxs-lookup"><span data-stu-id="ec259-119">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#view-and-download-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ec259-120">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ec259-120">Prerequisites</span></span>

<span data-ttu-id="ec259-121">Deberá configurar la máquina para ejecutar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ec259-121">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="ec259-122">Puede encontrar las instrucciones de instalación en la página [Descarga de .NET Core](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="ec259-122">You can find the installation instructions on the [.NET Core Download](https://dotnet.microsoft.com/download) page.</span></span> <span data-ttu-id="ec259-123">Puede ejecutar esta aplicación en Windows, Ubuntu Linux, OS X o en un contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="ec259-123">You can run this application on Windows, Ubuntu Linux, or OS X, or in a Docker container.</span></span> <span data-ttu-id="ec259-124">Deberá instalar su editor de código favorito.</span><span class="sxs-lookup"><span data-stu-id="ec259-124">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="ec259-125">En las siguientes descripciones se usa [Visual Studio Code](https://code.visualstudio.com/), que es un editor multiplataforma de código abierto.</span><span class="sxs-lookup"><span data-stu-id="ec259-125">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross-platform editor.</span></span> <span data-ttu-id="ec259-126">Sin embargo, puede usar las herramientas que le resulten más cómodas.</span><span class="sxs-lookup"><span data-stu-id="ec259-126">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="ec259-127">Crear la aplicación</span><span class="sxs-lookup"><span data-stu-id="ec259-127">Create the Application</span></span>

<span data-ttu-id="ec259-128">El primer paso es crear una nueva aplicación.</span><span class="sxs-lookup"><span data-stu-id="ec259-128">The first step is to create a new application.</span></span> <span data-ttu-id="ec259-129">Abra un símbolo del sistema y cree un nuevo directorio para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ec259-129">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="ec259-130">Conviértalo en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="ec259-130">Make that the current directory.</span></span> <span data-ttu-id="ec259-131">Escriba el comando `dotnet new console` en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="ec259-131">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="ec259-132">Esta acción crea los archivos de inicio para una aplicación básica "Hola a todos".</span><span class="sxs-lookup"><span data-stu-id="ec259-132">This creates the starter files for a basic "Hello World" application.</span></span>

<span data-ttu-id="ec259-133">Si nunca ha usado C# antes, en [este tutorial](console-teleprompter.md) se explica la estructura de un programa con C#.</span><span class="sxs-lookup"><span data-stu-id="ec259-133">If you've never used C# before, [this tutorial](console-teleprompter.md) explains the structure of a C# program.</span></span> <span data-ttu-id="ec259-134">Puede leerlo y después volver aquí para obtener más información sobre LINQ.</span><span class="sxs-lookup"><span data-stu-id="ec259-134">You can read that and then return here to learn more about LINQ.</span></span>

## <a name="create-the-data-set"></a><span data-ttu-id="ec259-135">Creación del conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="ec259-135">Create the Data Set</span></span>

<span data-ttu-id="ec259-136">Antes de empezar, asegúrese de que las líneas siguientes se encuentran al principio del archivo `Program.cs` generado por `dotnet new console`:</span><span class="sxs-lookup"><span data-stu-id="ec259-136">Before you begin, make sure that the following lines are at the top of the `Program.cs` file generated by `dotnet new console`:</span></span>

```csharp
// Program.cs
using System;
using System.Collections.Generic;
using System.Linq;
```

<span data-ttu-id="ec259-137">Si estas tres líneas (instrucciones `using`) no se encuentran al principio del archivo, nuestro programa no se compilará.</span><span class="sxs-lookup"><span data-stu-id="ec259-137">If these three lines (`using` statements) aren't at the top of the file, our program will not compile.</span></span>

<span data-ttu-id="ec259-138">Ahora que tiene todas las referencias que necesitará, tenga en cuenta lo que constituye una baraja de cartas.</span><span class="sxs-lookup"><span data-stu-id="ec259-138">Now that you have all of the references that you'll need, consider what constitutes a deck of cards.</span></span> <span data-ttu-id="ec259-139">Habitualmente, una baraja de cartas tiene cuatro palos y cada palo tiene trece valores.</span><span class="sxs-lookup"><span data-stu-id="ec259-139">Commonly, a deck of playing cards has four suits, and each suit has thirteen values.</span></span> <span data-ttu-id="ec259-140">Normalmente, podría plantearse crear una clase `Card` directamente del archivo bat y rellenar manualmente una colección de objetos `Card`.</span><span class="sxs-lookup"><span data-stu-id="ec259-140">Normally, you might consider creating a `Card` class right off the bat and populating a collection of `Card` objects by hand.</span></span> <span data-ttu-id="ec259-141">Con LINQ, puede ser más conciso que de costumbre al tratar con la creación de una baraja de cartas.</span><span class="sxs-lookup"><span data-stu-id="ec259-141">With LINQ, you can be more concise than the usual way of dealing with creating a deck of cards.</span></span> <span data-ttu-id="ec259-142">En lugar de crear una clase `Card`, puede crear dos secuencias para representar los palos y rangos, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="ec259-142">Instead of creating a `Card` class, you can create two sequences to represent suits and ranks, respectively.</span></span> <span data-ttu-id="ec259-143">Podrá crear un par sencillo de [*métodos iterator*](../iterators.md#enumeration-sources-with-iterator-methods) que generará las clasificaciones y palos como objetos <xref:System.Collections.Generic.IEnumerable%601> de cadenas:</span><span class="sxs-lookup"><span data-stu-id="ec259-143">You'll create a really simple pair of [*iterator methods*](../iterators.md#enumeration-sources-with-iterator-methods) that will generate the ranks and suits as <xref:System.Collections.Generic.IEnumerable%601>s of strings:</span></span>

```csharp
// Program.cs
// The Main() method

static IEnumerable<string> Suits()
{
    yield return "clubs";
    yield return "diamonds";
    yield return "hearts";
    yield return "spades";
}

static IEnumerable<string> Ranks()
{
    yield return "two";
    yield return "three";
    yield return "four";
    yield return "five";
    yield return "six";
    yield return "seven";
    yield return "eight";
    yield return "nine";
    yield return "ten";
    yield return "jack";
    yield return "queen";
    yield return "king";
    yield return "ace";
}
```

<span data-ttu-id="ec259-144">Colóquelos debajo del método `Main` en el archivo `Program.cs`.</span><span class="sxs-lookup"><span data-stu-id="ec259-144">Place these underneath the `Main` method in your `Program.cs` file.</span></span> <span data-ttu-id="ec259-145">Estos dos métodos utilizan la sintaxis `yield return` para generar una secuencia mientras se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="ec259-145">These two methods both utilize the `yield return` syntax to produce a sequence as they run.</span></span> <span data-ttu-id="ec259-146">El compilador crea un objeto que implementa <xref:System.Collections.Generic.IEnumerable%601> y genera la secuencia de cadenas conforme se solicitan.</span><span class="sxs-lookup"><span data-stu-id="ec259-146">The compiler builds an object that implements <xref:System.Collections.Generic.IEnumerable%601> and generates the sequence of strings as they are requested.</span></span>

<span data-ttu-id="ec259-147">Ahora, puede usar estos métodos iterator para crear la baraja de cartas.</span><span class="sxs-lookup"><span data-stu-id="ec259-147">Now, use these iterator methods to create the deck of cards.</span></span> <span data-ttu-id="ec259-148">Insertará la consulta LINQ en nuestro método `Main`.</span><span class="sxs-lookup"><span data-stu-id="ec259-148">You'll place the LINQ query in our `Main` method.</span></span> <span data-ttu-id="ec259-149">Aquí tiene una imagen:</span><span class="sxs-lookup"><span data-stu-id="ec259-149">Here's a look at it:</span></span>

```csharp
// Program.cs
static void Main(string[] args)
{
    var startingDeck = from s in Suits()
                       from r in Ranks()
                       select new { Suit = s, Rank = r };

    // Display each card that we've generated and placed in startingDeck in the console
    foreach (var card in startingDeck)
    {
        Console.WriteLine(card);
    }
}
```

<span data-ttu-id="ec259-150">Las cláusulas múltiples `from` generan una salida <xref:System.Linq.Enumerable.SelectMany%2A>, que crea una única secuencia a partir de la combinación de cada elemento de la primera secuencia con cada elemento de la segunda secuencia.</span><span class="sxs-lookup"><span data-stu-id="ec259-150">The multiple `from` clauses produce a <xref:System.Linq.Enumerable.SelectMany%2A>, which creates a single sequence from combining each element in the first sequence with each element in the second sequence.</span></span> <span data-ttu-id="ec259-151">El orden es importante para nuestros propósitos.</span><span class="sxs-lookup"><span data-stu-id="ec259-151">The order is important for our purposes.</span></span> <span data-ttu-id="ec259-152">El primer elemento de la primera secuencia de origen (palos) se combina con todos los elementos de la segunda secuencia (clasificaciones).</span><span class="sxs-lookup"><span data-stu-id="ec259-152">The first element in the first source sequence (Suits) is combined with every element in the second sequence (Ranks).</span></span> <span data-ttu-id="ec259-153">Esto genera las trece cartas del primer palo.</span><span class="sxs-lookup"><span data-stu-id="ec259-153">This produces all thirteen cards of first suit.</span></span> <span data-ttu-id="ec259-154">Dicho proceso se repite con cada elemento de la primera secuencia (palos).</span><span class="sxs-lookup"><span data-stu-id="ec259-154">That process is repeated with each element in the first sequence (Suits).</span></span> <span data-ttu-id="ec259-155">El resultado final es una baraja de cartas ordenadas por palos, seguidos de valores.</span><span class="sxs-lookup"><span data-stu-id="ec259-155">The end result is a deck of cards ordered by suits, followed by values.</span></span>

<span data-ttu-id="ec259-156">Es importante tener en cuenta que si decide escribir las instrucciones LINQ en la sintaxis de consulta usada anteriormente o utilizar la sintaxis de método en su lugar, siempre es posible pasar de una forma de sintaxis a la otra.</span><span class="sxs-lookup"><span data-stu-id="ec259-156">It's important to keep in mind that whether you choose to write your LINQ in the query syntax used above or use method syntax instead, it's always possible to go from one form of syntax to the other.</span></span> <span data-ttu-id="ec259-157">La consulta anterior escrita en la sintaxis de consulta puede escribirse en la sintaxis de método como:</span><span class="sxs-lookup"><span data-stu-id="ec259-157">The above query written in query syntax can be written in method syntax as:</span></span>

```csharp
var startingDeck = Suits().SelectMany(suit => Ranks().Select(rank => new { Suit = suit, Rank = rank }));
```

<span data-ttu-id="ec259-158">El compilador convierte las instrucciones LINQ escritas en la sintaxis de consulta a la sintaxis de llamada de método equivalente.</span><span class="sxs-lookup"><span data-stu-id="ec259-158">The compiler translates LINQ statements written with query syntax into the equivalent method call syntax.</span></span> <span data-ttu-id="ec259-159">Por consiguiente, independientemente de la sintaxis que prefiera, las dos versiones de la consulta producen el mismo resultado.</span><span class="sxs-lookup"><span data-stu-id="ec259-159">Therefore, regardless of your syntax choice, the two versions of the query produce the same result.</span></span> <span data-ttu-id="ec259-160">Elija la sintaxis más adecuada a su situación: por ejemplo, si trabaja en un equipo en el que algunos de sus miembros tienen dificultades con la sintaxis de método, procure usar la sintaxis de consulta.</span><span class="sxs-lookup"><span data-stu-id="ec259-160">Choose which syntax works best for your situation: for instance, if you're working in a team where some of the members have difficulty with method syntax, try to prefer using query syntax.</span></span>

<span data-ttu-id="ec259-161">Continúe y ejecute el ejemplo que se ha creado en este punto.</span><span class="sxs-lookup"><span data-stu-id="ec259-161">Go ahead and run the sample you've built at this point.</span></span> <span data-ttu-id="ec259-162">Mostrará todas las 52 cartas de la baraja.</span><span class="sxs-lookup"><span data-stu-id="ec259-162">It will display all 52 cards in the deck.</span></span> <span data-ttu-id="ec259-163">Puede ser muy útil ejecutar este ejemplo en un depurador para observar cómo se ejecutan los métodos `Suits()` y `Ranks()`.</span><span class="sxs-lookup"><span data-stu-id="ec259-163">You may find it very helpful to run this sample under a debugger to observe how the `Suits()` and `Ranks()` methods execute.</span></span> <span data-ttu-id="ec259-164">Puede ver claramente que cada cadena de cada secuencia se genera solo según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="ec259-164">You can clearly see that each string in each sequence is generated only as it is needed.</span></span>

![Una ventana de la consola que muestra la aplicación escribiendo 52 tarjetas.](./media/working-with-linq/console-52-card-application.png)

## <a name="manipulate-the-order"></a><span data-ttu-id="ec259-166">Manipulación del orden</span><span class="sxs-lookup"><span data-stu-id="ec259-166">Manipulate the Order</span></span>

<span data-ttu-id="ec259-167">Seguidamente, céntrese en cómo va a establecer el orden aleatorio de las cartas de la baraja.</span><span class="sxs-lookup"><span data-stu-id="ec259-167">Next, focus on how you're going to shuffle the cards in the deck.</span></span> <span data-ttu-id="ec259-168">El primer paso en cualquier orden aleatorio consiste en dividir la baraja en dos.</span><span class="sxs-lookup"><span data-stu-id="ec259-168">The first step in any good shuffle is to split the deck in two.</span></span> <span data-ttu-id="ec259-169">Los métodos <xref:System.Linq.Enumerable.Take%2A> y <xref:System.Linq.Enumerable.Skip%2A> que forman parte de las LINQ API le ofrecen esa característica:</span><span class="sxs-lookup"><span data-stu-id="ec259-169">The <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> methods that are part of the LINQ APIs provide that feature for you.</span></span> <span data-ttu-id="ec259-170">Colóquelos debajo del bucle `foreach`:</span><span class="sxs-lookup"><span data-stu-id="ec259-170">Place them underneath the `foreach` loop:</span></span>

```csharp
// Program.cs
public static void Main(string[] args)
{
    var startingDeck = from s in Suits()
                       from r in Ranks()
                       select new { Suit = s, Rank = r };

    foreach (var c in startingDeck)
    {
        Console.WriteLine(c);
    }

    // 52 cards in a deck, so 52 / 2 = 26
    var top = startingDeck.Take(26);
    var bottom = startingDeck.Skip(26);
}
```

<span data-ttu-id="ec259-171">Pero no existe ningún método de orden aleatorio en la biblioteca estándar que pueda aprovechar, por lo que tendrá que escribir el suyo propio.</span><span class="sxs-lookup"><span data-stu-id="ec259-171">However, there's no shuffle method to take advantage of in the standard library, so you'll have to write your own.</span></span> <span data-ttu-id="ec259-172">El método de orden aleatorio que cree mostrará varias técnicas que se utilizan con programas basados en LINQ, por lo que cada parte de este proceso se explica en pasos.</span><span class="sxs-lookup"><span data-stu-id="ec259-172">The shuffle method you'll be creating illustrates several techniques that you'll use with LINQ-based programs, so each part of this process will be explained in steps.</span></span>

<span data-ttu-id="ec259-173">Para agregar alguna funcionalidad a la forma de interactuar con el elemento <xref:System.Collections.Generic.IEnumerable%601> que obtendrá de las consultas LINQ, tendrá que escribir algunos tipos especiales de métodos llamados [métodos de extensión](../programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="ec259-173">In order to add some functionality to how you interact with the <xref:System.Collections.Generic.IEnumerable%601> you'll get back from LINQ queries, you'll need to write some special kinds of methods called [extension methods](../programming-guide/classes-and-structs/extension-methods.md).</span></span> <span data-ttu-id="ec259-174">En resumen, un método de extensión es un *método estático* con una finalidad específica que agrega nueva funcionalidad a un tipo existente sin tener que modificar el tipo original al que quiere agregar la funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="ec259-174">Briefly, an extension method is a special purpose *static method* that adds new functionality to an already-existing type without having to modify the original type you want to add functionality to.</span></span>

<span data-ttu-id="ec259-175">Proporcione un nuevo espacio a sus métodos de extensión agregando un nuevo archivo de clase *estática* al programa denominado `Extensions.cs` y comience a compilar el primer método de extensión:</span><span class="sxs-lookup"><span data-stu-id="ec259-175">Give your extension methods a new home by adding a new *static* class file to your program called `Extensions.cs`, and then start building out the first extension method:</span></span>

```csharp
// Extensions.cs
using System;
using System.Collections.Generic;
using System.Linq;

namespace LinqFaroShuffle
{
    public static class Extensions
    {
        public static IEnumerable<T> InterleaveSequenceWith<T>(this IEnumerable<T> first, IEnumerable<T> second)
        {
            // Your implementation will go here soon enough
        }
    }
}
```

<span data-ttu-id="ec259-176">Mire la firma del método por un momento, concretamente los parámetros:</span><span class="sxs-lookup"><span data-stu-id="ec259-176">Look at the method signature for a moment, specifically the parameters:</span></span>

```csharp
public static IEnumerable<T> InterleaveSequenceWith<T> (this IEnumerable<T> first, IEnumerable<T> second)
```

<span data-ttu-id="ec259-177">Puede ver la incorporación del modificador `this` del primer argumento al método.</span><span class="sxs-lookup"><span data-stu-id="ec259-177">You can see the addition of the `this` modifier on the first argument to the method.</span></span> <span data-ttu-id="ec259-178">Esto significa que se llama al método como si fuese un método de miembro del tipo del primer argumento.</span><span class="sxs-lookup"><span data-stu-id="ec259-178">That means you call the method as though it were a member method of the type of the first argument.</span></span> <span data-ttu-id="ec259-179">Esta declaración de método también sigue una expresión estándar donde los tipos de entrada y salida son `IEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="ec259-179">This method declaration also follows a standard idiom where the input and output types are `IEnumerable<T>`.</span></span> <span data-ttu-id="ec259-180">Dicha práctica permite que los métodos LINQ se encadenen entre sí para realizar consultas más complejas.</span><span class="sxs-lookup"><span data-stu-id="ec259-180">That practice enables LINQ methods to be chained together to perform more complex queries.</span></span>

<span data-ttu-id="ec259-181">Naturalmente, dado que dividió la baraja en mitades, tendrá que unir esas mitades.</span><span class="sxs-lookup"><span data-stu-id="ec259-181">Naturally, since you split the deck into halves, you'll need to join those halves together.</span></span> <span data-ttu-id="ec259-182">En el código, esto significa que enumerará las dos secuencias adquiridas a través de <xref:System.Linq.Enumerable.Take%2A> y <xref:System.Linq.Enumerable.Skip%2A> a la vez, *`interleaving`* los elementos y crear una sola secuencia: su baraja de cartas recién ordenada aleatoriamente.</span><span class="sxs-lookup"><span data-stu-id="ec259-182">In code, this means you'll be enumerating both of the sequences you acquired through <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> at once, *`interleaving`* the elements, and creating one sequence: your now-shuffled deck of cards.</span></span> <span data-ttu-id="ec259-183">Escribir un método LINQ que funciona con dos secuencias requiere que comprenda cómo funciona <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="ec259-183">Writing a LINQ method that works with two sequences requires that you understand how <xref:System.Collections.Generic.IEnumerable%601> works.</span></span>

<span data-ttu-id="ec259-184">La interfaz <xref:System.Collections.Generic.IEnumerable%601> tiene un método: <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>.</span><span class="sxs-lookup"><span data-stu-id="ec259-184">The <xref:System.Collections.Generic.IEnumerable%601> interface has one method: <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>.</span></span> <span data-ttu-id="ec259-185">El objeto devuelto por <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> tiene un método para desplazarse al siguiente elemento, así como una propiedad que recupera el elemento actual de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="ec259-185">The object returned by <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> has a method to move to the next element, and a property that retrieves the current element in the sequence.</span></span> <span data-ttu-id="ec259-186">Utilizará estos dos miembros para enumerar la colección y devolver los elementos.</span><span class="sxs-lookup"><span data-stu-id="ec259-186">You will use those two members to enumerate the collection and return the elements.</span></span> <span data-ttu-id="ec259-187">Este método de intercalación será un método iterador, por lo que en lugar de crear una colección y devolverla, usará la sintaxis `yield return` anterior.</span><span class="sxs-lookup"><span data-stu-id="ec259-187">This Interleave method will be an iterator method, so instead of building a collection and returning the collection, you'll use the `yield return` syntax shown above.</span></span>

<span data-ttu-id="ec259-188">A continuación se muestra la implementación de ese método:</span><span class="sxs-lookup"><span data-stu-id="ec259-188">Here's the implementation of that method:</span></span>

[!CODE-csharp[InterleaveSequenceWith](../../../samples/snippets/csharp/getting-started/console-linq/extensions.cs?name=snippet1)]

<span data-ttu-id="ec259-189">Ahora que ha escrito este método, vuelva al método `Main` y ordene la baraja aleatoriamente una vez:</span><span class="sxs-lookup"><span data-stu-id="ec259-189">Now that you've written this method, go back to the `Main` method and shuffle the deck once:</span></span>

```csharp
// Program.cs
public static void Main(string[] args)
{
    var startingDeck = from s in Suits()
                       from r in Ranks()
                       select new { Suit = s, Rank = r };

    foreach (var c in startingDeck)
    {
        Console.WriteLine(c);
    }

    var top = startingDeck.Take(26);
    var bottom = startingDeck.Skip(26);
    var shuffle = top.InterleaveSequenceWith(bottom);

    foreach (var c in shuffle)
    {
        Console.WriteLine(c);
    }
}
```

## <a name="comparisons"></a><span data-ttu-id="ec259-190">Comparaciones</span><span class="sxs-lookup"><span data-stu-id="ec259-190">Comparisons</span></span>

<span data-ttu-id="ec259-191">¿Cuántos órdenes aleatorios se necesitan para devolver la baraja a su orden original?</span><span class="sxs-lookup"><span data-stu-id="ec259-191">How many shuffles it takes to set the deck back to its original order?</span></span> <span data-ttu-id="ec259-192">Para averiguarlo, debe escribir un método que determine si dos secuencias son iguales.</span><span class="sxs-lookup"><span data-stu-id="ec259-192">To find out, you'll need to write a method that determines if two sequences are equal.</span></span> <span data-ttu-id="ec259-193">Cuando ya disponga del método, debe colocar el código que ordena la baraja aleatoriamente en un bucle y comprobarlo para ver cuándo la baraja vuelve a tener su orden original.</span><span class="sxs-lookup"><span data-stu-id="ec259-193">After you have that method, you'll need to place the code that shuffles the deck in a loop, and check to see when the deck is back in order.</span></span>

<span data-ttu-id="ec259-194">Debe ser sencillo escribir un método para determinar si las dos secuencias son iguales.</span><span class="sxs-lookup"><span data-stu-id="ec259-194">Writing a method to determine if the two sequences are equal should be straightforward.</span></span> <span data-ttu-id="ec259-195">Presenta una estructura similar al método que se escribió para ordenar la baraja aleatoriamente.</span><span class="sxs-lookup"><span data-stu-id="ec259-195">It's a similar structure to the method you wrote to shuffle the deck.</span></span> <span data-ttu-id="ec259-196">Solo que esta vez, en lugar de aplicar `yield return` a cada elemento, se compararán los elementos coincidentes de cada secuencia.</span><span class="sxs-lookup"><span data-stu-id="ec259-196">Only this time, instead of `yield return`ing each element, you'll compare the matching elements of each sequence.</span></span> <span data-ttu-id="ec259-197">Después de que se haya enumerado la secuencia completa, si cada elemento coincide, las secuencias son las mismas:</span><span class="sxs-lookup"><span data-stu-id="ec259-197">When the entire sequence has been enumerated, if every element matches, the sequences are the same:</span></span>

[!CODE-csharp[SequenceEquals](../../../samples/snippets/csharp/getting-started/console-linq/extensions.cs?name=snippet2)]

<span data-ttu-id="ec259-198">Esto muestra una segunda expresión LINQ: los métodos de terminal.</span><span class="sxs-lookup"><span data-stu-id="ec259-198">This shows a second LINQ idiom: terminal methods.</span></span> <span data-ttu-id="ec259-199">Adoptan una secuencia como entrada (o, en este caso, dos secuencias) y devuelven un único valor escalar.</span><span class="sxs-lookup"><span data-stu-id="ec259-199">They take a sequence as input (or in this case, two sequences), and return a single scalar value.</span></span> <span data-ttu-id="ec259-200">Cuando se utilizan métodos de terminal, siempre son el método final en una cadena de métodos para una consulta LINQ, de ahí el nombre "terminal".</span><span class="sxs-lookup"><span data-stu-id="ec259-200">When using terminal methods, they are always the final method in a chain of methods for a LINQ query, hence the name "terminal".</span></span>

<span data-ttu-id="ec259-201">Puede ver esto en acción cuando lo usa para determinar cuándo la baraja vuelve a tener su orden original.</span><span class="sxs-lookup"><span data-stu-id="ec259-201">You can see this in action when you use it to determine when the deck is back in its original order.</span></span> <span data-ttu-id="ec259-202">Coloque el código de orden aleatorio dentro de un bucle y deténgalo cuando la secuencia vuelva a su orden original, mediante la aplicación del método `SequenceEquals()`.</span><span class="sxs-lookup"><span data-stu-id="ec259-202">Put the shuffle code inside a loop, and stop when the sequence is back in its original order by applying the `SequenceEquals()` method.</span></span> <span data-ttu-id="ec259-203">Puede observar que siempre se tratará del método final de cualquier consulta, porque devuelve un único valor en lugar de una secuencia:</span><span class="sxs-lookup"><span data-stu-id="ec259-203">You can see it would always be the final method in any query, because it returns a single value instead of a sequence:</span></span>

```csharp
// Program.cs
static void Main(string[] args)
{
    // Query for building the deck

    // Shuffling using InterleaveSequenceWith<T>();

    var times = 0;
    // We can re-use the shuffle variable from earlier, or you can make a new one
    shuffle = startingDeck;
    do
    {
        shuffle = shuffle.Take(26).InterleaveSequenceWith(shuffle.Skip(26));

        foreach (var card in shuffle)
        {
            Console.WriteLine(card);
        }
        Console.WriteLine();
        times++;

    } while (!startingDeck.SequenceEquals(shuffle));

    Console.WriteLine(times);
}
```

<span data-ttu-id="ec259-204">Ejecute el código que tenga hasta el momento y tome nota de cómo la baraja se reorganiza en cada orden aleatorio.</span><span class="sxs-lookup"><span data-stu-id="ec259-204">Run the code you've got so far and take note of how the deck rearranges on each shuffle.</span></span> <span data-ttu-id="ec259-205">Después de ocho órdenes aleatorios (iteraciones del bucle do-while), la baraja vuelve a la configuración original en que se encontraba cuando la creó a partir la consulta LINQ inicial.</span><span class="sxs-lookup"><span data-stu-id="ec259-205">After 8 shuffles (iterations of the do-while loop), the deck returns to the original configuration it was in when you first created it from the starting LINQ query.</span></span>

## <a name="optimizations"></a><span data-ttu-id="ec259-206">Optimizaciones</span><span class="sxs-lookup"><span data-stu-id="ec259-206">Optimizations</span></span>

<span data-ttu-id="ec259-207">El ejemplo creado hasta el momento se ejecuta *en orden no aleatorio*, donde las cartas superiores e inferiores son las mismas en cada ejecución.</span><span class="sxs-lookup"><span data-stu-id="ec259-207">The sample you've built so far executes an *out shuffle*, where the top and bottom cards stay the same on each run.</span></span> <span data-ttu-id="ec259-208">Vamos a realizar un cambio: utilizaremos una ejecución *en orden aleatorio* en su lugar, donde las 52 cartas cambian de posición.</span><span class="sxs-lookup"><span data-stu-id="ec259-208">Let's make one change: we'll use an *in shuffle* instead, where all 52 cards change position.</span></span> <span data-ttu-id="ec259-209">Si se trata de un orden aleatorio, intercale la baraja de tal forma que la primera carta de la mitad inferior sea la primera carta de la baraja.</span><span class="sxs-lookup"><span data-stu-id="ec259-209">For an in shuffle, you interleave the deck so that the first card in the bottom half becomes the first card in the deck.</span></span> <span data-ttu-id="ec259-210">Esto significa que la última carta de la mitad superior será la carta inferior.</span><span class="sxs-lookup"><span data-stu-id="ec259-210">That means the last card in the top half becomes the bottom card.</span></span> <span data-ttu-id="ec259-211">Se trata de un cambio simple en una única línea de código.</span><span class="sxs-lookup"><span data-stu-id="ec259-211">This is a simple change to a singular line of code.</span></span> <span data-ttu-id="ec259-212">Actualice la consulta de orden aleatorio actual cambiando las posiciones de <xref:System.Linq.Enumerable.Take%2A> y <xref:System.Linq.Enumerable.Skip%2A>.</span><span class="sxs-lookup"><span data-stu-id="ec259-212">Update the current shuffle query by switching the positions of <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A>.</span></span> <span data-ttu-id="ec259-213">Se cambiará al orden de las mitades superior e inferior de la baraja:</span><span class="sxs-lookup"><span data-stu-id="ec259-213">This will change the order of the top and bottom halves of the deck:</span></span>

```csharp
shuffle = shuffle.Skip(26).InterleaveSequenceWith(shuffle.Take(26));
```

<span data-ttu-id="ec259-214">Vuelva a ejecutar el programa y verá que, para que la baraja se reordene, se necesitan 52 iteraciones.</span><span class="sxs-lookup"><span data-stu-id="ec259-214">Run the program again, and you'll see that it takes 52 iterations for the deck to reorder itself.</span></span> <span data-ttu-id="ec259-215">También empezará a observar algunas degradaciones graves de rendimiento a medida que el programa continúa en ejecución.</span><span class="sxs-lookup"><span data-stu-id="ec259-215">You'll also start to notice some serious performance degradations as the program continues to run.</span></span>

<span data-ttu-id="ec259-216">Esto se debe a varias razones.</span><span class="sxs-lookup"><span data-stu-id="ec259-216">There are a number of reasons for this.</span></span> <span data-ttu-id="ec259-217">Puede que se trate de una de las principales causas de este descenso de rendimiento: un uso ineficaz de la [*evaluación diferida*](../../standard/linq/deferred-execution-lazy-evaluation.md).</span><span class="sxs-lookup"><span data-stu-id="ec259-217">You can tackle one of the major causes of this performance drop: inefficient use of [*lazy evaluation*](../../standard/linq/deferred-execution-lazy-evaluation.md).</span></span>

<span data-ttu-id="ec259-218">En pocas palabras, la evaluación diferida indica que no se realiza la evaluación de una instrucción hasta que su valor es necesario.</span><span class="sxs-lookup"><span data-stu-id="ec259-218">Briefly, lazy evaluation states that the evaluation of a statement is not performed until its value is needed.</span></span> <span data-ttu-id="ec259-219">Las consultas LINQ son instrucciones se evalúan de forma diferida.</span><span class="sxs-lookup"><span data-stu-id="ec259-219">LINQ queries are statements that are evaluated lazily.</span></span> <span data-ttu-id="ec259-220">Las secuencias se generan solo a medida que se solicitan los elementos.</span><span class="sxs-lookup"><span data-stu-id="ec259-220">The sequences are generated only as the elements are requested.</span></span> <span data-ttu-id="ec259-221">Normalmente, es una ventaja importante de LINQ.</span><span class="sxs-lookup"><span data-stu-id="ec259-221">Usually, that's a major benefit of LINQ.</span></span> <span data-ttu-id="ec259-222">Sin embargo, en un uso como el que hace este programa, se produce un aumento exponencial del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ec259-222">However, in a use such as this program, this causes exponential growth in execution time.</span></span>

<span data-ttu-id="ec259-223">Recuerde que la baraja original se generó con una consulta LINQ.</span><span class="sxs-lookup"><span data-stu-id="ec259-223">Remember that we generated the original deck using a LINQ query.</span></span> <span data-ttu-id="ec259-224">Cada orden aleatorio se genera mediante la realización de tres consultas LINQ sobre la baraja anterior.</span><span class="sxs-lookup"><span data-stu-id="ec259-224">Each shuffle is generated by performing three LINQ queries on the previous deck.</span></span> <span data-ttu-id="ec259-225">Todas se realizan de forma diferida.</span><span class="sxs-lookup"><span data-stu-id="ec259-225">All these are performed lazily.</span></span> <span data-ttu-id="ec259-226">Eso también significa que se vuelven a llevar a cabo cada vez que se solicita la secuencia.</span><span class="sxs-lookup"><span data-stu-id="ec259-226">That also means they are performed again each time the sequence is requested.</span></span> <span data-ttu-id="ec259-227">Cuando llegue a la iteración número 52, habrá regenerado la baraja original demasiadas veces.</span><span class="sxs-lookup"><span data-stu-id="ec259-227">By the time you get to the 52nd iteration, you're regenerating the original deck many, many times.</span></span> <span data-ttu-id="ec259-228">Se va a escribir un registro para mostrar este comportamiento.</span><span class="sxs-lookup"><span data-stu-id="ec259-228">Let's write a log to demonstrate this behavior.</span></span> <span data-ttu-id="ec259-229">A continuación, podrá corregirlo.</span><span class="sxs-lookup"><span data-stu-id="ec259-229">Then, you'll fix it.</span></span>

<span data-ttu-id="ec259-230">En su archivo `Extensions.cs`, escriba o copie el siguiente método.</span><span class="sxs-lookup"><span data-stu-id="ec259-230">In your `Extensions.cs` file, type in or copy the method below.</span></span> <span data-ttu-id="ec259-231">Este método de extensión crea otro archivo denominado `debug.log` en el directorio del proyecto y registra la consulta que se ejecuta actualmente en el archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="ec259-231">This extension method creates a new file called `debug.log` within your project directory and records what query is currently being executed to the log file.</span></span> <span data-ttu-id="ec259-232">Este método de extensión se puede anexar a una consulta para marcar que se ha ejecutado.</span><span class="sxs-lookup"><span data-stu-id="ec259-232">This extension method can be appended to any query to mark that the query executed.</span></span>

[!CODE-csharp[LogQuery](../../../samples/snippets/csharp/getting-started/console-linq/extensions.cs?name=snippet3)]

<span data-ttu-id="ec259-233">Verá un subrayado en zigzag rojo bajo `File`, lo que indica que no existe.</span><span class="sxs-lookup"><span data-stu-id="ec259-233">You will see a red squiggle under `File`, meaning it doesn't exist.</span></span> <span data-ttu-id="ec259-234">No se compilará, ya que el compilador no sabe qué es `File`.</span><span class="sxs-lookup"><span data-stu-id="ec259-234">It won't compile, since the compiler doesn't know what `File` is.</span></span> <span data-ttu-id="ec259-235">Para solucionar este problema, asegúrese de agregar la siguiente línea de código bajo la primera línea de `Extensions.cs`:</span><span class="sxs-lookup"><span data-stu-id="ec259-235">To solve this problem, make sure to add the following line of code under the very first line in `Extensions.cs`:</span></span>

```csharp
using System.IO;
```

<span data-ttu-id="ec259-236">Esto debería resolver el problema y el error en rojo debería desaparecer.</span><span class="sxs-lookup"><span data-stu-id="ec259-236">This should solve the issue and the red error disappears.</span></span>

<span data-ttu-id="ec259-237">A continuación, instrumente la definición de cada consulta con un mensaje de registro:</span><span class="sxs-lookup"><span data-stu-id="ec259-237">Next, instrument the definition of each query with a log message:</span></span>

```csharp
// Program.cs
public static void Main(string[] args)
{
    var startingDeck = (from s in Suits().LogQuery("Suit Generation")
                        from r in Ranks().LogQuery("Rank Generation")
                        select new { Suit = s, Rank = r }).LogQuery("Starting Deck");

    foreach (var c in startingDeck)
    {
        Console.WriteLine(c);
    }

    Console.WriteLine();
    var times = 0;
    var shuffle = startingDeck;

    do
    {
        // Out shuffle
        /*
        shuffle = shuffle.Take(26)
            .LogQuery("Top Half")
            .InterleaveSequenceWith(shuffle.Skip(26)
            .LogQuery("Bottom Half"))
            .LogQuery("Shuffle");
        */

        // In shuffle
        shuffle = shuffle.Skip(26).LogQuery("Bottom Half")
                .InterleaveSequenceWith(shuffle.Take(26).LogQuery("Top Half"))
                .LogQuery("Shuffle");

        foreach (var c in shuffle)
        {
            Console.WriteLine(c);
        }

        times++;
        Console.WriteLine(times);
    } while (!startingDeck.SequenceEquals(shuffle));

    Console.WriteLine(times);
}
```

<span data-ttu-id="ec259-238">Observe que no se genera un registro cada vez que accede a una consulta.</span><span class="sxs-lookup"><span data-stu-id="ec259-238">Notice that you don't log every time you access a query.</span></span> <span data-ttu-id="ec259-239">El registro solo se genera cuando crea la consulta original.</span><span class="sxs-lookup"><span data-stu-id="ec259-239">You log only when you create the original query.</span></span> <span data-ttu-id="ec259-240">El programa todavía tarda mucho tiempo en ejecutarse, pero ahora puede ver por qué.</span><span class="sxs-lookup"><span data-stu-id="ec259-240">The program still takes a long time to run, but now you can see why.</span></span> <span data-ttu-id="ec259-241">Si se le agota la paciencia al ejecutar el orden aleatorio interno con los registros activados, vuelva al orden aleatorio externo.</span><span class="sxs-lookup"><span data-stu-id="ec259-241">If you run out of patience running the in shuffle with logging turned on, switch back to the out shuffle.</span></span> <span data-ttu-id="ec259-242">Aún puede ver los efectos de la evaluación diferida.</span><span class="sxs-lookup"><span data-stu-id="ec259-242">You'll still see the lazy evaluation effects.</span></span> <span data-ttu-id="ec259-243">En una ejecución, ejecuta 2592 consultas, incluida toda la generación de palos y valores.</span><span class="sxs-lookup"><span data-stu-id="ec259-243">In one run, it executes 2592 queries, including all the value and suit generation.</span></span>

<span data-ttu-id="ec259-244">Aquí puede mejorar el rendimiento del código para reducir el número de ejecuciones que realiza.</span><span class="sxs-lookup"><span data-stu-id="ec259-244">You can improve the performance of the code here to reduce the number of executions you make.</span></span> <span data-ttu-id="ec259-245">Una corrección sencilla que puede hacer es almacenar en *caché* los resultados de la consulta LINQ original que construye la baraja de cartas.</span><span class="sxs-lookup"><span data-stu-id="ec259-245">A simple fix you can make is to *cache* the results of the original LINQ query that constructs the deck of cards.</span></span> <span data-ttu-id="ec259-246">Actualmente, ejecuta las consultas una y otra vez siempre que el bucle do-while pasa por una iteración, lo que vuelve a construir la baraja de cartas y cambia continuamente el orden aleatorio.</span><span class="sxs-lookup"><span data-stu-id="ec259-246">Currently, you're executing the queries again and again every time the do-while loop goes through an iteration, re-constructing the deck of cards and reshuffling it every time.</span></span> <span data-ttu-id="ec259-247">Para almacenar en caché la baraja de cartas, puede aprovechar los métodos LINQ <xref:System.Linq.Enumerable.ToArray%2A> y <xref:System.Linq.Enumerable.ToList%2A>; cuando los anexe a las consultas, realizarán las mismas acciones que les ha indicado que hagan, pero ahora almacenarán los resultados en una matriz o una lista, según el método al que elija llamar.</span><span class="sxs-lookup"><span data-stu-id="ec259-247">To cache the deck of cards, you can leverage the LINQ methods <xref:System.Linq.Enumerable.ToArray%2A> and <xref:System.Linq.Enumerable.ToList%2A>; when you append them to the queries, they'll perform the same actions you've told them to, but now they'll store the results in an array or a list, depending on which method you choose to call.</span></span> <span data-ttu-id="ec259-248">Anexe el método <xref:System.Linq.Enumerable.ToArray%2A> de LINQ a las dos consultas y ejecute de nuevo el programa:</span><span class="sxs-lookup"><span data-stu-id="ec259-248">Append the LINQ method <xref:System.Linq.Enumerable.ToArray%2A> to both queries and run the program again:</span></span>

[!CODE-csharp[Main](../../../samples/snippets/csharp/getting-started/console-linq/Program.cs?name=snippet1)]

<span data-ttu-id="ec259-249">Ahora el orden aleatorio externo se reduce a 30 consultas.</span><span class="sxs-lookup"><span data-stu-id="ec259-249">Now the out shuffle is down to 30 queries.</span></span> <span data-ttu-id="ec259-250">Vuelva a ejecutarlo con el orden aleatorio interno y verá mejoras similares: ahora ejecuta 162 consultas.</span><span class="sxs-lookup"><span data-stu-id="ec259-250">Run again with the in shuffle and you'll see similar improvements: it now executes 162 queries.</span></span>

<span data-ttu-id="ec259-251">Este ejemplo está **diseñado** para resaltar los casos de uso en que la evaluación diferida puede generar dificultades de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="ec259-251">Please note that this example is **designed** to highlight the use cases where lazy evaluation can cause performance difficulties.</span></span> <span data-ttu-id="ec259-252">Si bien es importante ver dónde la evaluación diferida puede afectar al rendimiento del código, es igualmente importante entender que no todas las consultas deben ejecutarse de manera diligente.</span><span class="sxs-lookup"><span data-stu-id="ec259-252">While it's important to see where lazy evaluation can impact code performance, it's equally important to understand that not all queries should run eagerly.</span></span> <span data-ttu-id="ec259-253">El resultado de rendimiento en el que incurre sin usar <xref:System.Linq.Enumerable.ToArray%2A> se debe a que cada nueva disposición de la baraja de cartas se crea a partir de la disposición anterior.</span><span class="sxs-lookup"><span data-stu-id="ec259-253">The performance hit you incur without using <xref:System.Linq.Enumerable.ToArray%2A> is because each new arrangement of the deck of cards is built from the previous arrangement.</span></span> <span data-ttu-id="ec259-254">La evaluación diferida supone que cada nueva configuración de la baraja se realiza a partir de la baraja original, incluso con la ejecución del código que crea el elemento `startingDeck`.</span><span class="sxs-lookup"><span data-stu-id="ec259-254">Using lazy evaluation means each new deck configuration is built from the original deck, even executing the code that built the `startingDeck`.</span></span> <span data-ttu-id="ec259-255">Esto conlleva una gran cantidad de trabajo adicional.</span><span class="sxs-lookup"><span data-stu-id="ec259-255">That causes a large amount of extra work.</span></span>

<span data-ttu-id="ec259-256">En la práctica, algunos algoritmos se ejecutan bien con la evaluación diligente y otros, con la evaluación diferida.</span><span class="sxs-lookup"><span data-stu-id="ec259-256">In practice, some algorithms run well using eager evaluation, and others run well using lazy evaluation.</span></span> <span data-ttu-id="ec259-257">Para el uso diario, la evaluación diferida suele ser una mejor opción cuando el origen de datos es un proceso independiente, como un motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="ec259-257">For daily usage, lazy evaluation is usually a better choice when the data source is a separate process, like a database engine.</span></span> <span data-ttu-id="ec259-258">Para las bases de datos, la evaluación diferida permite realizar consultas más complejas que ejecuten un solo recorrido de ida y vuelta al procesamiento de la base de datos y vuelvan al resto del código.</span><span class="sxs-lookup"><span data-stu-id="ec259-258">For databases, lazy evaluation allows more complex queries to execute only one round trip to the database process and back to the rest of your code.</span></span> <span data-ttu-id="ec259-259">LINQ es flexible tanto si decide usar la evaluación diligente como la diferida, así que calibre sus procesos y elija el tipo de evaluación que le ofrece el mejor rendimiento.</span><span class="sxs-lookup"><span data-stu-id="ec259-259">LINQ is flexible whether you choose to utilize lazy or eager evaluation, so measure your processes and pick whichever kind of evaluation gives you the best performance.</span></span>

## <a name="conclusion"></a><span data-ttu-id="ec259-260">Conclusión</span><span class="sxs-lookup"><span data-stu-id="ec259-260">Conclusion</span></span>

<span data-ttu-id="ec259-261">En este proyecto ha tratado lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ec259-261">In this project, you covered:</span></span>

- <span data-ttu-id="ec259-262">Uso de consultas LINQ para agregar datos a una secuencia significativa</span><span class="sxs-lookup"><span data-stu-id="ec259-262">using LINQ queries to aggregate data into a meaningful sequence</span></span>
- <span data-ttu-id="ec259-263">Escritura de métodos de extensión para agregar nuestra propia funcionalidad personalizada a las consultas LINQ</span><span class="sxs-lookup"><span data-stu-id="ec259-263">writing Extension methods to add our own custom functionality to LINQ queries</span></span>
- <span data-ttu-id="ec259-264">Localización de áreas en nuestro código donde nuestras consultas LINQ pueden tener problemas de rendimiento como la degradación de la velocidad</span><span class="sxs-lookup"><span data-stu-id="ec259-264">locating areas in our code where our LINQ queries might run into performance issues like degraded speed</span></span>
- <span data-ttu-id="ec259-265">Evaluación diligente y diferida en lo que respecta a las consultas LINQ y las implicaciones que podrían tener en el rendimiento de la consulta</span><span class="sxs-lookup"><span data-stu-id="ec259-265">lazy and eager evaluation in regards to LINQ queries and the implications they might have on query performance</span></span>

<span data-ttu-id="ec259-266">Aparte de LINQ, ha aprendido algo sobre una técnica que los magos utilizan para hacer trucos de cartas.</span><span class="sxs-lookup"><span data-stu-id="ec259-266">Aside from LINQ, you learned a bit about a technique magicians use for card tricks.</span></span> <span data-ttu-id="ec259-267">Los magos usan el orden aleatorio Faro porque les permite controlar dónde está cada carta en la baraja.</span><span class="sxs-lookup"><span data-stu-id="ec259-267">Magicians use the Faro shuffle because they can control where every card moves in the deck.</span></span> <span data-ttu-id="ec259-268">Ahora que lo conoce, no se lo estropee a los demás.</span><span class="sxs-lookup"><span data-stu-id="ec259-268">Now that you know, don't spoil it for everyone else!</span></span>

<span data-ttu-id="ec259-269">Para más información sobre LINQ, vea:</span><span class="sxs-lookup"><span data-stu-id="ec259-269">For more information on LINQ, see:</span></span>

- [<span data-ttu-id="ec259-270">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="ec259-270">Language Integrated Query (LINQ)</span></span>](../programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="ec259-271">Introducción a LINQ</span><span class="sxs-lookup"><span data-stu-id="ec259-271">Introduction to LINQ</span></span>](../programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="ec259-272">Operaciones básicas de consulta LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="ec259-272">Basic LINQ Query Operations (C#)</span></span>](../programming-guide/concepts/linq/basic-linq-query-operations.md)
- [<span data-ttu-id="ec259-273">Transformaciones de datos con LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="ec259-273">Data Transformations With LINQ (C#)</span></span>](../programming-guide/concepts/linq/data-transformations-with-linq.md)
- [<span data-ttu-id="ec259-274">Sintaxis de consultas y sintaxis de métodos en LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="ec259-274">Query Syntax and Method Syntax in LINQ (C#)</span></span>](../programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md)
- [<span data-ttu-id="ec259-275">Características de C# compatibles con LINQ</span><span class="sxs-lookup"><span data-stu-id="ec259-275">C# Features That Support LINQ</span></span>](../programming-guide/concepts/linq/features-that-support-linq.md)
