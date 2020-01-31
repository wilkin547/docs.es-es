---
title: Operaciones Join (C#)
ms.date: 07/20/2015
ms.assetid: 5105e0da-1267-4c00-837a-f0e9602279b8
no-loc:
- Join
- GroupJoin
ms.openlocfilehash: d4bf9fe76238d8824c5255df8910c1000503dcdf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746960"
---
# <a name="opno-locjoin-operations-c"></a>Operaciones [!OP.NO-LOC(Join)] (C#)
Una *combinación* de dos orígenes de datos es la asociación de objetos de un origen de datos con los objetos que comparten un atributo común en otro origen de datos.  
  
 La combinación es una operación importante en las consultas destinadas a orígenes de datos cuyas relaciones entre sí no se puede seguir directamente. En la programación orientada a objetos, esto podría significar una correlación entre objetos que no está modelada, como el sentido contrario de una relación unidireccional. Un ejemplo de una relación unidireccional es una clase Cliente que tiene una propiedad de tipo Ciudad, pero la clase Ciudad no tiene una propiedad que sea una colección de objetos Cliente. Si tiene una lista de objetos Ciudad y quiere encontrar todos los clientes en cada ciudad, podría usar una operación de combinación para encontrarlos.  
  
 Los métodos de combinación que se han proporcionado en el marco de LINQ son <xref:System.Linq.Enumerable.[!OP.NO-LOC(Join)]%2A> y <xref:System.Linq.Enumerable.[!OP.NO-LOC(GroupJoin)]%2A>. Estos métodos efectúan combinaciones de igualdad, o combinaciones que hacen corresponder dos orígenes de datos en función de la igualdad de sus claves. (Para comparar, Transact-SQL admite otros operadores de combinación aparte de 'igual', por ejemplo, 'menor que'). En términos de base de datos relacional, <xref:System.Linq.Enumerable.[!OP.NO-LOC(Join)]%2A> implementa una combinación interna, un tipo de combinación en la que solo se devuelven los objetos que tienen una correspondencia en el otro conjunto de datos. El método <xref:System.Linq.Enumerable.[!OP.NO-LOC(GroupJoin)]%2A> no tiene equivalente directo en términos de bases de datos relacionales; pero implementa un superconjunto de combinaciones internas y combinaciones externas izquierdas. Una combinación externa izquierda es una combinación que devuelve cada elemento del primer origen de datos (izquierda), aunque no tenga elementos correlacionados en el otro origen de datos.  
  
 En la ilustración siguiente se muestra una vista conceptual de dos conjuntos y los elementos de esos conjuntos que se incluyen en una combinación interna o en una combinación externa izquierda.  
  
 ![Dos círculos superpuestos en los que se muestra el interior y el exterior.](./media/join-operations/join-method-overlapping-circles.png)  
  
## <a name="methods"></a>Métodos  
  
|Nombre del método|Descripción|Sintaxis de la expresión de consulta de C#|Más información|  
|-----------------|-----------------|---------------------------------|----------------------|  
|Join|Combina dos secuencias según las funciones de selector de claves y extrae pares de valores.|`join … in … on … equals …`|<xref:System.Linq.Enumerable.Join%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Join%2A?displayProperty=nameWithType>|  
|GroupJoin|Combina dos secuencias según las funciones de selector de claves y agrupa los resultados coincidentes para cada elemento.|`join … in … on … equals … into …`|<xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>Ejemplos de sintaxis de expresiones de consulta
  
### Join  
  
En el ejemplo siguiente se usa la cláusula `join … in … on … equals …` para combinar dos secuencias en función de un valor específico:
  
[!code-csharp[Join](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQJoin/CS/JoinOperation.cs#Join)]  

### GroupJoin  

En el ejemplo siguiente se usa la cláusula `join … in … on … equals … into …` para combinar dos secuencias en función de un valor específico y se agrupan las coincidencias resultantes de cada elemento:
  
[!code-csharp[GroupJoin](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQJoin/CS/JoinOperation.cs#GroupJoin)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Linq>
- [Información general sobre operadores de consulta estándar (C#)](./standard-query-operators-overview.md)
- [Tipos anónimos](../../classes-and-structs/anonymous-types.md)
- [Formulación de combinaciones y consultas entre productos](../../../../framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)
- [join (cláusula)](../../../language-reference/keywords/join-clause.md)
- [Join usando claves compuestas](../../../linq/join-by-using-composite-keys.md)
- [Procedimiento para combinar contenido de archivos no similares (LINQ) (C#)](./how-to-join-content-from-dissimilar-files-linq.md)
- [Ordenar los resultados de una cláusula join](../../../linq/order-the-results-of-a-join-clause.md)
- [Realizar operaciones de combinación personalizadas](../../../linq/perform-custom-join-operations.md)
- [Realizar combinaciones agrupadas](../../../linq/perform-grouped-joins.md)
- [Realizar combinaciones internas](../../../linq/perform-inner-joins.md)
- [Realizar operaciones de combinación externa izquierda](../../../linq/perform-left-outer-joins.md)
- [Procedimiento para rellenar colecciones de objetos de varios orígenes (LINQ) (C#)](./how-to-populate-object-collections-from-multiple-sources-linq.md)
