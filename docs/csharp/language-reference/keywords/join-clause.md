---
title: "join (Cláusula, Referencia de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- join
- join_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- join clause [C#]
- join keyword [C#]
ms.assetid: 76e9df84-092c-41a6-9537-c3f1cbd7f0fb
caps.latest.revision: 29
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 26027418b70d211dcadf6ace58b24927d94e427a
ms.contentlocale: es-es
ms.lasthandoff: 05/10/2017

---
# <a name="join-clause-c-reference"></a>join (Cláusula, Referencia de C#)
La cláusula `join` es útil para asociar elementos de secuencias de origen diferentes que no tienen ninguna relación directa en el modelo de objetos. El único requisito es que los elementos de cada origen compartan algún valor del que se pueda comparar la igualdad. Por ejemplo, imagínese que un distribuidor de comida tiene una lista de proveedores de un determinado producto y una lista de compradores. Se puede usar una cláusula `join`, por ejemplo, para crear una lista de los proveedores y compradores de dicho producto que se encuentran en la misma región especificada.  
  
 La cláusula `join` toma dos secuencias de origen como entrada. Los elementos de cada secuencia deben ser o deben contener una propiedad que se pueda comparar con una propiedad correspondiente en la otra secuencia. La cláusula `join` compara la igualdad de las claves especificadas mediante la palabra clave especial `equals`. Todas las combinaciones efectuadas por la cláusula `join` son combinaciones de igualdad. La forma de la salida de una cláusula `join` depende del tipo específico de combinación que se va a efectuar. Estos son los tres tipos de combinación más comunes:  
  
-   Combinación interna  
  
-   Combinación agrupada  
  
-   Combinación externa izquierda  
  
## <a name="inner-join"></a>Combinación interna  
 En el ejemplo siguiente se muestra una combinación de igualdad interna simple. Esta consulta genera una secuencia plana de pares de "nombre de producto y categoría". La misma cadena de categoría aparecerá en varios elementos. Si un elemento de `categories` no tiene ningún `products` que coincida, dicha categoría no aparecerá en los resultados.  
  
 [!code-cs[cscsrefQueryKeywords#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/join-clause_1.cs)]  
  
 Para obtener más información, vea [Cómo: Realizar combinaciones internas](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md).  
  
## <a name="group-join"></a>Combinación agrupada  
 Una cláusula `join` con una expresión `into` se denomina "combinación agrupada".  
  
 [!code-cs[cscsrefQueryKeywords#25](../../../csharp/language-reference/keywords/codesnippet/CSharp/join-clause_2.cs)]  
  
 Las combinaciones agrupadas generan una secuencia de resultados jerárquicos que asocia los elementos de la secuencia de origen izquierda con uno o más elementos coincidentes de la secuencia de origen derecha. Las combinaciones agrupadas no tienen ningún equivalente en términos relacionales; son básicamente una secuencia de matrices de objetos.  
  
 Si no se encuentra ningún elemento de la secuencia de origen derecha para que coincida con un elemento del origen izquierdo, la cláusula `join` generará una matriz vacía para ese elemento. Por lo tanto, la combinación agrupada es básicamente una combinación de igualdad interna, salvo que la secuencia del resultado se organiza en grupos.  
  
 Si solo selecciona los resultados de una combinación agrupada, puede tener acceso a los elementos, pero no podrá identificar la clave en la que coinciden. Por lo tanto, suele resultar más útil seleccionar los resultados de la combinación agrupada en un nuevo tipo que también tenga el nombre de la clave, como se muestra en el ejemplo anterior.  
  
 Por supuesto, también puede usar el resultado de una combinación agrupada como generador de otra subconsulta:  
  
 [!code-cs[cscsrefQueryKeywords#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/join-clause_3.cs)]  
  
 Para obtener más información, vea [Cómo: Realizar combinaciones agrupadas](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md).  
  
## <a name="left-outer-join"></a>Combinación externa izquierda  
 En una combinación externa izquierda se devuelven todos los elementos de la secuencia de origen izquierda, incluso si no hay elementos coincidentes en la secuencia derecha. Para efectuar una combinación externa izquierda en [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)], use el método `DefaultIfEmpty` junto con una combinación agrupada para especificar un elemento derecho predeterminado para que se genere si un elemento izquierdo no tiene coincidencias. Puede usar `null` como valor predeterminado para cualquier tipo de referencia, aunque también puede especificar un tipo predeterminado definido por el usuario. En el ejemplo siguiente se muestra un tipo predeterminado definido por el usuario:  
  
 [!code-cs[cscsrefQueryKeywords#27](../../../csharp/language-reference/keywords/codesnippet/CSharp/join-clause_4.cs)]  
  
 Para obtener más información, vea [Cómo: Realizar operaciones de combinación externa izquierda](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md).  
  
## <a name="the-equals-operator"></a>El operador de igualdad  
 La cláusula `join` efectúa una combinación de igualdad. En otras palabras, solo puede basar las coincidencias en la igualdad de dos claves. No se admiten otros tipos de comparaciones, como "mayor que" o "no es igual a". Para aclarar que todas las combinaciones son combinaciones de igualdad, la cláusula `join` usa la palabra clave `equals` en lugar del operador `==`. La palabra clave `equals` solo se puede usar en una cláusula `join` y difiere del operador `==` en un aspecto importante. Con `equals`, la clave izquierda usa la secuencia de origen externa, mientras que la clave derecha usa el origen interno. El origen externo solo está en el ámbito del lado izquierdo de `equals`, mientras que la secuencia de origen interna solo está en el ámbito del lado derecho.  
  
## <a name="non-equijoins"></a>Combinaciones de desigualdad  
 Puede efectuar combinaciones de desigualdad, combinaciones cruzadas y otras operaciones de combinación personalizadas usando varias cláusulas `from` para introducir nuevas secuencias en una consulta de manera independiente. Para obtener más información, vea [Cómo: Realizar operaciones de combinación personalizadas](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-custom-join-operations.md).  
  
## <a name="joins-on-object-collections-vs-relational-tables"></a>Uniones en las colecciones de objetos frente a las tablas relacionales  
 En una expresión de consulta [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)], las operaciones de combinación se efectúan en las colecciones de objetos. Las colecciones de objetos no se pueden "combinar" exactamente igual que dos tablas relacionales. En [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)], las cláusulas `join` explícitas solo son necesarias cuando dos secuencias de origen no están unidas por ninguna relación. Cuando se trabaja con [!INCLUDE[vbtecdlinq](../../../csharp/includes/vbtecdlinq_md.md)], las tablas de claves externas se representan en el modelo de objetos como propiedades de la tabla principal. Por ejemplo, en la base de datos Northwind, la tabla Customer (Cliente) tiene una relación de clave externa con la tabla Orders (Pedidos). Al asignar las tablas al modelo de objetos, la clase Customer tiene una propiedad Orders que contiene la colección Orders asociada a ese cliente. De hecho, la combinación ya se ha llevado a cabo automáticamente.  
  
 Para obtener más información sobre las consultas en tablas relacionadas en el contexto de [!INCLUDE[vbtecdlinq](../../../csharp/includes/vbtecdlinq_md.md)], vea [Cómo: Asignar relaciones de base de datos](../../../framework/data/adonet/sql/linq/how-to-map-database-relationships.md).  
  
## <a name="composite-keys"></a>Claves compuestas  
 Puede probar la igualdad de varios valores mediante una clave compuesta. Para obtener más información, vea [Cómo: Realizar una unión usando claves compuestas ](../../../csharp/programming-guide/linq-query-expressions/how-to-join-by-using-composite-keys.md). Las claves compuestas también se pueden usar en una cláusula `group`.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se comparan los resultados de una combinación interna, una combinación agrupada y una combinación externa izquierda en los mismos orígenes de datos mediante las mismas claves coincidentes. Se ha agregado algún código adicional a estos ejemplos para aclarar los resultados en la pantalla de la consola.  
  
 [!code-cs[cscsrefQueryKeywords#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/join-clause_5.cs)]  
  
## <a name="remarks"></a>Comentarios  
 Una cláusula `join` que no va seguida de `into` se convierte en una llamada al método <xref:System.Linq.Enumerable.Join%2A>. Una cláusula `join` que va seguida de `into` se convierte en una llamada al método <xref:System.Linq.Enumerable.GroupJoin%2A>.  
  
## <a name="see-also"></a>Vea también  
 [Palabras clave de consultas (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [Operaciones de combinación](http://msdn.microsoft.com/library/442d176d-028c-4beb-8d22-407d4ef89107)   
 [group (cláusula)](../../../csharp/language-reference/keywords/group-clause.md)   
 [Cómo: Realizar operaciones de combinación externa izquierda](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md)   
 [Cómo: Realizar combinaciones internas](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md)   
 [Cómo: Realizar combinaciones agrupadas](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md)   
 [Cómo: Ordenar los resultados de una cláusula join](../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md)   
 [Cómo: Realizar una unión usando claves compuestas](../../../csharp/programming-guide/linq-query-expressions/how-to-join-by-using-composite-keys.md)   
 [Cómo: Instalar bases de datos de ejemplo](http://msdn.microsoft.com/library/ed1291f6-604c-4972-ae22-0345c6dea12e)
