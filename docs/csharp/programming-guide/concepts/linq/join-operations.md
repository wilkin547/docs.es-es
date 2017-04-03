---
title: "Operaciones de combinación (C#) | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 5105e0da-1267-4c00-837a-f0e9602279b8
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 00ff7cd6547c7472afd81fb227158cfe0df51ab4
ms.lasthandoff: 03/13/2017

---
# <a name="join-operations-c"></a>Operaciones de combinación (C#)
Una *combinación* de dos orígenes de datos es la asociación de objetos de un origen de datos con los objetos que comparten un atributo común en otro origen de datos.  
  
 La combinación es una operación importante en las consultas destinadas a orígenes de datos cuyas relaciones entre sí no se puede seguir directamente. En la programación orientada a objetos, esto podría significar una correlación entre objetos que no está modelada, como el sentido contrario de una relación unidireccional. Un ejemplo de una relación unidireccional es una clase Cliente que tiene una propiedad de tipo Ciudad, pero la clase Ciudad no tiene una propiedad que sea una colección de objetos Cliente. Si tiene una lista de objetos Ciudad y quiere encontrar todos los clientes en cada ciudad, podría usar una operación de combinación para encontrarlos.  
  
 Los métodos de combinación proporcionados en el marco de trabajo de LINQ son <xref:System.Linq.Enumerable.Join%2A> y <xref:System.Linq.Enumerable.GroupJoin%2A>. Estos métodos efectúan combinaciones de igualdad, o combinaciones que hacen corresponder dos orígenes de datos en función de la igualdad de sus claves. (Para comparar, Transact-SQL admite otros operadores de combinación aparte de 'igual', por ejemplo, 'menor que'). En términos de bases de datos relacionales, <xref:System.Linq.Enumerable.Join%2A> implementa una combinación interna, un tipo de combinación en la que solo se devuelven los objetos que tienen una correspondencia en el otro conjunto de datos. El método <xref:System.Linq.Enumerable.GroupJoin%2A> no tiene ningún equivalente directo en términos de bases de datos relacionales, pero implementa un superconjunto de combinaciones internas y de combinaciones externas izquierdas. Una combinación externa izquierda es una combinación que devuelve cada elemento del primer origen de datos (izquierda), aunque no tenga elementos correlacionados en el otro origen de datos.  
  
 En la ilustración siguiente se muestra una vista conceptual de dos conjuntos y los elementos de esos conjuntos que se incluyen en una combinación interna o en una combinación externa izquierda.  
  
 ![Dos círculos superpuestos que muestran el interior y el exterior.](../../../../csharp/programming-guide/concepts/linq/media/joincircles.png "JoinCircles")  
  
## <a name="methods"></a>Métodos  
  
|Nombre del método|Descripción|Sintaxis de la expresión de consulta de C#|Más información|  
|-----------------|-----------------|---------------------------------|----------------------|  
|Join|Combina dos secuencias según las funciones de selector de claves y extrae pares de valores.|`join … in … on … equals …`|<xref:System.Linq.Enumerable.Join%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Join%2A?displayProperty=fullName>|  
|GroupJoin|Combina dos secuencias según las funciones de selector de claves y agrupa los resultados coincidentes para cada elemento.|`join … in … on … equals … into …`|<xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=fullName>|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Linq>   
 [Información general sobre operadores de consulta estándar (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Tipos anónimos](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Cómo: Formular combinaciones y consultas entre productos](http://msdn.microsoft.com/library/d8072ede-0521-4670-9bec-1778ceeb875b)   
 [Join (Cláusula)](../../../../csharp/language-reference/keywords/join-clause.md)   
 [Cómo: Realizar una unión usando claves compuestas](../../../../csharp/programming-guide/linq-query-expressions/how-to-join-by-using-composite-keys.md)   
 [Cómo: Combinar contenido de archivos no similares (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md)   
 [Cómo: Ordenar los resultados de una cláusula join](../../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md)   
 [Cómo: Realizar operaciones de combinación personalizadas](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-custom-join-operations.md)   
 [Cómo: Realizar combinaciones agrupadas](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md)   
 [Cómo: Realizar combinaciones internas](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md)   
 [Cómo: Realizar operaciones de combinación externa izquierda](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md)   
 [Cómo: Rellenar colecciones de objetos de varios orígenes (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md)
