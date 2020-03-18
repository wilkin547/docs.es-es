---
title: Delegados y expresiones lambda
description: Obtenga información sobre cómo los delegados definen un tipo, que especifica una firma de método determinada, que se puede llamar directamente o pasar a otro método y llamar.
author: richlander
ms.author: wiwagn
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: fe2e4b4c-6483-4106-a4b4-a33e2e306591
ms.openlocfilehash: 0abcc73e31eab89c422513acf778bc8bd092e788
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "75345553"
---
# <a name="delegates-and-lambdas"></a><span data-ttu-id="3a3cf-103">Delegados y expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="3a3cf-103">Delegates and lambdas</span></span>

<span data-ttu-id="3a3cf-104">Los delegados definen un tipo, que especifica una firma de método concreta.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-104">Delegates define a type, which specify a particular method signature.</span></span> <span data-ttu-id="3a3cf-105">Se puede asignar un método (estático o de instancia) que satisfaga esta firma a una variable de ese tipo y luego llamarlo directamente (con los argumentos adecuados) o pasarlo como argumento a otro método y después llamarlo.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-105">A method (static or instance) that satisfies this signature can be assigned to a variable of that type, then called directly (with the appropriate arguments) or passed as an argument itself to another method and then called.</span></span> <span data-ttu-id="3a3cf-106">El siguiente ejemplo muestra el uso de delegados.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-106">The following example demonstrates delegate use.</span></span>

```csharp
using System;
using System.Linq;

public class Program
{
    public delegate string Reverse(string s);

    static string ReverseString(string s)
    {
        return new string(s.Reverse().ToArray());
    }

    static void Main(string[] args)
    {
        Reverse rev = ReverseString;

        Console.WriteLine(rev("a string"));
    }
}
```

* <span data-ttu-id="3a3cf-107">En la línea `public delegate string Reverse(string s);` se crea un tipo delegado de una firma determinada, en este caso un método que toma un parámetro de cadena y luego devuelve un parámetro de cadena.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-107">The `public delegate string Reverse(string s);` line creates a delegate type of a certain signature, in this case a method that takes a string parameter and then returns a string parameter.</span></span>
* <span data-ttu-id="3a3cf-108">El método `static string ReverseString(string s)`, que tiene exactamente la misma firma que el tipo delegado definido, implementa el delegado.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-108">The `static string ReverseString(string s)` method, which has the exact same signature as the defined delegate type, implements the delegate.</span></span>
* <span data-ttu-id="3a3cf-109">En la línea `Reverse rev = ReverseString;` se muestra que se puede asignar un método a una variable del tipo de delegado correspondiente.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-109">The `Reverse rev = ReverseString;` line shows that you can assign a method to a variable of the corresponding delegate type.</span></span>
* <span data-ttu-id="3a3cf-110">En la línea `Console.WriteLine(rev("a string"));` se muestra cómo se usa una variable de un tipo de delegado para invocar al delegado.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-110">The `Console.WriteLine(rev("a string"));` line demonstrates how to use a variable of a delegate type to invoke the delegate.</span></span>

<span data-ttu-id="3a3cf-111">Para simplificar el proceso de desarrollo, .NET incluye un conjunto de tipos delegados que los programadores pueden volver a usar para no tener que crear nuevos tipos.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-111">In order to streamline the development process, .NET includes a set of delegate types that programmers can reuse and not have to create new types.</span></span> <span data-ttu-id="3a3cf-112">Estos son `Func<>`, `Action<>` y `Predicate<>`, y se pueden usar en varias ubicaciones de las API de .NET sin necesidad de definir nuevos tipos delegados.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-112">These are `Func<>`, `Action<>` and `Predicate<>`, and they can be used in various places throughout the .NET APIs without the need to define new delegate types.</span></span> <span data-ttu-id="3a3cf-113">Por supuesto, hay algunas diferencias entre los tres, como verá en sus firmas, que principalmente tienen que ver con la forma en que deberían emplearse:</span><span class="sxs-lookup"><span data-stu-id="3a3cf-113">Of course, there are some differences between the three as you will see in their signatures which mostly have to do with the way they were meant to be used:</span></span>

