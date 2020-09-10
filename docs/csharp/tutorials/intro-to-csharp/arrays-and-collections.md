---
title: 'Trabajo con colecciones: tutorial de introducción a C#'
description: Conozca C# a través de la colección de listas que se presenta en este tutorial.
ms.date: 10/13/2017
ms.custom: mvc
ms.openlocfilehash: e2282df21420630634911e07f4fb3b94f34a792b
ms.sourcegitcommit: b1f4756120deaecb8b554477bb040620f69a4209
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "89414688"
---
# <a name="learn-to-manage-data-collections-using-the-generic-list-type"></a><span data-ttu-id="31658-103">Obtenga información sobre cómo administrar colecciones de datos mediante el tipo de lista genérico</span><span class="sxs-lookup"><span data-stu-id="31658-103">Learn to manage data collections using the generic list type</span></span>

<span data-ttu-id="31658-104">En este tutorial de presentación se proporciona una introducción al lenguaje C# y se exponen los conceptos básicos de la clase <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="31658-104">This introductory tutorial provides an introduction to the C# language and the basics of the <xref:System.Collections.Generic.List%601> class.</span></span>

<span data-ttu-id="31658-105">En este tutorial se supone que cuenta con una máquina que puede usar para el desarrollo.</span><span class="sxs-lookup"><span data-stu-id="31658-105">This tutorial expects you to have a machine you can use for development.</span></span> <span data-ttu-id="31658-106">El tutorial de .NET [Hola mundo en 10 minutos](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) cuenta con instrucciones para configurar el entorno de desarrollo local en Windows, Linux o macOS.</span><span class="sxs-lookup"><span data-stu-id="31658-106">The .NET tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) has instructions for setting up your local development environment on Windows, Linux, or macOS.</span></span> <span data-ttu-id="31658-107">En [Familiarización con las herramientas de desarrollo de .NET](local-environment.md) puede obtener información general sobre los comandos que usará, donde hay vínculos que amplían la información.</span><span class="sxs-lookup"><span data-stu-id="31658-107">A quick overview of the commands you'll use is in [Become familiar with the development tools](local-environment.md), with links to more details.</span></span>

## <a name="a-basic-list-example"></a><span data-ttu-id="31658-108">Un ejemplo de lista básico</span><span class="sxs-lookup"><span data-stu-id="31658-108">A basic list example</span></span>

<span data-ttu-id="31658-109">Cree un directorio denominado *list-tutorial*.</span><span class="sxs-lookup"><span data-stu-id="31658-109">Create a directory named *list-tutorial*.</span></span> <span data-ttu-id="31658-110">Conviértalo en el directorio actual y ejecute `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="31658-110">Make that the current directory and run `dotnet new console`.</span></span>

<span data-ttu-id="31658-111">Abra *Program.cs* en su editor favorito y reemplace el código existente por el siguiente:</span><span class="sxs-lookup"><span data-stu-id="31658-111">Open *Program.cs* in your favorite editor, and replace the existing code with the following:</span></span>

```csharp
using System;
using System.Collections.Generic;

