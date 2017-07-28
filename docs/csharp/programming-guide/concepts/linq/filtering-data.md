---
title: Filtrado de datos (C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: fbaece0d-0f23-47f7-89c5-f3ea8db692b6
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: defa6716f677c44da5dd27cb64b3b1d140a65272
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="filtering-data-c"></a>Filtrado de datos (C#)
El filtrado hace referencia a la operación de restringir el conjunto de resultados, de manera que solo contenga los elementos que cumplen una condición especificada. También se conoce como selección.  
  
 En la ilustración siguiente se muestran los resultados de filtrar una secuencia de caracteres. El predicado de la operación de filtrado especifica que el carácter debe ser "A".  
  
 ![Operación de filtrado en LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_filter.png "LINQ_Filter")  
  
 Los métodos del operador de consulta estándar que realizan selecciones se indican en la sección siguiente.  
  
## <a name="methods"></a>Métodos  
  
|Nombre del método|Descripción|Sintaxis de la expresión de consulta de C#|Más información|  
|-----------------|-----------------|---------------------------------|----------------------|  
|OfType|Selecciona valores en función de su capacidad para convertirse en un tipo especificado.|No es aplicable.|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName>|  
|Where|Selecciona valores basados en una función de predicado.|`where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-example"></a>Ejemplo de sintaxis de expresiones de consulta  
 En el siguiente ejemplo se usa la cláusula `where` para filtrar de una matriz aquellas cadenas que tienen una longitud específica.  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            where word.Length == 3  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
*/  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Linq>   
 [Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) (Información general sobre operadores de consulta estándar (C#))  
 [where (Cláusula)](../../../../csharp/language-reference/keywords/where-clause.md)   
 [Cómo: Especificar dinámicamente filtros con predicado en tiempo de ejecución](../../../../csharp/programming-guide/linq-query-expressions/how-to-dynamically-specify-predicate-filters-at-runtime.md)   
 [Cómo: Consultar los metadatos de un ensamblado con reflexión (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-assembly-s-metadata-with-reflection-linq.md)   
 [How to: Query for Files with a Specified Attribute or Name (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-files-with-a-specified-attribute-or-name.md)  (Cómo: Consultar archivos con un nombre o atributo especificado (C#))  
 [Cómo ordenar o filtrar datos de texto por palabra o campo (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)

