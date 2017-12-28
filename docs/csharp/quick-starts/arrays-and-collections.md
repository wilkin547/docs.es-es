---
title: "Inicio rápido: colecciones (Guía de C#)"
description: "Conozca C# a través de la colección de listas que se presenta en esta guía de inicio rápido."
keywords: "C#, introducción, tutorial, colecciones, lista"
author: billwagner
ms.author: wiwagn
ms.date: 10/13/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 6f559c7a3290e7db2266e10ec792c283394fb904
ms.sourcegitcommit: 9bee08539b1886c9d57fa3d5bd8a58dfdd7cad94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2017
---
# <a name="c-quick-start-collections"></a><span data-ttu-id="b14f5-104">Inicio rápido de C#: colecciones</span><span class="sxs-lookup"><span data-stu-id="b14f5-104">C# Quick start: Collections</span></span> #

<span data-ttu-id="b14f5-105">En esta guía de inicio rápido se proporciona una introducción al lenguaje C# y se exponen los conceptos básicos de la clase <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="b14f5-105">This quick start provides an introduction to the C# language and the basics of the <xref:System.Collections.Generic.List%601> class.</span></span>

<span data-ttu-id="b14f5-106">En esta guía de inicio rápido se supone que cuenta con una máquina que puede usar para el desarrollo.</span><span class="sxs-lookup"><span data-stu-id="b14f5-106">This quick start expects you to have a machine you can use for development.</span></span> <span data-ttu-id="b14f5-107">El tema de .NET [Iniciar en 10 minutos](https://www.microsoft.com/net/core) cuenta con instrucciones para configurar el entorno de desarrollo local en Mac, PC o Linux.</span><span class="sxs-lookup"><span data-stu-id="b14f5-107">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="b14f5-108">En las [guías de inicio rápido de introducción al entorno local](local-environment.md) puede obtener información general sobre los comandos que usará con vínculos que amplían la información.</span><span class="sxs-lookup"><span data-stu-id="b14f5-108">A quick overview of the commands you'll use is in the [introduction to the local quick starts](local-environment.md) with links to more details.</span></span>

## <a name="a-basic-list-example"></a><span data-ttu-id="b14f5-109">Un ejemplo de lista básico.</span><span class="sxs-lookup"><span data-stu-id="b14f5-109">A basic list example.</span></span>

<span data-ttu-id="b14f5-110">Cree un directorio denominado **inicio rápido-lista**.</span><span class="sxs-lookup"><span data-stu-id="b14f5-110">Create a directory named **list-quickstart**.</span></span> <span data-ttu-id="b14f5-111">Conviértalo en el directorio actual y ejecute `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="b14f5-111">Make that the current directory and run `dotnet new console`.</span></span>

> [!NOTE]
> <span data-ttu-id="b14f5-112">Si acaba de completar [Get started with .NET in 10 minutes](https://www.microsoft.com/net) (Introducción a .NET en 10 minutos), puede seguir usando la aplicación myApp que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="b14f5-112">If you just completed [Get started with .NET in 10 minutes](https://www.microsoft.com/net), you can keep using the myApp application that you just created.</span></span>
 
<span data-ttu-id="b14f5-113">Abra **Program.cs** en su editor favorito y reemplace el código existente por el siguiente:</span><span class="sxs-lookup"><span data-stu-id="b14f5-113">Open **Program.cs** in your favorite editor, and replace the existing code with the following:</span></span>

```csharp
using System;
using System.Collections.Generic;

namespace list_quickstart
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

<span data-ttu-id="b14f5-114">Reemplace `<name>` por su propio nombre.</span><span class="sxs-lookup"><span data-stu-id="b14f5-114">Replace `<name>` with your name.</span></span> <span data-ttu-id="b14f5-115">Guarde **Program.cs**.</span><span class="sxs-lookup"><span data-stu-id="b14f5-115">Save **Program.cs**.</span></span> <span data-ttu-id="b14f5-116">Escriba `dotnet run` en la ventana de la consola para probarlo.</span><span class="sxs-lookup"><span data-stu-id="b14f5-116">Type `dotnet run` in your console window to try it.</span></span>

<span data-ttu-id="b14f5-117">Hasta ahora, solo ha creado una lista de cadenas, ha agregado tres nombres a dicha lista y ha impreso los nombres en MAYÚSCULA.</span><span class="sxs-lookup"><span data-stu-id="b14f5-117">You've just created a list of strings, added three names to that list, and printed out the names in all CAPS.</span></span> <span data-ttu-id="b14f5-118">Los conceptos aplicados ya se han aprendido en los inicios rápidos anteriores para recorrer la lista.</span><span class="sxs-lookup"><span data-stu-id="b14f5-118">You're using concepts that you've learned in earlier quick starts to loop through the list.</span></span>

<span data-ttu-id="b14f5-119">El código para mostrar los nombres usa **cadenas interpoladas**.</span><span class="sxs-lookup"><span data-stu-id="b14f5-119">The code to display names makes use of **interpolated strings**.</span></span>  <span data-ttu-id="b14f5-120">Si un valor de `string` va precedido del carácter `$`, significa que puede insertar código de C# en la declaración de cadena.</span><span class="sxs-lookup"><span data-stu-id="b14f5-120">When you precede a `string` with the `$` character, you can embed C# code in the string declaration.</span></span> <span data-ttu-id="b14f5-121">La cadena real reemplaza a ese código de C# con el valor que genera.</span><span class="sxs-lookup"><span data-stu-id="b14f5-121">The actual string replaces that C# code with the value it generates.</span></span> <span data-ttu-id="b14f5-122">En este ejemplo, reemplaza `{name.ToUpper()}` con cada nombre, convertido a mayúsculas, porque se llama al método <xref:System.String.ToUpper%2A>.</span><span class="sxs-lookup"><span data-stu-id="b14f5-122">In this example, it replaces the `{name.ToUpper()}` with each name, converted to capital letters, because you called the <xref:System.String.ToUpper%2A> method.</span></span>

<span data-ttu-id="b14f5-123">Vamos a continuar indagando.</span><span class="sxs-lookup"><span data-stu-id="b14f5-123">Let's keep exploring.</span></span>
    
## <a name="modify-list-contents"></a><span data-ttu-id="b14f5-124">Modificación del contenido de las listas</span><span class="sxs-lookup"><span data-stu-id="b14f5-124">Modify list contents</span></span>

<span data-ttu-id="b14f5-125">La colección creada usa el tipo <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="b14f5-125">The collection you created uses the <xref:System.Collections.Generic.List%601> type.</span></span> <span data-ttu-id="b14f5-126">Este tipo almacena las secuencias de elementos.</span><span class="sxs-lookup"><span data-stu-id="b14f5-126">This type stores sequences of elements.</span></span> <span data-ttu-id="b14f5-127">Especifique el tipo de los elementos entre corchetes angulares.</span><span class="sxs-lookup"><span data-stu-id="b14f5-127">You specify the type of the elements between the angle brackets.</span></span>
    
<span data-ttu-id="b14f5-128">Un aspecto importante de este tipo <xref:System.Collections.Generic.List%601> es que se puede aumentar o reducir, lo que permite agregar o quitar elementos.</span><span class="sxs-lookup"><span data-stu-id="b14f5-128">One important aspect of this <xref:System.Collections.Generic.List%601> type is that it can grow or shrink, enabling you to add or remove elements.</span></span> <span data-ttu-id="b14f5-129">Agregue este código antes del corchete de cierre `}` en el método `Main`:</span><span class="sxs-lookup"><span data-stu-id="b14f5-129">Add this code before the closing `}` in the `Main` method:</span></span>

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

<span data-ttu-id="b14f5-130">Se han agregado dos nombres más al final de la lista.</span><span class="sxs-lookup"><span data-stu-id="b14f5-130">You've added two more names to the end of the list.</span></span> <span data-ttu-id="b14f5-131">También se ha quitado uno.</span><span class="sxs-lookup"><span data-stu-id="b14f5-131">You've also removed one as well.</span></span> <span data-ttu-id="b14f5-132">Guarde el archivo y escriba `dotnet run` para probarlo.</span><span class="sxs-lookup"><span data-stu-id="b14f5-132">Save the file, and type `dotnet run` to try it.</span></span>
    
<span data-ttu-id="b14f5-133"><xref:System.Collections.Generic.List%601> también permite hacer referencia a elementos individuales a través del **índice**.</span><span class="sxs-lookup"><span data-stu-id="b14f5-133">The <xref:System.Collections.Generic.List%601> enables you to reference individual items by **index** as well.</span></span> <span data-ttu-id="b14f5-134">Coloque el índice entre los tokens `[` y `]` después del nombre de la lista.</span><span class="sxs-lookup"><span data-stu-id="b14f5-134">You place the index between `[` and `]` tokens following the list name.</span></span> <span data-ttu-id="b14f5-135">C# utiliza 0 para el primer índice.</span><span class="sxs-lookup"><span data-stu-id="b14f5-135">C# uses 0 for the first index.</span></span> <span data-ttu-id="b14f5-136">Agregue este código directamente después del código que acaba de agregar y pruébelo:</span><span class="sxs-lookup"><span data-stu-id="b14f5-136">Add this code directly below the code you just added and try it:</span></span>

```csharp
Console.WriteLine($"My name is {names[0]}");
Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");
```

<span data-ttu-id="b14f5-137">No se puede acceder a un índice si se coloca después del final de la lista.</span><span class="sxs-lookup"><span data-stu-id="b14f5-137">You cannot access an index beyond the end of the list.</span></span> <span data-ttu-id="b14f5-138">Recuerde que los índices empiezan en 0, por lo que el índice más grande válido es uno menos que el número de elementos de la lista.</span><span class="sxs-lookup"><span data-stu-id="b14f5-138">Remember that indices start at 0, so the largest valid index is one less than the number of items in the list.</span></span> <span data-ttu-id="b14f5-139">Puede comprobar durante cuánto tiempo la lista usa la propiedad <xref:System.Collections.Generic.List%601.Count%2A>.</span><span class="sxs-lookup"><span data-stu-id="b14f5-139">You can check how long the list is using the <xref:System.Collections.Generic.List%601.Count%2A> property.</span></span> <span data-ttu-id="b14f5-140">Agregue el código siguiente al final del método Main:</span><span class="sxs-lookup"><span data-stu-id="b14f5-140">Add the following code at the end of the Main method:</span></span>

```csharp
Console.WriteLine($"The list has {names.Count} people in it");
 ```

<span data-ttu-id="b14f5-141">Guarde el archivo y vuelva a escribir `dotnet run` para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="b14f5-141">Save the file, and type `dotnet run` again to see the results.</span></span>    

## <a name="search-and-sort-lists"></a><span data-ttu-id="b14f5-142">Búsqueda y orden en las listas</span><span class="sxs-lookup"><span data-stu-id="b14f5-142">Search and sort lists</span></span>
<span data-ttu-id="b14f5-143">En los ejemplos se usan listas relativamente pequeñas, pero las aplicaciones a menudo pueden crear listas que contengan muchos más elementos, en ocasiones, con una numeración que engloba millares.</span><span class="sxs-lookup"><span data-stu-id="b14f5-143">Our samples use relatively small lists, but your applications may often create lists with many more elements, sometimes numbering in the thousands.</span></span> <span data-ttu-id="b14f5-144">Para encontrar elementos en estas colecciones más grandes, debe buscar diferentes elementos en la lista.</span><span class="sxs-lookup"><span data-stu-id="b14f5-144">To find elements in these larger collections, you need to search the list for different items.</span></span> <span data-ttu-id="b14f5-145">El método <xref:System.Collections.Generic.List%601.IndexOf%2A> busca un elemento y devuelve su índice.</span><span class="sxs-lookup"><span data-stu-id="b14f5-145">The <xref:System.Collections.Generic.List%601.IndexOf%2A> method searches for an item and returns the index of the item.</span></span> <span data-ttu-id="b14f5-146">Agregue este código en la parte inferior del método `Main`:</span><span class="sxs-lookup"><span data-stu-id="b14f5-146">Add this code to the bottom of your `Main` method:</span></span>

```csharp
var index = names.IndexOf("Felipe");
if (index == -1)
{
    Console.WriteLine($"When an item is not found, IndexOf returns {index}");
} else
{
    Console.WriteLine($"The name {names[index]} is at index {index}");
}

index = names.IndexOf("Not Found");
if (index == -1)
{
    Console.WriteLine($"When an item is not found, IndexOf returns {index}");
} else
{
    Console.WriteLine($"The name {names[index]} is at index {index}");
    
}
```

<span data-ttu-id="b14f5-147">Los elementos de la lista también se pueden ordenar.</span><span class="sxs-lookup"><span data-stu-id="b14f5-147">The items in your list can be sorted as well.</span></span> <span data-ttu-id="b14f5-148">El método <xref:System.Collections.Generic.List%601.Sort%2A> ordena todos los elementos de la lista en su orden normal (por orden alfabético si se trata de cadenas).</span><span class="sxs-lookup"><span data-stu-id="b14f5-148">The <xref:System.Collections.Generic.List%601.Sort%2A> method sorts all the items in the list in their normal order (alphabetically in the case of strings).</span></span> <span data-ttu-id="b14f5-149">Agregue este código en la parte inferior del método `Main`:</span><span class="sxs-lookup"><span data-stu-id="b14f5-149">Add this code to the bottom of our `Main` method:</span></span>

```csharp
names.Sort();
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

<span data-ttu-id="b14f5-150">Guarde el archivo y escriba `dotnet run` para probar esta última versión.</span><span class="sxs-lookup"><span data-stu-id="b14f5-150">Save the file and type `dotnet run` to try this latest version.</span></span>

<span data-ttu-id="b14f5-151">Antes comenzar con la siguiente sección, se va a mover el código actual a un método independiente.</span><span class="sxs-lookup"><span data-stu-id="b14f5-151">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="b14f5-152">Con este paso, resulta más fácil empezar con un nuevo ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b14f5-152">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="b14f5-153">Cambie el nombre del método `Main` por `WorkingWithStrings` y escriba un método `Main` nuevo que llame a `WorkingWithStrings`.</span><span class="sxs-lookup"><span data-stu-id="b14f5-153">Rename your `Main` method to `WorkingWithStrings` and write a new `Main` method that calls `WorkingWithStrings`.</span></span> <span data-ttu-id="b14f5-154">Cuando termine, el código debe tener un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="b14f5-154">When you have finished, your code should look like this:</span></span>

```csharp
using System;
using System.Collections.Generic;

namespace list_quickstart
{
    class Program
    {
        static void Main(string[] args)
        {
            WorkingWithStrings();
        }

        public static void WorkingWithStrings()
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
            Console.WriteLine($"The name {names[index]} is at index {index}");

            var notFound = names.IndexOf("Not Found");
            Console.WriteLine($"When an item is not found, IndexOf returns {notFound}");

            names.Sort();
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }
        }
    }
}
```

## <a name="lists-of-other-types"></a><span data-ttu-id="b14f5-155">Listas de otros tipos</span><span class="sxs-lookup"><span data-stu-id="b14f5-155">Lists of other types</span></span>

<span data-ttu-id="b14f5-156">Hasta el momento, se ha usado el tipo `string` en las listas.</span><span class="sxs-lookup"><span data-stu-id="b14f5-156">You've been using the `string` type in lists so far.</span></span> <span data-ttu-id="b14f5-157">Se va a crear una lista <xref:System.Collections.Generic.List%601> con un tipo distinto.</span><span class="sxs-lookup"><span data-stu-id="b14f5-157">Let's make a <xref:System.Collections.Generic.List%601> using a different type.</span></span> <span data-ttu-id="b14f5-158">Se va a crear una serie de números.</span><span class="sxs-lookup"><span data-stu-id="b14f5-158">Let's build a set of numbers.</span></span> 

<span data-ttu-id="b14f5-159">Agregue lo siguiente en la parte inferior del método `Main` nuevo:</span><span class="sxs-lookup"><span data-stu-id="b14f5-159">Add the following to the bottom of your new `Main` method:</span></span>

```csharp
var fibonacciNumbers = new List<int> {1, 1};
```

<span data-ttu-id="b14f5-160">Se crea una lista de enteros y se definen los dos primeros enteros con el valor 1.</span><span class="sxs-lookup"><span data-stu-id="b14f5-160">That creates a list of integers, and sets the first two integers to the value 1.</span></span> <span data-ttu-id="b14f5-161">Son los dos primeros valores de una *sucesión de Fibonacci*, una secuencia de números.</span><span class="sxs-lookup"><span data-stu-id="b14f5-161">These are the first two values of a *Fibonacci Sequence*, a sequence of numbers.</span></span> <span data-ttu-id="b14f5-162">Cada número sucesivo de Fibonacci se obtiene con la suma de los dos números anteriores.</span><span class="sxs-lookup"><span data-stu-id="b14f5-162">Each next Fibonacci number is found by taking the sum of the previous two numbers.</span></span> <span data-ttu-id="b14f5-163">Agregue este código:</span><span class="sxs-lookup"><span data-stu-id="b14f5-163">Add this code:</span></span>

```csharp
var previous = fibonacciNumbers[fibonacciNumbers.Count - 1];
var previous2 = fibonacciNumbers[fibonacciNumbers.Count - 2];

