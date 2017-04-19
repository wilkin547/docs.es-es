---
title: "Clasificación de operadores de consulta estándar por modo de ejecución (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: 7f55b0be-9f6e-44f8-865c-6afbea50cc54
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a13f2fcf33c2faacd5b2662cd96d0f962b54322f
ms.lasthandoff: 03/13/2017

---
# <a name="classification-of-standard-query-operators-by-manner-of-execution-visual-basic"></a>Clasificación de operadores de consulta estándar por modo de ejecución (Visual Basic)
Para implementaciones de objetos de los métodos de operador de consulta estándar LINQ que se ejecutan en uno de dos formas principales: inmediata o aplazada. Los operadores de consulta que utilizan la ejecución aplazada pueden dividirse además en dos categorías: transmisión por secuencias y sin transmisión por secuencias. Si sabe cómo ejecutan los operadores de consulta diferentes, puede ser útil entender los resultados que obtendrá de una consulta determinada. Esto es especialmente cierto si está cambiando el origen de datos o si está creando una consulta sobre otra. Este tema clasifican los operadores de consulta estándar según su modo de ejecución.  
  
## <a name="manners-of-execution"></a>Modos de ejecución  
  
### <a name="immediate"></a>Inmediato  
 Ejecución inmediata significa que el origen de datos es de lectura y la operación se realiza en el punto en el código donde se declara la consulta. Todos los operadores de consulta estándar que devuelven un resultado único no enumerable se ejecutan inmediatamente.  
  
### <a name="deferred"></a>Aplazada  
 Ejecución diferida significa que la operación no se realiza en el punto en el código donde se declara la consulta. La operación se realiza solo cuando se enumera la variable de consulta, por ejemplo, con un `For Each` instrucción. Esto significa que los resultados de ejecutar la consulta dependen del contenido del origen de datos cuando se ejecuta la consulta en lugar de cuando se define la consulta. Si la variable de consulta se enumera varias veces, los resultados pueden diferir cada vez. Casi todos los operadores de consulta estándar cuyo tipo de valor devuelto es <xref:System.Collections.Generic.IEnumerable%601>o <xref:System.Linq.IOrderedEnumerable%601>ejecutar de manera aplazada.</xref:System.Linq.IOrderedEnumerable%601> </xref:System.Collections.Generic.IEnumerable%601>  
  
 Operadores de consulta que utilizan la ejecución aplazada pueden clasificarse como de transmisión por secuencias o sin transmisión por secuencias.  
  
#### <a name="streaming"></a>Streaming  
 Operadores de transmisión por secuencias no deben leer todos los datos de origen antes de que producen los elementos. En tiempo de ejecución, un operador realice su operación en cada elemento de origen, tal como se lee y proporciona el elemento si es necesario. Un operador de flujo continúa leer los elementos de origen hasta que se puede generar un elemento de resultado. Esto significa que se pueden leer más de un elemento de origen para generar un elemento de resultado.  
  
#### <a name="non-streaming"></a>Sin transmisión por secuencias  
 Operadores sin transmisión por secuencias deben leer todos los datos de origen para poder proporcionar un elemento de resultado. Las operaciones como la ordenación o agrupación pertenecen a esta categoría. En tiempo de ejecución, los operadores de consulta sin transmisión por secuencias leen todos los datos de origen, ponerla en una estructura de datos, realizan la operación y proporcionan los elementos resultantes.  
  
## <a name="classification-table"></a>Tabla de clasificación  
 En la tabla siguiente se clasifica cada método de operador de consulta estándar según su método de ejecución.  
  
> [!NOTE]
>  Si un operador aparece en dos columnas, dos secuencias de entrada intervienen en la operación, y cada secuencia se evalúa de manera diferente. En estos casos, siempre es la primera secuencia de la lista de parámetros que se evalúa en diferido, modo de transmisión.  
  
