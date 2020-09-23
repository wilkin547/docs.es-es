---
title: Operaciones de agregación
ms.date: 07/20/2015
ms.assetid: 0f47e92c-5dd2-4007-baf4-c5fe5dc3b4a8
ms.openlocfilehash: 1cf82d8acfdb1f8b0fc33c324064574b0dd01f4a
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91078403"
---
# <a name="aggregation-operations-visual-basic"></a>Operaciones de agregación (Visual Basic)

Una operación de agregación calcula un valor único a partir de una colección de valores. Un ejemplo de operación de agregación es calcular el promedio de temperatura diaria a partir de los valores de temperatura diaria durante un mes.  
  
 En la siguiente ilustración se muestran los resultados de dos operaciones de agregación diferentes en una secuencia de números. La primera operación suma los números. La segunda operación devuelve el valor máximo de la secuencia.  
  
 ![Ilustración en la que se muestran operaciones de agregación en LINQ.](./media/aggregation-operations/linq-aggregation-operations.png)  
  
 Los métodos del operador de consulta estándar que realizan operaciones de agregación se indican en la sección siguiente.  
  
## <a name="methods"></a>Métodos  
  
|Nombre del método|Descripción|Visual Basic sintaxis de expresiones de consulta|Más información|  
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

 En el ejemplo de código siguiente `Aggregate Into Average` se usa la cláusula en Visual Basic para calcular la temperatura media de una matriz de números que representan temperaturas.  
  
 [!code-vb[CsLINQAggregating#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#1)]  
  
### <a name="count"></a>Count  

 En el ejemplo de código siguiente `Aggregate Into Count` se usa la cláusula en Visual Basic para contar el número de valores de una matriz que son mayores o iguales que 80.  
  
 [!code-vb[CsLINQAggregating#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#2)]  
  
### <a name="longcount"></a>LongCount  

 En el ejemplo de código siguiente `Aggregate Into LongCount` se usa la cláusula para contar el número de valores de una matriz.  
  
 [!code-vb[CsLINQAggregating#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#3)]  
  
### <a name="max"></a>Max  

 En el ejemplo de código siguiente `Aggregate Into Max` se usa la cláusula para calcular la temperatura máxima de una matriz de números que representan temperaturas.  
  
 [!code-vb[CsLINQAggregating#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#4)]  
  
### <a name="min"></a>Min  

 En el ejemplo de código siguiente `Aggregate Into Min` se usa la cláusula para calcular la temperatura mínima de una matriz de números que representan temperaturas.  
  
 [!code-vb[CsLINQAggregating#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#5)]  
  
### <a name="sum"></a>Sum  

 En el ejemplo de código siguiente `Aggregate Into Sum` se usa la cláusula para calcular el importe total de los gastos de una matriz de valores que representan gastos.  
  
 [!code-vb[CsLINQAggregating#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQAggregating/VB/Aggregating.vb#6)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Linq>
- [Información general sobre operadores de consulta estándar (Visual Basic)](standard-query-operators-overview.md)
- [Aggregate Clause](../../../language-reference/queries/aggregate-clause.md)
- [Cómo: calcular valores de columna en un archivo de texto CSV (LINQ) (Visual Basic)](how-to-compute-column-values-in-a-csv-text-file-linq.md)
- [Cómo: Hacer el recuento, la suma o el promedio de datos](../../language-features/linq/how-to-count-sum-or-average-data-by-using-linq.md)
- [Cómo: Buscar los valores máximo y mínimo en el resultado de una consulta](../../language-features/linq/how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)
- [Cómo buscar el archivo o archivos de mayor tamaño en un árbol de directorios (LINQ) (Visual Basic)](how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)
- [Cómo: buscar el número total de bytes en un conjunto de carpetas (LINQ) (Visual Basic)](how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)
