---
description: 'Más información acerca de: operaciones de combinación (Visual Basic)'
title: Operaciones de combinación
ms.date: 07/20/2015
ms.assetid: 39ab4854-ac84-4738-9d0b-3cb79be84db4
ms.openlocfilehash: d5566de71bf96d2af86329929a5ab6ab34e6d154
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100426782"
---
# <a name="join-operations-visual-basic"></a>Operaciones de combinación (Visual Basic)

Una *combinación* de dos orígenes de datos es la asociación de objetos de un origen de datos con los objetos que comparten un atributo común en otro origen de datos.  
  
 La combinación es una operación importante en las consultas destinadas a orígenes de datos cuyas relaciones entre sí no se puede seguir directamente. En la programación orientada a objetos, esto podría significar una correlación entre objetos que no está modelada, como el sentido contrario de una relación unidireccional. Un ejemplo de una relación unidireccional es una clase Cliente que tiene una propiedad de tipo Ciudad, pero la clase Ciudad no tiene una propiedad que sea una colección de objetos Cliente. Si tiene una lista de objetos Ciudad y quiere encontrar todos los clientes en cada ciudad, podría usar una operación de combinación para encontrarlos.  
  
 Los métodos de combinación que se han proporcionado en el marco de LINQ son <xref:System.Linq.Enumerable.Join%2A> y <xref:System.Linq.Enumerable.GroupJoin%2A>. Estos métodos efectúan combinaciones de igualdad, o combinaciones que hacen corresponder dos orígenes de datos en función de la igualdad de sus claves. (Para comparar, Transact-SQL admite otros operadores de combinación aparte de 'igual', por ejemplo, 'menor que'). En términos de base de datos relacional, <xref:System.Linq.Enumerable.Join%2A> implementa una combinación interna, un tipo de combinación en la que solo se devuelven los objetos que tienen una correspondencia en el otro conjunto de datos. El método <xref:System.Linq.Enumerable.GroupJoin%2A> no tiene equivalente directo en términos de bases de datos relacionales; pero implementa un superconjunto de combinaciones internas y combinaciones externas izquierdas. Una combinación externa izquierda es una combinación que devuelve cada elemento del primer origen de datos (izquierda), aunque no tenga elementos correlacionados en el otro origen de datos.  
  
 En la ilustración siguiente se muestra una vista conceptual de dos conjuntos y los elementos de esos conjuntos que se incluyen en una combinación interna o en una combinación externa izquierda.  
  
 ![Dos círculos superpuestos en los que se muestra el interior y el exterior.](./media/join-operations/join-method-overlapping-circles.png)  
  
## <a name="methods"></a>Métodos  
  
|Nombre del método|Descripción|Visual Basic sintaxis de expresiones de consulta|Más información|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|Join|Combina dos secuencias según las funciones de selector de claves y extrae pares de valores.|`From x In …, y In … Where x.a = y.a`<br /><br /> o bien<br /><br /> `Join … [As …]In … On …`|<xref:System.Linq.Enumerable.Join%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Join%2A?displayProperty=nameWithType>|  
|GroupJoin|Combina dos secuencias según las funciones de selector de claves y agrupa los resultados coincidentes para cada elemento.|`Group Join … In … On …`|<xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Linq>
- [Información general sobre operadores de consulta estándar (Visual Basic)](standard-query-operators-overview.md)
- [Tipos anónimos](../../language-features/objects-and-classes/anonymous-types.md)
- [Cómo: Formular combinaciones y consultas entre productos](../../../../framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)
- [Cláusula Join](../../../language-reference/queries/join-clause.md)
- [Cómo: combinar contenido de archivos no similares (LINQ) (Visual Basic)](how-to-join-content-from-dissimilar-files-linq.md)
- [Cómo: rellenar colecciones de objetos de varios orígenes (LINQ) (Visual Basic)](how-to-populate-object-collections-from-multiple-sources-linq.md)
