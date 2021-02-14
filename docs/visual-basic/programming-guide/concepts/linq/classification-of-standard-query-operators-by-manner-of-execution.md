---
description: Más información acerca de la clasificación de operadores de consulta estándar por modo de ejecución (Visual Basic)
title: Clasificación de operadores de consulta estándar por modo de ejecución
ms.date: 07/20/2015
ms.assetid: 7f55b0be-9f6e-44f8-865c-6afbea50cc54
ms.openlocfilehash: 286520f7697d7d88de903bd1965864942c1728e1
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100424572"
---
# <a name="classification-of-standard-query-operators-by-manner-of-execution-visual-basic"></a>Clasificación de operadores de consulta estándar por modo de ejecución (Visual Basic)

Las implementaciones de LINQ to Objects de los métodos de operador de consulta estándar se ejecutan de una de dos formas principales: inmediata o aplazada. Los operadores de consulta que usan la ejecución aplazada pueden dividirse además en dos categorías: de streaming y de no streaming. Si sabe cómo se ejecutan los diferentes operadores de consulta, puede servirle para entender los resultados que se obtienen de una consulta determinada. Esto es especialmente cierto si se está cambiando el origen de datos o si se está creando una consulta sobre otra. En este tema se clasifican los operadores de consulta estándar según su modo de ejecución.  
  
## <a name="manners-of-execution"></a>Modos de ejecución  
  
### <a name="immediate"></a>Inmediato  

 La ejecución inmediata significa que se lee el origen de datos y la operación se realiza en el punto en el código donde se declara la consulta. Todos los operadores de consulta estándar que devuelven un resultado único no enumerable se ejecutan de manera inmediata.  
  
### <a name="deferred"></a>Aplazada  

 La ejecución aplazada significa que la operación no se realiza en el punto en el código donde se declara la consulta. La operación se realiza solo cuando se enumera la variable de consulta, por ejemplo, mediante una instrucción `For Each`. Esto significa que los resultados de ejecutar la consulta dependen del contenido del origen de datos cuando se ejecuta la consulta en lugar de cuando se define la consulta. Si la variable de consulta se enumera varias veces, es posible que los resultados difieran cada vez. Casi todos los operadores de consulta estándar cuyo tipo de valor devuelto es <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IOrderedEnumerable%601> se ejecutan de una manera diferida.  
  
 Los operadores de consulta que usan la ejecución aplazada pueden clasificarse además como de streaming o de no streaming.  
  
#### <a name="streaming"></a>Streaming  

 Los operadores de streaming no deben leer todos los datos de origen antes de que produzcan elementos. En el momento de la ejecución, un operador de streaming realiza su operación en cada elemento de origen mientras se lee y proporciona el elemento si es necesario. Un operador de streaming continúa leyendo los elementos de origen hasta que se puede generar un elemento de resultado. Esto significa que es posible leer más de un elemento de origen para generar un elemento de resultado.  
  
#### <a name="non-streaming"></a>No streaming  

 Los operadores de no streaming deben leer todos los datos de origen antes de poder proporcionar un elemento de resultado. Las operaciones como la ordenación o la agrupación pertenecen a esta categoría. En tiempo de ejecución, los operadores de consulta de no streaming leen todos los datos de origen, los colocan en una estructura de datos, realizan la operación y proporcionan los elementos resultantes.  
  
## <a name="classification-table"></a>Tabla de clasificación  

 En la tabla siguiente se clasifica cada método de operador de consulta estándar según su método de ejecución.  
  
> [!NOTE]
> Si un operador se marca en dos columnas, dos secuencias de entrada intervienen en la operación, y cada secuencia se evalúa de manera diferente. En estos casos, siempre es la primera secuencia de la lista de parámetros la que se evalúa en un modo de transmisión diferido.  
  
