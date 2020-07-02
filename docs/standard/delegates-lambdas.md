---
title: Delegados y expresiones lambda
description: Obtenga información sobre cómo los delegados, que definen un tipo que especifica una firma de método determinada, se pueden llamar directamente o pasar a otro método y llamar.
author: richlander
ms.author: wiwagn
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: fe2e4b4c-6483-4106-a4b4-a33e2e306591
ms.openlocfilehash: 184c9f61fd8456b22e8ecb262c131793160b49b0
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244015"
---
# <a name="delegates-and-lambdas"></a><span data-ttu-id="53b45-103">Delegados y expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="53b45-103">Delegates and lambdas</span></span>

<span data-ttu-id="53b45-104">Los delegados definen un tipo que especifica una firma de método concreta.</span><span class="sxs-lookup"><span data-stu-id="53b45-104">Delegates define a type that specifies a particular method signature.</span></span> <span data-ttu-id="53b45-105">Se puede asignar un método (estático o de instancia) que satisfaga esta firma a una variable de ese tipo y luego llamarlo directamente (con los argumentos adecuados) o pasarlo como argumento a otro método y después llamarlo.</span><span class="sxs-lookup"><span data-stu-id="53b45-105">A method (static or instance) that satisfies this signature can be assigned to a variable of that type, then called directly (with the appropriate arguments) or passed as an argument itself to another method and then called.</span></span> <span data-ttu-id="53b45-106">El siguiente ejemplo muestra el uso de delegados.</span><span class="sxs-lookup"><span data-stu-id="53b45-106">The following example demonstrates delegate use.</span></span>

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

* <span data-ttu-id="53b45-107">En la línea `public delegate string Reverse(string s);` se crea un tipo delegado de una firma determinada, en este caso un método que toma un parámetro de cadena y luego devuelve un parámetro de cadena.</span><span class="sxs-lookup"><span data-stu-id="53b45-107">The `public delegate string Reverse(string s);` line creates a delegate type of a certain signature, in this case a method that takes a string parameter and then returns a string parameter.</span></span>
* <span data-ttu-id="53b45-108">El método `static string ReverseString(string s)`, que tiene exactamente la misma firma que el tipo delegado definido, implementa el delegado.</span><span class="sxs-lookup"><span data-stu-id="53b45-108">The `static string ReverseString(string s)` method, which has the exact same signature as the defined delegate type, implements the delegate.</span></span>
* <span data-ttu-id="53b45-109">En la línea `Reverse rev = ReverseString;` se muestra que se puede asignar un método a una variable del tipo de delegado correspondiente.</span><span class="sxs-lookup"><span data-stu-id="53b45-109">The `Reverse rev = ReverseString;` line shows that you can assign a method to a variable of the corresponding delegate type.</span></span>
* <span data-ttu-id="53b45-110">En la línea `Console.WriteLine(rev("a string"));` se muestra cómo se usa una variable de un tipo de delegado para invocar al delegado.</span><span class="sxs-lookup"><span data-stu-id="53b45-110">The `Console.WriteLine(rev("a string"));` line demonstrates how to use a variable of a delegate type to invoke the delegate.</span></span>

<span data-ttu-id="53b45-111">Para simplificar el proceso de desarrollo, .NET incluye un conjunto de tipos delegados que los programadores pueden volver a usar para no tener que crear nuevos tipos.</span><span class="sxs-lookup"><span data-stu-id="53b45-111">In order to streamline the development process, .NET includes a set of delegate types that programmers can reuse and not have to create new types.</span></span> <span data-ttu-id="53b45-112">Estos tipos son `Func<>`, `Action<>` y `Predicate<>`, y se pueden usar sin necesidad de definir nuevos tipos de delegado.</span><span class="sxs-lookup"><span data-stu-id="53b45-112">These types are `Func<>`, `Action<>` and `Predicate<>`, and they can be used without having to define new delegate types.</span></span> <span data-ttu-id="53b45-113">Hay algunas diferencias entre los tres tipos que tienen que ver con la forma en que se van a usar:</span><span class="sxs-lookup"><span data-stu-id="53b45-113">There are some differences between the three types that have to do with the way they were intended to be used:</span></span>

