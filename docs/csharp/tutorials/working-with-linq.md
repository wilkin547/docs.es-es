---
title: Trabajar con LINQ
description: En este tutorial se enseña cómo generar secuencias con LINQ, escribir métodos para su uso en consultas LINQ y distinguir entre la evaluación diligente y diferida.
ms.date: 03/28/2017
ms.assetid: 0db12548-82cb-4903-ac88-13103d70aa77
ms.openlocfilehash: e5f9baab13cddfb9e294de1e1a6ce967ccbe0813
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2018
---
# <a name="working-with-linq"></a><span data-ttu-id="a278a-103">Trabajar con LINQ</span><span class="sxs-lookup"><span data-stu-id="a278a-103">Working with LINQ</span></span>

## <a name="introduction"></a><span data-ttu-id="a278a-104">Introducción</span><span class="sxs-lookup"><span data-stu-id="a278a-104">Introduction</span></span>

<span data-ttu-id="a278a-105">Este tutorial le enseña varias características de .NET Core y el lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="a278a-105">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="a278a-106">Aprenderá lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a278a-106">You’ll learn:</span></span>

*   <span data-ttu-id="a278a-107">Cómo generar secuencias con LINQ</span><span class="sxs-lookup"><span data-stu-id="a278a-107">How to generate sequences with LINQ</span></span>
*   <span data-ttu-id="a278a-108">Cómo escribir métodos que pueden utilizarse fácilmente en las consultas LINQ.</span><span class="sxs-lookup"><span data-stu-id="a278a-108">How to write methods that can be easily used in LINQ queries.</span></span>
*   <span data-ttu-id="a278a-109">Cómo distinguir entre la evaluación diligente y diferida.</span><span class="sxs-lookup"><span data-stu-id="a278a-109">How to distinguish between eager and lazy evaluation.</span></span>