fibonacciNumbers.Add(previous + previous2);

foreach(var item in fibonacciNumbers)
    Console.WriteLine(item);
```

<span data-ttu-id="b14f5-164">Guarde el archivo y escriba `dotnet run` para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="b14f5-164">Save the file and type `dotnet run` to see the results.</span></span> 

> [!TIP]
> <span data-ttu-id="b14f5-165">Para centrarse solo en esta sección, puede comentar el código que llama a `WorkingWithStrings();`.</span><span class="sxs-lookup"><span data-stu-id="b14f5-165">To concentrate on just this section, you can comment out the code that calls `WorkingWithStrings();`.</span></span> <span data-ttu-id="b14f5-166">Solo debe colocar dos caracteres `/` delante de la llamada, como en: `// WorkingWithStrings();`.</span><span class="sxs-lookup"><span data-stu-id="b14f5-166">Just put two `/` characters in front of the call like this:  `// WorkingWithStrings();`.</span></span> 

## <a name="challenge"></a><span data-ttu-id="b14f5-167">Desafío</span><span class="sxs-lookup"><span data-stu-id="b14f5-167">Challenge</span></span>
<span data-ttu-id="b14f5-168">Trate de recopilar los conceptos que ha aprendido en esta lección y en las anteriores.</span><span class="sxs-lookup"><span data-stu-id="b14f5-168">See if you can put together some of the concepts from this and earlier lessons.</span></span> <span data-ttu-id="b14f5-169">Amplíe lo que ha creado hasta el momento con los números de Fibonacci.</span><span class="sxs-lookup"><span data-stu-id="b14f5-169">Expand on what you've built so far with Fibonacci Numbers.</span></span> <span data-ttu-id="b14f5-170">Pruebe a escribir el código para generar los veinte primeros números de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="b14f5-170">Try to write the code to generate the first 20 numbers in the sequence.</span></span> <span data-ttu-id="b14f5-171">(Como sugerencia, el 20º número de la serie de Fibonacci es 6765).</span><span class="sxs-lookup"><span data-stu-id="b14f5-171">(As a hint, the 20th Fibonacci number is 6765.)</span></span>

