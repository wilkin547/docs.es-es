---
title: 'Trabajo con colecciones: tutorial de introducción a C#'
description: Conozca C# a través de la colección de listas que se presenta en este tutorial.
ms.date: 02/05/2021
ms.openlocfilehash: 7a04a983622a6ae36ec5b12d279aa29e52c52a4f
ms.sourcegitcommit: f0fc5db7bcbf212e46933e9cf2d555bb82666141
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "100626685"
---
# <a name="learn-to-manage-data-collections-using-the-generic-list-type"></a><span data-ttu-id="73ed6-103">Obtenga información sobre cómo administrar colecciones de datos mediante el tipo de lista genérico</span><span class="sxs-lookup"><span data-stu-id="73ed6-103">Learn to manage data collections using the generic list type</span></span>

<span data-ttu-id="73ed6-104">En este tutorial de presentación se proporciona una introducción al lenguaje C# y se exponen los conceptos básicos de la clase <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="73ed6-104">This introductory tutorial provides an introduction to the C# language and the basics of the <xref:System.Collections.Generic.List%601> class.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="73ed6-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="73ed6-105">Prerequisites</span></span>

<span data-ttu-id="73ed6-106">En el tutorial se espera que tenga una máquina configurada para el desarrollo local.</span><span class="sxs-lookup"><span data-stu-id="73ed6-106">The tutorial expects that you have a machine set up for local development.</span></span> <span data-ttu-id="73ed6-107">En Windows, Linux o macOS, puede usar la CLI de .NET para crear, compilar y ejecutar aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="73ed6-107">On Windows, Linux, or macOS, you can use the .NET CLI to create, build, and run applications.</span></span> <span data-ttu-id="73ed6-108">En Mac y Windows, también puede usar Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="73ed6-108">On Mac and Windows, you can use Visual Studio 2019.</span></span> <span data-ttu-id="73ed6-109">Para obtener instrucciones de configuración, consulte cómo [configurar el entorno local](local-environment.md).</span><span class="sxs-lookup"><span data-stu-id="73ed6-109">For setup instructions, see [Set up your local environment](local-environment.md).</span></span>

## <a name="a-basic-list-example"></a><span data-ttu-id="73ed6-110">Un ejemplo de lista básico</span><span class="sxs-lookup"><span data-stu-id="73ed6-110">A basic list example</span></span>

<span data-ttu-id="73ed6-111">Cree un directorio denominado *list-tutorial*.</span><span class="sxs-lookup"><span data-stu-id="73ed6-111">Create a directory named *list-tutorial*.</span></span> <span data-ttu-id="73ed6-112">Conviértalo en el directorio actual y ejecute `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="73ed6-112">Make that the current directory and run `dotnet new console`.</span></span>

<span data-ttu-id="73ed6-113">Abra *Program.cs* en su editor favorito y reemplace el código existente por el siguiente:</span><span class="sxs-lookup"><span data-stu-id="73ed6-113">Open *Program.cs* in your favorite editor, and replace the existing code with the following:</span></span>

```csharp
using System;
using System.Collections.Generic;

var names = new List<string> { "<name>", "Ana", "Felipe" };
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

<span data-ttu-id="73ed6-114">Reemplace `<name>` por su propio nombre.</span><span class="sxs-lookup"><span data-stu-id="73ed6-114">Replace `<name>` with your name.</span></span> <span data-ttu-id="73ed6-115">Guarde *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="73ed6-115">Save *Program.cs*.</span></span> <span data-ttu-id="73ed6-116">Escriba `dotnet run` en la ventana de la consola para probarlo.</span><span class="sxs-lookup"><span data-stu-id="73ed6-116">Type `dotnet run` in your console window to try it.</span></span>

<span data-ttu-id="73ed6-117">Ha creado una lista de cadenas, ha agregado tres nombres a esa lista y ha impreso los nombres en MAYÚSCULAS.</span><span class="sxs-lookup"><span data-stu-id="73ed6-117">You've created a list of strings, added three names to that list, and printed the names in all CAPS.</span></span> <span data-ttu-id="73ed6-118">Los conceptos aplicados ya se han aprendido en los tutoriales anteriores para recorrer en bucle la lista.</span><span class="sxs-lookup"><span data-stu-id="73ed6-118">You're using concepts that you've learned in earlier tutorials to loop through the list.</span></span>