* <span data-ttu-id="53b45-114">`Action<>` se usa cuando es necesario realizar una acción mediante los argumentos del delegado.</span><span class="sxs-lookup"><span data-stu-id="53b45-114">`Action<>` is used when there is a need to perform an action using the arguments of the delegate.</span></span> <span data-ttu-id="53b45-115">El método que encapsula no devuelve ningún valor.</span><span class="sxs-lookup"><span data-stu-id="53b45-115">The method it encapsulates does not return a value.</span></span>
* <span data-ttu-id="53b45-116">`Func<>` se usa normalmente cuando se tiene una transformación a mano; es decir, cuando se necesita transformar los argumentos del delegado en un resultado diferente.</span><span class="sxs-lookup"><span data-stu-id="53b45-116">`Func<>` is used usually when you have a transformation on hand, that is, you need to transform the arguments of the delegate into a different result.</span></span> <span data-ttu-id="53b45-117">Las proyecciones son un buen ejemplo.</span><span class="sxs-lookup"><span data-stu-id="53b45-117">Projections are a good example.</span></span> <span data-ttu-id="53b45-118">El método que encapsula devuelve un valor especificado.</span><span class="sxs-lookup"><span data-stu-id="53b45-118">The method it encapsulates returns a specified value.</span></span>
* <span data-ttu-id="53b45-119">`Predicate<>` se usa cuando es necesario determinar si el argumento cumple la condición del delegado.</span><span class="sxs-lookup"><span data-stu-id="53b45-119">`Predicate<>` is used when you need to determine if the argument satisfies the condition of the delegate.</span></span> <span data-ttu-id="53b45-120">También se puede escribir como `Func<T, bool>`, lo que significa que el método devuelve un valor booleano.</span><span class="sxs-lookup"><span data-stu-id="53b45-120">It can also be written as a `Func<T, bool>`, which means the method returns a boolean value.</span></span>

<span data-ttu-id="53b45-121">Ahora podemos tomar el ejemplo anterior y volver a escribirlo mediante el delegado `Func<>` en lugar de un tipo personalizado.</span><span class="sxs-lookup"><span data-stu-id="53b45-121">We can now take our example above and rewrite it using the `Func<>` delegate instead of a custom type.</span></span> <span data-ttu-id="53b45-122">El programa seguirá ejecutándose de la misma forma.</span><span class="sxs-lookup"><span data-stu-id="53b45-122">The program will continue running exactly the same.</span></span>

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

<span data-ttu-id="53b45-123">En este ejemplo sencillo, tener un método definido fuera del método `Main` parece un poco superfluo.</span><span class="sxs-lookup"><span data-stu-id="53b45-123">For this simple example, having a method defined outside of the `Main` method seems a bit superfluous.</span></span> <span data-ttu-id="53b45-124">.NET Framework 2.0 ha introducido el concepto de *delegados anónimos*, que permiten crear delegados "insertados" sin necesidad de especificar ningún otro tipo o método.</span><span class="sxs-lookup"><span data-stu-id="53b45-124">.NET Framework 2.0 introduced the concept of *anonymous delegates*, which let you create "inline" delegates without having to specify any additional type or method.</span></span>

<span data-ttu-id="53b45-125">En el ejemplo siguiente, un delegado anónimo filtra una lista solo por los números pares y, después, los imprime en la consola.</span><span class="sxs-lookup"><span data-stu-id="53b45-125">In the following example, an anonymous delegate filters a list to just the even numbers and then prints them to the console.</span></span>

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

