---
title: Procedimiento para agregar métodos personalizados para las consultas LINQ (C#)
ms.date: 07/20/2015
ms.assetid: 1a500f60-2e10-49fb-8b2a-d8d08e4817cb
ms.openlocfilehash: e3f8ba8810d06a2e79093e6022ad6e79f3599468
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2020
ms.locfileid: "84447035"
---
# <a name="how-to-add-custom-methods-for-linq-queries-c"></a>Procedimiento para agregar métodos personalizados para las consultas LINQ (C#)

Puede extender el conjunto de métodos que puede usar para consultas LINQ agregando métodos de extensión a la interfaz <xref:System.Collections.Generic.IEnumerable%601>. Por ejemplo, además de las operaciones habituales de promedio o de máximo, puede crear un método de agregación personalizado para calcular un valor a partir de una secuencia de valores. También puede crear un método que funcione como un filtro personalizado o como una transformación de datos específica para una secuencia de valores y que devuelva una secuencia nueva. Ejemplos de dichos métodos son <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A> y <xref:System.Linq.Enumerable.Reverse%2A>.

Si extiende la interfaz <xref:System.Collections.Generic.IEnumerable%601>, puede aplicar los métodos personalizados a cualquier colección enumerable. Para más información, vea [Métodos de extensión](../../classes-and-structs/extension-methods.md).

## <a name="adding-an-aggregate-method"></a>Agregar un método de agregación

Un método de agregación calcula un valor único a partir de un conjunto de valores. LINQ proporciona varios métodos de agregación, incluidos <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A> y <xref:System.Linq.Enumerable.Max%2A>. Si quiere crear su propio método de agregación, agregue un método de extensión a la interfaz <xref:System.Collections.Generic.IEnumerable%601>.

En el ejemplo de código siguiente se muestra cómo crear un método de extensión denominado `Median` para calcular la mediana de una secuencia de números de tipo `double`.

```csharp
public static class LINQExtension
{
    public static double Median(this IEnumerable<double> source)
    {
        var countOfElementsInTheSet = source?.Count() ?? 0;

        if (countOfElementsInTheSet == 0)
        {
            throw new InvalidOperationException("Cannot compute median for a null or empty set.");
        }

        var sortedList = (from number in source
                         orderby number
                         select number).ToList();

        int itemIndex = countOfElementsInTheSet / 2;

        if (countOfElementsInTheSet % 2 == 0)
        {
            // Even number of items.
            return (sortedList[itemIndex] + sortedList[itemIndex - 1]) / 2;
        }
        else
        {
            // Odd number of items.
            return sortedList[itemIndex];
        }
    }
}
```

Puede llamar a este método de extensión para cualquier colección enumerable de la misma manera en la que llamaría a otros métodos de agregación desde la interfaz <xref:System.Collections.Generic.IEnumerable%601>.

En el ejemplo de código siguiente se muestra cómo usar el método `Median` para una matriz de tipo `double`.

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

### <a name="overloading-an-aggregate-method-to-accept-various-types"></a>Sobrecargar un método de agregación para que acepte varios tipos

Puede sobrecargar el método de agregación para que acepte secuencias de varios tipos. El enfoque estándar consiste en crear una sobrecarga para cada tipo. Otro enfoque consiste en crear una sobrecarga que tome un tipo genérico y lo convierta a un tipo específico mediante un delegado. También puede combinar ambos enfoques.

#### <a name="to-create-an-overload-for-each-type"></a>Para crear una sobrecarga para cada tipo

Puede crear una sobrecarga específica para cada tipo que desee admitir. En el siguiente ejemplo de código se muestra una sobrecarga del método `Median` para el tipo `integer`.

```csharp
//int overload

public static double Median(this IEnumerable<int> source)
{
    return (from num in source select (double)num).Median();
}
```

Ahora puede llamar a las sobrecargas `Median` para los tipos `integer` y `double`, como se muestra en el código siguiente:

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

#### <a name="to-create-a-generic-overload"></a>Para crear una sobrecarga genérica

También puede crear una sobrecarga que acepte una secuencia de objetos genéricos. Esta sobrecarga toma un delegado como parámetro y lo usa para convertir una secuencia de objetos de un tipo genérico a un tipo específico.

En el código siguiente se muestra una sobrecarga del método `Median` que toma el delegado <xref:System.Func%602> como parámetro. Este delegado toma un objeto del tipo genérico T y devuelve un objeto de tipo `double`.

```csharp
// Generic overload.

public static double Median<T>(this IEnumerable<T> numbers,
                       Func<T, double> selector)
{
    return (from num in numbers select selector(num)).Median();
}
```

Ahora puede llamar al método `Median` para una secuencia de objetos de cualquier tipo. Si el tipo no tiene su propia sobrecarga de métodos, deberá pasar un parámetro de delegado. En C# puede usar una expresión lambda para este propósito. Además, solo en Visual Basic, si usa la cláusula `Aggregate` o `Group By` en lugar de la llamada al método, puede pasar cualquier valor o expresión que esté en el ámbito de esta cláusula.

En el ejemplo de código siguiente se muestra cómo llamar al método `Median` para una matriz de enteros y una matriz de cadenas. Para las cadenas, se calcula la mediana de las longitudes de las cadenas de la matriz. En el ejemplo se muestra cómo pasar el parámetro del delegado <xref:System.Func%602> al método `Median` para cada caso.

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

## <a name="adding-a-method-that-returns-a-collection"></a>Agregar un método que devuelva una colección

Puede extender la interfaz <xref:System.Collections.Generic.IEnumerable%601> con un método de consulta personalizado que devuelve una secuencia de valores. En este caso, el método debe devolver una colección de tipo <xref:System.Collections.Generic.IEnumerable%601>. Estos métodos se pueden usar para aplicar filtros o transformaciones de datos a una secuencia de valores.

En el ejemplo siguiente se muestra cómo crear un método de extensión denominado `AlternateElements` que devuelve los demás elementos de una colección, empezando por el primer elemento.

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

Puede llamar a este método de extensión para cualquier colección enumerable de la misma manera en la que llamaría a otros métodos desde la interfaz <xref:System.Collections.Generic.IEnumerable%601>, como se muestra en el siguiente código:

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

## <a name="see-also"></a>Vea también

- <xref:System.Collections.Generic.IEnumerable%601>
- [Métodos de extensión](../../classes-and-structs/extension-methods.md)
