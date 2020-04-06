---
title: Conservar el orden en PLINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, order preservation
ms.assetid: 10d202bc-19e1-4b5c-bbf1-9a977322a9ca
ms.openlocfilehash: 0e9b4510757fc0f98b2edfbe1c656cdb5f6bce72
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588635"
---
# <a name="order-preservation-in-plinq"></a>Conservar el orden en PLINQ
En PLINQ, el objetivo es maximizar el rendimiento manteniendo la exactitud. Una consulta se debería ejecutar lo más rápido que fuese posible pero con resultados correctos. La exactitud exige que se conserve el orden de la secuencia de origen en algunos casos; sin embargo, la ordenación puede suponer la utilización de muchos recursos de computación. Por consiguiente, de forma predeterminada, PLINQ no conserva el orden de la secuencia de origen. En este sentido, PLINQ se parece a [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)], pero es diferente de LINQ to Objects, que conserva el orden.  
  
 Para reemplazar el comportamiento predeterminado, puede activar la capacidad de conservar el orden utilizando el operador <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> en la secuencia de origen. Después, puede desactivarla en la consulta, utilizando el método <xref:System.Linq.ParallelEnumerable.AsUnordered%2A>. Con ambos métodos, se procesa la consulta basándose en la heurística que determina si la consulta se debe ejecutar de forma paralela o secuencial. Para más información, consulte [Introducción a la velocidad en PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
 En el siguiente ejemplo se muestra una consulta paralela no ordenada que filtra todos los elementos que coinciden con una condición, sin intentar ordenar los resultados de forma alguna.  
  
 [!code-csharp[PLINQ#8](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#8)]
 [!code-vb[PLINQ#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#8)]  
  
 Esta consulta no obtiene necesariamente las 1000 primeras ciudades de la secuencia de origen que cumplen la condición, sino que algún conjunto de las 1000 ciudades que la cumplen. Los operadores de consulta PLINQ particionan la secuencia de origen en varias secuencias secundarias que se procesan como tareas simultáneas. Si no se especifica que se conserve el orden, los resultados de cada partición se presentan a la siguiente etapa de la consulta con un orden arbitrario. Por otra parte, una partición puede producir un subconjunto de los resultados antes de continuar procesando los elementos restantes. El orden resultante puede ser diferente cada vez. Una aplicación no puede controlar este hecho, porque depende de cómo programe los subprocesos el sistema operativo.  
  
 En el siguiente ejemplo se reemplaza el comportamiento predeterminado utilizando al operador <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> en la secuencia de origen. De esta forma se garantiza que el método <xref:System.Linq.ParallelEnumerable.Take%2A> devuelve las 1000 primeras ciudades de la secuencia de origen que cumplen la condición.  
  
 [!code-csharp[PLINQ#9](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#9)]
 [!code-vb[PLINQ#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#9)]  
  
 Sin embargo, esta consulta probablemente no se ejecute tan rápido como la versión no ordenada, porque debe realizar el seguimiento del orden original en todas las particiones y, en el momento de la fusión mediante combinación, garantizar que el orden es coherente. Por consiguiente, recomendamos usar <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> solo cuando sea estrictamente necesario y únicamente para las partes de la consulta que lo requieran. Cuando ya no sea necesario conservar el orden, use <xref:System.Linq.ParallelEnumerable.AsUnordered%2A> para desactivarlo. En el siguiente ejemplo se consigue mediante la creación de dos consultas.  
  
 [!code-csharp[PLINQ#6](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#6)]
 [!code-vb[PLINQ#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#6)]  
  
 Observe que PLINQ conserva el orden de una secuencia generada por operadores que imponen el orden para el resto de la consulta. En otras palabras, los operadores de tipo <xref:System.Linq.ParallelEnumerable.OrderBy%2A> y <xref:System.Linq.ParallelEnumerable.ThenBy%2A> se tratan como si fuesen seguidos de una llamada a <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>.  
  
## <a name="query-operators-and-ordering"></a>Operadores de consulta y ordenación  
 Los siguientes operadores de consulta introducen la conservación del orden en todas las operaciones posteriores de una consulta o hasta que se llame a <xref:System.Linq.ParallelEnumerable.AsUnordered%2A>:  
  
- <xref:System.Linq.ParallelEnumerable.OrderBy%2A>  
  
- <xref:System.Linq.ParallelEnumerable.OrderByDescending%2A>  
  
- <xref:System.Linq.ParallelEnumerable.ThenBy%2A>  
  
- <xref:System.Linq.ParallelEnumerable.ThenByDescending%2A>  
  
 En algunos casos, los siguientes operadores de consulta PLINQ pueden requerir secuencias de origen ordenadas para generar resultados correctos:  
  
- <xref:System.Linq.ParallelEnumerable.Reverse%2A>  
  
- <xref:System.Linq.ParallelEnumerable.SequenceEqual%2A>  
  
- <xref:System.Linq.ParallelEnumerable.TakeWhile%2A>  
  
- <xref:System.Linq.ParallelEnumerable.SkipWhile%2A>  
  
- <xref:System.Linq.ParallelEnumerable.Zip%2A>  
  
 Algunos operadores de consulta PLINQ se comportan de manera diferente, dependiendo de si su secuencia de origen está ordenada o no. En la siguiente tabla se enumeran estos operadores.  
  
|"??"|Resultado cuando la secuencia de origen está ordenada|Resultado cuando la secuencia de origen no está ordenada|  
|--------------|------------------------------------------------|--------------------------------------------------|  
|<xref:System.Linq.ParallelEnumerable.Aggregate%2A>|Salida no determinista para operaciones no asociativas o no conmutativas.|Salida no determinista para operaciones no asociativas o no conmutativas.|  
|<xref:System.Linq.ParallelEnumerable.All%2A>|No aplicable|No aplicable|  
|<xref:System.Linq.ParallelEnumerable.Any%2A>|No aplicable|No aplicable|  
|<xref:System.Linq.ParallelEnumerable.AsEnumerable%2A>|No aplicable|No aplicable|  
|<xref:System.Linq.ParallelEnumerable.Average%2A>|Salida no determinista para operaciones no asociativas o no conmutativas.|Salida no determinista para operaciones no asociativas o no conmutativas.|  
|<xref:System.Linq.ParallelEnumerable.Cast%2A>|Resultados ordenados|Resultados no ordenados|  
|<xref:System.Linq.ParallelEnumerable.Concat%2A>|Resultados ordenados|Resultados no ordenados|  
|<xref:System.Linq.ParallelEnumerable.Count%2A>|No aplicable|No aplicable|  
|<xref:System.Linq.ParallelEnumerable.DefaultIfEmpty%2A>|No aplicable|No aplicable|  
|<xref:System.Linq.ParallelEnumerable.Distinct%2A>|Resultados ordenados|Resultados no ordenados|  
|<xref:System.Linq.ParallelEnumerable.ElementAt%2A>|Se devuelve el elemento especificado|Elemento arbitrario|  
|<xref:System.Linq.ParallelEnumerable.ElementAtOrDefault%2A>|Se devuelve el elemento especificado|Elemento arbitrario|  
|<xref:System.Linq.ParallelEnumerable.Except%2A>|Resultados no ordenados|Resultados no ordenados|  
|<xref:System.Linq.ParallelEnumerable.First%2A>|Se devuelve el elemento especificado|Elemento arbitrario|  
|<xref:System.Linq.ParallelEnumerable.FirstOrDefault%2A>|Se devuelve el elemento especificado|Elemento arbitrario|  
|<xref:System.Linq.ParallelEnumerable.ForAll%2A>|Ejecución no determinista en paralelo|Ejecución no determinista en paralelo|  
|<xref:System.Linq.ParallelEnumerable.GroupBy%2A>|Resultados ordenados|Resultados no ordenados|  
|<xref:System.Linq.ParallelEnumerable.GroupJoin%2A>|Resultados ordenados|Resultados no ordenados|  
|<xref:System.Linq.ParallelEnumerable.Intersect%2A>|Resultados ordenados|Resultados no ordenados|  
|<xref:System.Linq.ParallelEnumerable.Join%2A>|Resultados ordenados|Resultados no ordenados|  
|<xref:System.Linq.ParallelEnumerable.Last%2A>|Se devuelve el elemento especificado|Elemento arbitrario|  
|<xref:System.Linq.ParallelEnumerable.LastOrDefault%2A>|Se devuelve el elemento especificado|Elemento arbitrario|  
|<xref:System.Linq.ParallelEnumerable.LongCount%2A>|No aplicable|No aplicable|  
|<xref:System.Linq.ParallelEnumerable.Min%2A>|No aplicable|No aplicable|  
|<xref:System.Linq.ParallelEnumerable.OrderBy%2A>|Reordena la secuencia|Inicia una nueva sección ordenada|  
|<xref:System.Linq.ParallelEnumerable.OrderByDescending%2A>|Reordena la secuencia|Inicia una nueva sección ordenada|  
|<xref:System.Linq.ParallelEnumerable.Range%2A>|No aplicable (el mismo valor predeterminado que <xref:System.Linq.ParallelEnumerable.AsParallel%2A>)|No aplicable|  
|<xref:System.Linq.ParallelEnumerable.Repeat%2A>|No aplicable (el mismo valor predeterminado que <xref:System.Linq.ParallelEnumerable.AsParallel%2A>)|No aplicable|  
|<xref:System.Linq.ParallelEnumerable.Reverse%2A>|Invierte el orden|No hace nada|  
|<xref:System.Linq.ParallelEnumerable.Select%2A>|Resultados ordenados|Resultados no ordenados|  
|<xref:System.Linq.ParallelEnumerable.Select%2A> (indexada)|Resultados ordenados|Resultados no ordenados.|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A>|Resultados ordenados.|Resultados no ordenados|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A> (indexada)|Resultados ordenados.|Resultados no ordenados.|  
|<xref:System.Linq.ParallelEnumerable.SequenceEqual%2A>|Comparación ordenada|Comparación no ordenada|  
|<xref:System.Linq.ParallelEnumerable.Single%2A>|No aplicable|No aplicable|  
|<xref:System.Linq.ParallelEnumerable.SingleOrDefault%2A>|No aplicable|No aplicable|  
|<xref:System.Linq.ParallelEnumerable.Skip%2A>|Omite los primeros *n* elementos|Omite todos los *n* elementos|  
|<xref:System.Linq.ParallelEnumerable.SkipWhile%2A>|Resultados ordenados.|No determinista. Ejecuta SkipWhile en el orden arbitrario actual|  
|<xref:System.Linq.ParallelEnumerable.Sum%2A>|Salida no determinista para operaciones no asociativas o no conmutativas.|Salida no determinista para operaciones no asociativas o no conmutativas.|  
|<xref:System.Linq.ParallelEnumerable.Take%2A>|Toma los `n` primeros elementos|Toma cualquier elemento `n`|  
|<xref:System.Linq.ParallelEnumerable.TakeWhile%2A>|Resultados ordenados|No determinista. Ejecuta TakeWhile en el orden arbitrario actual|  
|<xref:System.Linq.ParallelEnumerable.ThenBy%2A>|Complementa `OrderBy`|Complementa `OrderBy`|  
|<xref:System.Linq.ParallelEnumerable.ThenByDescending%2A>|Complementa `OrderBy`|Complementa `OrderBy`|  
|<xref:System.Linq.ParallelEnumerable.ToArray%2A>|Resultados ordenados|Resultados no ordenados|  
|<xref:System.Linq.ParallelEnumerable.ToDictionary%2A>|No aplicable|No aplicable|  
|<xref:System.Linq.ParallelEnumerable.ToList%2A>|Resultados ordenados|Resultados no ordenados|  
|<xref:System.Linq.ParallelEnumerable.ToLookup%2A>|Resultados ordenados|Resultados no ordenados|  
|<xref:System.Linq.ParallelEnumerable.Union%2A>|Resultados ordenados|Resultados no ordenados|  
|<xref:System.Linq.ParallelEnumerable.Where%2A>|Resultados ordenados|Resultados no ordenados|  
|<xref:System.Linq.ParallelEnumerable.Where%2A> (indexada)|Resultados ordenados|Resultados no ordenados|  
|<xref:System.Linq.ParallelEnumerable.Zip%2A>|Resultados ordenados|Resultados no ordenados|  
  
 Los resultados desordenados no se ordenan aleatoriamente de forma activa; simplemente no se les aplica ninguna lógica de ordenación especial. En algunos casos, una consulta desordenada puede conservar el orden de la secuencia de origen. En las consultas que usan el operador Select indizado, PLINQ garantiza que los elementos de salida aparecerán en el orden de los índices ascendentes, pero no ofrece ninguna garantía sobre qué índices se asignarán a qué elementos.  
  
## <a name="see-also"></a>Vea también

- [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/introduction-to-plinq.md)
- [Programación en paralelo](../../../docs/standard/parallel-programming/index.md)
