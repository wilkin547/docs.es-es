---
title: Ejemplos de consultas basadas en métodos (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: d340775c-7f39-4087-a290-5cbec6cfa68e
ms.openlocfilehash: 1c1ef8f1b6c05415ac6f5ee59d9a415bfab2c410
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175387"
---
# <a name="method-based-query-examples-linq-to-dataset"></a>Ejemplos de consultas basadas en métodos (LINQ to DataSet)

En esta sección se proporciona LINQ to DataSet ejemplos de programación de la sintaxis de consulta basada en métodos que usan los operadores de consulta estándar. El <xref:System.Data.DataSet> usado en estos ejemplos se rellena con el `FillDataSet` método, que se especifica en [cargar datos en un conjunto de datos](loading-data-into-a-dataset.md). Para obtener más información, vea información general sobre [operadores de consulta estándar (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) o [información general sobre operadores de consulta estándar (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
## <a name="in-this-section"></a>En esta sección  

 [Proyección](method-based-query-syntax-examples-projection.md)  
 Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.Select%2A> y <xref:System.Linq.Enumerable.SelectMany%2A> para consultar un <xref:System.Data.DataSet>.  
  
 [Partitioning](method-based-query-syntax-examples-partitioning-linq.md)  
 Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.Skip%2A> y <xref:System.Linq.Enumerable.Take%2A> para consultar un <xref:System.Data.DataSet> y particionar los resultados.  
  
 [Ordenación](method-based-query-syntax-examples-ordering-linq-to-dataset.md)  
 Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A> y <xref:System.Linq.Enumerable.ThenByDescending%2A> para consultar un <xref:System.Data.DataSet> y ordenar los resultados.  
  
 [Operadores de conjuntos](method-based-query-syntax-examples-set-operators.md)  
 Los ejemplos de este tema muestran cómo usar los operadores <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A> y <xref:System.Linq.Enumerable.Union%2A> para operaciones de comparación basadas en valores en conjuntos de filas de datos.  
  
 [Operadores de conversión](method-based-query-syntax-examples-conversion-operators.md)  
 Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> y <xref:System.Linq.Enumerable.ToList%2A> para ejecutar inmediatamente una expresión de consulta.  
  
 [Operadores de elementos](method-based-query-syntax-examples-element-operators.md)  
 Los ejemplos de este tema muestran cómo utilizar los métodos <xref:System.Linq.Enumerable.First%2A> y <xref:System.Linq.Enumerable.ElementAt%2A> para obtener elementos <xref:System.Data.DataRow> de un <xref:System.Data.DataSet>.  
  
 [Operadores de agregado](method-based-query-syntax-examples-aggregate-operators.md)  
 Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A> y <xref:System.Linq.Enumerable.Sum%2A> para consultar <xref:System.Data.DataSet> y agregar datos.  
  
 [Join](method-based-query-syntax-examples-join-linq-to-dataset.md)  
 Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.GroupJoin%2A> y <xref:System.Linq.Enumerable.Join%2A> para consultar un <xref:System.Data.DataSet>.  
  
## <a name="see-also"></a>Consulte también

- [Ejemplos de expresiones de consultas](query-expression-examples-linq-to-dataset.md)
- [Ejemplos de operadores específicos de conjuntos de datos](dataset-specific-operator-examples-linq-to-dataset.md)
- [Ejemplos de LINQ to DataSet](linq-to-dataset-examples.md)
