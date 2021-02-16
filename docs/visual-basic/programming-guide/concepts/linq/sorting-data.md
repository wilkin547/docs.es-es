---
description: Más información acerca de la ordenación de datos (Visual Basic)
title: Ordenación de datos
ms.date: 07/20/2015
ms.assetid: 6f81065c-0c89-4bf3-a6d8-442273f8810e
ms.openlocfilehash: 83e05b2af1b3421d004a87630cd5df43f2a21ae4
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100468556"
---
# <a name="sorting-data-visual-basic"></a>Ordenar datos (Visual Basic)

Una operación de ordenación ordena los elementos de una secuencia según uno o varios atributos. El primer criterio de ordenación realiza una ordenación primaria de los elementos. Al especificar un segundo criterio de ordenación, se pueden ordenar los elementos dentro de cada grupo de ordenación primaria.

En la ilustración siguiente se muestran los resultados de una operación de ordenación alfabética en una secuencia de caracteres.

![Gráfico que muestra una operación de ordenación alfabética.](./media/sorting-data/alphabetical-sort-operation.png)

Los métodos de operador de consulta estándar que ordenan datos de datos se enumeran en la sección siguiente.

## <a name="methods"></a>Métodos

|Nombre del método|Descripción|Visual Basic sintaxis de expresiones de consulta|Más información|
|-----------------|-----------------|------------------------------------------|----------------------|
|OrderBy|Ordena valores en orden ascendente.|`Order By`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|
|OrderByDescending|Ordena valores en orden descendente.|`Order By … Descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|
|ThenBy|Realiza una ordenación secundaria en orden ascendente.|`Order By …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|
|ThenByDescending|Realiza una ordenación secundaria en orden descendente.|`Order By …, … Descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|
|Reverse|Invierte el orden de los elementos de una colección.|No es aplicable.|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-examples"></a>Ejemplos de sintaxis de expresiones de consulta

### <a name="primary-sort-examples"></a>Ejemplos de ordenación principal

#### <a name="primary-ascending-sort"></a>Orden ascendente principal

En el siguiente ejemplo se muestra cómo usar la cláusula `Order By` en una consulta LINQ para ordenar las cadenas de una matriz por la longitud de la cadena, en orden ascendente.

```vb
Dim words = {"the", "quick", "brown", "fox", "jumps"}

Dim sortQuery = From word In words
                Order By word.Length
                Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In sortQuery
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' the
' fox
' quick
' brown
' jumps
```

#### <a name="primary-descending-sort"></a>Orden descendente principal

En el siguiente ejemplo se muestra cómo usar la cláusula `Order By Descending` en una consulta LINQ para ordenar las cadenas por su letra inicial, en orden descendente.

```vb
Dim words = {"the", "quick", "brown", "fox", "jumps"}

Dim sortQuery = From word In words
                Order By word.Substring(0, 1) Descending
                Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In sortQuery
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' the
' quick
' jumps
' fox
' brown
```

### <a name="secondary-sort-examples"></a>Ejemplos de ordenación secundaria

#### <a name="secondary-ascending-sort"></a>Orden ascendente secundario

En el siguiente ejemplo se muestra cómo usar la cláusula `Order By` en una consulta LINQ para realizar una ordenación principal y secundaria de las cadenas de una matriz. Las cadenas se ordenan primero por su longitud y, después, por la letra inicial de la cadena, en orden ascendente.

```vb
Dim words = {"the", "quick", "brown", "fox", "jumps"}

Dim sortQuery = From word In words
                Order By word.Length, word.Substring(0, 1)
                Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In sortQuery
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' fox
' the
' brown
' jumps
' quick
```

#### <a name="secondary-descending-sort"></a>Orden descendente secundario

En el siguiente ejemplo se muestra cómo usar la cláusula `Order By Descending` en una consulta LINQ para realizar una ordenación principal en orden ascendente y una ordenación secundaria en orden descendente. Las cadenas se ordenan primero por su longitud y, después, por la letra inicial de la cadena.

```vb
Dim words = {"the", "quick", "brown", "fox", "jumps"}

Dim sortQuery = From word In words
                Order By word.Length, word.Substring(0, 1) Descending
                Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In sortQuery
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' fox
' the
' quick
' jumps
' brown
```

## <a name="see-also"></a>Consulte también

- <xref:System.Linq>
- [Información general sobre operadores de consulta estándar (Visual Basic)](standard-query-operators-overview.md)
- [Cláusula order by](../../../language-reference/queries/order-by-clause.md)
- [Cómo: Ordenar los resultados de una consulta](../../language-features/linq/how-to-sort-query-results-by-using-linq.md)
- [Cómo ordenar o filtrar datos de texto por palabra o campo (LINQ) (Visual Basic)](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