* <span data-ttu-id="3a3cf-114">`Action<>` se usa cuando es necesario realizar una acción mediante los argumentos del delegado.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-114">`Action<>` is used when there is a need to perform an action using the arguments of the delegate.</span></span>
* <span data-ttu-id="3a3cf-115">`Func<>` se usa normalmente cuando se tiene una transformación a mano; es decir, cuando se necesita transformar los argumentos del delegado en un resultado diferente.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-115">`Func<>` is used usually when you have a transformation on hand, that is, you need to transform the arguments of the delegate into a different result.</span></span> <span data-ttu-id="3a3cf-116">Las proyecciones son un buen ejemplo de esto.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-116">Projections are a prime example of this.</span></span>
* <span data-ttu-id="3a3cf-117">`Predicate<>` se usa cuando es necesario determinar si el argumento cumple la condición del delegado.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-117">`Predicate<>` is used when you need to determine if the argument satisfies the condition of the delegate.</span></span> <span data-ttu-id="3a3cf-118">También puede escribirse como `Func<T, bool>`.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-118">It can also be written as a `Func<T, bool>`.</span></span>

<span data-ttu-id="3a3cf-119">Ahora podemos tomar el ejemplo anterior y volver a escribirlo mediante el delegado `Func<>` en lugar de un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-119">We can now take our example above and rewrite it using the `Func<>` delegate instead of a custom type.</span></span> <span data-ttu-id="3a3cf-120">El programa seguirá ejecutándose de la misma forma.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-120">The program will continue running exactly the same.</span></span>

```csharp
using System;
using System.Linq;

public class Program
{
    static string ReverseString(string s)
    {
        return new string(s.Reverse().ToArray());
    }

    static void Main(string[] args)
    {
        Func<string, string> rev = ReverseString;

        Console.WriteLine(rev("a string"));
    }
}
```

<span data-ttu-id="3a3cf-121">En este ejemplo sencillo, tener un método definido fuera del método `Main` parece un poco superfluo.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-121">For this simple example, having a method defined outside of the `Main` method seems a bit superfluous.</span></span> <span data-ttu-id="3a3cf-122">Es por ello que .NET Framework 2.0 presentó el concepto de **delegados anónimos**.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-122">It is because of this that .NET Framework 2.0 introduced the concept of **anonymous delegates**.</span></span> <span data-ttu-id="3a3cf-123">Con ellos es posible crear delegados "insertados" sin tener que especificar ningún otro tipo o método.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-123">With their support you are able to create "inline" delegates without having to specify any additional type or method.</span></span> <span data-ttu-id="3a3cf-124">Simplemente se inserta la definición del delegado allí donde se necesita.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-124">You simply inline the definition of the delegate where you need it.</span></span>

<span data-ttu-id="3a3cf-125">Para que vea un ejemplo, se va a activar y a usar el delegado anónimo para filtrar una lista de números pares e imprimirlos en la consola.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-125">For an example, we are going to switch it up and use our anonymous delegate to filter out a list of only even numbers and then print them to the console.</span></span>

```csharp
using System;
using System.Collections.Generic;

public class Program
{
    public static void Main(string[] args)
    {
        List<int> list = new List<int>();

        for (int i = 1; i <= 100; i++)
        {
            list.Add(i);
        }

        List<int> result = list.FindAll(
          delegate (int no)
          {
              return (no % 2 == 0);
          }
        );

        foreach (var item in result)
        {
            Console.WriteLine(item);
        }
    }
}
```

<span data-ttu-id="3a3cf-126">Como puede ver, el cuerpo del delegado es simplemente un conjunto de expresiones, como cualquier otro delegado.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-126">As you can see, the body of the delegate is just a set of expressions, as any other delegate.</span></span> <span data-ttu-id="3a3cf-127">Pero en lugar de ser una definición independiente, se ha introducido _ad hoc_ en la llamada al método <xref:System.Collections.Generic.List%601.FindAll%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-127">But instead of it being a separate definition, we’ve introduced it _ad hoc_ in our call to the <xref:System.Collections.Generic.List%601.FindAll%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="3a3cf-128">Pero incluso con este enfoque, sigue habiendo mucho código del que es posible deshacerse.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-128">However, even with this approach, there is still much code that we can throw away.</span></span> <span data-ttu-id="3a3cf-129">Aquí es donde entran en juego las **expresiones lambda**.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-129">This is where **lambda expressions** come into play.</span></span>

