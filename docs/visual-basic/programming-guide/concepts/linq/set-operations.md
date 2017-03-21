---
title: Conjunto de operaciones (Visual Basic) | Documentos de Microsoft
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
ms.assetid: 2b06e822-e030-438f-9db7-ee402bd3a706
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
ms.openlocfilehash: e835737b388427445a15b6658c7d148801f29b79
ms.lasthandoff: 03/13/2017

---
# <a name="set-operations-visual-basic"></a>Operaciones Set (Visual Basic)
Operaciones Set de LINQ, consulte operaciones de consulta que producen un conjunto de resultados que se basa en la presencia o ausencia de elementos equivalentes dentro de las mismas u otras colecciones (o conjuntos).  
  
 Los métodos de operador de consulta estándar que realizan operaciones de conjuntos se enumeran en la sección siguiente.  
  
## <a name="methods"></a>Métodos  
  
|Nombre del método|Descripción|Sintaxis de expresiones de consulta de Visual Basic|Más información|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|Distinct|Quita los valores duplicados de una colección.|`Distinct`|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=fullName></xref:System.Linq.Queryable.Distinct%2A?displayProperty=fullName>|  
|Except|Devuelve la diferencia de conjuntos, lo que significa que los elementos de una colección que no aparecen en una segunda colección.|No es aplicable.|<xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=fullName></xref:System.Linq.Queryable.Except%2A?displayProperty=fullName>|  
|Formar intersección|Devuelve la intersección de conjuntos, lo que significa que los elementos que aparecen en cada una de las dos colecciones.|No es aplicable.|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=fullName></xref:System.Linq.Queryable.Intersect%2A?displayProperty=fullName>|  
|Unión|Devuelve la unión de conjuntos, lo que significa elementos únicos que aparecen en cualquiera de las dos colecciones.|No es aplicable.|<xref:System.Linq.Enumerable.Union%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Union%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=fullName></xref:System.Linq.Queryable.Union%2A?displayProperty=fullName>|  
  
## <a name="comparison-of-set-operations"></a>Comparación de operaciones Set  
  
### <a name="distinct"></a>Distinct  
 La siguiente ilustración muestra el comportamiento de la <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName>método en una secuencia de caracteres.</xref:System.Linq.Enumerable.Distinct%2A?displayProperty=fullName> La secuencia devuelta contiene los elementos únicos de la secuencia de entrada.  
  
 ![Gráfico mostrando el comportamiento de Distinct(). ] (../../../../csharp/programming-guide/concepts/linq/media/distinct.png "Distinct")  
  
### <a name="except"></a>Except  
 La siguiente ilustración muestra el comportamiento de <xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName>.</xref:System.Linq.Enumerable.Except%2A?displayProperty=fullName> La secuencia devuelta contiene sólo los elementos de la primera secuencia de entrada que no están en la segunda secuencia de entrada.  
  
 ![Gráfico mostrando la acción de Except(). ](../../../../csharp/programming-guide/concepts/linq/media/except.png "Except")  
  
### <a name="intersect"></a>Formar intersección  
 La siguiente ilustración muestra el comportamiento de <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName>.</xref:System.Linq.Enumerable.Intersect%2A?displayProperty=fullName> La secuencia devuelta contiene los elementos que son comunes a los de las secuencias de entrada.  
  
 ![Gráfico mostrando la intersección de dos secuencias. ] (../../../../csharp/programming-guide/concepts/linq/media/intersect.png "Intersect")  
  
### <a name="union"></a>Unión  
 La siguiente ilustración muestra una operación de unión de dos secuencias de caracteres. La secuencia devuelta contiene los elementos únicos de dos secuencias de entrada.  
  
 ![Gráfico mostrando la unión de dos secuencias. ](../../../../csharp/programming-guide/concepts/linq/media/union.png "Union")  
  
## <a name="query-expression-syntax-example"></a>Ejemplo de sintaxis de expresiones de consulta  
 En el ejemplo siguiente se usa el `Distinct` cláusula en una consulta LINQ para devolver los números únicos de una lista de enteros.  
  
 [!code-vb[1 CsLINQSetOps](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/set-operations_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Linq></xref:System.Linq>   
 [Información general sobre operadores de consulta estándar (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [DISTINCT (cláusula)](../../../../visual-basic/language-reference/queries/distinct-clause.md)   
 [Cómo: combinar y comparar colecciones de cadenas (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)   
 [Cómo: buscar la diferencia de conjuntos entre dos listas (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)