namespace list_tutorial
{
    class Program
    {
        static void Main(string[] args)
        {
            var names = new List<string> { "<name>", "Ana", "Felipe" };
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }
        }
    }
}
```

<span data-ttu-id="31658-112">Reemplace `<name>` por su propio nombre.</span><span class="sxs-lookup"><span data-stu-id="31658-112">Replace `<name>` with your name.</span></span> <span data-ttu-id="31658-113">Guarde *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="31658-113">Save *Program.cs*.</span></span> <span data-ttu-id="31658-114">Escriba `dotnet run` en la ventana de la consola para probarlo.</span><span class="sxs-lookup"><span data-stu-id="31658-114">Type `dotnet run` in your console window to try it.</span></span>

<span data-ttu-id="31658-115">Ha creado una lista de cadenas, ha agregado tres nombres a esa lista y ha impreso los nombres en MAYÚSCULA.</span><span class="sxs-lookup"><span data-stu-id="31658-115">You've created a list of strings, added three names to that list, and printed out the names in all CAPS.</span></span> <span data-ttu-id="31658-116">Los conceptos aplicados ya se han aprendido en los tutoriales anteriores para recorrer en bucle la lista.</span><span class="sxs-lookup"><span data-stu-id="31658-116">You're using concepts that you've learned in earlier tutorials to loop through the list.</span></span>

<span data-ttu-id="31658-117">El código para mostrar los nombres usa la característica [interpolación de cadenas](../../language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="31658-117">The code to display names makes use of the [string interpolation](../../language-reference/tokens/interpolated.md) feature.</span></span>  <span data-ttu-id="31658-118">Si un valor de `string` va precedido del carácter `$`, significa que puede insertar código de C# en la declaración de cadena.</span><span class="sxs-lookup"><span data-stu-id="31658-118">When you precede a `string` with the `$` character, you can embed C# code in the string declaration.</span></span> <span data-ttu-id="31658-119">La cadena real reemplaza a ese código de C# con el valor que genera.</span><span class="sxs-lookup"><span data-stu-id="31658-119">The actual string replaces that C# code with the value it generates.</span></span> <span data-ttu-id="31658-120">En este ejemplo, reemplaza `{name.ToUpper()}` con cada nombre, convertido a mayúsculas, porque se llama al método <xref:System.String.ToUpper%2A>.</span><span class="sxs-lookup"><span data-stu-id="31658-120">In this example, it replaces the `{name.ToUpper()}` with each name, converted to capital letters, because you called the <xref:System.String.ToUpper%2A> method.</span></span>

<span data-ttu-id="31658-121">Vamos a continuar indagando.</span><span class="sxs-lookup"><span data-stu-id="31658-121">Let's keep exploring.</span></span>

## <a name="modify-list-contents"></a><span data-ttu-id="31658-122">Modificación del contenido de las listas</span><span class="sxs-lookup"><span data-stu-id="31658-122">Modify list contents</span></span>

<span data-ttu-id="31658-123">La colección creada usa el tipo <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="31658-123">The collection you created uses the <xref:System.Collections.Generic.List%601> type.</span></span> <span data-ttu-id="31658-124">Este tipo almacena las secuencias de elementos.</span><span class="sxs-lookup"><span data-stu-id="31658-124">This type stores sequences of elements.</span></span> <span data-ttu-id="31658-125">Especifique el tipo de los elementos entre corchetes angulares.</span><span class="sxs-lookup"><span data-stu-id="31658-125">You specify the type of the elements between the angle brackets.</span></span>

<span data-ttu-id="31658-126">Un aspecto importante de este tipo <xref:System.Collections.Generic.List%601> es que se puede aumentar o reducir, lo que permite agregar o quitar elementos.</span><span class="sxs-lookup"><span data-stu-id="31658-126">One important aspect of this <xref:System.Collections.Generic.List%601> type is that it can grow or shrink, enabling you to add or remove elements.</span></span> <span data-ttu-id="31658-127">Agregue este código antes del corchete de cierre `}` en el método `Main`:</span><span class="sxs-lookup"><span data-stu-id="31658-127">Add this code before the closing `}` in the `Main` method:</span></span>

```csharp
Console.WriteLine();
names.Add("Maria");
names.Add("Bill");
names.Remove("Ana");
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

<span data-ttu-id="31658-128">Se han agregado dos nombres más al final de la lista.</span><span class="sxs-lookup"><span data-stu-id="31658-128">You've added two more names to the end of the list.</span></span> <span data-ttu-id="31658-129">También se ha quitado uno.</span><span class="sxs-lookup"><span data-stu-id="31658-129">You've also removed one as well.</span></span> <span data-ttu-id="31658-130">Guarde el archivo y escriba `dotnet run` para probarlo.</span><span class="sxs-lookup"><span data-stu-id="31658-130">Save the file, and type `dotnet run` to try it.</span></span>

<span data-ttu-id="31658-131"><xref:System.Collections.Generic.List%601> también permite hacer referencia a elementos individuales a través del **índice**.</span><span class="sxs-lookup"><span data-stu-id="31658-131">The <xref:System.Collections.Generic.List%601> enables you to reference individual items by **index** as well.</span></span> <span data-ttu-id="31658-132">Coloque el índice entre los tokens `[` y `]` después del nombre de la lista.</span><span class="sxs-lookup"><span data-stu-id="31658-132">You place the index between `[` and `]` tokens following the list name.</span></span> <span data-ttu-id="31658-133">C# utiliza 0 para el primer índice.</span><span class="sxs-lookup"><span data-stu-id="31658-133">C# uses 0 for the first index.</span></span> <span data-ttu-id="31658-134">Agregue este código directamente después del código que acaba de agregar y pruébelo:</span><span class="sxs-lookup"><span data-stu-id="31658-134">Add this code directly below the code you just added and try it:</span></span>

