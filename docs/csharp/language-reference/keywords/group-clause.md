---
title: "group (Cláusula, Referencia de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- group
- group_CSharpKeyword
helpviewer_keywords:
- group keyword [C#]
- group clause [C#]
ms.assetid: c817242e-b12c-4baa-a57e-73ee138f34d1
caps.latest.revision: "24"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a2f67b2c90e1cced92d6fc7d47768b58bf155360
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="group-clause-c-reference"></a>group (Cláusula, Referencia de C#)
La cláusula `group` devuelve una secuencia de objetos <xref:System.Linq.IGrouping%602> que contienen cero o más elementos que coinciden con el valor de clave del grupo. Por ejemplo, puede agrupar una secuencia de cadenas según la primera letra de cada cadena. En este caso, la primera letra es la clave, es de tipo [char](../../../csharp/language-reference/keywords/char.md) y se almacena en la propiedad `Key` de cada objeto <xref:System.Linq.IGrouping%602>. El compilador deduce el tipo de la clave.  
  
 Puede finalizar una expresión de consulta con una cláusula `group`, como se muestra en el ejemplo siguiente:  
  
 [!code-csharp[cscsrefQueryKeywords#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/group-clause_1.cs)]  
  
 Si quiere realizar operaciones de consulta adicionales en cada grupo, puede especificar un identificador temporal mediante la palabra clave contextual [into](../../../csharp/language-reference/keywords/into.md). Cuando se usa `into`, es necesario continuar con la consulta y finalmente terminarla con una instrucción `select` u otra cláusula `group`, como se muestra en el extracto siguiente:  
  
 [!code-csharp[cscsrefQueryKeywords#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/group-clause_2.cs)]  
  
 En la sección Ejemplo de este tema se proporcionan ejemplos más completos sobre el uso de `group` con y sin `into`.  
  
## <a name="enumerating-the-results-of-a-group-query"></a>Enumerar los resultados de una consulta Group  
 Dado que los objetos <xref:System.Linq.IGrouping%602> generados por una consulta `group` son esencialmente una lista de listas, debe usar un bucle [foreach](../../../csharp/language-reference/keywords/foreach-in.md) anidado para tener acceso a los elementos de cada grupo. El bucle exterior recorre en iteración las claves de grupo y el bucle interno recorre en iteración cada elemento del propio grupo. Un grupo puede tener una clave pero ningún elemento. A continuación se muestra el bucle `foreach` que ejecuta la consulta en los ejemplos de código anteriores:  
  
 [!code-csharp[cscsrefQueryKeywords#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/group-clause_3.cs)]  
  
## <a name="key-types"></a>Tipos de clave  
 Las claves de grupo pueden ser de cualquier tipo, como una cadena, un tipo numérico integrado, un tipo con nombre definido por el usuario o un tipo anónimo.  
  
### <a name="grouping-by-string"></a>Agrupar por cadena  
 En los ejemplos de código anteriores se ha usado el tipo `char`. En su lugar, podría haberse especificado una clave de cadena, por ejemplo, los apellidos completos:  
  
 [!code-csharp[cscsrefQueryKeywords#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/group-clause_4.cs)]  
  
### <a name="grouping-by-bool"></a>Agrupar por valor booleano  
 En el ejemplo siguiente se muestra el uso de un valor booleano para una clave con el fin de dividir los resultados en dos grupos. Observe que el valor se genera a partir de una subexpresión en la cláusula `group`.  
  
 [!code-csharp[cscsrefQueryKeywords#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/group-clause_5.cs)]  
  
### <a name="grouping-by-numeric-range"></a>Agrupar por intervalo numérico  
 En el ejemplo siguiente se usa una expresión para crear claves de grupo numéricas que representan un intervalo de percentil. Observe el uso de [let](../../../csharp/language-reference/keywords/let-clause.md) como lugar adecuado para almacenar un resultado de una llamada a método, para no tener que llamar al método dos veces en la cláusula `group`. Observe también cómo en la cláusula `group`, para evitar una excepción por "división entre cero", el código comprueba que el estudiante no tenga ninguna media de cero. Para obtener más información sobre cómo usar métodos en expresiones de consulta de manera segura, vea [Cómo: Controlar excepciones en expresiones de consulta](../../../csharp/programming-guide/linq-query-expressions/how-to-handle-exceptions-in-query-expressions.md).  
  
 [!code-csharp[cscsrefQueryKeywords#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/group-clause_6.cs)]  
  
### <a name="grouping-by-composite-keys"></a>Agrupar por claves compuestas  
 Use una clave compuesta cuando quiera agrupar los elementos según más de una clave. Para crear una clave compuesta se usa un tipo anónimo o un tipo con nombre para contener el elemento de clave. En el ejemplo siguiente, supongamos que una clase `Person` se ha declarado con los miembros denominados `surname` y `city`. La cláusula `group` hace que se cree un grupo independiente para cada conjunto de personas con el mismo apellido y la misma ciudad.  
  
```csharp  
group person by new {name = person.surname, city = person.city};  
```  
  
 Use un tipo con nombre si debe pasar la variable de consulta a otro método. Cree una clase especial usando las propiedades autoimplementadas para las claves y, luego, invalide los métodos <xref:System.Object.Equals%2A> y <xref:System.Object.GetHashCode%2A>. También puede usar un struct, en cuyo caso no es estrictamente necesario invalidar esos métodos. Para obtener más información, vea [Cómo: Implementar una clase ligera con propiedades autoimplementadas](../../../csharp/programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md) y [How to: Query for Duplicate Files in a Directory Tree](../../programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md) (Cómo: Consultar archivos duplicados en un árbol de directorio). El último tema contiene un ejemplo de código que muestra cómo usar una clave compuesta con un tipo con nombre.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra el patrón estándar para ordenar los datos de origen en grupos cuando no se aplica ninguna lógica de consulta adicional a los grupos. Esto se denomina agrupación sin continuación. Los elementos de una matriz de cadenas se agrupan por la primera letra. El resultado de la consulta es un tipo <xref:System.Linq.IGrouping%602> que contiene una propiedad `Key` pública de tipo `char` y una colección <xref:System.Collections.Generic.IEnumerable%601> que contiene cada elemento de la agrupación.  
  
 El resultado de una cláusula `group` es una secuencia de secuencias. Por consiguiente, para tener acceso a los elementos individuales de cada grupo devuelto, use un bucle `foreach` anidado dentro del bucle que recorre en iteración las claves de grupo, como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[cscsrefQueryKeywords#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/group-clause_7.cs)]  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra cómo aplicar lógica adicional a los grupos después de haberlos creado, mediante el uso de una *continuación* con `into`. Para obtener más información, vea [into](../../../csharp/language-reference/keywords/into.md). En el ejemplo siguiente se consulta cada grupo para seleccionar solo aquellos cuyo valor de clave sea una vocal.  
  
 [!code-csharp[cscsrefQueryKeywords#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/group-clause_8.cs)]  
  
## <a name="remarks"></a>Comentarios  
 En tiempo de compilación, las cláusulas `group` se convierten en llamadas al método <xref:System.Linq.Enumerable.GroupBy%2A>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Linq.IGrouping%602>  
 <xref:System.Linq.Enumerable.GroupBy%2A>  
 <xref:System.Linq.Enumerable.ThenBy%2A>  
 <xref:System.Linq.Enumerable.ThenByDescending%2A>  
 [Palabras clave para consultas (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)  
 [Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [Cómo: Crear grupos anidados](../../../csharp/programming-guide/linq-query-expressions/how-to-create-a-nested-group.md)  
 [Cómo: Agrupar los resultados de consultas](../../../csharp/programming-guide/linq-query-expressions/how-to-group-query-results.md)  
 [Cómo: Realizar una subconsulta en una operación de agrupación](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md)