<span data-ttu-id="73ed6-119">El código para mostrar los nombres usa la característica [interpolación de cadenas](../../language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="73ed6-119">The code to display names makes use of the [string interpolation](../../language-reference/tokens/interpolated.md) feature.</span></span>  <span data-ttu-id="73ed6-120">Si un valor de `string` va precedido del carácter `$`, significa que puede insertar código de C# en la declaración de cadena.</span><span class="sxs-lookup"><span data-stu-id="73ed6-120">When you precede a `string` with the `$` character, you can embed C# code in the string declaration.</span></span> <span data-ttu-id="73ed6-121">La cadena real reemplaza a ese código de C# con el valor que genera.</span><span class="sxs-lookup"><span data-stu-id="73ed6-121">The actual string replaces that C# code with the value it generates.</span></span> <span data-ttu-id="73ed6-122">En este ejemplo, reemplaza `{name.ToUpper()}` con cada nombre, convertido a mayúsculas, porque se llama al método <xref:System.String.ToUpper%2A>.</span><span class="sxs-lookup"><span data-stu-id="73ed6-122">In this example, it replaces the `{name.ToUpper()}` with each name, converted to capital letters, because you called the <xref:System.String.ToUpper%2A> method.</span></span>

<span data-ttu-id="73ed6-123">Vamos a continuar indagando.</span><span class="sxs-lookup"><span data-stu-id="73ed6-123">Let's keep exploring.</span></span>

## <a name="modify-list-contents"></a><span data-ttu-id="73ed6-124">Modificación del contenido de las listas</span><span class="sxs-lookup"><span data-stu-id="73ed6-124">Modify list contents</span></span>

<span data-ttu-id="73ed6-125">La colección creada usa el tipo <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="73ed6-125">The collection you created uses the <xref:System.Collections.Generic.List%601> type.</span></span> <span data-ttu-id="73ed6-126">Este tipo almacena las secuencias de elementos.</span><span class="sxs-lookup"><span data-stu-id="73ed6-126">This type stores sequences of elements.</span></span> <span data-ttu-id="73ed6-127">Especifique el tipo de los elementos entre corchetes angulares.</span><span class="sxs-lookup"><span data-stu-id="73ed6-127">You specify the type of the elements between the angle brackets.</span></span>

<span data-ttu-id="73ed6-128">Un aspecto importante de este tipo <xref:System.Collections.Generic.List%601> es que se puede aumentar o reducir, lo que permite agregar o quitar elementos.</span><span class="sxs-lookup"><span data-stu-id="73ed6-128">One important aspect of this <xref:System.Collections.Generic.List%601> type is that it can grow or shrink, enabling you to add or remove elements.</span></span> <span data-ttu-id="73ed6-129">Agregue este código al final del programa:</span><span class="sxs-lookup"><span data-stu-id="73ed6-129">Add this code at the end of your program:</span></span>

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

<span data-ttu-id="73ed6-130">Se han agregado dos nombres más al final de la lista.</span><span class="sxs-lookup"><span data-stu-id="73ed6-130">You've added two more names to the end of the list.</span></span> <span data-ttu-id="73ed6-131">También se ha quitado uno.</span><span class="sxs-lookup"><span data-stu-id="73ed6-131">You've also removed one as well.</span></span> <span data-ttu-id="73ed6-132">Guarde el archivo y escriba `dotnet run` para probarlo.</span><span class="sxs-lookup"><span data-stu-id="73ed6-132">Save the file, and type `dotnet run` to try it.</span></span>

<span data-ttu-id="73ed6-133"><xref:System.Collections.Generic.List%601> también permite hacer referencia a elementos individuales a través del **índice**.</span><span class="sxs-lookup"><span data-stu-id="73ed6-133">The <xref:System.Collections.Generic.List%601> enables you to reference individual items by **index** as well.</span></span> <span data-ttu-id="73ed6-134">Coloque el índice entre los tokens `[` y `]` después del nombre de la lista.</span><span class="sxs-lookup"><span data-stu-id="73ed6-134">You place the index between `[` and `]` tokens following the list name.</span></span> <span data-ttu-id="73ed6-135">C# utiliza 0 para el primer índice.</span><span class="sxs-lookup"><span data-stu-id="73ed6-135">C# uses 0 for the first index.</span></span> <span data-ttu-id="73ed6-136">Agregue este código directamente después del código que acaba de agregar y pruébelo:</span><span class="sxs-lookup"><span data-stu-id="73ed6-136">Add this code directly below the code you just added and try it:</span></span>

```csharp
Console.WriteLine($"My name is {names[0]}");
Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");
```

<span data-ttu-id="73ed6-137">No se puede acceder a un índice si se coloca después del final de la lista.</span><span class="sxs-lookup"><span data-stu-id="73ed6-137">You can't access an index beyond the end of the list.</span></span> <span data-ttu-id="73ed6-138">Recuerde que los índices empiezan en 0, por lo que el índice más grande válido es uno menos que el número de elementos de la lista.</span><span class="sxs-lookup"><span data-stu-id="73ed6-138">Remember that indices start at 0, so the largest valid index is one less than the number of items in the list.</span></span> <span data-ttu-id="73ed6-139">Puede comprobar durante cuánto tiempo la lista usa la propiedad <xref:System.Collections.Generic.List%601.Count%2A>.</span><span class="sxs-lookup"><span data-stu-id="73ed6-139">You can check how long the list is using the <xref:System.Collections.Generic.List%601.Count%2A> property.</span></span> <span data-ttu-id="73ed6-140">Agregue el código siguiente al final del programa:</span><span class="sxs-lookup"><span data-stu-id="73ed6-140">Add the following code at the end of your program:</span></span>

```csharp
Console.WriteLine($"The list has {names.Count} people in it");
 ```

<span data-ttu-id="73ed6-141">Guarde el archivo y vuelva a escribir `dotnet run` para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="73ed6-141">Save the file, and type `dotnet run` again to see the results.</span></span>

## <a name="search-and-sort-lists"></a><span data-ttu-id="73ed6-142">Búsqueda y orden en las listas</span><span class="sxs-lookup"><span data-stu-id="73ed6-142">Search and sort lists</span></span>

<span data-ttu-id="73ed6-143">En los ejemplos se usan listas relativamente pequeñas, pero las aplicaciones a menudo pueden crear listas que contengan muchos más elementos, en ocasiones, con una numeración que engloba millares.</span><span class="sxs-lookup"><span data-stu-id="73ed6-143">Our samples use relatively small lists, but your applications may often create lists with many more elements, sometimes numbering in the thousands.</span></span> <span data-ttu-id="73ed6-144">Para encontrar elementos en estas colecciones más grandes, debe buscar diferentes elementos en la lista.</span><span class="sxs-lookup"><span data-stu-id="73ed6-144">To find elements in these larger collections, you need to search the list for different items.</span></span> <span data-ttu-id="73ed6-145">El método <xref:System.Collections.Generic.List%601.IndexOf%2A> busca un elemento y devuelve su índice.</span><span class="sxs-lookup"><span data-stu-id="73ed6-145">The <xref:System.Collections.Generic.List%601.IndexOf%2A> method searches for an item and returns the index of the item.</span></span> <span data-ttu-id="73ed6-146">Si el elemento no está en la lista, `IndexOf` devuelve `-1`.</span><span class="sxs-lookup"><span data-stu-id="73ed6-146">If the item isn't in the list, `IndexOf` returns `-1`.</span></span> <span data-ttu-id="73ed6-147">Agregue este código a la parte inferior del programa:</span><span class="sxs-lookup"><span data-stu-id="73ed6-147">Add this code to the bottom of your program:</span></span>

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

<span data-ttu-id="73ed6-148">Los elementos de la lista también se pueden ordenar.</span><span class="sxs-lookup"><span data-stu-id="73ed6-148">The items in your list can be sorted as well.</span></span> <span data-ttu-id="73ed6-149">El método <xref:System.Collections.Generic.List%601.Sort%2A> clasifica todos los elementos de la lista en su orden normal (por orden alfabético si se trata de cadenas).</span><span class="sxs-lookup"><span data-stu-id="73ed6-149">The <xref:System.Collections.Generic.List%601.Sort%2A> method sorts all the items in the list in their normal order (alphabetically for strings).</span></span> <span data-ttu-id="73ed6-150">Agregue este código a la parte inferior del programa:</span><span class="sxs-lookup"><span data-stu-id="73ed6-150">Add this code to the bottom of your program:</span></span>

```csharp
names.Sort();
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

<span data-ttu-id="73ed6-151">Guarde el archivo y escriba `dotnet run` para probar esta última versión.</span><span class="sxs-lookup"><span data-stu-id="73ed6-151">Save the file and type `dotnet run` to try this latest version.</span></span>

<span data-ttu-id="73ed6-152">Antes comenzar con la siguiente sección, se va a mover el código actual a un método independiente.</span><span class="sxs-lookup"><span data-stu-id="73ed6-152">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="73ed6-153">Con este paso, resulta más fácil empezar con un nuevo ejemplo.</span><span class="sxs-lookup"><span data-stu-id="73ed6-153">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="73ed6-154">Coloque todo el código que ha escrito en un nuevo método denominado `WorkWithStrings()`.</span><span class="sxs-lookup"><span data-stu-id="73ed6-154">Place all the code you've written in a new method called `WorkWithStrings()`.</span></span> <span data-ttu-id="73ed6-155">Llame a ese método en la parte superior del programa.</span><span class="sxs-lookup"><span data-stu-id="73ed6-155">Call that method at the top of your program.</span></span> <span data-ttu-id="73ed6-156">Cuando termine, el código debe tener un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="73ed6-156">When you finish, your code should look like this:</span></span>

```csharp
using System;
using System.Collections.Generic;

WorkWithString();

void WorkWithString()
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
```

## <a name="lists-of-other-types"></a><span data-ttu-id="73ed6-157">Listas de otros tipos</span><span class="sxs-lookup"><span data-stu-id="73ed6-157">Lists of other types</span></span>

<span data-ttu-id="73ed6-158">Hasta el momento, se ha usado el tipo `string` en las listas.</span><span class="sxs-lookup"><span data-stu-id="73ed6-158">You've been using the `string` type in lists so far.</span></span> <span data-ttu-id="73ed6-159">Se va a crear una lista <xref:System.Collections.Generic.List%601> con un tipo distinto.</span><span class="sxs-lookup"><span data-stu-id="73ed6-159">Let's make a <xref:System.Collections.Generic.List%601> using a different type.</span></span> <span data-ttu-id="73ed6-160">Se va a crear una serie de números.</span><span class="sxs-lookup"><span data-stu-id="73ed6-160">Let's build a set of numbers.</span></span>

<span data-ttu-id="73ed6-161">Agregue lo siguiente al programa después de llamar a `WorkWithStrings()`:</span><span class="sxs-lookup"><span data-stu-id="73ed6-161">Add the following to your program after you call `WorkWithStrings()`:</span></span>

```csharp
var fibonacciNumbers = new List<int> {1, 1};
```

<span data-ttu-id="73ed6-162">Se crea una lista de enteros y se definen los dos primeros enteros con el valor 1.</span><span class="sxs-lookup"><span data-stu-id="73ed6-162">That creates a list of integers, and sets the first two integers to the value 1.</span></span> <span data-ttu-id="73ed6-163">Son los dos primeros valores de una *sucesión de Fibonacci*, una secuencia de números.</span><span class="sxs-lookup"><span data-stu-id="73ed6-163">These are the first two values of a *Fibonacci Sequence*, a sequence of numbers.</span></span> <span data-ttu-id="73ed6-164">Cada número sucesivo de Fibonacci se obtiene con la suma de los dos números anteriores.</span><span class="sxs-lookup"><span data-stu-id="73ed6-164">Each next Fibonacci number is found by taking the sum of the previous two numbers.</span></span> <span data-ttu-id="73ed6-165">Agregue este código:</span><span class="sxs-lookup"><span data-stu-id="73ed6-165">Add this code:</span></span>

```csharp
var previous = fibonacciNumbers[fibonacciNumbers.Count - 1];
var previous2 = fibonacciNumbers[fibonacciNumbers.Count - 2];

fibonacciNumbers.Add(previous + previous2);

foreach (var item in fibonacciNumbers)
    Console.WriteLine(item);
```

<span data-ttu-id="73ed6-166">Guarde el archivo y escriba `dotnet run` para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="73ed6-166">Save the file and type `dotnet run` to see the results.</span></span>

> [!TIP]
> <span data-ttu-id="73ed6-167">Para centrarse solo en esta sección, puede comentar el código que llama a `WorkingWithStrings();`.</span><span class="sxs-lookup"><span data-stu-id="73ed6-167">To concentrate on just this section, you can comment out the code that calls `WorkingWithStrings();`.</span></span> <span data-ttu-id="73ed6-168">Solo debe colocar dos caracteres `/` delante de la llamada, como en: `// WorkingWithStrings();`.</span><span class="sxs-lookup"><span data-stu-id="73ed6-168">Just put two `/` characters in front of the call like this:  `// WorkingWithStrings();`.</span></span>

## <a name="challenge"></a><span data-ttu-id="73ed6-169">Desafío</span><span class="sxs-lookup"><span data-stu-id="73ed6-169">Challenge</span></span>

<span data-ttu-id="73ed6-170">Trate de recopilar los conceptos que ha aprendido en esta lección y en las anteriores.</span><span class="sxs-lookup"><span data-stu-id="73ed6-170">See if you can put together some of the concepts from this and earlier lessons.</span></span> <span data-ttu-id="73ed6-171">Amplíe lo que ha creado hasta el momento con los números de Fibonacci.</span><span class="sxs-lookup"><span data-stu-id="73ed6-171">Expand on what you've built so far with Fibonacci Numbers.</span></span> <span data-ttu-id="73ed6-172">Pruebe a escribir el código para generar los veinte primeros números de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="73ed6-172">Try to write the code to generate the first 20 numbers in the sequence.</span></span> <span data-ttu-id="73ed6-173">(Como sugerencia, el 20º número de la serie de Fibonacci es 6765).</span><span class="sxs-lookup"><span data-stu-id="73ed6-173">(As a hint, the 20th Fibonacci number is 6765.)</span></span>

## <a name="complete-challenge"></a><span data-ttu-id="73ed6-174">Desafío completo</span><span class="sxs-lookup"><span data-stu-id="73ed6-174">Complete challenge</span></span>

<span data-ttu-id="73ed6-175">Puede ver un ejemplo de solución en el [ejemplo de código terminado en GitHub](https://github.com/dotnet/samples/tree/master/csharp/list-quickstart/Program.cs#L8-L16).</span><span class="sxs-lookup"><span data-stu-id="73ed6-175">You can see an example solution by [looking at the finished sample code on GitHub](https://github.com/dotnet/samples/tree/master/csharp/list-quickstart/Program.cs#L8-L16).</span></span>

<span data-ttu-id="73ed6-176">Con cada iteración del bucle, se obtienen los dos últimos enteros de la lista, se suman y se agrega el valor resultante a la lista.</span><span class="sxs-lookup"><span data-stu-id="73ed6-176">With each iteration of the loop, you're taking the last two integers in the list, summing them, and adding that value to the list.</span></span> <span data-ttu-id="73ed6-177">El bucle se repite hasta que se hayan agregado veinte elementos a la lista.</span><span class="sxs-lookup"><span data-stu-id="73ed6-177">The loop repeats until you've added 20 items to the list.</span></span>

<span data-ttu-id="73ed6-178">Enhorabuena, ha completado el tutorial sobre las listas.</span><span class="sxs-lookup"><span data-stu-id="73ed6-178">Congratulations, you've completed the list tutorial.</span></span> <span data-ttu-id="73ed6-179">Puede seguir estos tutoriales [adicionales](../../tutorials/index.md) en su propio entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="73ed6-179">You can continue with [additional](../../tutorials/index.md) tutorials in your own development environment.</span></span>

<span data-ttu-id="73ed6-180">Puede obtener más información sobre cómo trabajar con el tipo `List` en el artículo de los aspectos básicos de .NET que trata sobre las [colecciones](../../../standard/collections/index.md).</span><span class="sxs-lookup"><span data-stu-id="73ed6-180">You can learn more about working with the `List` type in the .NET fundamentals article on [collections](../../../standard/collections/index.md).</span></span> <span data-ttu-id="73ed6-181">Ahí también podrá conocer muchos otros tipos de colecciones.</span><span class="sxs-lookup"><span data-stu-id="73ed6-181">You'll also learn about many other collection types.</span></span>