```csharp
Console.WriteLine($"My name is {names[0]}");
Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");
```

<span data-ttu-id="31658-135">No se puede acceder a un índice si se coloca después del final de la lista.</span><span class="sxs-lookup"><span data-stu-id="31658-135">You can't access an index beyond the end of the list.</span></span> <span data-ttu-id="31658-136">Recuerde que los índices empiezan en 0, por lo que el índice más grande válido es uno menos que el número de elementos de la lista.</span><span class="sxs-lookup"><span data-stu-id="31658-136">Remember that indices start at 0, so the largest valid index is one less than the number of items in the list.</span></span> <span data-ttu-id="31658-137">Puede comprobar durante cuánto tiempo la lista usa la propiedad <xref:System.Collections.Generic.List%601.Count%2A>.</span><span class="sxs-lookup"><span data-stu-id="31658-137">You can check how long the list is using the <xref:System.Collections.Generic.List%601.Count%2A> property.</span></span> <span data-ttu-id="31658-138">Agregue el código siguiente al final del método Main:</span><span class="sxs-lookup"><span data-stu-id="31658-138">Add the following code at the end of the Main method:</span></span>

```csharp
Console.WriteLine($"The list has {names.Count} people in it");
 ```

<span data-ttu-id="31658-139">Guarde el archivo y vuelva a escribir `dotnet run` para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="31658-139">Save the file, and type `dotnet run` again to see the results.</span></span>

## <a name="search-and-sort-lists"></a><span data-ttu-id="31658-140">Búsqueda y orden en las listas</span><span class="sxs-lookup"><span data-stu-id="31658-140">Search and sort lists</span></span>

<span data-ttu-id="31658-141">En los ejemplos se usan listas relativamente pequeñas, pero las aplicaciones a menudo pueden crear listas que contengan muchos más elementos, en ocasiones, con una numeración que engloba millares.</span><span class="sxs-lookup"><span data-stu-id="31658-141">Our samples use relatively small lists, but your applications may often create lists with many more elements, sometimes numbering in the thousands.</span></span> <span data-ttu-id="31658-142">Para encontrar elementos en estas colecciones más grandes, debe buscar diferentes elementos en la lista.</span><span class="sxs-lookup"><span data-stu-id="31658-142">To find elements in these larger collections, you need to search the list for different items.</span></span> <span data-ttu-id="31658-143">El método <xref:System.Collections.Generic.List%601.IndexOf%2A> busca un elemento y devuelve su índice.</span><span class="sxs-lookup"><span data-stu-id="31658-143">The <xref:System.Collections.Generic.List%601.IndexOf%2A> method searches for an item and returns the index of the item.</span></span> <span data-ttu-id="31658-144">Si el elemento no está en la lista, `IndexOf` devuelve `-1`.</span><span class="sxs-lookup"><span data-stu-id="31658-144">If the item isn't in the list, `IndexOf` returns `-1`.</span></span> <span data-ttu-id="31658-145">Agregue este código en la parte inferior del método `Main`:</span><span class="sxs-lookup"><span data-stu-id="31658-145">Add this code to the bottom of your `Main` method:</span></span>

```csharp
var index = names.IndexOf("Felipe");
if (index == -1)
{
    Console.WriteLine($"When an item is not found, IndexOf returns {index}");
}
else
{
    Console.WriteLine($"The name {names[index]} is at index {index}");
}

index = names.IndexOf("Not Found");
if (index == -1)
{
    Console.WriteLine($"When an item is not found, IndexOf returns {index}");
}
else
{
    Console.WriteLine($"The name {names[index]} is at index {index}");

}
```

<span data-ttu-id="31658-146">Los elementos de la lista también se pueden ordenar.</span><span class="sxs-lookup"><span data-stu-id="31658-146">The items in your list can be sorted as well.</span></span> <span data-ttu-id="31658-147">El método <xref:System.Collections.Generic.List%601.Sort%2A> clasifica todos los elementos de la lista en su orden normal (por orden alfabético si se trata de cadenas).</span><span class="sxs-lookup"><span data-stu-id="31658-147">The <xref:System.Collections.Generic.List%601.Sort%2A> method sorts all the items in the list in their normal order (alphabetically for strings).</span></span> <span data-ttu-id="31658-148">Agregue este código en la parte inferior del método `Main`:</span><span class="sxs-lookup"><span data-stu-id="31658-148">Add this code to the bottom of our `Main` method:</span></span>