<span data-ttu-id="53b45-126">Como puede ver, el cuerpo del delegado es simplemente un conjunto de expresiones, como cualquier otro delegado.</span><span class="sxs-lookup"><span data-stu-id="53b45-126">As you can see, the body of the delegate is just a set of expressions, as any other delegate.</span></span> <span data-ttu-id="53b45-127">Pero en lugar de ser una definición independiente, se ha introducido _ad hoc_ en la llamada al método <xref:System.Collections.Generic.List%601.FindAll%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="53b45-127">But instead of it being a separate definition, we've introduced it _ad hoc_ in our call to the <xref:System.Collections.Generic.List%601.FindAll%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="53b45-128">Pero incluso con este enfoque, sigue habiendo mucho código del que es posible deshacerse.</span><span class="sxs-lookup"><span data-stu-id="53b45-128">However, even with this approach, there is still much code that we can throw away.</span></span> <span data-ttu-id="53b45-129">Aquí es donde entran en juego las *expresiones lambda*.</span><span class="sxs-lookup"><span data-stu-id="53b45-129">This is where *lambda expressions* come into play.</span></span> <span data-ttu-id="53b45-130">Las expresiones lambda, o las "lambda", para abreviar, se presentaron en C# 3.0 como uno de los bloques de compilación fundamentales de Language Integrated Query (LINQ).</span><span class="sxs-lookup"><span data-stu-id="53b45-130">Lambda expressions, or just "lambdas" for short, were introduced in C# 3.0 as one of the core building blocks of Language Integrated Query (LINQ).</span></span> <span data-ttu-id="53b45-131">Constituyen una sintaxis más cómoda para el uso de delegados.</span><span class="sxs-lookup"><span data-stu-id="53b45-131">They are just a more convenient syntax for using delegates.</span></span> <span data-ttu-id="53b45-132">Declaran una firma y un cuerpo de método, pero no tienen una identidad formal propia, a menos que se asignen a un delegado.</span><span class="sxs-lookup"><span data-stu-id="53b45-132">They declare a signature and a method body, but don't have a formal identity of their own, unless they are assigned to a delegate.</span></span> <span data-ttu-id="53b45-133">A diferencia de los delegados, se pueden asignar directamente como lado izquierdo del registro de eventos, o bien en distintas cláusulas y métodos de LINQ.</span><span class="sxs-lookup"><span data-stu-id="53b45-133">Unlike delegates, they can be directly assigned as the right-hand side of event registration or in various LINQ clauses and methods.</span></span>

<span data-ttu-id="53b45-134">Puesto que una expresión lambda es solo otra forma de especificar un delegado, debería ser posible volver a escribir el ejemplo anterior para usar una expresión lambda en lugar de un delegado anónimo.</span><span class="sxs-lookup"><span data-stu-id="53b45-134">Since a lambda expression is just another way of specifying a delegate, we should be able to rewrite the above sample to use a lambda expression instead of an anonymous delegate.</span></span>

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

<span data-ttu-id="53b45-135">En el ejemplo anterior, la expresión lambda que se usa es `i => i % 2 == 0`.</span><span class="sxs-lookup"><span data-stu-id="53b45-135">In the preceding example, the lambda expression used is `i => i % 2 == 0`.</span></span> <span data-ttu-id="53b45-136">De nuevo, constituyen una sintaxis más cómoda para el uso de delegados.</span><span class="sxs-lookup"><span data-stu-id="53b45-136">Again, it is just a convenient syntax for using delegates.</span></span> <span data-ttu-id="53b45-137">Lo que sucede en segundo plano es similar a lo que ocurre con el delegado anónimo.</span><span class="sxs-lookup"><span data-stu-id="53b45-137">What happens under the covers is similar to what happens with the anonymous delegate.</span></span>

<span data-ttu-id="53b45-138">De nuevo, las expresiones lambda son solo delegados, lo que significa que se pueden usar como controlador de eventos sin problemas, como se muestra en el siguiente fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="53b45-138">Again, lambdas are just delegates, which means that they can be used as an event handler without any problems, as the following code snippet illustrates.</span></span>

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

<span data-ttu-id="53b45-139">En este contexto, el operador `+=` se usa para suscribirse a un [evento](../csharp/language-reference/keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="53b45-139">The `+=` operator in this context is used to subscribe to an [event](../csharp/language-reference/keywords/event.md).</span></span> <span data-ttu-id="53b45-140">Para obtener más información, vea [Procedimiento para suscribir y cancelar la suscripción a eventos](../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="53b45-140">For more information, see [How to subscribe to and unsubscribe from events](../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>

## <a name="further-reading-and-resources"></a><span data-ttu-id="53b45-141">Más información y recursos</span><span class="sxs-lookup"><span data-stu-id="53b45-141">Further reading and resources</span></span>

* [<span data-ttu-id="53b45-142">Delegados</span><span class="sxs-lookup"><span data-stu-id="53b45-142">Delegates</span></span>](../csharp/programming-guide/delegates/index.md)
* [<span data-ttu-id="53b45-143">Funciones anónimas</span><span class="sxs-lookup"><span data-stu-id="53b45-143">Anonymous Functions</span></span>](../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)
* [<span data-ttu-id="53b45-144">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="53b45-144">Lambda expressions</span></span>](../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
