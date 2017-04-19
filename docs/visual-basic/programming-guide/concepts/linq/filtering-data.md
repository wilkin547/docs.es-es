---
title: Filtrar datos (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 7749519a-7edc-49fe-aef9-6a353864af6c
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3751164b7697b63937611c77d9fda0e2873625d8
ms.lasthandoff: 03/13/2017

---
# <a name="filtering-data-visual-basic"></a>Filtrar datos (Visual Basic)
Filtrado hace referencia a la operación de restringir el conjunto de resultados a sólo contenga los elementos que cumplen una condición especificada. Es también conocida como selección.  
  
 La ilustración siguiente muestra los resultados de filtrar una secuencia de caracteres. El predicado de la operación de filtrado especifica que el carácter debe ser 'A'.  
  
 ![Operación de filtrado de LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")  
  
 Los métodos de operador de consulta estándar que realizan la selección se enumeran en la sección siguiente.  
  
## <a name="methods"></a>Métodos  
  
|Nombre del método|Descripción|Sintaxis de expresiones de consulta de Visual Basic|Más información|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|OfType|Selecciona valores en función de su capacidad para convertirse en un tipo especificado.|No es aplicable.|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName>|  
|Where|Selecciona los valores que se basan en una función de predicado.|`Where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=fullName></xref:System.Linq.Queryable.Where%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-example"></a>Ejemplo de sintaxis de expresiones de consulta  
 En el ejemplo siguiente se usa el `Where` filtrar a partir de una matriz las cadenas que tienen una longitud concreta.  
  
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
 <xref:System.Linq></xref:System.Linq>   
 [Información general sobre operadores de consulta estándar (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Donde cláusula](../../../../visual-basic/language-reference/queries/where-clause.md)   
 [Cómo: filtrar los resultados de consulta](../../../../visual-basic/programming-guide/language-features/linq/how-to-filter-query-results-by-using-linq.md)   
 [Cómo: consultar los metadatos de un ensamblado con reflexión (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md)   
 [Cómo: buscar archivos con un atributo especificado o un nombre (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)   
 [Cómo: ordenar o filtrar los datos de texto por palabra o campo (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