```csharp
names.Sort();
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

<span data-ttu-id="31658-149">Guarde el archivo y escriba `dotnet run` para probar esta última versión.</span><span class="sxs-lookup"><span data-stu-id="31658-149">Save the file and type `dotnet run` to try this latest version.</span></span>

<span data-ttu-id="31658-150">Antes comenzar con la siguiente sección, se va a mover el código actual a un método independiente.</span><span class="sxs-lookup"><span data-stu-id="31658-150">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="31658-151">Con este paso, resulta más fácil empezar con un nuevo ejemplo.</span><span class="sxs-lookup"><span data-stu-id="31658-151">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="31658-152">Cambie el nombre del método `Main` por `WorkingWithStrings` y escriba un método `Main` nuevo que llame a `WorkingWithStrings`.</span><span class="sxs-lookup"><span data-stu-id="31658-152">Rename your `Main` method to `WorkingWithStrings` and write a new `Main` method that calls `WorkingWithStrings`.</span></span> <span data-ttu-id="31658-153">Cuando termine, el código debe tener un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="31658-153">When you've finished, your code should look like this:</span></span>

```csharp
using System;
using System.Collections.Generic;

namespace list_tutorial
{
    class Program
    {
        static void Main(string[] args)
        {
            WorkingWithStrings();
        }

        static void WorkingWithStrings()
        {
            var names = new List<string> { "<name>", "Ana", "Felipe" };
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }

            Console.WriteLine();
            names.Add("Maria");
            names.Add("Bill");
            names.Remove("Ana");
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }

            Console.WriteLine($"My name is {names[0]}");
            Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");

            Console.WriteLine($"The list has {names.Count} people in it");

            var index = names.IndexOf("Felipe");
            if (index == -1)
            {
                Console.WriteLine($"When an item is not found, IndexOf returns {index}");
            }
            else
            {
                Console.WriteLine($"The name {names[index]} is at index {index}");
            }

            index = names.IndexOf("Not Found");
            if (index == -1)
            {
                Console.WriteLine($"When an item is not found, IndexOf returns {index}");
            }
            else
            {
                Console.WriteLine($"The name {names[index]} is at index {index}");

            }

            names.Sort();
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }
        }
    }
}
```

## <a name="lists-of-other-types"></a><span data-ttu-id="31658-154">Listas de otros tipos</span><span class="sxs-lookup"><span data-stu-id="31658-154">Lists of other types</span></span>

<span data-ttu-id="31658-155">Hasta el momento, se ha usado el tipo `string` en las listas.</span><span class="sxs-lookup"><span data-stu-id="31658-155">You've been using the `string` type in lists so far.</span></span> <span data-ttu-id="31658-156">Se va a crear una lista <xref:System.Collections.Generic.List%601> con un tipo distinto.</span><span class="sxs-lookup"><span data-stu-id="31658-156">Let's make a <xref:System.Collections.Generic.List%601> using a different type.</span></span> <span data-ttu-id="31658-157">Se va a crear una serie de números.</span><span class="sxs-lookup"><span data-stu-id="31658-157">Let's build a set of numbers.</span></span>

<span data-ttu-id="31658-158">Agregue lo siguiente en la parte inferior del método `Main` nuevo:</span><span class="sxs-lookup"><span data-stu-id="31658-158">Add the following to the bottom of your new `Main` method:</span></span>

```csharp
var fibonacciNumbers = new List<int> {1, 1};
```

<span data-ttu-id="31658-159">Se crea una lista de enteros y se definen los dos primeros enteros con el valor 1.</span><span class="sxs-lookup"><span data-stu-id="31658-159">That creates a list of integers, and sets the first two integers to the value 1.</span></span> <span data-ttu-id="31658-160">Son los dos primeros valores de una *sucesión de Fibonacci*, una secuencia de números.</span><span class="sxs-lookup"><span data-stu-id="31658-160">These are the first two values of a *Fibonacci Sequence*, a sequence of numbers.</span></span> <span data-ttu-id="31658-161">Cada número sucesivo de Fibonacci se obtiene con la suma de los dos números anteriores.</span><span class="sxs-lookup"><span data-stu-id="31658-161">Each next Fibonacci number is found by taking the sum of the previous two numbers.</span></span> <span data-ttu-id="31658-162">Agregue este código:</span><span class="sxs-lookup"><span data-stu-id="31658-162">Add this code:</span></span>

```csharp
var previous = fibonacciNumbers[fibonacciNumbers.Count - 1];
var previous2 = fibonacciNumbers[fibonacciNumbers.Count - 2];

