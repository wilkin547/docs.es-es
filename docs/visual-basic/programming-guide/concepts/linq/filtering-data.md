---
description: Más información acerca de cómo filtrar datos (Visual Basic)
title: Filtrado de datos
ms.date: 07/20/2015
ms.assetid: 7749519a-7edc-49fe-aef9-6a353864af6c
ms.openlocfilehash: 2e259209df35a89eb4730f79ffccfee7cb64b9e9
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100428602"
---
# <a name="filtering-data-visual-basic"></a>Filtrar datos (Visual Basic)

El filtrado hace referencia a la operación de restringir el conjunto de resultados, de manera que solo contenga los elementos que cumplen una condición especificada. También se conoce como selección.

En la ilustración siguiente se muestran los resultados de filtrar una secuencia de caracteres. El predicado de la operación de filtrado especifica que el carácter debe ser "A".

![Diagrama que muestra una operación de filtrado en LINQ](./media/filtering-data/linq-filter-operation.png)

Los métodos del operador de consulta estándar que realizan selecciones se indican en la sección siguiente.

## <a name="methods"></a>Métodos

|Nombre del método|Descripción|Visual Basic sintaxis de expresiones de consulta|Más información|
|-----------------|-----------------|------------------------------------------|----------------------|
|OfType|Selecciona valores en función de su capacidad para convertirse en un tipo especificado.|No es aplicable.|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|
|Where|Selecciona valores basados en una función de predicado.|`Where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a>Ejemplo de sintaxis de expresiones de consulta

En el ejemplo siguiente `Where` se utiliza para filtrar de una matriz las cadenas que tienen una longitud específica.

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

## <a name="see-also"></a>Consulte también

- <xref:System.Linq>
- [Información general sobre operadores de consulta estándar (Visual Basic)](standard-query-operators-overview.md)
- [Cláusula WHERE](../../../language-reference/queries/where-clause.md)
- [Cómo: Filtrar los resultados de una consulta](../../language-features/linq/how-to-filter-query-results-by-using-linq.md)
- [Cómo: consultar los metadatos de un ensamblado con reflexión (LINQ) (Visual Basic)](how-to-query-an-assembly-s-metadata-with-reflection-linq.md)
- [Cómo: buscar archivos con un nombre o atributo especificados (Visual Basic)](how-to-query-for-files-with-a-specified-attribute-or-name.md)
- [Cómo ordenar o filtrar datos de texto por palabra o campo (LINQ) (Visual Basic)](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