|Operador de consulta estándar|Tipo devuelto|Ejecución inmediata|Ejecución aplazada de transmisión por secuencias|Aplaza la ejecución de secuencias no|  
|-----------------------------|-----------------|-------------------------|----------------------------------|---------------------------------------|  
|<xref:System.Linq.Enumerable.Aggregate%2A></xref:System.Linq.Enumerable.Aggregate%2A>|TSource|x|||  
|<xref:System.Linq.Enumerable.All%2A></xref:System.Linq.Enumerable.All%2A>|<xref:System.Boolean></xref:System.Boolean>|x|||  
|<xref:System.Linq.Enumerable.Any%2A></xref:System.Linq.Enumerable.Any%2A>|<xref:System.Boolean></xref:System.Boolean>|x|||  
|<xref:System.Linq.Enumerable.AsEnumerable%2A></xref:System.Linq.Enumerable.AsEnumerable%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.Average%2A></xref:System.Linq.Enumerable.Average%2A>|Valor numérico único|x|||  
|<xref:System.Linq.Enumerable.Cast%2A></xref:System.Linq.Enumerable.Cast%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.Concat%2A></xref:System.Linq.Enumerable.Concat%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.Contains%2A></xref:System.Linq.Enumerable.Contains%2A>|<xref:System.Boolean></xref:System.Boolean>|x|||  
|<xref:System.Linq.Enumerable.Count%2A></xref:System.Linq.Enumerable.Count%2A>|<xref:System.Int32></xref:System.Int32>|x|||  
|<xref:System.Linq.Enumerable.DefaultIfEmpty%2A></xref:System.Linq.Enumerable.DefaultIfEmpty%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.Distinct%2A></xref:System.Linq.Enumerable.Distinct%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.ElementAt%2A></xref:System.Linq.Enumerable.ElementAt%2A>|TSource|x|||  
|<xref:System.Linq.Enumerable.ElementAtOrDefault%2A></xref:System.Linq.Enumerable.ElementAtOrDefault%2A>|TSource|x|||  
|<xref:System.Linq.Enumerable.Empty%2A></xref:System.Linq.Enumerable.Empty%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>|x|||  
|<xref:System.Linq.Enumerable.Except%2A></xref:System.Linq.Enumerable.Except%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||x|x|  
|<xref:System.Linq.Enumerable.First%2A></xref:System.Linq.Enumerable.First%2A>|TSource|x|||  
|<xref:System.Linq.Enumerable.FirstOrDefault%2A></xref:System.Linq.Enumerable.FirstOrDefault%2A>|TSource|x|||  
|<xref:System.Linq.Enumerable.GroupBy%2A></xref:System.Linq.Enumerable.GroupBy%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>|||x|  
|<xref:System.Linq.Enumerable.GroupJoin%2A></xref:System.Linq.Enumerable.GroupJoin%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||x|x|  
<xref:System.Linq.Enumerable.Intersect%2A></xref:System.Linq.Enumerable.Intersect%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||x|x|  
|<xref:System.Linq.Enumerable.Join%2A></xref:System.Linq.Enumerable.Join%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||x|x|  
|<xref:System.Linq.Enumerable.Last%2A></xref:System.Linq.Enumerable.Last%2A>|TSource|x|||  
|<xref:System.Linq.Enumerable.LastOrDefault%2A></xref:System.Linq.Enumerable.LastOrDefault%2A>|TSource|x|||  
|<xref:System.Linq.Enumerable.LongCount%2A></xref:System.Linq.Enumerable.LongCount%2A>|<xref:System.Int64></xref:System.Int64>|x|||  
|<xref:System.Linq.Enumerable.Max%2A></xref:System.Linq.Enumerable.Max%2A>|Valor numérico único, TSource o TResult|x|||  
|<xref:System.Linq.Enumerable.Min%2A></xref:System.Linq.Enumerable.Min%2A>|Valor numérico único, TSource o TResult|x|||  
|<xref:System.Linq.Enumerable.OfType%2A></xref:System.Linq.Enumerable.OfType%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.OrderBy%2A></xref:System.Linq.Enumerable.OrderBy%2A>|<xref:System.Linq.IOrderedEnumerable%601></xref:System.Linq.IOrderedEnumerable%601>|||x|  
|<xref:System.Linq.Enumerable.OrderByDescending%2A></xref:System.Linq.Enumerable.OrderByDescending%2A>|<xref:System.Linq.IOrderedEnumerable%601></xref:System.Linq.IOrderedEnumerable%601>|||x|  
|<xref:System.Linq.Enumerable.Range%2A></xref:System.Linq.Enumerable.Range%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.Repeat%2A></xref:System.Linq.Enumerable.Repeat%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.Reverse%2A></xref:System.Linq.Enumerable.Reverse%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>|||x|  
|<xref:System.Linq.Enumerable.Select%2A></xref:System.Linq.Enumerable.Select%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.SelectMany%2A></xref:System.Linq.Enumerable.SelectMany%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.SequenceEqual%2A></xref:System.Linq.Enumerable.SequenceEqual%2A>|<xref:System.Boolean></xref:System.Boolean>|x|||  
|<xref:System.Linq.Enumerable.Single%2A></xref:System.Linq.Enumerable.Single%2A>|TSource|x|||  
|<xref:System.Linq.Enumerable.SingleOrDefault%2A></xref:System.Linq.Enumerable.SingleOrDefault%2A>|TSource|x|||  
|<xref:System.Linq.Enumerable.Skip%2A></xref:System.Linq.Enumerable.Skip%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.SkipWhile%2A></xref:System.Linq.Enumerable.SkipWhile%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.Sum%2A></xref:System.Linq.Enumerable.Sum%2A>|Valor numérico único|x|||  
|<xref:System.Linq.Enumerable.Take%2A></xref:System.Linq.Enumerable.Take%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||x||  
<xref:System.Linq.Enumerable.TakeWhile%2A></xref:System.Linq.Enumerable.TakeWhile%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.ThenBy%2A></xref:System.Linq.Enumerable.ThenBy%2A>|<xref:System.Linq.IOrderedEnumerable%601></xref:System.Linq.IOrderedEnumerable%601>|||x|  
|<xref:System.Linq.Enumerable.ThenByDescending%2A></xref:System.Linq.Enumerable.ThenByDescending%2A>|<xref:System.Linq.IOrderedEnumerable%601></xref:System.Linq.IOrderedEnumerable%601>|||x|  
|<xref:System.Linq.Enumerable.ToArray%2A></xref:System.Linq.Enumerable.ToArray%2A>|Matriz de TSource|x|||  
|<xref:System.Linq.Enumerable.ToDictionary%2A></xref:System.Linq.Enumerable.ToDictionary%2A>|<xref:System.Collections.Generic.Dictionary%602></xref:System.Collections.Generic.Dictionary%602>|x|||  
|<xref:System.Linq.Enumerable.ToList%2A></xref:System.Linq.Enumerable.ToList%2A>|<xref:System.Collections.Generic.IList%601></xref:System.Collections.Generic.IList%601>|x|||  
|<xref:System.Linq.Enumerable.ToLookup%2A></xref:System.Linq.Enumerable.ToLookup%2A>|<xref:System.Linq.ILookup%602></xref:System.Linq.ILookup%602>|x|||  
|<xref:System.Linq.Enumerable.Union%2A></xref:System.Linq.Enumerable.Union%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.Where%2A></xref:System.Linq.Enumerable.Where%2A>|<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>||x||  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Linq.Enumerable></xref:System.Linq.Enumerable>   
 [Información general sobre operadores de consulta estándar (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Sintaxis de expresiones de consulta para operadores de consulta estándar (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md)   
 [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
