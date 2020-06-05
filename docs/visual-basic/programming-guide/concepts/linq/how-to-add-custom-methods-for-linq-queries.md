---
title: Procedimiento para agregar métodos personalizados para las consultas LINQ
ms.date: 07/20/2015
ms.assetid: 099b2e2a-83cd-45c6-aa4d-01b398b5faaf
ms.openlocfilehash: 55004441d2d1d74556da6841f28d113b876d1048
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400609"
---
# <a name="how-to-add-custom-methods-for-linq-queries-visual-basic"></a><span data-ttu-id="6b9df-102">Cómo: agregar métodos personalizados para las consultas LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6b9df-102">How to: Add Custom Methods for LINQ Queries (Visual Basic)</span></span>

<span data-ttu-id="6b9df-103">Puede extender el conjunto de métodos que puede usar para consultas LINQ agregando métodos de extensión a la interfaz <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="6b9df-103">You can extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="6b9df-104">Por ejemplo, además de las operaciones habituales de promedio o de máximo, puede crear un método de agregación personalizado para calcular un valor a partir de una secuencia de valores.</span><span class="sxs-lookup"><span data-stu-id="6b9df-104">For example, in addition to the standard average or maximum operations, you can create a custom aggregate method to compute a single value from a sequence of values.</span></span> <span data-ttu-id="6b9df-105">También puede crear un método que funcione como un filtro personalizado o como una transformación de datos específica para una secuencia de valores y que devuelva una secuencia nueva.</span><span class="sxs-lookup"><span data-stu-id="6b9df-105">You can also create a method that works as a custom filter or a specific data transform for a sequence of values and returns a new sequence.</span></span> <span data-ttu-id="6b9df-106">Ejemplos de dichos métodos son <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A> y <xref:System.Linq.Enumerable.Reverse%2A>.</span><span class="sxs-lookup"><span data-stu-id="6b9df-106">Examples of such methods are <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A>, and <xref:System.Linq.Enumerable.Reverse%2A>.</span></span>

