---
title: Escribir consultas LINQ en C#
description: Obtenga información sobre cómo escribir consultas de LINQ en C#.
ms.date: 12/01/2016
ms.assetid: 30703f79-cf3a-4d02-b892-c95d58a1d9ed
ms.openlocfilehash: bd7da81f2873c6a25570cab32fafecc66fd98be4
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063450"
---
# <a name="write-linq-queries-in-c"></a>Escribir consultas LINQ en C\#

En este artículo se muestran las tres formas de escribir una consulta LINQ en C#:

1. Usar sintaxis de consulta.

2. Usar sintaxis de método.

3. Usar una combinación de sintaxis de consulta y sintaxis de método.

Los ejemplos siguientes muestran algunas consultas LINQ sencillas mediante cada enfoque enumerado anteriormente. En general, la regla es usar (1) siempre que sea posible y usar (2) y (3) cuando sea necesario.

> [!NOTE]
> Estas consultas funcionan en colecciones en memoria simples, pero la sintaxis básica es idéntica a la empleada en LINQ to Entities y LINQ to XML.

## <a name="example---query-syntax"></a>Ejemplo: Sintaxis de consulta

La manera recomendada de escribir la mayoría de las consultas es usar *sintaxis de consulta* para crear *expresiones de consulta*. En el siguiente ejemplo se muestran tres expresiones de consulta. La primera expresión de consulta muestra cómo filtrar o restringir los resultados mediante la aplicación de condiciones con una cláusula `where`. Devuelve todos los elementos de la secuencia de origen cuyos valores sean mayores que 7 o menores que 3. La segunda expresión muestra cómo ordenar los resultados devueltos. La tercera expresión muestra cómo agrupar los resultados según una clave. Esta consulta devuelve dos grupos en función de la primera letra de la palabra.

[!code-csharp[csProgGuideLINQ#5](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_1.cs)]

Tenga en cuenta que el tipo de las consultas es <xref:System.Collections.Generic.IEnumerable%601>. Todas estas consultas podrían escribirse mediante `var` como se muestra en el ejemplo siguiente:

`var query = from num in numbers...`

En cada ejemplo anterior, las consultas no se ejecutan realmente hasta que se recorre en iteración la variable de consulta en una instrucción `foreach` o cualquier otra instrucción. Para más información, vea [Introduction to LINQ Queries (Introducción a las consultas LINQ)](../programming-guide/concepts/linq/introduction-to-linq-queries.md).

## <a name="example---method-syntax"></a>Ejemplo: Sintaxis de método

Algunas operaciones de consulta deben expresarse como una llamada a método. Los más comunes de dichos métodos son los que devuelven valores numéricos de singleton, como <xref:System.Linq.Enumerable.Sum%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, <xref:System.Linq.Enumerable.Average%2A> y así sucesivamente. A estos métodos siempre se los debe llamar en último lugar en cualquier consulta porque representan un solo valor y no pueden servir como origen para una operación de consulta adicional. En el ejemplo siguiente se muestra una llamada a método en una expresión de consulta:

[!code-csharp[csProgGuideLINQ#6](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_2.cs)]

Si el método tiene parámetros Action o Func, se proporcionan en forma de expresión [lambda](../language-reference/operators/lambda-expressions.md), como se muestra en el ejemplo siguiente:

[!code-csharp[csProgGuideLINQ#7](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_3.cs)]

En las consultas anteriores, solo la número 4 se ejecuta inmediatamente. Esto se debe a que devuelve un valor único, y no una colección <xref:System.Collections.Generic.IEnumerable%601> genérica. El propio método tiene que usar `foreach` para calcular su valor.

Cada una de las consultas anteriores puede escribirse mediante tipos implícitos con [var](../language-reference/keywords/var.md), como se muestra en el ejemplo siguiente:

[!code-csharp[csProgGuideLINQ#8](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_4.cs)]

## <a name="example---mixed-query-and-method-syntax"></a>Ejemplo: Sintaxis de consulta y método combinada

En este ejemplo se muestra cómo usar la sintaxis de método en los resultados de una cláusula de consulta. Simplemente escriba entre paréntesis la expresión de consulta y luego aplique el operador punto y llame al método. En el ejemplo siguiente la consulta número 7 devuelve un recuento de los números cuyo valor está comprendido entre 3 y 7. Pero en general es mejor usar una segunda variable para almacenar el resultado de la llamada a método. De esta manera es menos probable que la consulta se confunda con los resultados de la consulta.

[!code-csharp[csProgGuideLINQ#9](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_5.cs)]

Dado que la consulta número 7 devuelve un solo valor y no una colección, se ejecuta inmediatamente.

La consulta anterior puede escribirse mediante tipos implícitos con `var` como sigue:

```csharp
var numCount = (from num in numbers...
```

Puede escribirse en sintaxis de método como sigue:

```csharp
var numCount = numbers.Where(n => n < 3 || n > 7).Count();
```

Puede escribirse mediante tipos explícitos como sigue:

```csharp
int numCount = numbers.Where(n => n < 3 || n > 7).Count();
```

## <a name="see-also"></a>Vea también

- [Walkthrough: Writing Queries in C#](../programming-guide/concepts/linq/walkthrough-writing-queries-linq.md) (Tutorial: Escribir consultas en C#)
- [Language-Integrated Query (LINQ)](index.md)
- [where (cláusula)](../language-reference/keywords/where-clause.md)