fibonacciNumbers.Add(previous + previous2);

foreach (var item in fibonacciNumbers)
    Console.WriteLine(item);
```

<span data-ttu-id="31658-163">Guarde el archivo y escriba `dotnet run` para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="31658-163">Save the file and type `dotnet run` to see the results.</span></span>

> [!TIP]
> <span data-ttu-id="31658-164">Para centrarse solo en esta sección, puede comentar el código que llama a `WorkingWithStrings();`.</span><span class="sxs-lookup"><span data-stu-id="31658-164">To concentrate on just this section, you can comment out the code that calls `WorkingWithStrings();`.</span></span> <span data-ttu-id="31658-165">Solo debe colocar dos caracteres `/` delante de la llamada, como en: `// WorkingWithStrings();`.</span><span class="sxs-lookup"><span data-stu-id="31658-165">Just put two `/` characters in front of the call like this:  `// WorkingWithStrings();`.</span></span>

## <a name="challenge"></a><span data-ttu-id="31658-166">Desafío</span><span class="sxs-lookup"><span data-stu-id="31658-166">Challenge</span></span>

<span data-ttu-id="31658-167">Trate de recopilar los conceptos que ha aprendido en esta lección y en las anteriores.</span><span class="sxs-lookup"><span data-stu-id="31658-167">See if you can put together some of the concepts from this and earlier lessons.</span></span> <span data-ttu-id="31658-168">Amplíe lo que ha creado hasta el momento con los números de Fibonacci.</span><span class="sxs-lookup"><span data-stu-id="31658-168">Expand on what you've built so far with Fibonacci Numbers.</span></span> <span data-ttu-id="31658-169">Pruebe a escribir el código para generar los veinte primeros números de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="31658-169">Try to write the code to generate the first 20 numbers in the sequence.</span></span> <span data-ttu-id="31658-170">(Como sugerencia, el 20º número de la serie de Fibonacci es 6765).</span><span class="sxs-lookup"><span data-stu-id="31658-170">(As a hint, the 20th Fibonacci number is 6765.)</span></span>

## <a name="complete-challenge"></a><span data-ttu-id="31658-171">Desafío completo</span><span class="sxs-lookup"><span data-stu-id="31658-171">Complete challenge</span></span>

<span data-ttu-id="31658-172">Puede ver un ejemplo de solución en el [ejemplo de código terminado en GitHub](https://github.com/dotnet/samples/tree/master/csharp/list-quickstart/Program.cs#L13-L23).</span><span class="sxs-lookup"><span data-stu-id="31658-172">You can see an example solution by [looking at the finished sample code on GitHub](https://github.com/dotnet/samples/tree/master/csharp/list-quickstart/Program.cs#L13-L23).</span></span>

<span data-ttu-id="31658-173">Con cada iteración del bucle, se obtienen los dos últimos enteros de la lista, se suman y se agrega el valor resultante a la lista.</span><span class="sxs-lookup"><span data-stu-id="31658-173">With each iteration of the loop, you're taking the last two integers in the list, summing them, and adding that value to the list.</span></span> <span data-ttu-id="31658-174">El bucle se repite hasta que se hayan agregado veinte elementos a la lista.</span><span class="sxs-lookup"><span data-stu-id="31658-174">The loop repeats until you've added 20 items to the list.</span></span>

<span data-ttu-id="31658-175">Enhorabuena, ha completado el tutorial sobre las listas.</span><span class="sxs-lookup"><span data-stu-id="31658-175">Congratulations, you've completed the list tutorial.</span></span> <span data-ttu-id="31658-176">Puede continuar con el tutorial [Introducción a las clases](introduction-to-classes.md) en su propio entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="31658-176">You can continue with the [Introduction to classes](introduction-to-classes.md) tutorial in your own development environment.</span></span>

<span data-ttu-id="31658-177">Puede obtener más información sobre cómo trabajar con el tipo `List` en el artículo de los aspectos básicos de .NET que trata sobre las [colecciones](../../../standard/collections/index.md).</span><span class="sxs-lookup"><span data-stu-id="31658-177">You can learn more about working with the `List` type in the .NET fundamentals article on [collections](../../../standard/collections/index.md).</span></span> <span data-ttu-id="31658-178">Ahí también podrá conocer muchos otros tipos de colecciones.</span><span class="sxs-lookup"><span data-stu-id="31658-178">You'll also learn about many other collection types.</span></span>
