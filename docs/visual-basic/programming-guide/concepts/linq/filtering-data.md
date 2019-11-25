---
title: Filtrar datos
ms.date: 07/20/2015
ms.assetid: 7749519a-7edc-49fe-aef9-6a353864af6c
ms.openlocfilehash: 81e207e451055fb2952e4bf393db067f0851afb4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353493"
---
# <a name="filtering-data-visual-basic"></a>Filtering Data (Visual Basic)

El filtrado hace referencia a la operación de restringir el conjunto de resultados, de manera que solo contenga los elementos que cumplen una condición especificada. También se conoce como selección.

En la ilustración siguiente se muestran los resultados de filtrar una secuencia de caracteres. El predicado de la operación de filtrado especifica que el carácter debe ser "A".

![Diagrama que muestra una operación de filtrado en LINQ](./media/filtering-data/linq-filter-operation.png)

Los métodos del operador de consulta estándar que realizan selecciones se indican en la sección siguiente.

## <a name="methods"></a>Métodos

|Nombre del método|Descripción|Visual Basic Query Expression Syntax|Más información|
|-----------------|-----------------|------------------------------------------|----------------------|
|OfType|Selecciona valores en función de su capacidad para convertirse en un tipo especificado.|No disponible.|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|
|Where|Selecciona valores basados en una función de predicado.|`Where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a>Ejemplo de sintaxis de expresiones de consulta

The following example uses the `Where` to filter from an array those strings that have a specific length.

```vb
Dim words() As String = {"the", "quick", "brown", "fox", "jumps"}

Dim query = From word In words
            Where word.Length = 3
            Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In query
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' the
' fox
```

## <a name="see-also"></a>Vea también

- <xref:System.Linq>
- [Información general sobre operadores de consulta estándar (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Where (cláusula)](../../../../visual-basic/language-reference/queries/where-clause.md)
- [Cómo: Filtrar los resultados de una consulta](../../../../visual-basic/programming-guide/language-features/linq/how-to-filter-query-results-by-using-linq.md)
- [How to: Query An Assembly's Metadata with Reflection (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md)
- [How to: Query for Files with a Specified Attribute or Name (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)
- [How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
