---
title: "Operaciones de agregación (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: 0f47e92c-5dd2-4007-baf4-c5fe5dc3b4a8
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 17d1f18f9acc2f3a62c106f7cff2cf68f8f58a07
ms.lasthandoff: 03/13/2017

---
# <a name="aggregation-operations-visual-basic"></a>Operaciones de agregación (Visual Basic)
Una operación de agregación calcula un valor único a partir de una colección de valores. Un ejemplo de operación de agregación es calcular el promedio de temperatura diaria a partir de los valores de temperatura diaria durante un mes.  
  
 La ilustración siguiente muestra los resultados de dos operaciones de agregación diferentes en una secuencia de números. La primera operación suma los números. La segunda operación devuelve el valor máximo de la secuencia.  
  
 ![Operaciones de agregación en LINQ](../../../../csharp/programming-guide/concepts/linq/media/linq_aggregation.png "LINQ_Aggregation")  
  
 Los métodos de operador de consulta estándar que realizan operaciones de agregación se enumeran en la sección siguiente.  
  
## <a name="methods"></a>Métodos  
  
|Nombre del método|Descripción|Sintaxis de expresiones de consulta de Visual Basic|Más información|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|Agregar|Realiza una operación de agregación personalizada en los valores de una colección.|No es aplicable.|<xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Aggregate%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Aggregate%2A?displayProperty=fullName></xref:System.Linq.Queryable.Aggregate%2A?displayProperty=fullName>|  
|Average|Calcula el valor medio de una colección de valores.|`Aggregate … In … Into Average()`|<xref:System.Linq.Enumerable.Average%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Average%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Average%2A?displayProperty=fullName></xref:System.Linq.Queryable.Average%2A?displayProperty=fullName>|  
|Recuento|Cuenta los elementos de una colección y, opcionalmente, sólo los elementos que satisfacen una función de predicado.|`Aggregate … In … Into Count()`|<xref:System.Linq.Enumerable.Count%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Count%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Count%2A?displayProperty=fullName></xref:System.Linq.Queryable.Count%2A?displayProperty=fullName>|  
|LongCount|Cuenta los elementos en una colección grande, opcionalmente, sólo los elementos que satisfacen una función de predicado.|`Aggregate … In … Into LongCount()`|<xref:System.Linq.Enumerable.LongCount%2A?displayProperty=fullName></xref:System.Linq.Enumerable.LongCount%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.LongCount%2A?displayProperty=fullName></xref:System.Linq.Queryable.LongCount%2A?displayProperty=fullName>|  
|Máx.|Determina el valor máximo de una colección.|`Aggregate … In … Into Max()`|<xref:System.Linq.Enumerable.Max%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Max%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Max%2A?displayProperty=fullName></xref:System.Linq.Queryable.Max%2A?displayProperty=fullName>|  
|Mín.|Determina el valor mínimo de una colección.|`Aggregate … In … Into Min()`|<xref:System.Linq.Enumerable.Min%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Min%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Min%2A?displayProperty=fullName></xref:System.Linq.Queryable.Min%2A?displayProperty=fullName>|  
|Sum|Calcula la suma de los valores de una colección.|`Aggregate … In … Into Sum()`|<xref:System.Linq.Enumerable.Sum%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Sum%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Sum%2A?displayProperty=fullName></xref:System.Linq.Queryable.Sum%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-examples"></a>Ejemplos de sintaxis de expresiones de consulta  
  
### <a name="average"></a>Average  
 El siguiente ejemplo de código utiliza el `Aggregate Into Average` cláusula en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] para calcular el promedio de temperatura en una matriz de números que representan temperaturas.  
  
 [!code-vb[1 CsLINQAggregating](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_1.vb)]  
  
### <a name="count"></a>Recuento  
 El siguiente ejemplo de código utiliza el `Aggregate Into Count` cláusula en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] para contar el número de valores de una matriz que son mayores o iguales que 80.  
  
 [!code-vb[CsLINQAggregating&#2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_2.vb)]  
  
### <a name="longcount"></a>LongCount  
 El siguiente ejemplo de código utiliza el `Aggregate Into LongCount` cláusula para contar el número de valores de una matriz.  
  
 [!code-vb[CsLINQAggregating&3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_3.vb)]  
  
### <a name="max"></a>Máx.  
 El siguiente ejemplo de código utiliza el `Aggregate Into Max` cláusula para calcular la temperatura máxima en una matriz de números que representan temperaturas.  
  
 [!code-vb[CsLINQAggregating Nº&4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_4.vb)]  
  
### <a name="min"></a>Mín.  
 El siguiente ejemplo de código utiliza el `Aggregate Into Min` cláusula para calcular la temperatura mínima en una matriz de números que representan temperaturas.  
  
 [!code-vb[CsLINQAggregating&#5;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_5.vb)]  
  
### <a name="sum"></a>Sum  
 El siguiente ejemplo de código utiliza el `Aggregate Into Sum` cláusula para calcular el importe de gasto total de una matriz de valores que representan gastos.  
  
 [!code-vb[CsLINQAggregating Nº&6;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/aggregation-operations_6.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Linq></xref:System.Linq>   
 [Información general sobre operadores de consulta estándar (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Aggregate (cláusula)](../../../../visual-basic/language-reference/queries/aggregate-clause.md)   
 [Cómo: calcular valores de columna en un archivo de texto CSV (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-compute-column-values-in-a-csv-text-file-linq.md)   
 [Cómo: recuento, suma o promedio de datos](../../../../visual-basic/programming-guide/language-features/linq/how-to-count-sum-or-average-data-by-using-linq.md)   
 [Cómo: buscar el valor mínimo o máximo en un resultado de consulta](../../../../visual-basic/programming-guide/language-features/linq/how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)   
 [Cómo: buscar el mayor tamaño o archivos en un árbol de directorios (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree.md)   
 [Cómo: buscar el número Total de Bytes en un conjunto de carpetas (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders.md)