<span data-ttu-id="3a3cf-130">Las expresiones lambda, o las "lambda" para abreviar, se presentaron en C# 3.0 como uno de los bloques de creación fundamentales de Language Integrated Query (LINQ).</span><span class="sxs-lookup"><span data-stu-id="3a3cf-130">Lambda expressions, or just "lambdas" for short, were introduced first in C# 3.0, as one of the core building blocks of Language Integrated Query (LINQ).</span></span> <span data-ttu-id="3a3cf-131">Constituyen una sintaxis más cómoda para el uso de delegados.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-131">They are just a more convenient syntax for using delegates.</span></span> <span data-ttu-id="3a3cf-132">Declaran una firma y un cuerpo de método, pero no tienen una identidad formal propia, a menos que se asignen a un delegado.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-132">They declare a signature and a method body, but don’t have an formal identity of their own, unless they are assigned to a delegate.</span></span> <span data-ttu-id="3a3cf-133">A diferencia de los delegados, se pueden asignar directamente como lado izquierdo del registro de eventos, o bien en distintas cláusulas y métodos de LINQ.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-133">Unlike delegates, they can be directly assigned as the left-hand side of event registration or in various LINQ clauses and methods.</span></span>

<span data-ttu-id="3a3cf-134">Puesto que una expresión lambda es solo otra forma de especificar un delegado, debería ser posible volver a escribir el ejemplo anterior para usar una expresión lambda en lugar de un delegado anónimo.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-134">Since a lambda expression is just another way of specifying a delegate, we should be able to rewrite the above sample to use a lambda expression instead of an anonymous delegate.</span></span>

```csharp
using System;
using System.Collections.Generic;

public class Program
{
    public static void Main(string[] args)
    {
        List<int> list = new List<int>();

        for (int i = 1; i <= 100; i++)
        {
            list.Add(i);
        }

        List<int> result = list.FindAll(i => i % 2 == 0);

        foreach (var item in result)
        {
            Console.WriteLine(item);
        }
    }
}
```

<span data-ttu-id="3a3cf-135">En el ejemplo anterior, la expresión lambda que se usa es `i => i % 2 == 0`.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-135">In the preceding example, the lambda expression used is `i => i % 2 == 0`.</span></span> <span data-ttu-id="3a3cf-136">Una vez más, se trata solo de una sintaxis **muy** cómoda para usar delegados, así que lo que sucede en segundo plano es similar a lo que ocurre con el delegado anónimo.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-136">Again, it is just a **very** convenient syntax for using delegates, so what happens under the covers is similar to what happens with the anonymous delegate.</span></span>

<span data-ttu-id="3a3cf-137">De nuevo, las expresiones lambda son solo delegados, lo que significa que se pueden usar como controlador de eventos sin problemas, como se muestra en el siguiente fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="3a3cf-137">Again, lambdas are just delegates, which means that they can be used as an event handler without any problems, as the following code snippet illustrates.</span></span>

```csharp
public MainWindow()
{
    InitializeComponent();

    Loaded += (o, e) =>
    {
        this.Title = "Loaded";
    };
}
```

<span data-ttu-id="3a3cf-138">En este contexto, el operador `+=` se usa para suscribirse a un [evento](../../docs/csharp/language-reference/keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="3a3cf-138">The `+=` operator in this context is used to subscribe to an [event](../../docs/csharp/language-reference/keywords/event.md).</span></span> <span data-ttu-id="3a3cf-139">Para obtener más información, vea [Procedimiento para suscribir y cancelar la suscripción a eventos](../../docs/csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="3a3cf-139">For more information, see [How to subscribe to and unsubscribe from events](../../docs/csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="further-reading-and-resources"></a><span data-ttu-id="3a3cf-140">Más información y recursos</span><span class="sxs-lookup"><span data-stu-id="3a3cf-140">Further reading and resources</span></span>

* [<span data-ttu-id="3a3cf-141">Delegados</span><span class="sxs-lookup"><span data-stu-id="3a3cf-141">Delegates</span></span>](../../docs/csharp/programming-guide/delegates/index.md)
* [<span data-ttu-id="3a3cf-142">Funciones anónimas</span><span class="sxs-lookup"><span data-stu-id="3a3cf-142">Anonymous Functions</span></span>](../../docs/csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)
* [<span data-ttu-id="3a3cf-143">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="3a3cf-143">Lambda expressions</span></span>](../../docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
