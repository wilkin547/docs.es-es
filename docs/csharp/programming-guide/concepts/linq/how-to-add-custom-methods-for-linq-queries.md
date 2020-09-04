---
title: Procedimiento para agregar métodos personalizados para las consultas LINQ (C#)
description: Obtenga información sobre cómo ampliar la sintaxis de las consultas LINQ mediante la adición de métodos de extensión a la interfaz IEnumerable<T> en C#.
ms.date: 08/26/2020
ms.assetid: 1a500f60-2e10-49fb-8b2a-d8d08e4817cb
ms.openlocfilehash: 768882fce40a2fc6e018f24c8928341e7c65bc4b
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89122431"
---
# <a name="how-to-add-custom-methods-for-linq-queries-c"></a>Procedimiento para agregar métodos personalizados para las consultas LINQ (C#)

Para extender el conjunto de métodos que usa para consultas LINQ, agregue métodos de extensión a la interfaz <xref:System.Collections.Generic.IEnumerable%601>. Por ejemplo, además de las operaciones habituales de promedio o de máximo, puede crear un método de agregación personalizado para calcular un solo valor a partir de una secuencia de valores. También puede crear un método que funcione como un filtro personalizado o como una transformación de datos específica para una secuencia de valores y que devuelva una nueva secuencia. Ejemplos de dichos métodos son <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A> y <xref:System.Linq.Enumerable.Reverse%2A>.

Si extiende la interfaz <xref:System.Collections.Generic.IEnumerable%601>, puede aplicar los métodos personalizados a cualquier colección enumerable. Para obtener más información, vea [Métodos de extensión](../../classes-and-structs/extension-methods.md).

## <a name="adding-an-aggregate-method"></a>Adición de un método de agregación

Un método de agregación calcula un valor único a partir de un conjunto de valores. LINQ proporciona varios métodos de agregación, incluidos <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A> y <xref:System.Linq.Enumerable.Max%2A>. Si quiere crear su propio método de agregación, agregue un método de extensión a la interfaz <xref:System.Collections.Generic.IEnumerable%601>.

En el ejemplo de código siguiente se muestra cómo crear un método de extensión denominado `Median` para calcular la mediana de una secuencia de números de tipo `double`.

:::code language="csharp" source="./snippets/LinqExtensions.cs" ID="LinqExtensionClass":::

Puede llamar a este método de extensión para cualquier colección enumerable de la misma manera en la que llamaría a otros métodos de agregación desde la interfaz <xref:System.Collections.Generic.IEnumerable%601>.

En el ejemplo de código siguiente se muestra cómo usar el método `Median` para una matriz de tipo `double`.

:::code language="csharp" source="./snippets/Program.cs" ID="MedianUsage":::

### <a name="overloading-an-aggregate-method-to-accept-various-types"></a>Sobrecargar un método de agregación para que acepte varios tipos

Puede sobrecargar el método de agregación para que acepte secuencias de varios tipos. El enfoque estándar consiste en crear una sobrecarga para cada tipo. Otro enfoque consiste en crear una sobrecarga que tome un tipo genérico y lo convierta a un tipo específico mediante un delegado. También puede combinar ambos enfoques.

#### <a name="to-create-an-overload-for-each-type"></a>Para crear una sobrecarga para cada tipo

Puede crear una sobrecarga específica para cada tipo que desee admitir. En el siguiente ejemplo de código se muestra una sobrecarga del método `Median` para el tipo `int`.

:::code language="csharp" source="./snippets/LinqExtensions.cs" ID="IntOverload":::

Ahora puede llamar a las sobrecargas `Median` para los tipos `integer` y `double`, como se muestra en el código siguiente:

:::code language="csharp" source="./snippets/Program.cs" ID="OverloadUsage":::

#### <a name="to-create-a-generic-overload"></a>Para crear una sobrecarga genérica

También puede crear una sobrecarga que acepte una secuencia de objetos genéricos. Esta sobrecarga toma un delegado como parámetro y lo usa para convertir una secuencia de objetos de un tipo genérico a un tipo específico.

En el código siguiente se muestra una sobrecarga del método `Median` que toma el delegado <xref:System.Func%602> como parámetro. Este delegado toma un objeto del tipo genérico T y devuelve un objeto de tipo `double`.

:::code language="csharp" source="./snippets/LinqExtensions.cs" ID="GenericOverload":::

Ahora puede llamar al método `Median` para una secuencia de objetos de cualquier tipo. Si el tipo no tiene su propia sobrecarga de métodos, deberá pasar un parámetro de delegado. En C# puede usar una expresión lambda para este propósito. Además, solo en Visual Basic, si usa la cláusula `Aggregate` o `Group By` en lugar de la llamada al método, puede pasar cualquier valor o expresión que esté en el ámbito de esta cláusula.

En el ejemplo de código siguiente se muestra cómo llamar al método `Median` para una matriz de enteros y una matriz de cadenas. Para las cadenas, se calcula la mediana de las longitudes de las cadenas de la matriz. En el ejemplo se muestra cómo pasar el parámetro del delegado <xref:System.Func%602> al método `Median` para cada caso.

:::code language="csharp" source="./snippets/Program.cs" ID="GenericUsage":::

## <a name="adding-a-method-that-returns-a-sequence"></a>Adición de un método que devuelva una secuencia

Puede extender la interfaz <xref:System.Collections.Generic.IEnumerable%601> con un método de consulta personalizado que devuelve una secuencia de valores. En este caso, el método debe devolver una colección de tipo <xref:System.Collections.Generic.IEnumerable%601>. Estos métodos se pueden usar para aplicar filtros o transformaciones de datos a una secuencia de valores.

En el ejemplo siguiente se muestra cómo crear un método de extensión denominado `AlternateElements` que devuelve los demás elementos de una colección, empezando por el primer elemento.

:::code language="csharp" source="./snippets/LinqExtensions.cs" ID="SequenceElement":::

Puede llamar a este método de extensión para cualquier colección enumerable de la misma manera en la que llamaría a otros métodos desde la interfaz <xref:System.Collections.Generic.IEnumerable%601>, como se muestra en el siguiente código:

:::code language="csharp" source="./snippets/Program.cs" ID="SequenceUsage":::

## <a name="see-also"></a>Consulte también

- <xref:System.Collections.Generic.IEnumerable%601>
- [Métodos de extensión](../../classes-and-structs/extension-methods.md)