<span data-ttu-id="a278a-110">Aprenderá estas técnicas mediante la creación de una aplicación que muestra uno de los conocimientos básicos de cualquier mago: el [orden aleatorio faro](https://en.wikipedia.org/wiki/Faro_shuffle).</span><span class="sxs-lookup"><span data-stu-id="a278a-110">You'll learn these techniques by building an application that demonstrates one of the basic skills of any magician: the [faro shuffle](https://en.wikipedia.org/wiki/Faro_shuffle).</span></span> <span data-ttu-id="a278a-111">En resumen, el orden aleatorio faro es una técnica basada en dividir la baraja exactamente por la mitad; a continuación, el orden aleatorio intercala cada carta de cada mitad de la baraja hasta volver a crear la original.</span><span class="sxs-lookup"><span data-stu-id="a278a-111">Briefly, a faro shuffle is a technique where you split a card deck exactly in half, then the shuffle interleaves each one card from each half to rebuild the original deck.</span></span>

<span data-ttu-id="a278a-112">Los magos usan esta técnica porque cada carta está en una ubicación conocida después de cada orden aleatorio, y el orden sigue un patrón de repetición.</span><span class="sxs-lookup"><span data-stu-id="a278a-112">Magicians use this technique because every card is in a known location after each shuffle, and the order is a repeating pattern.</span></span> 

<span data-ttu-id="a278a-113">Para el propósito sobre el que trata este artículo, resulta divertido ocuparnos de la manipulación de secuencias de datos.</span><span class="sxs-lookup"><span data-stu-id="a278a-113">For our purposes, it is a light hearted look at manipulating sequences of data.</span></span> <span data-ttu-id="a278a-114">La aplicación que se va a crear compilará una baraja y después realizará una secuencia de órdenes aleatorios, escribiendo cada vez la secuencia completa.</span><span class="sxs-lookup"><span data-stu-id="a278a-114">The application you'll build will construct a card deck, and then perform a sequence of shuffles, writing the sequence out each time.</span></span> <span data-ttu-id="a278a-115">También podrá comparar el orden actualizado con el original.</span><span class="sxs-lookup"><span data-stu-id="a278a-115">You'll also compare the updated order to the original order.</span></span>

<span data-ttu-id="a278a-116">Este tutorial consta de varios pasos.</span><span class="sxs-lookup"><span data-stu-id="a278a-116">This tutorial has multiple steps.</span></span> <span data-ttu-id="a278a-117">Después de cada paso, puede ejecutar la aplicación y ver el progreso.</span><span class="sxs-lookup"><span data-stu-id="a278a-117">After each step, you can run the application and see the progress.</span></span> <span data-ttu-id="a278a-118">También puede ver el [ejemplo completo](https://github.com/dotnet/samples/blob/master/csharp/getting-started/console-linq) en el repositorio dotnet/samples de GitHub.</span><span class="sxs-lookup"><span data-stu-id="a278a-118">You can also see the [completed sample](https://github.com/dotnet/samples/blob/master/csharp/getting-started/console-linq) in the dotnet/samples GitHub repository.</span></span> <span data-ttu-id="a278a-119">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="a278a-119">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a278a-120">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a278a-120">Prerequisites</span></span>

<span data-ttu-id="a278a-121">Deberá configurar la máquina para ejecutar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a278a-121">You’ll need to setup your machine to run .NET core.</span></span> <span data-ttu-id="a278a-122">Puede encontrar las instrucciones de instalación en la página de [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="a278a-122">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span> <span data-ttu-id="a278a-123">Puede ejecutar esta aplicación en Windows, Ubuntu Linux, OS X o en un contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="a278a-123">You can run this application on Windows, Ubuntu Linux, OS X or in a Docker container.</span></span> <span data-ttu-id="a278a-124">Deberá instalar su editor de código favorito.</span><span class="sxs-lookup"><span data-stu-id="a278a-124">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="a278a-125">En las siguientes descripciones se usa [Visual Studio Code](https://code.visualstudio.com/), que es un editor multiplataforma de código abierto.</span><span class="sxs-lookup"><span data-stu-id="a278a-125">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="a278a-126">Sin embargo, puede usar las herramientas que le resulten más cómodas.</span><span class="sxs-lookup"><span data-stu-id="a278a-126">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="a278a-127">Crear la aplicación</span><span class="sxs-lookup"><span data-stu-id="a278a-127">Create the Application</span></span>

<span data-ttu-id="a278a-128">El primer paso es crear una nueva aplicación.</span><span class="sxs-lookup"><span data-stu-id="a278a-128">The first step is to create a new application.</span></span> <span data-ttu-id="a278a-129">Abra un símbolo del sistema y cree un nuevo directorio para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a278a-129">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="a278a-130">Conviértalo en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="a278a-130">Make that the current directory.</span></span> <span data-ttu-id="a278a-131">Escriba el comando `dotnet new console` en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="a278a-131">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="a278a-132">Esta acción crea los archivos de inicio para una aplicación básica "Hola a todos".</span><span class="sxs-lookup"><span data-stu-id="a278a-132">This creates the starter files for a basic "Hello World" application.</span></span>

<span data-ttu-id="a278a-133">Si nunca ha usado C# antes, en [este tutorial](console-teleprompter.md) se explica la estructura de un programa con C#.</span><span class="sxs-lookup"><span data-stu-id="a278a-133">If you've never used C# before, [this tutorial](console-teleprompter.md) explains the structure of a C# program.</span></span> <span data-ttu-id="a278a-134">Puede leerlo y después volver aquí para obtener más información sobre LINQ.</span><span class="sxs-lookup"><span data-stu-id="a278a-134">You can read that and then return here to learn more about LINQ.</span></span> 

## <a name="creating-the-data-set"></a><span data-ttu-id="a278a-135">Creación del conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="a278a-135">Creating the Data Set</span></span>

<span data-ttu-id="a278a-136">Comencemos por crear una baraja de cartas.</span><span class="sxs-lookup"><span data-stu-id="a278a-136">Let's start by creating a deck of cards.</span></span> <span data-ttu-id="a278a-137">Para ello, debe usar una consulta LINQ que tenga dos orígenes (uno para los cuatro palos y otro para los valores trece).</span><span class="sxs-lookup"><span data-stu-id="a278a-137">You'll do this using a LINQ query that has two sources (one for the four suits, one for the thirteen values).</span></span> <span data-ttu-id="a278a-138">Podrá combinar esos orígenes en una baraja de 52 cartas.</span><span class="sxs-lookup"><span data-stu-id="a278a-138">You'll combine those sources into a 52 card deck.</span></span> <span data-ttu-id="a278a-139">Una instrucción `Console.WriteLine` dentro de un bucle `foreach` muestra las cartas.</span><span class="sxs-lookup"><span data-stu-id="a278a-139">A `Console.WriteLine` statement inside a `foreach` loop displays the cards.</span></span>

<span data-ttu-id="a278a-140">Aquí está la consulta:</span><span class="sxs-lookup"><span data-stu-id="a278a-140">Here's the query:</span></span>

```csharp
var startingDeck = from s in Suits()
                   from r in Ranks()
                   select new { Suit = s, Rank = r };

foreach (var c in startingDeck)
{
    Console.WriteLine(c);
}
```

<span data-ttu-id="a278a-141">Las cláusulas múltiples `from` generan una salida `SelectMany`, que crea una única secuencia a partir de la combinación de cada elemento de la primera secuencia con cada elemento de la segunda secuencia.</span><span class="sxs-lookup"><span data-stu-id="a278a-141">The multiple `from` clauses produce a `SelectMany`, which creates a single sequence from combining each element in the first sequence with each element in the second sequence.</span></span> <span data-ttu-id="a278a-142">El orden es importante para nuestros propósitos.</span><span class="sxs-lookup"><span data-stu-id="a278a-142">The order is important for our purposes.</span></span> <span data-ttu-id="a278a-143">El primer elemento de la primera secuencia de origen (palos) se combina con cada elemento de la segunda secuencia (valores).</span><span class="sxs-lookup"><span data-stu-id="a278a-143">The first element in the first source sequence (Suits) is combined with every element in the second sequence (Values).</span></span> <span data-ttu-id="a278a-144">Esto genera las trece cartas del primer palo.</span><span class="sxs-lookup"><span data-stu-id="a278a-144">This produces all thirteen cards of first suit.</span></span> <span data-ttu-id="a278a-145">Dicho proceso se repite con cada elemento de la primera secuencia (palos).</span><span class="sxs-lookup"><span data-stu-id="a278a-145">That process is repeated with each element in the first sequence (Suits).</span></span> <span data-ttu-id="a278a-146">El resultado final es una baraja de cartas ordenadas por palos, seguidos de valores.</span><span class="sxs-lookup"><span data-stu-id="a278a-146">The end result is a deck of cards ordered by suits, followed by values.</span></span>

<span data-ttu-id="a278a-147">A continuación, necesita compilar los métodos Suits() y Ranks().</span><span class="sxs-lookup"><span data-stu-id="a278a-147">Next, you'll need to build the Suits() and Ranks() methods.</span></span> <span data-ttu-id="a278a-148">Comencemos con un conjunto muy sencillo de *métodos iteradores* que generan la secuencia como una enumeración de cadenas:</span><span class="sxs-lookup"><span data-stu-id="a278a-148">Let's start with a really simple set of *iterator methods* that generate the sequence as an enumerable of strings:</span></span>

```csharp
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

<span data-ttu-id="a278a-149">Estos dos métodos utilizan la sintaxis `yield return` para generar una secuencia mientras se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="a278a-149">These two methods both utilize the `yield return` syntax to produce a sequence as they run.</span></span> <span data-ttu-id="a278a-150">El compilador crea un objeto que implementa `IEnumerable<T>` y genera la secuencia de cadenas conforme se solicitan.</span><span class="sxs-lookup"><span data-stu-id="a278a-150">The compiler builds an object that implements `IEnumerable<T>` and generates the sequence of strings as they are requested.</span></span>

<span data-ttu-id="a278a-151">Continúe y ejecute el ejemplo que se ha creado en este punto.</span><span class="sxs-lookup"><span data-stu-id="a278a-151">Go ahead and run the sample you've built at this point.</span></span> <span data-ttu-id="a278a-152">Mostrará todas las 52 cartas de la baraja.</span><span class="sxs-lookup"><span data-stu-id="a278a-152">It will display all 52 cards in the deck.</span></span> <span data-ttu-id="a278a-153">Puede ser muy útil ejecutar este ejemplo en un depurador para observar cómo se ejecutan los métodos `Suits()` y `Values()`.</span><span class="sxs-lookup"><span data-stu-id="a278a-153">You may find it very helpful to run this sample under a debugger to observe how the `Suits()` and `Values()` methods execute.</span></span> <span data-ttu-id="a278a-154">Puede ver claramente que cada cadena de cada secuencia se genera solo según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a278a-154">You can clearly see that each string in each sequence is generated only as it is needed.</span></span>

![Ventana de la consola que muestra la aplicación escribiendo 52 cartas](./media/working-with-linq/console.png)

## <a name="manipulating-the-order"></a><span data-ttu-id="a278a-156">Manipulación del orden</span><span class="sxs-lookup"><span data-stu-id="a278a-156">Manipulating the Order</span></span>

<span data-ttu-id="a278a-157">A continuación, se va a crear un método de utilidad que puede llevar a cabo el orden aleatorio.</span><span class="sxs-lookup"><span data-stu-id="a278a-157">Next, let's build a utility method that can perform the shuffle.</span></span> <span data-ttu-id="a278a-158">El primer paso consiste en dividir la baraja en dos.</span><span class="sxs-lookup"><span data-stu-id="a278a-158">The first step is to split the deck in two.</span></span> <span data-ttu-id="a278a-159">Los métodos `Take()` y `Skip()` que forman parte de las API de LINQ ofrecen esa característica:</span><span class="sxs-lookup"><span data-stu-id="a278a-159">The `Take()` and `Skip()` methods that are part of the LINQ APIs provide that feature for us:</span></span>

```csharp
var top = startingDeck.Take(26);
var bottom = startingDeck.Skip(26);
```

<span data-ttu-id="a278a-160">El método de orden aleatorio no existe en la biblioteca estándar, por lo que tendrá que escribir el suyo propio.</span><span class="sxs-lookup"><span data-stu-id="a278a-160">The shuffle method doesn't exist in the standard library, so you'll have to write your own.</span></span> <span data-ttu-id="a278a-161">Este nuevo método muestra varias técnicas que va a utilizar con programas basados en LINQ, cuyas partes se van a explicar en distintos pasos.</span><span class="sxs-lookup"><span data-stu-id="a278a-161">This new method illustrates several techniques that you'll use with LINQ-based programs, so let's explain each part of the method in steps.</span></span>

<span data-ttu-id="a278a-162">La firma del método crea un *método de extensión*:</span><span class="sxs-lookup"><span data-stu-id="a278a-162">The signature for the method creates an *extension method*:</span></span>

```csharp
public static IEnumerable<T> InterleaveSequenceWith<T>
    (this IEnumerable<T> first, IEnumerable<T> second)
```

<span data-ttu-id="a278a-163">Un método de extensión es un *método estático* para un fin especial.</span><span class="sxs-lookup"><span data-stu-id="a278a-163">An extension method is a special purpose *static method.*</span></span> <span data-ttu-id="a278a-164">Puede ver la incorporación del modificador `this` del primer argumento al método.</span><span class="sxs-lookup"><span data-stu-id="a278a-164">You can see the addition of the `this` modifier on the first argument to the method.</span></span> <span data-ttu-id="a278a-165">Esto significa que se llama al método como si fuese un método de miembro del tipo del primer argumento.</span><span class="sxs-lookup"><span data-stu-id="a278a-165">That means you call the method as though it were a member method of the type of the first argument.</span></span>

<span data-ttu-id="a278a-166">Los métodos de extensión se pueden declarar únicamente dentro de las clases `static`, así que se va a crear una nueva clase estática llamada `extensions` para esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="a278a-166">Extension methods can be declared only inside `static` classes, so let's create a new static class called `extensions` for this functionality.</span></span> <span data-ttu-id="a278a-167">A medida que avance en este tutorial, va a crear más métodos de extensión, que se colocarán en la misma clase.</span><span class="sxs-lookup"><span data-stu-id="a278a-167">You'll add more extension methods as you continue this tutorial, and those will be placed in the same class.</span></span>

<span data-ttu-id="a278a-168">Esta declaración de método también sigue una expresión estándar donde los tipos de entrada y salida son `IEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="a278a-168">This method declaration also follows a standard idiom where the input and output types are `IEnumerable<T>`.</span></span> <span data-ttu-id="a278a-169">Dicha práctica permite que los métodos LINQ se encadenen entre sí para realizar consultas más complejas.</span><span class="sxs-lookup"><span data-stu-id="a278a-169">That practice enables LINQ methods to be chained together to perform more complex queries.</span></span>

```csharp
using System.Collections.Generic;

namespace LinqFaroShuffle
{
    public static class Extensions
    {
        public static IEnumerable<T> InterleaveSequenceWith<T>
            (this IEnumerable<T> first, IEnumerable<T> second)
        {
            // implementation coming.
        }
    }
}
```

<span data-ttu-id="a278a-170">Debe enumerar ambas secuencias al mismo tiempo, de tal forma que se intercalarán los elementos y se creará un objeto.</span><span class="sxs-lookup"><span data-stu-id="a278a-170">You will be enumerating both sequences at once, interleaving the elements, and creating one object.</span></span>  <span data-ttu-id="a278a-171">Escribir un método LINQ que funciona con dos secuencias requiere que comprenda cómo funciona `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="a278a-171">Writing a LINQ method that works with two sequences requires that you understand how `IEnumerable` works.</span></span>

<span data-ttu-id="a278a-172">La interfaz `IEnumerable` tiene un método: `GetEnumerator()`.</span><span class="sxs-lookup"><span data-stu-id="a278a-172">The `IEnumerable` interface has one method: `GetEnumerator()`.</span></span> <span data-ttu-id="a278a-173">El objeto devuelto por `GetEnumerator()` tiene un método para desplazarse al siguiente elemento, así como una propiedad que recupera el elemento actual de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="a278a-173">The object returned by `GetEnumerator()` has a method to move to the next element, and a property that retrieves the current element in the sequence.</span></span> <span data-ttu-id="a278a-174">Utilizará estos dos miembros para enumerar la colección y devolver los elementos.</span><span class="sxs-lookup"><span data-stu-id="a278a-174">You will use those two members to enumerate the collection and return the elements.</span></span> <span data-ttu-id="a278a-175">Este método de intercalación será un método iterador, por lo que en lugar de crear una colección y devolverla, usará la sintaxis `yield return` anterior.</span><span class="sxs-lookup"><span data-stu-id="a278a-175">This Interleave method will be an iterator method, so instead of building a collection and returning the collection, you'll use the `yield return` syntax shown above.</span></span> 

<span data-ttu-id="a278a-176">A continuación se muestra la implementación de ese método:</span><span class="sxs-lookup"><span data-stu-id="a278a-176">Here's the implementation of that method:</span></span>

[!CODE-csharp[InterleaveSequenceWith](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet1)]

<span data-ttu-id="a278a-177">Ahora que ha escrito este método, vuelva al método `Main` y ordene la baraja aleatoriamente una vez:</span><span class="sxs-lookup"><span data-stu-id="a278a-177">Now that you've written this method, go back to the `Main` method and shuffle the deck once:</span></span>

```csharp
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

## <a name="comparisons"></a><span data-ttu-id="a278a-178">Comparaciones</span><span class="sxs-lookup"><span data-stu-id="a278a-178">Comparisons</span></span>

<span data-ttu-id="a278a-179">Se va a ver cuántos órdenes aleatorios se necesitan para devolver la baraja a su orden original.</span><span class="sxs-lookup"><span data-stu-id="a278a-179">Let's see how many shuffles it takes to set the deck back to its original order.</span></span> <span data-ttu-id="a278a-180">Debe escribir un método que determine si dos secuencias son iguales.</span><span class="sxs-lookup"><span data-stu-id="a278a-180">You'll need to write a method that determines if two sequences are equal.</span></span> <span data-ttu-id="a278a-181">Cuando ya disponga del método, debe colocar el código que ordena la baraja aleatoriamente en un bucle y comprobarlo para ver cuándo la baraja vuelve a tener su orden original.</span><span class="sxs-lookup"><span data-stu-id="a278a-181">After you have that method, you'll need to place the code that shuffles the deck in a loop, and check to see when the deck is back in order.</span></span>

<span data-ttu-id="a278a-182">Debe ser sencillo escribir un método para determinar si las dos secuencias son iguales.</span><span class="sxs-lookup"><span data-stu-id="a278a-182">Writing a method to determine if the two sequences are equal should be straightforward.</span></span> <span data-ttu-id="a278a-183">Presenta una estructura similar al método que se escribió para ordenar la baraja aleatoriamente.</span><span class="sxs-lookup"><span data-stu-id="a278a-183">It's a similar structure to the method you wrote to shuffle the deck.</span></span> <span data-ttu-id="a278a-184">Solo esta vez, en lugar de devolver el resultado de cada elemento, se compararán los elementos coincidentes de cada secuencia.</span><span class="sxs-lookup"><span data-stu-id="a278a-184">Only this time, instead of yield returning each element, you'll compare the matching elements of each sequence.</span></span> <span data-ttu-id="a278a-185">Después de que se haya enumerado la secuencia completa, si cada elemento coincide, las secuencias son las mismas:</span><span class="sxs-lookup"><span data-stu-id="a278a-185">When the entire sequence has been enumerated, if every element matches, the sequences are the same:</span></span>

[!CODE-csharp[SequenceEquals](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet2)]

<span data-ttu-id="a278a-186">Esto muestra una segunda expresión LINQ: métodos de terminales.</span><span class="sxs-lookup"><span data-stu-id="a278a-186">This shows a second Linq idiom: terminal methods.</span></span> <span data-ttu-id="a278a-187">Adoptan una secuencia como entrada (o, en este caso, dos secuencias) y devuelven un único valor escalar.</span><span class="sxs-lookup"><span data-stu-id="a278a-187">They take a sequence as input (or in this case, two sequences), and return a single scalar value.</span></span> <span data-ttu-id="a278a-188">Estos métodos, cuando se utilizan, son siempre el método final de una consulta.</span><span class="sxs-lookup"><span data-stu-id="a278a-188">These methods, when they are used, are always the final method of a query.</span></span> <span data-ttu-id="a278a-189">(Por lo tanto, el nombre).</span><span class="sxs-lookup"><span data-stu-id="a278a-189">(Hence the name).</span></span> 

<span data-ttu-id="a278a-190">Puede ver esto en acción cuando lo usa para determinar cuándo la baraja vuelve a tener su orden original.</span><span class="sxs-lookup"><span data-stu-id="a278a-190">You can see this in action when you use it to determine when the deck is back in its original order.</span></span> <span data-ttu-id="a278a-191">Coloque el código de orden aleatorio dentro de un bucle y deténgalo cuando la secuencia vuelva a su orden original, mediante la aplicación del método `SequenceEquals()`.</span><span class="sxs-lookup"><span data-stu-id="a278a-191">Put the shuffle code inside a loop, and stop when the sequence is back in its original order by applying the `SequenceEquals()` method.</span></span> <span data-ttu-id="a278a-192">Puede observar que siempre se tratará del método final de cualquier consulta, porque devuelve un único valor en lugar de una secuencia:</span><span class="sxs-lookup"><span data-stu-id="a278a-192">You can see it would always be the final method in any query, because it returns a single value instead of a sequence:</span></span>

```csharp
var times = 0;
var shuffle = startingDeck;

do
{
    shuffle = shuffle.Take(26).InterleaveSequenceWith(shuffle.Skip(26));

    foreach (var c in shuffle)
    {
        Console.WriteLine(c);
    }

    Console.WriteLine();
    times++;
} while (!startingDeck.SequenceEquals(shuffle));

Console.WriteLine(times);
```

<span data-ttu-id="a278a-193">Ejecute el ejemplo y observe cómo la baraja se reorganiza en cada orden aleatorio, hasta que vuelva a su configuración original después de 8 iteraciones.</span><span class="sxs-lookup"><span data-stu-id="a278a-193">Run the sample, and see how the deck rearranges on each shuffle, until it returns to its original configuration after 8 iterations.</span></span>

## <a name="optimizations"></a><span data-ttu-id="a278a-194">Optimizaciones</span><span class="sxs-lookup"><span data-stu-id="a278a-194">Optimizations</span></span>

<span data-ttu-id="a278a-195">El ejemplo creado hasta el momento se ejecuta *en orden no aleatorio*, donde las cartas superiores e inferiores son las mismas en cada ejecución.</span><span class="sxs-lookup"><span data-stu-id="a278a-195">The sample you've built so far executes an *out shuffle*, where the top and bottom cards stay the same on each run.</span></span> <span data-ttu-id="a278a-196">Se va a realizar un cambio y realice una ejecución *en orden no aleatorio*, donde las 52 cartas cambian de posición.</span><span class="sxs-lookup"><span data-stu-id="a278a-196">Let's make one change, and run an *in shuffle*, where all 52 cards change position.</span></span> <span data-ttu-id="a278a-197">Si se trata de un orden aleatorio, intercale la baraja de tal forma que la primera carta de la mitad inferior sea la primera carta de la baraja.</span><span class="sxs-lookup"><span data-stu-id="a278a-197">For an in shuffle, you interleave the deck so that the first card in the bottom half becomes the first card in the deck.</span></span> <span data-ttu-id="a278a-198">Esto significa que la última carta de la mitad superior será la carta inferior.</span><span class="sxs-lookup"><span data-stu-id="a278a-198">That means the last card in the top half becomes the bottom card.</span></span> <span data-ttu-id="a278a-199">Se trata solo de un cambio de línea.</span><span class="sxs-lookup"><span data-stu-id="a278a-199">That's just a one line change.</span></span> <span data-ttu-id="a278a-200">Actualice la llamada al orden aleatorio para cambiar el orden de las mitades superior e inferior de la baraja:</span><span class="sxs-lookup"><span data-stu-id="a278a-200">Update the call to shuffle to change the order of the top and bottom halves of the deck:</span></span>

```csharp
shuffle = shuffle.Skip(26).InterleaveSequenceWith(shuffle.Take(26));
```

<span data-ttu-id="a278a-201">Vuelva a ejecutar el programa y verá que, para que la baraja se reordene, se necesitan 52 iteraciones.</span><span class="sxs-lookup"><span data-stu-id="a278a-201">Run the program again, and you'll see that it takes 52 iterations for the deck to reorder itself.</span></span> <span data-ttu-id="a278a-202">También empezará a observar algunas degradaciones graves de rendimiento a medida que el programa continúa en ejecución.</span><span class="sxs-lookup"><span data-stu-id="a278a-202">You'll also start to notice some serious performance degradations as the program continues to run.</span></span>

<span data-ttu-id="a278a-203">Esto se debe a varias razones.</span><span class="sxs-lookup"><span data-stu-id="a278a-203">There are a number of reasons for this.</span></span> <span data-ttu-id="a278a-204">Vamos a tratar una de las causas principales: un uso ineficaz de la *evaluación diferida*.</span><span class="sxs-lookup"><span data-stu-id="a278a-204">Let's tackle one of the major causes: inefficient use of *lazy evaluation*.</span></span>

<span data-ttu-id="a278a-205">Las consultas LINQ se evalúan de forma diferida.</span><span class="sxs-lookup"><span data-stu-id="a278a-205">LINQ queries are evaluated lazily.</span></span> <span data-ttu-id="a278a-206">Las secuencias se generan solo a medida que se solicitan los elementos.</span><span class="sxs-lookup"><span data-stu-id="a278a-206">The sequences are generated only as the elements are requested.</span></span> <span data-ttu-id="a278a-207">Normalmente, es una ventaja importante de LINQ.</span><span class="sxs-lookup"><span data-stu-id="a278a-207">Usually, that's a major benefit of LINQ.</span></span> <span data-ttu-id="a278a-208">Sin embargo, en un uso como el que hace este programa, se produce un aumento exponencial del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a278a-208">However, in a use such as this program, this causes exponential growth in execution time.</span></span>

<span data-ttu-id="a278a-209">La baraja original se ha generado mediante una consulta LINQ.</span><span class="sxs-lookup"><span data-stu-id="a278a-209">The original deck was generated using a LINQ query.</span></span> <span data-ttu-id="a278a-210">Cada orden aleatorio se genera mediante la realización de tres consultas LINQ sobre la baraja anterior.</span><span class="sxs-lookup"><span data-stu-id="a278a-210">Each shuffle is generated by performing three LINQ queries on the previous deck.</span></span> <span data-ttu-id="a278a-211">Todas se realizan de forma diferida.</span><span class="sxs-lookup"><span data-stu-id="a278a-211">All these are performed lazily.</span></span> <span data-ttu-id="a278a-212">Eso también significa que se vuelven a llevar a cabo cada vez que se solicita la secuencia.</span><span class="sxs-lookup"><span data-stu-id="a278a-212">That also means they are performed again each time the sequence is requested.</span></span> <span data-ttu-id="a278a-213">Cuando llegue a la iteración número 52, habrá regenerado la baraja original demasiadas veces.</span><span class="sxs-lookup"><span data-stu-id="a278a-213">By the time you get to the 52nd iteration, you're regenerating the original deck many, many times.</span></span> <span data-ttu-id="a278a-214">Se va a escribir un registro para mostrar este comportamiento.</span><span class="sxs-lookup"><span data-stu-id="a278a-214">Let's write a log to demonstrate this behavior.</span></span> <span data-ttu-id="a278a-215">A continuación, podrá corregirlo.</span><span class="sxs-lookup"><span data-stu-id="a278a-215">Then, you'll fix it.</span></span>

<span data-ttu-id="a278a-216">Se trata de un método de registro que se puede anexar a una consulta para marcar que esta se ha ejecutado.</span><span class="sxs-lookup"><span data-stu-id="a278a-216">Here's a log method that can be appended to any query to mark that the query executed.</span></span>

[!CODE-csharp[LogQuery](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet3)]

<span data-ttu-id="a278a-217">A continuación, instrumente la definición de cada consulta con un mensaje de registro:</span><span class="sxs-lookup"><span data-stu-id="a278a-217">Next, instrument the definition of each query with a log message:</span></span>

```csharp
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
        /*
        shuffle = shuffle.Take(26)
            .LogQuery("Top Half")
            .InterleaveSequenceWith(shuffle.Skip(26)
            .LogQuery("Bottom Half"))
            .LogQuery("Shuffle");
        */

        shuffle = shuffle.Skip(26)
            .LogQuery("Bottom Half")
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

<span data-ttu-id="a278a-218">Observe que no se genera un registro cada vez que accede a una consulta.</span><span class="sxs-lookup"><span data-stu-id="a278a-218">Notice that you don't log every time you access a query.</span></span> <span data-ttu-id="a278a-219">El registro solo se genera cuando crea la consulta original.</span><span class="sxs-lookup"><span data-stu-id="a278a-219">You log only when you create the original query.</span></span> <span data-ttu-id="a278a-220">El programa todavía tarda mucho tiempo en ejecutarse, pero ahora puede ver por qué.</span><span class="sxs-lookup"><span data-stu-id="a278a-220">The program still takes a long time to run, but now you can see why.</span></span> <span data-ttu-id="a278a-221">Si se le agota la paciencia al ejecutar el orden aleatorio interno con los registros activados, cambie de nuevo al orden aleatorio externo.</span><span class="sxs-lookup"><span data-stu-id="a278a-221">If you run out of patience running the inner shuffle with logging turned on, switch back to the outer shuffle.</span></span> <span data-ttu-id="a278a-222">Aún puede ver los efectos de la evaluación diferida.</span><span class="sxs-lookup"><span data-stu-id="a278a-222">You'll still see the lazy evaluation effects.</span></span> <span data-ttu-id="a278a-223">En una ejecución, ejecuta 2592 consultas, incluida toda la generación de palos y valores.</span><span class="sxs-lookup"><span data-stu-id="a278a-223">In one run, it executes 2592 queries, including all the value and suit generation.</span></span>

<span data-ttu-id="a278a-224">Hay una manera fácil de actualizar este programa para evitar todas esas ejecuciones.</span><span class="sxs-lookup"><span data-stu-id="a278a-224">There is an easy way to update this program to avoid all those executions.</span></span> <span data-ttu-id="a278a-225">Existen los métodos LINQ `ToArray()` y `ToList()` que hacen que la consulta se ejecute y almacenan los resultados en una matriz o en una lista, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="a278a-225">There are LINQ methods `ToArray()` and `ToList()` that cause the query to run, and store the results in an array or a list, respectively.</span></span> <span data-ttu-id="a278a-226">Utilice estos métodos para almacenar en caché los resultados de una consulta, en lugar de volver a ejecutar la consulta de origen.</span><span class="sxs-lookup"><span data-stu-id="a278a-226">You use these methods to cache the data results of a query rather than execute the source query again.</span></span>  <span data-ttu-id="a278a-227">Anexe las consultas que generan las barajas con una llamada a `ToArray()` y vuelva a ejecutar la consulta:</span><span class="sxs-lookup"><span data-stu-id="a278a-227">Append the queries that generate the card decks with a call to `ToArray()` and run the query again:</span></span>

[!CODE-csharp[Main](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet1)]

<span data-ttu-id="a278a-228">Vuelva a realizar la ejecución, y el orden aleatorio externo baja a 30 consultas.</span><span class="sxs-lookup"><span data-stu-id="a278a-228">Run again, and the outer shuffle is down to 30 queries.</span></span> <span data-ttu-id="a278a-229">Ejecute de nuevo con el orden aleatorio interno y verá mejoras similares.</span><span class="sxs-lookup"><span data-stu-id="a278a-229">Run again with the inner shuffle and you'll see similar improvements.</span></span> <span data-ttu-id="a278a-230">(Ahora ejecuta 162 consultas).</span><span class="sxs-lookup"><span data-stu-id="a278a-230">(It now executes 162 queries).</span></span>

<span data-ttu-id="a278a-231">No interprete este ejemplo incorrectamente al pensar que todas las consultas deben ejecutarse de manera diligente.</span><span class="sxs-lookup"><span data-stu-id="a278a-231">Don't misinterpret this example by thinking that all queries should run eagerly.</span></span> <span data-ttu-id="a278a-232">Este ejemplo está diseñado para resaltar los casos de uso en que la evaluación diferida puede generar dificultades de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="a278a-232">This example is designed to highlight the use cases where lazy evaluation can cause performance difficulties.</span></span> <span data-ttu-id="a278a-233">Eso se debe a que cada nueva disposición de la baraja de cartas se crea a partir de la disposición anterior.</span><span class="sxs-lookup"><span data-stu-id="a278a-233">That's because each new arrangement of the deck of cards is built from the previous arrangement.</span></span> <span data-ttu-id="a278a-234">La evaluación diferida supone que cada nueva configuración de la baraja se realiza a partir de la baraja original, incluso con la ejecución del código que crea el elemento `startingDeck`.</span><span class="sxs-lookup"><span data-stu-id="a278a-234">Using lazy evaluation means each new deck configuration is built from the original deck, even executing the code that built the `startingDeck`.</span></span> <span data-ttu-id="a278a-235">Esto conlleva una gran cantidad de trabajo adicional.</span><span class="sxs-lookup"><span data-stu-id="a278a-235">That causes a large amount of extra work.</span></span> 

<span data-ttu-id="a278a-236">En la práctica, algunos algoritmos se ejecutan mucho mejor con la evaluación diligente y otros, con la evaluación diferida.</span><span class="sxs-lookup"><span data-stu-id="a278a-236">In practice, some algorithms run much better using eager evaluation, and others run much better using lazy evaluation.</span></span> <span data-ttu-id="a278a-237">(En general, la evaluación diferida es una opción mucho más conveniente cuando el origen de datos es un proceso independiente, como un motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="a278a-237">(In general, lazy evaluation is a much better choice when the data source is a separate process, like a database engine.</span></span> <span data-ttu-id="a278a-238">En esos casos, la evaluación diferida permite realizar consultas más complejas para ejecutarlas solo con un recorrido de ida y vuelta en el procesamiento de la base de datos). LINQ permite realizar la evaluación diferida y diligente.</span><span class="sxs-lookup"><span data-stu-id="a278a-238">In those cases, lazy evaluation enables more complex queries to execute only one round trip to the database process.) LINQ enables both lazy and eager evaluation.</span></span> <span data-ttu-id="a278a-239">Piénselo y elija la mejor opción.</span><span class="sxs-lookup"><span data-stu-id="a278a-239">Measure, and pick the best choice.</span></span>

## <a name="preparing-for-new-features"></a><span data-ttu-id="a278a-240">Preparación de las nuevas características</span><span class="sxs-lookup"><span data-stu-id="a278a-240">Preparing for New Features</span></span>

<span data-ttu-id="a278a-241">El código que ha escrito para este ejemplo es un ejemplo de creación de un prototipo sencillo que realiza el trabajo.</span><span class="sxs-lookup"><span data-stu-id="a278a-241">The code you've written for this sample is an example of creating a simple prototype that does the job.</span></span> <span data-ttu-id="a278a-242">Se trata de una manera excelente de explorar un espacio de problemas y, para muchas características, puede ser la mejor solución permanente.</span><span class="sxs-lookup"><span data-stu-id="a278a-242">This is a great way to explore a problem space, and for many features, it may be the best permanent solution.</span></span> <span data-ttu-id="a278a-243">Ha aprovechado *tipos anónimos* para las cartas, y cada carta se representa mediante cadenas.</span><span class="sxs-lookup"><span data-stu-id="a278a-243">You've leveraged *anonymous types* for the cards, and each card is represented by strings.</span></span>

<span data-ttu-id="a278a-244">Los *tipos anónimos* ofrecen numerosas ventajas de productividad.</span><span class="sxs-lookup"><span data-stu-id="a278a-244">*Anonymous Types* have many productivity advantages.</span></span> <span data-ttu-id="a278a-245">No es necesario definir una clase para representar el almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="a278a-245">You don't need to define a class yourself to represent the storage.</span></span> <span data-ttu-id="a278a-246">El compilador genera el tipo.</span><span class="sxs-lookup"><span data-stu-id="a278a-246">The compiler generates the type for you.</span></span> <span data-ttu-id="a278a-247">El tipo generado por el compilador usa muchos de los procedimientos recomendados para objetos de datos sencillos.</span><span class="sxs-lookup"><span data-stu-id="a278a-247">The compiler generated type utilizes many of the best practices for simple data objects.</span></span> <span data-ttu-id="a278a-248">Es *inmutable*, lo que significa que no se pueden cambiar ninguna de sus propiedades después de que se haya construido.</span><span class="sxs-lookup"><span data-stu-id="a278a-248">It's *immutable*, meaning that none of its properties can be changed after it has been constructed.</span></span> <span data-ttu-id="a278a-249">Los tipos anónimos son internos a un ensamblado, por lo que no se ven como parte de la API pública de ese ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a278a-249">Anonymous types are internal to an assembly, so they aren't seen as part of the public API for that assembly.</span></span> <span data-ttu-id="a278a-250">Los tipos anónimos también contienen una invalidación del método `ToString()` que devuelve una cadena con formato con cada uno de los valores.</span><span class="sxs-lookup"><span data-stu-id="a278a-250">Anonymous types also contain an override of the `ToString()` method that returns a formatted string with each of the values.</span></span>

<span data-ttu-id="a278a-251">Los tipos anónimos también tienen desventajas.</span><span class="sxs-lookup"><span data-stu-id="a278a-251">Anonymous types also have disadvantages.</span></span> <span data-ttu-id="a278a-252">No tienen nombres accesibles, por lo que no puede utilizarlos como argumentos o valores devueltos.</span><span class="sxs-lookup"><span data-stu-id="a278a-252">They don't have accessible names, so you can't use them as return values or arguments.</span></span> <span data-ttu-id="a278a-253">Observará que los métodos anteriores que usan estos tipos anónimos son métodos genéricos.</span><span class="sxs-lookup"><span data-stu-id="a278a-253">You'll notice that any methods above that used these anonymous types are generic methods.</span></span> <span data-ttu-id="a278a-254">La invalidación de `ToString()` puede no ser la opción más conveniente a medida que la aplicación incorpora más características.</span><span class="sxs-lookup"><span data-stu-id="a278a-254">The override of `ToString()` may not be what you want as the application grows more features.</span></span> 

<span data-ttu-id="a278a-255">El ejemplo también utiliza cadenas para el palo y la clasificación de cada carta.</span><span class="sxs-lookup"><span data-stu-id="a278a-255">The sample also uses strings for the suit and the rank of each card.</span></span> <span data-ttu-id="a278a-256">Se trata de un ejemplo de amplio alcance.</span><span class="sxs-lookup"><span data-stu-id="a278a-256">That's quite open ended.</span></span> <span data-ttu-id="a278a-257">El sistema de tipos de C# facilita la escritura de un código mejor, aprovechando los tipos `enum` para esos valores.</span><span class="sxs-lookup"><span data-stu-id="a278a-257">The C# type system can help us make better code, by leveraging `enum` types for those values.</span></span>

<span data-ttu-id="a278a-258">Empieza con los palos.</span><span class="sxs-lookup"><span data-stu-id="a278a-258">Start with the suits.</span></span> <span data-ttu-id="a278a-259">Este es el momento perfecto para usar `enum`:</span><span class="sxs-lookup"><span data-stu-id="a278a-259">This is a perfect time to use an `enum`:</span></span>

[!CODE-csharp[Suit enum](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet2)]

<span data-ttu-id="a278a-260">El método `Suits()` también cambia el tipo y la implementación:</span><span class="sxs-lookup"><span data-stu-id="a278a-260">The `Suits()` method also changes type and implementation:</span></span>

[!CODE-csharp[Suit IEnumerable](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet4)]

<span data-ttu-id="a278a-261">A continuación, realice los mismos cambios con la clasificación de las cartas:</span><span class="sxs-lookup"><span data-stu-id="a278a-261">Next, do the same change with the Rank of the cards:</span></span>

[!CODE-csharp[Rank enum](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet3)]

<span data-ttu-id="a278a-262">Y el método que las genera:</span><span class="sxs-lookup"><span data-stu-id="a278a-262">And the method that generates them:</span></span>

[!CODE-csharp[Rank IEnumerable](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet5)]

<span data-ttu-id="a278a-263">Para terminar, se va a crear un tipo para representar la carta, en lugar de depender de un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="a278a-263">As one final cleanup, let's make a type to represent the card, instead of relying on an anonymous type.</span></span> <span data-ttu-id="a278a-264">Los tipos anónimos son excelentes para tipos ligeros locales, pero, en este ejemplo, el juego de naipes es uno de los principales conceptos.</span><span class="sxs-lookup"><span data-stu-id="a278a-264">Anonymous types are great for lightweight, local types, but in this example, the playing card is one of the main concepts.</span></span> <span data-ttu-id="a278a-265">Debe ser un tipo concreto.</span><span class="sxs-lookup"><span data-stu-id="a278a-265">It should be a concrete type.</span></span>

[!CODE-csharp[PlayingCard](../../../samples/csharp/getting-started/console-linq/playingcard.cs?name=snippet1)]

<span data-ttu-id="a278a-266">Este tipo utiliza *propiedades autoimplementadas de solo lectura* que se establece en el constructor y, por tanto, no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="a278a-266">This type uses *auto-implemented read-only properties* which are set in the constructor, and then cannot be modified.</span></span> <span data-ttu-id="a278a-267">También usa la nueva característica de [interpolación de cadena](../language-reference/tokens/interpolated.md) que simplifica la salida de la cadena de formato.</span><span class="sxs-lookup"><span data-stu-id="a278a-267">It also makes use of the [string interpolation](../language-reference/tokens/interpolated.md) feature that makes it easier to format string output.</span></span>

<span data-ttu-id="a278a-268">Actualice la consulta que genera la baraja original para usar el nuevo tipo:</span><span class="sxs-lookup"><span data-stu-id="a278a-268">Update the query that generates the starting deck to use the new type:</span></span>

```csharp
var startingDeck = (from s in Suits().LogQuery("Suit Generation")
                    from r in Ranks().LogQuery("Value Generation")
                    select new PlayingCard(s, r))
                    .LogQuery("Starting Deck")
                    .ToArray();
```

<span data-ttu-id="a278a-269">Realice la compilación y vuelva a ejecutarla.</span><span class="sxs-lookup"><span data-stu-id="a278a-269">Compile and run again.</span></span> <span data-ttu-id="a278a-270">La salida está un poco más limpia, y el código es algo más claro y puede extenderse con más facilidad.</span><span class="sxs-lookup"><span data-stu-id="a278a-270">The output is a little cleaner, and the code is a bit more clear and can be extended more easily.</span></span>

## <a name="conclusion"></a><span data-ttu-id="a278a-271">Conclusión</span><span class="sxs-lookup"><span data-stu-id="a278a-271">Conclusion</span></span>

<span data-ttu-id="a278a-272">En este ejemplo se han mostrado algunos de los métodos usados en LINQ, como la forma de crear métodos propios que pueden usarse con facilidad con código habilitado para LINQ.</span><span class="sxs-lookup"><span data-stu-id="a278a-272">This sample showed you some of the methods used in LINQ, how to create your own methods that will be easily used with LINQ enabled code.</span></span> <span data-ttu-id="a278a-273">También se presentan las diferencias entre la evaluación diligente y diferida, y el efecto que puede tener la decisión en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="a278a-273">It also showed you the differences between lazy and eager evaluation, and the effect that decision can have on performance.</span></span>

<span data-ttu-id="a278a-274">Ha obtenido un poco de información sobre una técnica de magia.</span><span class="sxs-lookup"><span data-stu-id="a278a-274">You learned a bit about one magician's technique.</span></span> <span data-ttu-id="a278a-275">Los magos usan la mezcla faro porque les permite controlar dónde está cada carta en la baraja.</span><span class="sxs-lookup"><span data-stu-id="a278a-275">Magicians use the faro shuffle because they can control where every card moves in the deck.</span></span> <span data-ttu-id="a278a-276">En algunos trucos, el mago pide a un miembro de la audiencia que coloque una carta en la parte superior de la baraja, y la mezcla en orden aleatorio durante algunos minutos, pero puede controlar dónde se encuentra la carta en cuestión.</span><span class="sxs-lookup"><span data-stu-id="a278a-276">In some tricks, the magician has an audience member place a card on top of the deck, and shuffles a few times, knowing where that card goes.</span></span> <span data-ttu-id="a278a-277">En otras ilusiones, es necesario organizar la baraja de una forma determinada.</span><span class="sxs-lookup"><span data-stu-id="a278a-277">Other illusions require the deck set a certain way.</span></span> <span data-ttu-id="a278a-278">Un mago debe organizar la baraja antes de realizar el truco.</span><span class="sxs-lookup"><span data-stu-id="a278a-278">A magician will set the deck prior to performing the trick.</span></span> <span data-ttu-id="a278a-279">Después, mezclará la baraja en orden aleatorio 5 veces usando un orden aleatorio externo.</span><span class="sxs-lookup"><span data-stu-id="a278a-279">Then she will shuffle the deck 5 times using an outer shuffle.</span></span> <span data-ttu-id="a278a-280">En el escenario, el mago puede mostrar qué aspecto tiene una baraja aleatoria, ordenarla aleatoriamente 3 veces más y organizar la baraja exactamente como lo desea.</span><span class="sxs-lookup"><span data-stu-id="a278a-280">On stage, she can show what looks like a random deck, shuffle it 3 more times, and have the deck set exactly how she wants.</span></span>
