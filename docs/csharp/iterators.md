---
title: Iterators
description: Obtenga información sobre cómo usar iteradores de C# integrados y cómo crear sus propios métodos de iterador personalizados.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: 5cf36f45-f91a-4fca-a0b7-87f233e108e9
ms.openlocfilehash: ee72331cb85ba1a03d48e2f58526ad432c7fe6d4
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656103"
---
# <a name="iterators"></a><span data-ttu-id="6fd78-103">Iterators</span><span class="sxs-lookup"><span data-stu-id="6fd78-103">Iterators</span></span>

<span data-ttu-id="6fd78-104">Prácticamente todos los programas que escriba tendrán alguna necesidad de recorrer en iteración una colección.</span><span class="sxs-lookup"><span data-stu-id="6fd78-104">Almost every program you write will have some need to iterate over a collection.</span></span> <span data-ttu-id="6fd78-105">Va a escribir código que examine cada elemento de una colección.</span><span class="sxs-lookup"><span data-stu-id="6fd78-105">You'll write code that examines every item in a collection.</span></span>

<span data-ttu-id="6fd78-106">También va a crear métodos de iterador, que son los métodos que genera un iterador (un objeto que atraviesa un contenedor, especialmente listas) para los elementos de esa clase.</span><span class="sxs-lookup"><span data-stu-id="6fd78-106">You'll also create iterator methods which are methods that produces an iterator (which is an object that traverses a container, particularly lists) for the elements of that class.</span></span> <span data-ttu-id="6fd78-107">Se pueden usar para:</span><span class="sxs-lookup"><span data-stu-id="6fd78-107">These can be used for:</span></span>

+ <span data-ttu-id="6fd78-108">Realizar una acción en cada elemento de una colección.</span><span class="sxs-lookup"><span data-stu-id="6fd78-108">Performing an action on each item in a collection.</span></span>
+ <span data-ttu-id="6fd78-109">Enumerar una colección personalizada.</span><span class="sxs-lookup"><span data-stu-id="6fd78-109">Enumerating a custom collection.</span></span>
+ <span data-ttu-id="6fd78-110">Extender [LINQ](linq/index.md) u otras bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="6fd78-110">Extending [LINQ](linq/index.md) or other libraries.</span></span>
+ <span data-ttu-id="6fd78-111">Crear una canalización de datos en la que los datos fluyan de forma eficaz mediante métodos de iterador.</span><span class="sxs-lookup"><span data-stu-id="6fd78-111">Creating a data pipeline where data flows efficiently through iterator methods.</span></span>

<span data-ttu-id="6fd78-112">El lenguaje C# proporciona características para ambos escenarios.</span><span class="sxs-lookup"><span data-stu-id="6fd78-112">The C# language provides features for both these scenarios.</span></span> <span data-ttu-id="6fd78-113">Este artículo proporciona información general sobre esas características.</span><span class="sxs-lookup"><span data-stu-id="6fd78-113">This article provides an overview of those features.</span></span>

