---
title: Operaciones de agregación (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 0f47e92c-5dd2-4007-baf4-c5fe5dc3b4a8
ms.openlocfilehash: 5d8e5c589b19527062f7752b2f795c8396683bbd
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2019
ms.locfileid: "58675645"
---
# <a name="aggregation-operations-visual-basic"></a>Operaciones de agregación (Visual Basic)
Una operación de agregación calcula un valor único a partir de una colección de valores. Un ejemplo de operación de agregación es calcular el promedio de temperatura diaria a partir de los valores de temperatura diaria durante un mes.  
  
 En la siguiente ilustración se muestran los resultados de dos operaciones de agregación diferentes en una secuencia de números. La primera operación suma los números. La segunda operación devuelve el valor máximo de la secuencia.  
  
 ![Ilustración que muestra las operaciones de agregación en LINQ.](./media/aggregation-operations/linq-aggregation-operations.png)  
  
 Los métodos del operador de consulta estándar que realizan operaciones de agregación se indican en la sección siguiente.  
  
## <a name="methods"></a>Métodos  
  
|Nombre del método|Descripción|Sintaxis de expresión de consulta de Visual Basic|Más información|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|Agregar|Realiza una operación de agregación personalizada en los valores de una colección.|No es aplicable.|<xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Aggregate%2A?displayProperty=nameWithType>|  
|Average|Calcula el valor medio de una colección de valores.|`Aggregate … In … Into Average()`|<xref:System.Linq.Enumerable.Average%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Average%2A?displayProperty=nameWithType>|  
|Recuento|Cuenta los elementos de una colección; opcionalmente, solo aquellos que satisfacen una función de predicado.|`Aggregate … In … Into Count()`|<xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Count%2A?displayProperty=nameWithType>|  
|LongCount|Cuenta los elementos de una gran colección; opcionalmente, solo aquellos que satisfacen una función de predicado.|`Aggregate … In … Into LongCount()`|<xref:System.Linq.Enumerable.LongCount%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.LongCount%2A?displayProperty=nameWithType>|  
|Máx.|Determina el valor máximo de una colección.|`Aggregate … In … Into Max()`|<xref:System.Linq.Enumerable.Max%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Max%2A?displayProperty=nameWithType>|  
|Mín.|Determina el valor mínimo de una colección.|`Aggregate … In … Into Min()`|<xref:System.Linq.Enumerable.Min%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Min%2A?displayProperty=nameWithType>|  
|Sum|Calcula la suma de los valores de una colección.|`Aggregate … In … Into Sum()`|<xref:System.Linq.Enumerable.Sum%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Sum%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>Ejemplos de sintaxis de expresiones de consulta  
  
### <a name="average"></a>Average  
 El siguiente ejemplo de código utiliza el `Aggregate Into Average` cláusula en Visual Basic para calcular el promedio de temperatura en una matriz de números que representan las temperaturas.  
  
 [!code-vb[CsLINQAggregating#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#1)]  
  
### <a name="count"></a>Recuento  
 El siguiente ejemplo de código utiliza el `Aggregate Into Count` cláusula en Visual Basic para contar el número de valores de una matriz que son mayores que o igual a 80.  
  
 [!code-vb[CsLINQAggregating#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#2)]  
  
### <a name="longcount"></a>LongCount  
 El siguiente ejemplo de código utiliza el `Aggregate Into LongCount` cláusula para contar el número de valores en una matriz.  
  
 [!code-vb[CsLINQAggregating#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#3)]  
  
### <a name="max"></a>Máx.  
 El siguiente ejemplo de código utiliza el `Aggregate Into Max` cláusula para calcular la temperatura máxima en una matriz de números que representan las temperaturas.  
  
 [!code-vb[CsLINQAggregating#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#4)]  
  
### <a name="min"></a>Mín.  
 El siguiente ejemplo de código utiliza el `Aggregate Into Min` cláusula para calcular la temperatura mínima en una matriz de números que representan las temperaturas.  
  
 [!code-vb[CsLINQAggregating#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#5)]  
  
### <a name="sum"></a>Sum  
 El siguiente ejemplo de código utiliza el `Aggregate Into Sum` cláusula para calcular el importe del gasto total de una matriz de valores que representan los gastos.  
  
 [!code-vb[CsLINQAggregating#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#6)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Linq>
- [Información general sobre operadores de consulta estándar (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Aggregate (cláusula)](../../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [Cómo: Calcular valores de columna en un archivo de texto CSV (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-compute-column-values-in-a-csv-text-file-linq.md)
- [Cómo: Recuento, suma o promedio de datos](../../../../visual-basic/programming-guide/language-features/linq/how-to-count-sum-or-average-data-by-using-linq.md)
- [Cómo: Buscar el valor mínimo o máximo en un resultado de consulta](../../../../visual-basic/programming-guide/language-features/linq/how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)
- [Cómo: Consulta para el archivo de mayor tamaño o archivos en un árbol de directorios (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)
- [Cómo: Buscar el número Total de Bytes en un conjunto de carpetas (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)