|Operador de consulta estándar|Tipo devuelto|Ejecución inmediata|Ejecución aplazada de streaming|Ejecución aplazada de no streaming|  
|-----------------------------|-----------------|-------------------------|----------------------------------|---------------------------------------|  
|<xref:System.Linq.Enumerable.Aggregate%2A>|TSource|x|||  
|<xref:System.Linq.Enumerable.All%2A>|<xref:System.Boolean>|x|||  
|<xref:System.Linq.Enumerable.Any%2A>|<xref:System.Boolean>|x|||  
|<xref:System.Linq.Enumerable.AsEnumerable%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Average%2A>|Valor numérico único|x|||  
|<xref:System.Linq.Enumerable.Cast%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.Concat%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.Contains%2A>|<xref:System.Boolean>|x|||  
|<xref:System.Linq.Enumerable.Count%2A>|<xref:System.Int32>|x|||  
|<xref:System.Linq.Enumerable.DefaultIfEmpty%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.Distinct%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.ElementAt%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.ElementAtOrDefault%2A>|TSource|x|||  
|<xref:System.Linq.Enumerable.Empty%2A>|<xref:System.Collections.Generic.IEnumerable%601>|x|||  
|<xref:System.Linq.Enumerable.Except%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x|X|  
|<xref:System.Linq.Enumerable.First%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.FirstOrDefault%2A>|TSource|x|||  
|<xref:System.Linq.Enumerable.GroupBy%2A>|<xref:System.Collections.Generic.IEnumerable%601>|||x|  
|<xref:System.Linq.Enumerable.GroupJoin%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x|x|  
<xref:System.Linq.Enumerable.Intersect%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x|x|  
|<xref:System.Linq.Enumerable.Join%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x|X|  
|<xref:System.Linq.Enumerable.Last%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.LastOrDefault%2A>|TSource|x|||  
|<xref:System.Linq.Enumerable.LongCount%2A>|<xref:System.Int64>|X|||  
|<xref:System.Linq.Enumerable.Max%2A>|Valor numérico único, TSource o TResult|X|||  
|<xref:System.Linq.Enumerable.Min%2A>|Valor numérico único, TSource o TResult|x|||  
|<xref:System.Linq.Enumerable.OfType%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.OrderBy%2A>|<xref:System.Linq.IOrderedEnumerable%601>|||x|  
|<xref:System.Linq.Enumerable.OrderByDescending%2A>|<xref:System.Linq.IOrderedEnumerable%601>|||x|  
|<xref:System.Linq.Enumerable.Range%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.Repeat%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.Reverse%2A>|<xref:System.Collections.Generic.IEnumerable%601>|||x|  
|<xref:System.Linq.Enumerable.Select%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.SelectMany%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.SequenceEqual%2A>|<xref:System.Boolean>|X|||  
|<xref:System.Linq.Enumerable.Single%2A>|TSource|X|||  
|<xref:System.Linq.Enumerable.SingleOrDefault%2A>|TSource|x|||  
|<xref:System.Linq.Enumerable.Skip%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.SkipWhile%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
|<xref:System.Linq.Enumerable.Sum%2A>|Valor numérico único|x|||  
|<xref:System.Linq.Enumerable.Take%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x||  
<xref:System.Linq.Enumerable.TakeWhile%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.ThenBy%2A>|<xref:System.Linq.IOrderedEnumerable%601>|||x|  
|<xref:System.Linq.Enumerable.ThenByDescending%2A>|<xref:System.Linq.IOrderedEnumerable%601>|||X|  
|<xref:System.Linq.Enumerable.ToArray%2A>|Matriz de TSource|x|||  
|<xref:System.Linq.Enumerable.ToDictionary%2A>|<xref:System.Collections.Generic.Dictionary%602>|x|||  
|<xref:System.Linq.Enumerable.ToList%2A>|<xref:System.Collections.Generic.IList%601>|x|||  
|<xref:System.Linq.Enumerable.ToLookup%2A>|<xref:System.Linq.ILookup%602>|x|||  
|<xref:System.Linq.Enumerable.Union%2A>|<xref:System.Collections.Generic.IEnumerable%601>||x||  
|<xref:System.Linq.Enumerable.Where%2A>|<xref:System.Collections.Generic.IEnumerable%601>||X||  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Linq.Enumerable>
- [Información general sobre operadores de consulta estándar (Visual Basic)](standard-query-operators-overview.md)
- [Sintaxis de expresiones de consulta para operadores de consulta estándar (Visual Basic)](query-expression-syntax-for-standard-query-operators.md)
- [LINQ to Objects (Visual Basic)](linq-to-objects.md)
