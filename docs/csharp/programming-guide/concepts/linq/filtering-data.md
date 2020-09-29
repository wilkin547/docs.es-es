---
title: Filtrado de datos (C#)
description: El filtrado, también conocido como selección, restringe los resultados en función de una condición. Obtenga información sobre los métodos de operador de consulta estándar de LINQ en C# que realizan el filtrado.
ms.date: 07/20/2015
ms.assetid: fbaece0d-0f23-47f7-89c5-f3ea8db692b6
ms.openlocfilehash: 51bf9f930ba67ba07c7c0f357910d5e36014138d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186047"
---
# <a name="filtering-data-c"></a>Filtrado de datos (C#)

El filtrado hace referencia a la operación de restringir el conjunto de resultados, de manera que solo contenga los elementos que cumplen una condición especificada. También se conoce como selección.  
  
 En la ilustración siguiente se muestran los resultados de filtrar una secuencia de caracteres. El predicado de la operación de filtrado especifica que el carácter debe ser "A".  
  
 ![Diagrama que muestra una operación de filtrado en LINQ](./media/filtering-data/linq-filter-operation.png)  
  
 Los métodos del operador de consulta estándar que realizan selecciones se indican en la sección siguiente.  
  
## <a name="methods"></a>Métodos  
  
|Nombre del método|Descripción|Sintaxis de la expresión de consulta de C#|Más información|  
|-----------------|-----------------|---------------------------------|----------------------|  
|OfType|Selecciona valores en función de su capacidad para convertirse en un tipo especificado.|No es aplicable.|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|Where|Selecciona valores basados en una función de predicado.|`where`|<xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>|  
  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.Linq>
- [Información general sobre operadores de consulta estándar (C#)](./standard-query-operators-overview.md)
- [where (cláusula)](../../../language-reference/keywords/where-clause.md)
- [Especificar dinámicamente filtros con predicado en tiempo de ejecución](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
- [Procedimiento para consultar los metadatos de un ensamblado con reflexión (LINQ) (C#)](./how-to-query-an-assembly-s-metadata-with-reflection-linq.md)
- [Procedimiento para buscar archivos con un nombre o atributo especificados (C#)](./how-to-query-for-files-with-a-specified-attribute-or-name.md)
- [Procedimiento para ordenar o filtrar datos de texto por palabra o campo (LINQ) (C#)](./how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
