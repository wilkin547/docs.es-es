---
title: Operaciones de combinación
ms.date: 07/20/2015
ms.assetid: 39ab4854-ac84-4738-9d0b-3cb79be84db4
ms.openlocfilehash: b09574369185be13664276c2e84697fc4969c6f5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353295"
---
# <a name="join-operations-visual-basic"></a>Join Operations (Visual Basic)
Una *combinación* de dos orígenes de datos es la asociación de objetos de un origen de datos con los objetos que comparten un atributo común en otro origen de datos.  
  
 La combinación es una operación importante en las consultas destinadas a orígenes de datos cuyas relaciones entre sí no se puede seguir directamente. En la programación orientada a objetos, esto podría significar una correlación entre objetos que no está modelada, como el sentido contrario de una relación unidireccional. Un ejemplo de una relación unidireccional es una clase Cliente que tiene una propiedad de tipo Ciudad, pero la clase Ciudad no tiene una propiedad que sea una colección de objetos Cliente. Si tiene una lista de objetos Ciudad y quiere encontrar todos los clientes en cada ciudad, podría usar una operación de combinación para encontrarlos.  
  
 Los métodos de combinación que se han proporcionado en el marco de LINQ son <xref:System.Linq.Enumerable.Join%2A> y <xref:System.Linq.Enumerable.GroupJoin%2A>. Estos métodos efectúan combinaciones de igualdad, o combinaciones que hacen corresponder dos orígenes de datos en función de la igualdad de sus claves. (For comparison, Transact-SQL supports join operators other than 'equals', for example the 'less than' operator.) In relational database terms, <xref:System.Linq.Enumerable.Join%2A> implements an inner join, a type of join in which only those objects that have a match in the other data set are returned. El método <xref:System.Linq.Enumerable.GroupJoin%2A> no tiene equivalente directo en términos de bases de datos relacionales; pero implementa un superconjunto de combinaciones internas y combinaciones externas izquierdas. Una combinación externa izquierda es una combinación que devuelve cada elemento del primer origen de datos (izquierda), aunque no tenga elementos correlacionados en el otro origen de datos.  
  
 En la ilustración siguiente se muestra una vista conceptual de dos conjuntos y los elementos de esos conjuntos que se incluyen en una combinación interna o en una combinación externa izquierda.  
  
 ![Dos círculos superpuestos en los que se muestra el interior y el exterior.](./media/join-operations/join-method-overlapping-circles.png)  
  
## <a name="methods"></a>Métodos  
  
|Nombre del método|Descripción|Visual Basic Query Expression Syntax|Más información|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|Join|Combina dos secuencias según las funciones de selector de claves y extrae pares de valores.|`From x In …, y In … Where x.a = y.a`<br /><br /> o bien<br /><br /> `Join … [As …]In … On …`|<xref:System.Linq.Enumerable.Join%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Join%2A?displayProperty=nameWithType>|  
|GroupJoin|Combina dos secuencias según las funciones de selector de claves y agrupa los resultados coincidentes para cada elemento.|`Group Join … In … On …`|<xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Linq>
- [Información general sobre operadores de consulta estándar (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Formulación de combinaciones y consultas entre productos](../../../../framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)
- [Join (cláusula)](../../../../visual-basic/language-reference/queries/join-clause.md)
- [How to: Join Content from Dissimilar Files (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md)
- [How to: Populate Object Collections from Multiple Sources (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md)
