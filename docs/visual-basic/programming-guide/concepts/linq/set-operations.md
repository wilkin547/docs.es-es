---
title: Operaciones Set
ms.date: 07/20/2015
ms.assetid: 2b06e822-e030-438f-9db7-ee402bd3a706
ms.openlocfilehash: fe9d910415f30fe672dc702f719fdefdb9c0b3d1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350617"
---
# <a name="set-operations-visual-basic"></a>Operaciones Set (Visual Basic)

Las operaciones set de LINQ se refieren a operaciones de consulta que generan un conjunto de resultados en función de la presencia o ausencia de elementos equivalentes dentro de la misma colección o en distintas colecciones (o conjuntos).

Los métodos del operador de consulta estándar que realizan operaciones set se indican en la sección siguiente.

## <a name="methods"></a>Métodos

|Nombre del método|Descripción|Visual Basic sintaxis de expresiones de consulta|Más información|
|-----------------|-----------------|------------------------------------------|----------------------|
|Distinct|Quita valores duplicados de una colección.|`Distinct`|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|
|Except|Devuelve la diferencia de conjuntos, es decir, los elementos de una colección que no aparecen en una segunda colección.|No disponible.|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|
|Formar intersección|Devuelve la intersección de conjuntos, es decir, los elementos que aparecen en las dos colecciones.|No disponible.|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|
|Union|Devuelve la unión de conjuntos, es decir, los elementos únicos que aparecen en una de las dos colecciones.|No disponible.|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|

## <a name="comparison-of-set-operations"></a>Comparación de operaciones set

### <a name="distinct"></a>Distinct

En la siguiente ilustración se muestra el comportamiento del método <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> en una secuencia de caracteres. La secuencia devuelta contiene los elementos únicos de la secuencia de entrada.

![Gráfico en el que se muestra el comportamiento de Distinct&#40;&#41;.](./media/set-operations/distinct-method-behavior.png)

### <a name="except"></a>Except

En la siguiente ilustración se muestra el comportamiento de <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>. La secuencia devuelta solo contiene los elementos de la primera secuencia de entrada que no están en la segunda secuencia de entrada.

![Gráfico que muestra la acción de Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Muestra el comportamiento de Except.")

### <a name="intersect"></a>Formar intersección

En la siguiente ilustración se muestra el comportamiento de <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>. La secuencia devuelta contiene los elementos que son comunes a las dos secuencias de entrada.

![Gráfico mostrando la intersección de dos secuencias.](./media/set-operations/intersection-two-sequences.png)

### <a name="union"></a>Union

En la siguiente ilustración se muestra una operación de unión en dos secuencias de caracteres. La secuencia devuelta contiene los elementos únicos de las dos secuencias de entrada.

![Gráfico mostrando la unión de dos secuencias.](./media/set-operations/union-operation-two-sequences.png)

## <a name="query-expression-syntax-example"></a>Ejemplo de sintaxis de expresiones de consulta

En el ejemplo siguiente se usa la cláusula `Distinct` en una consulta LINQ para devolver los números únicos de una lista de enteros.

[!code-vb[CsLINQSetOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQSetOps/VB/setops.vb#1)]

## <a name="see-also"></a>Vea también

- <xref:System.Linq>
- [Información general sobre operadores de consulta estándar (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Distinct (cláusula)](../../../../visual-basic/language-reference/queries/distinct-clause.md)
- [Cómo: combinar y comparar colecciones de cadenas (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)
- [Cómo: buscar la diferencia de conjuntos entre dos listas (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)