<span data-ttu-id="6fd78-114">Este tutorial consta de varios pasos.</span><span class="sxs-lookup"><span data-stu-id="6fd78-114">This tutorial has multiple steps.</span></span> <span data-ttu-id="6fd78-115">Después de cada paso, puede ejecutar la aplicación y ver el progreso.</span><span class="sxs-lookup"><span data-stu-id="6fd78-115">After each step, you can run the application and see the progress.</span></span> <span data-ttu-id="6fd78-116">También puede [ver o descargar el ejemplo completo](https://github.com/dotnet/samples/blob/master/csharp/iterators) para este tema.</span><span class="sxs-lookup"><span data-stu-id="6fd78-116">You can also [view or download the completed sample](https://github.com/dotnet/samples/blob/master/csharp/iterators) for this topic.</span></span> <span data-ttu-id="6fd78-117">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../samples-and-tutorials/index.md#view-and-download-samples).</span><span class="sxs-lookup"><span data-stu-id="6fd78-117">For download instructions, see [Samples and Tutorials](../samples-and-tutorials/index.md#view-and-download-samples).</span></span>

## <a name="iterating-with-foreach"></a><span data-ttu-id="6fd78-118">Iteración con foreach</span><span class="sxs-lookup"><span data-stu-id="6fd78-118">Iterating with foreach</span></span>

<span data-ttu-id="6fd78-119">Enumerar una colección es sencillo: la palabra clave `foreach` enumera una colección, ejecutando la instrucción incrustada una vez para cada elemento de la colección:</span><span class="sxs-lookup"><span data-stu-id="6fd78-119">Enumerating a collection is simple: The `foreach` keyword enumerates a collection, executing the embedded statement once for each element in the collection:</span></span>

```csharp
foreach (var item in collection)
{
   Console.WriteLine(item.ToString());
}
```

<span data-ttu-id="6fd78-120">Así de simple.</span><span class="sxs-lookup"><span data-stu-id="6fd78-120">That's all there is to it.</span></span> <span data-ttu-id="6fd78-121">Para recorrer en iteración todo el contenido de una colección, la instrucción `foreach` es todo lo que necesita.</span><span class="sxs-lookup"><span data-stu-id="6fd78-121">To iterate over all the contents of a collection, the `foreach` statement is all you need.</span></span> <span data-ttu-id="6fd78-122">Pero la instrucción `foreach` no es mágica.</span><span class="sxs-lookup"><span data-stu-id="6fd78-122">The `foreach` statement isn't magic, though.</span></span> <span data-ttu-id="6fd78-123">Depende de dos interfaces genéricas definidas en la biblioteca de .NET Core para generar el código necesario para recorrer en iteración una colección: `IEnumerable<T>` e `IEnumerator<T>`.</span><span class="sxs-lookup"><span data-stu-id="6fd78-123">It relies on two generic interfaces defined in the .NET core library in order to generate the code necessary to iterate a collection: `IEnumerable<T>` and `IEnumerator<T>`.</span></span> <span data-ttu-id="6fd78-124">Este mecanismo se explica con más detalle a continuación.</span><span class="sxs-lookup"><span data-stu-id="6fd78-124">This mechanism is explained in more detail below.</span></span>

<span data-ttu-id="6fd78-125">Ambas interfaces tienen también homólogas no genéricas: `IEnumerable` e `IEnumerator`.</span><span class="sxs-lookup"><span data-stu-id="6fd78-125">Both of these interfaces also have non-generic counterparts: `IEnumerable` and `IEnumerator`.</span></span> <span data-ttu-id="6fd78-126">Para el código moderno se prefieren las versiones [genéricas](programming-guide/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="6fd78-126">The [generic](programming-guide/generics/index.md) versions are preferred for modern code.</span></span>

## <a name="enumeration-sources-with-iterator-methods"></a><span data-ttu-id="6fd78-127">Orígenes de enumeración con métodos de iterador</span><span class="sxs-lookup"><span data-stu-id="6fd78-127">Enumeration sources with iterator methods</span></span>

<span data-ttu-id="6fd78-128">Otra magnífica característica del lenguaje C# permite generar métodos que crean un origen para una enumeración.</span><span class="sxs-lookup"><span data-stu-id="6fd78-128">Another great feature of the C# language enables you to build methods that create a source for an enumeration.</span></span> <span data-ttu-id="6fd78-129">Se conocen como *métodos de iterador*.</span><span class="sxs-lookup"><span data-stu-id="6fd78-129">These are referred to as *iterator methods*.</span></span> <span data-ttu-id="6fd78-130">Un método de iterador define cómo generar los objetos de una secuencia cuando se solicita.</span><span class="sxs-lookup"><span data-stu-id="6fd78-130">An iterator method defines how to generate the objects in a sequence when requested.</span></span> <span data-ttu-id="6fd78-131">Para definir un método de iterador se usan las palabras clave contextuales `yield return`.</span><span class="sxs-lookup"><span data-stu-id="6fd78-131">You use the `yield return` contextual keywords to define an iterator method.</span></span>

<span data-ttu-id="6fd78-132">Podría escribir este método para generar la secuencia de enteros de 0 a 9:</span><span class="sxs-lookup"><span data-stu-id="6fd78-132">You could write this method to produce the sequence of integers from 0 through 9:</span></span>

```csharp
public IEnumerable<int> GetSingleDigitNumbers()
{
    yield return 0;
    yield return 1;
    yield return 2;
    yield return 3;
    yield return 4;
    yield return 5;
    yield return 6;
    yield return 7;
    yield return 8;
    yield return 9;
}
```

<span data-ttu-id="6fd78-133">El código anterior muestra instrucciones distintivas `yield return` para resaltar el hecho de que se pueden usar varias instrucciones discretas `yield return` en un método de iterador.</span><span class="sxs-lookup"><span data-stu-id="6fd78-133">The code above shows distinct `yield return` statements to highlight the fact that you can use multiple discrete `yield return` statements in an iterator method.</span></span>
<span data-ttu-id="6fd78-134">Puede usar (y hágalo a menudo) otras construcciones de lenguaje para simplificar el código de un método de iterador.</span><span class="sxs-lookup"><span data-stu-id="6fd78-134">You can (and often do) use other language constructs to simplify the code of an iterator method.</span></span> <span data-ttu-id="6fd78-135">La definición del método siguiente genera la misma secuencia de números:</span><span class="sxs-lookup"><span data-stu-id="6fd78-135">The method definition below produces the exact same sequence of numbers:</span></span>

```csharp
public IEnumerable<int> GetSingleDigitNumbers()
{
    int index = 0;
    while (index < 10)
        yield return index++;
}
```

<span data-ttu-id="6fd78-136">No tiene que elegir entre una y otra.</span><span class="sxs-lookup"><span data-stu-id="6fd78-136">You don't have to decide one or the other.</span></span> <span data-ttu-id="6fd78-137">Puede tener tantas instrucciones `yield return` como sea necesario para satisfacer las necesidades del método:</span><span class="sxs-lookup"><span data-stu-id="6fd78-137">You can have as many `yield return` statements as necessary to meet the needs of your method:</span></span>

```csharp
public IEnumerable<int> GetSingleDigitNumbers()
{
    int index = 0;
    while (index < 10)
        yield return index++;

    yield return 50;

    index = 100;
    while (index < 110)
        yield return index++;
}
```

<span data-ttu-id="6fd78-138">Esa es la sintaxis básica.</span><span class="sxs-lookup"><span data-stu-id="6fd78-138">That's the basic syntax.</span></span> <span data-ttu-id="6fd78-139">Veamos un ejemplo del mundo real en el que se escribe un método de iterador.</span><span class="sxs-lookup"><span data-stu-id="6fd78-139">Let's consider a real world example where you would write an iterator method.</span></span> <span data-ttu-id="6fd78-140">Imagine que se encuentra en un proyecto de IoT y los sensores del dispositivo generan un flujo de datos muy grande.</span><span class="sxs-lookup"><span data-stu-id="6fd78-140">Imagine you're on an IoT project and the device sensors generate a very large stream of data.</span></span> <span data-ttu-id="6fd78-141">Para hacerse una idea de los datos, podría escribir un método que tomara muestras de cada enésimo elemento de datos.</span><span class="sxs-lookup"><span data-stu-id="6fd78-141">To get a feel for the data, you might write a method that samples every Nth data element.</span></span> <span data-ttu-id="6fd78-142">Este pequeño método de iterador lo hace:</span><span class="sxs-lookup"><span data-stu-id="6fd78-142">This small iterator method does the trick:</span></span>

```csharp
public static IEnumerable<T> Sample(this IEnumerable<T> sourceSequence, int interval)
{
    int index = 0;
    foreach (T item in sourceSequence)
    {
        if (index++ % interval == 0)
            yield return item;
    }
}
```

<span data-ttu-id="6fd78-143">Hay una restricción importante en los métodos de iterador: no puede tener una instrucción `return` y una instrucción `yield return` en el mismo método.</span><span class="sxs-lookup"><span data-stu-id="6fd78-143">There is one important restriction on iterator methods: you can't have both a `return` statement and a `yield return` statement in the same method.</span></span> <span data-ttu-id="6fd78-144">Lo siguiente no se compilará:</span><span class="sxs-lookup"><span data-stu-id="6fd78-144">The following will not compile:</span></span>

```csharp
public IEnumerable<int> GetSingleDigitNumbers()
{
    int index = 0;
    while (index < 10)
        yield return index++;

    yield return 50;

    // generates a compile time error:
    var items = new int[] {100, 101, 102, 103, 104, 105, 106, 107, 108, 109 };
    return items;
}
```

<span data-ttu-id="6fd78-145">Normalmente esta restricción no supone un problema.</span><span class="sxs-lookup"><span data-stu-id="6fd78-145">This restriction normally isn't a problem.</span></span> <span data-ttu-id="6fd78-146">Tiene la opción de usar `yield return` en todo el método o de separar el método original en varios métodos, unos con `return` y otros con `yield return`.</span><span class="sxs-lookup"><span data-stu-id="6fd78-146">You have a choice of either using `yield return` throughout the method, or separating the original method into multiple methods, some using `return`, and some using `yield return`.</span></span>

<span data-ttu-id="6fd78-147">Puede modificar el último método ligeramente para usar `yield return` en todas partes:</span><span class="sxs-lookup"><span data-stu-id="6fd78-147">You can modify the last method slightly to use `yield return` everywhere:</span></span>

```csharp
public IEnumerable<int> GetSingleDigitNumbers()
{
    int index = 0;
    while (index < 10)
        yield return index++;

    yield return 50;

    var items = new int[] {100, 101, 102, 103, 104, 105, 106, 107, 108, 109 };
    foreach (var item in items)
        yield return item;
}
```

<span data-ttu-id="6fd78-148">A veces, la respuesta correcta es dividir un método de iterador en dos métodos distintos.</span><span class="sxs-lookup"><span data-stu-id="6fd78-148">Sometimes, the right answer is to split an iterator method into two different methods.</span></span> <span data-ttu-id="6fd78-149">Uno que use `return` y un segundo que use `yield return`.</span><span class="sxs-lookup"><span data-stu-id="6fd78-149">One that uses `return`, and a second that uses `yield return`.</span></span> <span data-ttu-id="6fd78-150">Imagine una situación en la que quiera devolver una colección vacía, o los 5 primeros números impares, basándose en un argumento booleano.</span><span class="sxs-lookup"><span data-stu-id="6fd78-150">Consider a situation where you might want to return an empty collection, or the first 5 odd numbers, based on a boolean argument.</span></span> <span data-ttu-id="6fd78-151">Eso se podría escribir como estos dos métodos:</span><span class="sxs-lookup"><span data-stu-id="6fd78-151">You could write that as these two methods:</span></span>

```csharp
public IEnumerable<int> GetSingleDigitOddNumbers(bool getCollection)
{
    if (getCollection == false)
        return new int[0];
    else
        return IteratorMethod();
}

private IEnumerable<int> IteratorMethod()
{
    int index = 0;
    while (index < 10)
    {
        if (index % 2 == 1)
            yield return index;
        index++;
    }
}
```

<span data-ttu-id="6fd78-152">Observe los métodos anteriores.</span><span class="sxs-lookup"><span data-stu-id="6fd78-152">Look at the methods above.</span></span> <span data-ttu-id="6fd78-153">El primero usa la instrucción estándar `return` para devolver una colección vacía o el iterador creado por el segundo método.</span><span class="sxs-lookup"><span data-stu-id="6fd78-153">The first uses the standard `return` statement to return either an empty collection, or the iterator created by the second method.</span></span> <span data-ttu-id="6fd78-154">El segundo método usa la instrucción `yield return` para crear la secuencia solicitada.</span><span class="sxs-lookup"><span data-stu-id="6fd78-154">The second method uses the `yield return` statement to create the requested sequence.</span></span>

## <a name="deeper-dive-into-foreach"></a><span data-ttu-id="6fd78-155">Profundización en `foreach`</span><span class="sxs-lookup"><span data-stu-id="6fd78-155">Deeper Dive into `foreach`</span></span>

<span data-ttu-id="6fd78-156">La instrucción `foreach` se expande en un elemento estándar que usa las interfaces `IEnumerable<T>` e `IEnumerator<T>` para recorrer en iteración todos los elementos de una colección.</span><span class="sxs-lookup"><span data-stu-id="6fd78-156">The `foreach` statement expands into a standard idiom that uses the `IEnumerable<T>` and `IEnumerator<T>` interfaces to iterate across all elements of a collection.</span></span> <span data-ttu-id="6fd78-157">También minimiza los errores cometidos por los desarrolladores al no administrar correctamente los recursos.</span><span class="sxs-lookup"><span data-stu-id="6fd78-157">It also  minimizes errors developers make by not properly managing resources.</span></span>

<span data-ttu-id="6fd78-158">El compilador traduce el bucle `foreach` que se muestra en el primer ejemplo en algo similar a esta construcción:</span><span class="sxs-lookup"><span data-stu-id="6fd78-158">The compiler translates the `foreach` loop shown in the first example into something similar to this construct:</span></span>

```csharp
IEnumerator<int> enumerator = collection.GetEnumerator();
while (enumerator.MoveNext())
{
    var item = enumerator.Current;
    Console.WriteLine(item.ToString());
}
```

<span data-ttu-id="6fd78-159">La construcción anterior representa el código generado por el compilador de C# a partir de la versión 5 y superiores.</span><span class="sxs-lookup"><span data-stu-id="6fd78-159">The construct above represents the code generated by the C# compiler as of version 5 and above.</span></span> <span data-ttu-id="6fd78-160">Antes de la versión 5, la variable `item` tenía un ámbito diferente:</span><span class="sxs-lookup"><span data-stu-id="6fd78-160">Prior to version 5, the `item` variable had a different scope:</span></span>

```csharp
// C# versions 1 through 4:
IEnumerator<int> enumerator = collection.GetEnumerator();
int item = default(int);
while (enumerator.MoveNext())
{
    item = enumerator.Current;
    Console.WriteLine(item.ToString());
}
```

<span data-ttu-id="6fd78-161">Se modificó porque el comportamiento anterior podía provocar errores leves y difíciles de diagnosticar en las expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="6fd78-161">This was changed because the earlier behavior could lead to subtle and hard to diagnose bugs involving lambda expressions.</span></span> <span data-ttu-id="6fd78-162">Para más información sobre las expresiones lambda, consulte [Expresiones lambda](language-reference/operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="6fd78-162">For more information about lambda expressions, see [Lambda expressions](language-reference/operators/lambda-expressions.md).</span></span>

<span data-ttu-id="6fd78-163">El código exacto generado por el compilador es algo más complicado y controla las situaciones en las que el objeto devuelto por `GetEnumerator()` implementa la interfaz `IDisposable`.</span><span class="sxs-lookup"><span data-stu-id="6fd78-163">The exact code generated by the compiler is somewhat more complicated, and handles situations where the object returned by `GetEnumerator()` implements the `IDisposable` interface.</span></span> <span data-ttu-id="6fd78-164">La expansión completa genera código más parecido al siguiente:</span><span class="sxs-lookup"><span data-stu-id="6fd78-164">The full expansion generates code more like this:</span></span>

```csharp
{
    var enumerator = collection.GetEnumerator();
    try
    {
        while (enumerator.MoveNext())
        {
            var item = enumerator.Current;
            Console.WriteLine(item.ToString());
        }
    } finally
    {
        // dispose of enumerator.
    }
}
```

<span data-ttu-id="6fd78-165">La manera en que el enumerador se elimina depende de las características del tipo de `enumerator`.</span><span class="sxs-lookup"><span data-stu-id="6fd78-165">The manner in which the enumerator is disposed of depends on the characteristics of the type of `enumerator`.</span></span> <span data-ttu-id="6fd78-166">En el caso general, la cláusula `finally` se expande en:</span><span class="sxs-lookup"><span data-stu-id="6fd78-166">In the general case, the `finally` clause expands to:</span></span>

```csharp
finally
{
   (enumerator as IDisposable)?.Dispose();
}
```

<span data-ttu-id="6fd78-167">Pero si el tipo de `enumerator` es un tipo sellado y no hay conversión implícita del tipo de `enumerator` a `IDisposable`, la cláusula `finally` se expande en un bloque vacío:</span><span class="sxs-lookup"><span data-stu-id="6fd78-167">However, if the type of `enumerator` is a sealed type and there is no implicit conversion from the type of `enumerator` to `IDisposable`, the `finally` clause expands to an empty block:</span></span>

```csharp
finally
{
}
```

<span data-ttu-id="6fd78-168">Si hay una conversión implícita del tipo de `enumerator` a `IDisposable`, y `enumerator` es un tipo de valor que no acepta valores Null, la cláusula `finally` se expande en:</span><span class="sxs-lookup"><span data-stu-id="6fd78-168">If there is an implicit conversion from the type of `enumerator` to `IDisposable`, and `enumerator` is a non-nullable value type, the `finally` clause expands to:</span></span>

```csharp
finally
{
   ((IDisposable)enumerator).Dispose();
}
```

<span data-ttu-id="6fd78-169">Afortunadamente, no es necesario recordar todos estos detalles.</span><span class="sxs-lookup"><span data-stu-id="6fd78-169">Thankfully, you don't need to remember all these details.</span></span> <span data-ttu-id="6fd78-170">La instrucción `foreach` controla todos esos matices.</span><span class="sxs-lookup"><span data-stu-id="6fd78-170">The `foreach` statement handles all those nuances for you.</span></span> <span data-ttu-id="6fd78-171">El compilador generará el código correcto para cualquiera de estas construcciones.</span><span class="sxs-lookup"><span data-stu-id="6fd78-171">The compiler will generate the correct code for any of these constructs.</span></span>