<span data-ttu-id="6b9df-107">Si extiende la interfaz <xref:System.Collections.Generic.IEnumerable%601>, puede aplicar los métodos personalizados a cualquier colección enumerable.</span><span class="sxs-lookup"><span data-stu-id="6b9df-107">When you extend the <xref:System.Collections.Generic.IEnumerable%601> interface, you can apply your custom methods to any enumerable collection.</span></span> <span data-ttu-id="6b9df-108">Para más información, vea [Métodos de extensión](../../language-features/procedures/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="6b9df-108">For more information, see [Extension Methods](../../language-features/procedures/extension-methods.md).</span></span>

## <a name="adding-an-aggregate-method"></a><span data-ttu-id="6b9df-109">Agregar un método de agregación</span><span class="sxs-lookup"><span data-stu-id="6b9df-109">Adding an Aggregate Method</span></span>

<span data-ttu-id="6b9df-110">Un método de agregación calcula un valor único a partir de un conjunto de valores.</span><span class="sxs-lookup"><span data-stu-id="6b9df-110">An aggregate method computes a single value from a set of values.</span></span> <span data-ttu-id="6b9df-111">LINQ proporciona varios métodos de agregación, incluidos <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A> y <xref:System.Linq.Enumerable.Max%2A>.</span><span class="sxs-lookup"><span data-stu-id="6b9df-111">LINQ provides several aggregate methods, including <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Max%2A>.</span></span> <span data-ttu-id="6b9df-112">Si quiere crear su propio método de agregación, agregue un método de extensión a la interfaz <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="6b9df-112">You can create your own aggregate method by adding an extension method to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>

<span data-ttu-id="6b9df-113">En el ejemplo de código siguiente se muestra cómo crear un método de extensión denominado `Median` para calcular la mediana de una secuencia de números de tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="6b9df-113">The following code example shows how to create an extension method called `Median` to compute a median for a sequence of numbers of type `double`.</span></span>

```vb
Imports System.Runtime.CompilerServices

Module LINQExtension

    ' Extension method for the IEnumerable(of T) interface.
    ' The method accepts only values of the Double type.
    <Extension()>
    Function Median(ByVal source As IEnumerable(Of Double)) As Double
        If source.Count = 0 Then
            Throw New InvalidOperationException("Cannot compute median for an empty set.")
        End If

        Dim sortedSource = From number In source
                           Order By number

        Dim itemIndex = sortedSource.Count \ 2

        If sortedSource.Count Mod 2 = 0 Then
            ' Even number of items in list.
            Return (sortedSource(itemIndex) + sortedSource(itemIndex - 1)) / 2
        Else
            ' Odd number of items in list.
            Return sortedSource(itemIndex)
        End If
    End Function
End Module
```

<span data-ttu-id="6b9df-114">Puede llamar a este método de extensión para cualquier colección enumerable de la misma manera en la que llamaría a otros métodos de agregación desde la interfaz <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="6b9df-114">You call this extension method for any enumerable collection in the same way you call other aggregate methods from the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>

> [!NOTE]
> <span data-ttu-id="6b9df-115">En Visual Basic, puede usar una llamada de método o una sintaxis de consulta estándar para `Aggregate` la `Group By` cláusula o.</span><span class="sxs-lookup"><span data-stu-id="6b9df-115">In Visual Basic, you can either use a method call or standard query syntax for the `Aggregate` or `Group By` clause.</span></span> <span data-ttu-id="6b9df-116">Para obtener más información, vea [cláusula Aggregate](../../../language-reference/queries/aggregate-clause.md) y [cláusula Group by](../../../language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6b9df-116">For more information, see [Aggregate Clause](../../../language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../language-reference/queries/group-by-clause.md).</span></span>

<span data-ttu-id="6b9df-117">En el ejemplo de código siguiente se muestra cómo usar el método `Median` para una matriz de tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="6b9df-117">The following code example shows how to use the `Median` method for an array of type `double`.</span></span>

```vb
Dim numbers1() As Double = {1.9, 2, 8, 4, 5.7, 6, 7.2, 0}

Dim query1 = Aggregate num In numbers1 Into Median()

Console.WriteLine("Double: Median = " & query1)
```

```vb
' This code produces the following output:
'
' Double: Median = 4.85
```

### <a name="overloading-an-aggregate-method-to-accept-various-types"></a><span data-ttu-id="6b9df-118">Sobrecargar un método de agregación para que acepte varios tipos</span><span class="sxs-lookup"><span data-stu-id="6b9df-118">Overloading an Aggregate Method to Accept Various Types</span></span>

<span data-ttu-id="6b9df-119">Puede sobrecargar el método de agregación para que acepte secuencias de varios tipos.</span><span class="sxs-lookup"><span data-stu-id="6b9df-119">You can overload your aggregate method so that it accepts sequences of various types.</span></span> <span data-ttu-id="6b9df-120">El enfoque estándar consiste en crear una sobrecarga para cada tipo.</span><span class="sxs-lookup"><span data-stu-id="6b9df-120">The standard approach is to create an overload for each type.</span></span> <span data-ttu-id="6b9df-121">Otro enfoque consiste en crear una sobrecarga que tome un tipo genérico y lo convierta a un tipo específico mediante un delegado.</span><span class="sxs-lookup"><span data-stu-id="6b9df-121">Another approach is to create an overload that will take a generic type and convert it to a specific type by using a delegate.</span></span> <span data-ttu-id="6b9df-122">También puede combinar ambos enfoques.</span><span class="sxs-lookup"><span data-stu-id="6b9df-122">You can also combine both approaches.</span></span>

#### <a name="to-create-an-overload-for-each-type"></a><span data-ttu-id="6b9df-123">Para crear una sobrecarga para cada tipo</span><span class="sxs-lookup"><span data-stu-id="6b9df-123">To create an overload for each type</span></span>

<span data-ttu-id="6b9df-124">Puede crear una sobrecarga específica para cada tipo que desee admitir.</span><span class="sxs-lookup"><span data-stu-id="6b9df-124">You can create a specific overload for each type that you want to support.</span></span> <span data-ttu-id="6b9df-125">En el siguiente ejemplo de código se muestra una sobrecarga del método `Median` para el tipo `integer`.</span><span class="sxs-lookup"><span data-stu-id="6b9df-125">The following code example shows an overload of the `Median` method for the `integer` type.</span></span>

```vb
' Integer overload

<Extension()>
Function Median(ByVal source As IEnumerable(Of Integer)) As Double
    Return Aggregate num In source Select CDbl(num) Into med = Median()
End Function
```

<span data-ttu-id="6b9df-126">Ahora puede llamar a las sobrecargas `Median` para los tipos `integer` y `double`, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="6b9df-126">You can now call the `Median` overloads for both `integer` and `double` types, as shown in the following code:</span></span>

```vb
Dim numbers1() As Double = {1.9, 2, 8, 4, 5.7, 6, 7.2, 0}

Dim query1 = Aggregate num In numbers1 Into Median()

Console.WriteLine("Double: Median = " & query1)
```

```vb
Dim numbers2() As Integer = {1, 2, 3, 4, 5}

Dim query2 = Aggregate num In numbers2 Into Median()

Console.WriteLine("Integer: Median = " & query2)
```

```vb
' This code produces the following output:
'
' Double: Median = 4.85
' Integer: Median = 3
```

#### <a name="to-create-a-generic-overload"></a><span data-ttu-id="6b9df-127">Para crear una sobrecarga genérica</span><span class="sxs-lookup"><span data-stu-id="6b9df-127">To create a generic overload</span></span>

<span data-ttu-id="6b9df-128">También puede crear una sobrecarga que acepte una secuencia de objetos genéricos.</span><span class="sxs-lookup"><span data-stu-id="6b9df-128">You can also create an overload that accepts a sequence of generic objects.</span></span> <span data-ttu-id="6b9df-129">Esta sobrecarga toma un delegado como parámetro y lo usa para convertir una secuencia de objetos de un tipo genérico a un tipo específico.</span><span class="sxs-lookup"><span data-stu-id="6b9df-129">This overload takes a delegate as a parameter and uses it to convert a sequence of objects of a generic type to a specific type.</span></span>

<span data-ttu-id="6b9df-130">En el código siguiente se muestra una sobrecarga del método `Median` que toma el delegado <xref:System.Func%602> como parámetro.</span><span class="sxs-lookup"><span data-stu-id="6b9df-130">The following code shows an overload of the `Median` method that takes the <xref:System.Func%602> delegate as a parameter.</span></span> <span data-ttu-id="6b9df-131">Este delegado toma un objeto del tipo genérico T y devuelve un objeto de tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="6b9df-131">This delegate takes an object of generic type T and returns an object of type `double`.</span></span>

```vb
' Generic overload.

<Extension()>
Function Median(Of T)(ByVal source As IEnumerable(Of T),
                      ByVal selector As Func(Of T, Double)) As Double
    Return Aggregate num In source Select selector(num) Into med = Median()
End Function
```

<span data-ttu-id="6b9df-132">Ahora puede llamar al método `Median` para una secuencia de objetos de cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="6b9df-132">You can now call the `Median` method for a sequence of objects of any type.</span></span> <span data-ttu-id="6b9df-133">Si el tipo no tiene su propia sobrecarga de métodos, deberá pasar un parámetro de delegado.</span><span class="sxs-lookup"><span data-stu-id="6b9df-133">If the type does not have its own method overload, you have to pass a delegate parameter.</span></span> <span data-ttu-id="6b9df-134">En Visual Basic, puede usar una expresión lambda para este fin.</span><span class="sxs-lookup"><span data-stu-id="6b9df-134">In Visual Basic, you can use a lambda expression for this purpose.</span></span> <span data-ttu-id="6b9df-135">Además, si usa la `Aggregate` cláusula o en `Group By` lugar de la llamada al método, puede pasar cualquier valor o expresión que esté en el ámbito de esta cláusula.</span><span class="sxs-lookup"><span data-stu-id="6b9df-135">Also, if you use the `Aggregate` or `Group By` clause instead of the method call, you can pass any value or expression that is in the scope this clause.</span></span>

<span data-ttu-id="6b9df-136">En el ejemplo de código siguiente se muestra cómo llamar al método `Median` para una matriz de enteros y una matriz de cadenas.</span><span class="sxs-lookup"><span data-stu-id="6b9df-136">The following example code shows how to call the `Median` method for an array of integers and an array of strings.</span></span> <span data-ttu-id="6b9df-137">Para las cadenas, se calcula la mediana de las longitudes de las cadenas de la matriz.</span><span class="sxs-lookup"><span data-stu-id="6b9df-137">For strings, the median for the lengths of strings in the array is calculated.</span></span> <span data-ttu-id="6b9df-138">En el ejemplo se muestra cómo pasar el parámetro del delegado <xref:System.Func%602> al método `Median` para cada caso.</span><span class="sxs-lookup"><span data-stu-id="6b9df-138">The example shows how to pass the <xref:System.Func%602> delegate parameter to the `Median` method for each case.</span></span>

```vb
Dim numbers3() As Integer = {1, 2, 3, 4, 5}

' You can use num as a parameter for the Median method
' so that the compiler will implicitly convert its value to double.
' If there is no implicit conversion, the compiler will
' display an error message.

Dim query3 = Aggregate num In numbers3 Into Median(num)

Console.WriteLine("Integer: Median = " & query3)

Dim numbers4() As String = {"one", "two", "three", "four", "five"}

' With the generic overload, you can also use numeric properties of objects.

Dim query4 = Aggregate str In numbers4 Into Median(str.Length)

Console.WriteLine("String: Median = " & query4)

' This code produces the following output:
'
' Integer: Median = 3
' String: Median = 4
```

## <a name="adding-a-method-that-returns-a-collection"></a><span data-ttu-id="6b9df-139">Agregar un método que devuelva una colección</span><span class="sxs-lookup"><span data-stu-id="6b9df-139">Adding a Method That Returns a Collection</span></span>

<span data-ttu-id="6b9df-140">Puede extender la interfaz <xref:System.Collections.Generic.IEnumerable%601> con un método de consulta personalizado que devuelve una secuencia de valores.</span><span class="sxs-lookup"><span data-stu-id="6b9df-140">You can extend the <xref:System.Collections.Generic.IEnumerable%601> interface with a custom query method that returns a sequence of values.</span></span> <span data-ttu-id="6b9df-141">En este caso, el método debe devolver una colección de tipo <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="6b9df-141">In this case, the method must return a collection of type <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="6b9df-142">Estos métodos se pueden usar para aplicar filtros o transformaciones de datos a una secuencia de valores.</span><span class="sxs-lookup"><span data-stu-id="6b9df-142">Such methods can be used to apply filters or data transforms to a sequence of values.</span></span>

<span data-ttu-id="6b9df-143">En el ejemplo siguiente se muestra cómo crear un método de extensión denominado `AlternateElements` que devuelve los demás elementos de una colección, empezando por el primer elemento.</span><span class="sxs-lookup"><span data-stu-id="6b9df-143">The following example shows how to create an extension method named `AlternateElements` that returns every other element in a collection, starting from the first element.</span></span>

```vb
' Extension method for the IEnumerable(of T) interface.
' The method returns every other element of a sequence.

<Extension()>
Function AlternateElements(Of T)(
    ByVal source As IEnumerable(Of T)
    ) As IEnumerable(Of T)

    Dim list As New List(Of T)
    Dim i = 0
    For Each element In source
        If (i Mod 2 = 0) Then
            list.Add(element)
        End If
        i = i + 1
    Next
    Return list
End Function
```

<span data-ttu-id="6b9df-144">Puede llamar a este método de extensión para cualquier colección enumerable de la misma manera en la que llamaría a otros métodos desde la interfaz <xref:System.Collections.Generic.IEnumerable%601>, como se muestra en el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="6b9df-144">You can call this extension method for any enumerable collection just as you would call other methods from the <xref:System.Collections.Generic.IEnumerable%601> interface, as shown in the following code:</span></span>

```vb
Dim strings() As String = {"a", "b", "c", "d", "e"}

Dim query = strings.AlternateElements()

For Each element In query
    Console.WriteLine(element)
Next

' This code produces the following output:
'
' a
' c
' e
```

## <a name="see-also"></a><span data-ttu-id="6b9df-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6b9df-145">See also</span></span>

- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="6b9df-146">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="6b9df-146">Extension Methods</span></span>](../../language-features/procedures/extension-methods.md)