## <a name="complete-challenge"></a><span data-ttu-id="b14f5-172">Desafío completo</span><span class="sxs-lookup"><span data-stu-id="b14f5-172">Complete challenge</span></span>

<span data-ttu-id="b14f5-173">Puede ver un ejemplo de solución si [consulta el ejemplo de código terminado en GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/list-quickstart/Program.cs#L13-L23).</span><span class="sxs-lookup"><span data-stu-id="b14f5-173">You can see an example solution by [looking at the finished sample code on GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/list-quickstart/Program.cs#L13-L23)</span></span>

<span data-ttu-id="b14f5-174">Con cada iteración del bucle, se obtienen los dos últimos enteros de la lista, se suman y se agrega el valor resultante a la lista.</span><span class="sxs-lookup"><span data-stu-id="b14f5-174">With each iteration of the loop, you're taking the last two integers in the list, summing them, and adding that value to the list.</span></span> <span data-ttu-id="b14f5-175">El bucle se repite hasta que se hayan agregado veinte elementos a la lista.</span><span class="sxs-lookup"><span data-stu-id="b14f5-175">The loop repeats until you've added 20 items to the list.</span></span>

<span data-ttu-id="b14f5-176">Enhorabuena, ha completado la guía de inicio rápido sobre las listas.</span><span class="sxs-lookup"><span data-stu-id="b14f5-176">Congratulations, you've completed the list quick start.</span></span> <span data-ttu-id="b14f5-177">Puede continuar con la guía de inicio rápido [Introducción a las clases](introduction-to-classes.md) en su propio entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="b14f5-177">You can continue with the [Introduction to classes](introduction-to-classes.md) quick start in your own development environment.</span></span>

<span data-ttu-id="b14f5-178">Puede obtener más información sobre cómo trabajar con el tipo `List` en el tema de la [Guía de .NET](../../standard/index.md) que trata sobre las [colecciones](../../standard/collections/index.md).</span><span class="sxs-lookup"><span data-stu-id="b14f5-178">You can learn more about working with the `List` type in the [.NET Guide](../../standard/index.md) topic on [collections](../../standard/collections/index.md).</span></span> <span data-ttu-id="b14f5-179">Ahí también podrá conocer muchos otros tipos de colecciones.</span><span class="sxs-lookup"><span data-stu-id="b14f5-179">You'll also learn about many other collection types.</span></span>
