---
title: Operaciones de agregación
ms.date: 07/20/2015
ms.assetid: 0f47e92c-5dd2-4007-baf4-c5fe5dc3b4a8
ms.openlocfilehash: 5c7f9344d379af2fed2a8f3d9f7c031c8ca00e8c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345776"
---
# <a name="aggregation-operations-visual-basic"></a>Aggregation Operations (Visual Basic)
Una operación de agregación calcula un valor único a partir de una colección de valores. Un ejemplo de operación de agregación es calcular el promedio de temperatura diaria a partir de los valores de temperatura diaria durante un mes.  
  
 En la siguiente ilustración se muestran los resultados de dos operaciones de agregación diferentes en una secuencia de números. La primera operación suma los números. La segunda operación devuelve el valor máximo de la secuencia.  
  
 ![Ilustración en la que se muestran operaciones de agregación en LINQ.](./media/aggregation-operations/linq-aggregation-operations.png)  
  
 Los métodos del operador de consulta estándar que realizan operaciones de agregación se indican en la sección siguiente.  
  
## <a name="methods"></a>Métodos  
  
|Nombre del método|Descripción|Visual Basic Query Expression Syntax|Más información|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|Agregar|Realiza una operación de agregación personalizada en los valores de una colección.|No disponible.|<xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Aggregate%2A?displayProperty=nameWithType>|  
|Average|Calcula el valor medio de una colección de valores.|`Aggregate … In … Into Average()`|<xref:System.Linq.Enumerable.Average%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Average%2A?displayProperty=nameWithType>|  
|Recuento|Cuenta los elementos de una colección; opcionalmente, solo aquellos que satisfacen una función de predicado.|`Aggregate … In … Into Count()`|<xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Count%2A?displayProperty=nameWithType>|  
|LongCount|Cuenta los elementos de una gran colección; opcionalmente, solo aquellos que satisfacen una función de predicado.|`Aggregate … In … Into LongCount()`|<xref:System.Linq.Enumerable.LongCount%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.LongCount%2A?displayProperty=nameWithType>|  
|Máx.|Determina el valor máximo de una colección.|`Aggregate … In … Into Max()`|<xref:System.Linq.Enumerable.Max%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Max%2A?displayProperty=nameWithType>|  
|Mín.|Determina el valor mínimo de una colección.|`Aggregate … In … Into Min()`|<xref:System.Linq.Enumerable.Min%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Min%2A?displayProperty=nameWithType>|  
|Sum|Calcula la suma de los valores de una colección.|`Aggregate … In … Into Sum()`|<xref:System.Linq.Enumerable.Sum%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Sum%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>Ejemplos de sintaxis de expresiones de consulta  
  
### <a name="average"></a>Average  
 The following code example uses the `Aggregate Into Average` clause in Visual Basic to calculate the average temperature in an array of numbers that represent temperatures.  
  
 [!code-vb[CsLINQAggregating#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#1)]  
  
### <a name="count"></a>Recuento  
 The following code example uses the `Aggregate Into Count` clause in Visual Basic to count the number of values in an array that are greater than or equal to 80.  
  
 [!code-vb[CsLINQAggregating#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#2)]  
  
### <a name="longcount"></a>LongCount  
 The following code example uses the `Aggregate Into LongCount` clause to count the number of values in an array.  
  
 [!code-vb[CsLINQAggregating#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#3)]  
  
### <a name="max"></a>Máx.  
 The following code example uses the `Aggregate Into Max` clause  to calculate the maximum temperature in an array of numbers that represent temperatures.  
  
 [!code-vb[CsLINQAggregating#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#4)]  
  
### <a name="min"></a>Mín.  
 The following code example uses the `Aggregate Into Min` clause  to calculate the minimum temperature in an array of numbers that represent temperatures.  
  
 [!code-vb[CsLINQAggregating#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#5)]  
  
### <a name="sum"></a>Sum  
 The following code example uses the `Aggregate Into Sum` clause  to calculate the total expense amount from an array of values that represent expenses.  
  
 [!code-vb[CsLINQAggregating#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#6)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Linq>
- [Información general sobre operadores de consulta estándar (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Aggregate (cláusula)](../../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [How to: Compute Column Values in a CSV Text File (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-compute-column-values-in-a-csv-text-file-linq.md)
- [Cómo: Hacer el recuento, la suma o el promedio de datos](../../../../visual-basic/programming-guide/language-features/linq/how-to-count-sum-or-average-data-by-using-linq.md)
- [Cómo: Buscar los valores máximo y mínimo en el resultado de una consulta](../../../../visual-basic/programming-guide/language-features/linq/how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)
- [How to: Query for the Largest File or Files in a Directory Tree (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)
- [How to: Query for the Total Number of Bytes in a Set of Folders (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)
