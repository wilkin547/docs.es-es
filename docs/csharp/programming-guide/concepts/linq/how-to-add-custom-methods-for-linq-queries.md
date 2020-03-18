---
title: Procedimiento para agregar métodos personalizados para las consultas LINQ (C#)
ms.date: 07/20/2015
ms.assetid: 1a500f60-2e10-49fb-8b2a-d8d08e4817cb
ms.openlocfilehash: e16175d3332b6ce36458eaa78af093e4f8772723
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141470"
---
# <a name="how-to-add-custom-methods-for-linq-queries-c"></a><span data-ttu-id="7bf8f-102">Procedimiento para agregar métodos personalizados para las consultas LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="7bf8f-102">How to add custom methods for LINQ queries (C#)</span></span>

<span data-ttu-id="7bf8f-103">Puede extender el conjunto de métodos que puede usar para consultas LINQ agregando métodos de extensión a la interfaz <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-103">You can extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="7bf8f-104">Por ejemplo, además de las operaciones habituales de promedio o de máximo, puede crear un método de agregación personalizado para calcular un valor a partir de una secuencia de valores.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-104">For example, in addition to the standard average or maximum operations, you can create a custom aggregate method to compute a single value from a sequence of values.</span></span> <span data-ttu-id="7bf8f-105">También puede crear un método que funcione como un filtro personalizado o como una transformación de datos específica para una secuencia de valores y que devuelva una secuencia nueva.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-105">You can also create a method that works as a custom filter or a specific data transform for a sequence of values and returns a new sequence.</span></span> <span data-ttu-id="7bf8f-106">Ejemplos de dichos métodos son <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A> y <xref:System.Linq.Enumerable.Reverse%2A>.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-106">Examples of such methods are <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A>, and <xref:System.Linq.Enumerable.Reverse%2A>.</span></span>

<span data-ttu-id="7bf8f-107">Si extiende la interfaz <xref:System.Collections.Generic.IEnumerable%601>, puede aplicar los métodos personalizados a cualquier colección enumerable.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-107">When you extend the <xref:System.Collections.Generic.IEnumerable%601> interface, you can apply your custom methods to any enumerable collection.</span></span> <span data-ttu-id="7bf8f-108">Para más información, vea [Métodos de extensión](../../classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="7bf8f-108">For more information, see [Extension Methods](../../classes-and-structs/extension-methods.md).</span></span>

## <a name="adding-an-aggregate-method"></a><span data-ttu-id="7bf8f-109">Agregar un método de agregación</span><span class="sxs-lookup"><span data-stu-id="7bf8f-109">Adding an Aggregate Method</span></span>

<span data-ttu-id="7bf8f-110">Un método de agregación calcula un valor único a partir de un conjunto de valores.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-110">An aggregate method computes a single value from a set of values.</span></span> <span data-ttu-id="7bf8f-111">LINQ proporciona varios métodos de agregación, incluidos <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A> y <xref:System.Linq.Enumerable.Max%2A>.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-111">LINQ provides several aggregate methods, including <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Max%2A>.</span></span> <span data-ttu-id="7bf8f-112">Si quiere crear su propio método de agregación, agregue un método de extensión a la interfaz <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-112">You can create your own aggregate method by adding an extension method to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>

<span data-ttu-id="7bf8f-113">En el ejemplo de código siguiente se muestra cómo crear un método de extensión denominado `Median` para calcular la mediana de una secuencia de números de tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-113">The following code example shows how to create an extension method called `Median` to compute a median for a sequence of numbers of type `double`.</span></span>

```csharp
public static class LINQExtension
{
    public static double Median(this IEnumerable<double> source)
    {
        if (source.Count() == 0)
        {
            throw new InvalidOperationException("Cannot compute median for an empty set.");
        }

        var sortedList = from number in source
                         orderby number
                         select number;

        int itemIndex = (int)sortedList.Count() / 2;

        if (sortedList.Count() % 2 == 0)
        {
            // Even number of items.
            return (sortedList.ElementAt(itemIndex) + sortedList.ElementAt(itemIndex - 1)) / 2;
        }
        else
        {
            // Odd number of items.
            return sortedList.ElementAt(itemIndex);
        }
    }
}
```

<span data-ttu-id="7bf8f-114">Puede llamar a este método de extensión para cualquier colección enumerable de la misma manera en la que llamaría a otros métodos de agregación desde la interfaz <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-114">You call this extension method for any enumerable collection in the same way you call other aggregate methods from the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>

<span data-ttu-id="7bf8f-115">En el ejemplo de código siguiente se muestra cómo usar el método `Median` para una matriz de tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-115">The following code example shows how to use the `Median` method for an array of type `double`.</span></span>

```csharp
double[] numbers1 = { 1.9, 2, 8, 4, 5.7, 6, 7.2, 0 };

var query1 = numbers1.Median();

Console.WriteLine("double: Median = " + query1);
```

```csharp
/*
 This code produces the following output:

 Double: Median = 4.85
*/
```

### <a name="overloading-an-aggregate-method-to-accept-various-types"></a><span data-ttu-id="7bf8f-116">Sobrecargar un método de agregación para que acepte varios tipos</span><span class="sxs-lookup"><span data-stu-id="7bf8f-116">Overloading an Aggregate Method to Accept Various Types</span></span>

<span data-ttu-id="7bf8f-117">Puede sobrecargar el método de agregación para que acepte secuencias de varios tipos.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-117">You can overload your aggregate method so that it accepts sequences of various types.</span></span> <span data-ttu-id="7bf8f-118">El enfoque estándar consiste en crear una sobrecarga para cada tipo.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-118">The standard approach is to create an overload for each type.</span></span> <span data-ttu-id="7bf8f-119">Otro enfoque consiste en crear una sobrecarga que tome un tipo genérico y lo convierta a un tipo específico mediante un delegado.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-119">Another approach is to create an overload that will take a generic type and convert it to a specific type by using a delegate.</span></span> <span data-ttu-id="7bf8f-120">También puede combinar ambos enfoques.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-120">You can also combine both approaches.</span></span>

#### <a name="to-create-an-overload-for-each-type"></a><span data-ttu-id="7bf8f-121">Para crear una sobrecarga para cada tipo</span><span class="sxs-lookup"><span data-stu-id="7bf8f-121">To create an overload for each type</span></span>

<span data-ttu-id="7bf8f-122">Puede crear una sobrecarga específica para cada tipo que desee admitir.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-122">You can create a specific overload for each type that you want to support.</span></span> <span data-ttu-id="7bf8f-123">En el siguiente ejemplo de código se muestra una sobrecarga del método `Median` para el tipo `integer`.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-123">The following code example shows an overload of the `Median` method for the `integer` type.</span></span>

```csharp
//int overload

public static double Median(this IEnumerable<int> source)
{
    return (from num in source select (double)num).Median();
}
```

<span data-ttu-id="7bf8f-124">Ahora puede llamar a las sobrecargas `Median` para los tipos `integer` y `double`, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="7bf8f-124">You can now call the `Median` overloads for both `integer` and `double` types, as shown in the following code:</span></span>

```csharp
double[] numbers1 = { 1.9, 2, 8, 4, 5.7, 6, 7.2, 0 };

var query1 = numbers1.Median();

Console.WriteLine("double: Median = " + query1);
```

```csharp
int[] numbers2 = { 1, 2, 3, 4, 5 };

var query2 = numbers2.Median();

Console.WriteLine("int: Median = " + query2);
```

```csharp
/*
 This code produces the following output:

 Double: Median = 4.85
 Integer: Median = 3
*/
```

#### <a name="to-create-a-generic-overload"></a><span data-ttu-id="7bf8f-125">Para crear una sobrecarga genérica</span><span class="sxs-lookup"><span data-stu-id="7bf8f-125">To create a generic overload</span></span>

<span data-ttu-id="7bf8f-126">También puede crear una sobrecarga que acepte una secuencia de objetos genéricos.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-126">You can also create an overload that accepts a sequence of generic objects.</span></span> <span data-ttu-id="7bf8f-127">Esta sobrecarga toma un delegado como parámetro y lo usa para convertir una secuencia de objetos de un tipo genérico a un tipo específico.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-127">This overload takes a delegate as a parameter and uses it to convert a sequence of objects of a generic type to a specific type.</span></span>

<span data-ttu-id="7bf8f-128">En el código siguiente se muestra una sobrecarga del método `Median` que toma el delegado <xref:System.Func%602> como parámetro.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-128">The following code shows an overload of the `Median` method that takes the <xref:System.Func%602> delegate as a parameter.</span></span> <span data-ttu-id="7bf8f-129">Este delegado toma un objeto del tipo genérico T y devuelve un objeto de tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-129">This delegate takes an object of generic type T and returns an object of type `double`.</span></span>

```csharp
// Generic overload.

public static double Median<T>(this IEnumerable<T> numbers,
                       Func<T, double> selector)
{
    return (from num in numbers select selector(num)).Median();
}
```

<span data-ttu-id="7bf8f-130">Ahora puede llamar al método `Median` para una secuencia de objetos de cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-130">You can now call the `Median` method for a sequence of objects of any type.</span></span> <span data-ttu-id="7bf8f-131">Si el tipo no tiene su propia sobrecarga de métodos, deberá pasar un parámetro de delegado.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-131">If the type does not have its own method overload, you have to pass a delegate parameter.</span></span> <span data-ttu-id="7bf8f-132">En C# puede usar una expresión lambda para este propósito.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-132">In C#, you can use a lambda expression for this purpose.</span></span> <span data-ttu-id="7bf8f-133">Además, solo en Visual Basic, si usa la cláusula `Aggregate` o `Group By` en lugar de la llamada al método, puede pasar cualquier valor o expresión que esté en el ámbito de esta cláusula.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-133">Also, in Visual Basic only, if you use the `Aggregate` or `Group By` clause instead of the method call, you can pass any value or expression that is in the scope this clause.</span></span>

<span data-ttu-id="7bf8f-134">En el ejemplo de código siguiente se muestra cómo llamar al método `Median` para una matriz de enteros y una matriz de cadenas.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-134">The following example code shows how to call the `Median` method for an array of integers and an array of strings.</span></span> <span data-ttu-id="7bf8f-135">Para las cadenas, se calcula la mediana de las longitudes de las cadenas de la matriz.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-135">For strings, the median for the lengths of strings in the array is calculated.</span></span> <span data-ttu-id="7bf8f-136">En el ejemplo se muestra cómo pasar el parámetro del delegado <xref:System.Func%602> al método `Median` para cada caso.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-136">The example shows how to pass the <xref:System.Func%602> delegate parameter to the `Median` method for each case.</span></span>

```csharp
int[] numbers3 = { 1, 2, 3, 4, 5 };

/*
  You can use the num=>num lambda expression as a parameter for the Median method
  so that the compiler will implicitly convert its value to double.
  If there is no implicit conversion, the compiler will display an error message.
*/

var query3 = numbers3.Median(num => num);

Console.WriteLine("int: Median = " + query3);

string[] numbers4 = { "one", "two", "three", "four", "five" };

// With the generic overload, you can also use numeric properties of objects.

var query4 = numbers4.Median(str => str.Length);

Console.WriteLine("String: Median = " + query4);

/*
 This code produces the following output:

 Integer: Median = 3
 String: Median = 4
*/
```

## <a name="adding-a-method-that-returns-a-collection"></a><span data-ttu-id="7bf8f-137">Agregar un método que devuelva una colección</span><span class="sxs-lookup"><span data-stu-id="7bf8f-137">Adding a Method That Returns a Collection</span></span>

<span data-ttu-id="7bf8f-138">Puede extender la interfaz <xref:System.Collections.Generic.IEnumerable%601> con un método de consulta personalizado que devuelve una secuencia de valores.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-138">You can extend the <xref:System.Collections.Generic.IEnumerable%601> interface with a custom query method that returns a sequence of values.</span></span> <span data-ttu-id="7bf8f-139">En este caso, el método debe devolver una colección de tipo <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-139">In this case, the method must return a collection of type <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="7bf8f-140">Estos métodos se pueden usar para aplicar filtros o transformaciones de datos a una secuencia de valores.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-140">Such methods can be used to apply filters or data transforms to a sequence of values.</span></span>

<span data-ttu-id="7bf8f-141">En el ejemplo siguiente se muestra cómo crear un método de extensión denominado `AlternateElements` que devuelve los demás elementos de una colección, empezando por el primer elemento.</span><span class="sxs-lookup"><span data-stu-id="7bf8f-141">The following example shows how to create an extension method named `AlternateElements` that returns every other element in a collection, starting from the first element.</span></span>

```csharp
// Extension method for the IEnumerable<T> interface.
// The method returns every other element of a sequence.

public static IEnumerable<T> AlternateElements<T>(this IEnumerable<T> source)
{
    List<T> list = new List<T>();

    int i = 0;

    foreach (var element in source)
    {
        if (i % 2 == 0)
        {
            list.Add(element);
        }

        i++;
    }

    return list;
}
```

<span data-ttu-id="7bf8f-142">Puede llamar a este método de extensión para cualquier colección enumerable de la misma manera en la que llamaría a otros métodos desde la interfaz <xref:System.Collections.Generic.IEnumerable%601>, como se muestra en el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="7bf8f-142">You can call this extension method for any enumerable collection just as you would call other methods from the <xref:System.Collections.Generic.IEnumerable%601> interface, as shown in the following code:</span></span>

```csharp
string[] strings = { "a", "b", "c", "d", "e" };

var query = strings.AlternateElements();

foreach (var element in query)
{
    Console.WriteLine(element);
}
/*
 This code produces the following output:

 a
 c
 e
*/
```

## <a name="see-also"></a><span data-ttu-id="7bf8f-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="7bf8f-143">See also</span></span>

- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="7bf8f-144">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="7bf8f-144">Extension Methods</span></span>](../../classes-and-structs/extension-methods.md)
