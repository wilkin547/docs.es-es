---
title: 'Cláusula group: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- group
- group_CSharpKeyword
helpviewer_keywords:
- group keyword [C#]
- group clause [C#]
ms.assetid: c817242e-b12c-4baa-a57e-73ee138f34d1
ms.openlocfilehash: 75a366ec24e4e48af7e87d3372950aad8d76435b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713467"
---
# <a name="group-clause-c-reference"></a>group (Cláusula, Referencia de C#)

La cláusula `group` devuelve una secuencia de objetos <xref:System.Linq.IGrouping%602> que contienen cero o más elementos que coinciden con el valor de clave del grupo. Por ejemplo, puede agrupar una secuencia de cadenas según la primera letra de cada cadena. En este caso, la primera letra es la clave, es de tipo [char](../builtin-types/char.md) y se almacena en la propiedad `Key` de cada objeto <xref:System.Linq.IGrouping%602>. El compilador deduce el tipo de la clave.

Puede finalizar una expresión de consulta con una cláusula `group`, como se muestra en el ejemplo siguiente:

[!code-csharp[cscsrefQueryKeywords#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#10)]

Si quiere realizar operaciones de consulta adicionales en cada grupo, puede especificar un identificador temporal mediante la palabra clave contextual [into](into.md). Cuando se usa `into`, es necesario continuar con la consulta y finalmente terminarla con una instrucción `select` u otra cláusula `group`, como se muestra en el extracto siguiente:

[!code-csharp[cscsrefQueryKeywords#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#11)]

En la sección Ejemplo de este artículo se proporcionan ejemplos más completos sobre el uso de `group` con y sin `into`.

## <a name="enumerating-the-results-of-a-group-query"></a>Enumeración de los resultados de una consulta de grupo

Dado que los objetos <xref:System.Linq.IGrouping%602> generados por una consulta `group` son esencialmente una lista de listas, debe usar un bucle [foreach](foreach-in.md) anidado para tener acceso a los elementos de cada grupo. El bucle exterior recorre en iteración las claves de grupo y el bucle interno recorre en iteración cada elemento del propio grupo. Un grupo puede tener una clave pero ningún elemento. A continuación se muestra el bucle `foreach` que ejecuta la consulta en los ejemplos de código anteriores:

[!code-csharp[cscsrefQueryKeywords#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#12)]

## <a name="key-types"></a>Tipos de clave

Las claves de grupo pueden ser de cualquier tipo, como una cadena, un tipo numérico integrado, un tipo con nombre definido por el usuario o un tipo anónimo.

### <a name="grouping-by-string"></a>Agrupar por cadena

En los ejemplos de código anteriores se ha usado el tipo `char`. En su lugar, podría haberse especificado una clave de cadena, por ejemplo, los apellidos completos:

[!code-csharp[cscsrefQueryKeywords#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#13)]

### <a name="grouping-by-bool"></a>Agrupar por valor booleano

En el ejemplo siguiente se muestra el uso de un valor booleano para una clave con el fin de dividir los resultados en dos grupos. Observe que el valor se genera a partir de una subexpresión en la cláusula `group`.

[!code-csharp[cscsrefQueryKeywords#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#14)]

### <a name="grouping-by-numeric-range"></a>Agrupar por intervalo numérico

En el ejemplo siguiente se usa una expresión para crear claves de grupo numéricas que representan un intervalo de percentil. Observe el uso de [let](let-clause.md) como ubicación adecuada para almacenar el resultado de una llamada de método, para no tener que llamar al método dos veces en la cláusula `group`. Para más información sobre cómo usar métodos en expresiones de consulta de manera segura, consulte [Controlar excepciones en expresiones de consulta](../../linq/handle-exceptions-in-query-expressions.md).

[!code-csharp[cscsrefQueryKeywords#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#15)]

### <a name="grouping-by-composite-keys"></a>Agrupación por claves compuestas

Use una clave compuesta cuando quiera agrupar los elementos según más de una clave. Para crear una clave compuesta se usa un tipo anónimo o un tipo con nombre para contener el elemento de clave. En el ejemplo siguiente, supongamos que una clase `Person` se ha declarado con los miembros denominados `surname` y `city`. La cláusula `group` hace que se cree un grupo independiente para cada conjunto de personas con el mismo apellido y la misma ciudad.

```csharp
group person by new {name = person.surname, city = person.city};
```

Use un tipo con nombre si debe pasar la variable de consulta a otro método. Cree una clase especial usando las propiedades autoimplementadas para las claves y, luego, invalide los métodos <xref:System.Object.Equals%2A> y <xref:System.Object.GetHashCode%2A>. También puede usar un struct, en cuyo caso no es estrictamente necesario invalidar esos métodos. Para más información, consulte [Procedimiento Implementar una clase ligera con propiedades autoimplementadas](../../programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md) y [Procedimiento para buscar archivos duplicados en un árbol de directorios](../../programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md). El último artículo contiene un ejemplo de código en el que se muestra cómo usar una clave compuesta con un tipo con nombre.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra el patrón estándar para ordenar los datos de origen en grupos cuando no se aplica ninguna lógica de consulta adicional a los grupos. Esto se denomina agrupación sin continuación. Los elementos de una matriz de cadenas se agrupan por la primera letra. El resultado de la consulta es un tipo <xref:System.Linq.IGrouping%602> que contiene una propiedad `Key` pública de tipo `char` y una colección <xref:System.Collections.Generic.IEnumerable%601> que contiene cada elemento de la agrupación.

El resultado de una cláusula `group` es una secuencia de secuencias. Por consiguiente, para tener acceso a los elementos individuales de cada grupo devuelto, use un bucle `foreach` anidado dentro del bucle que recorre en iteración las claves de grupo, como se muestra en el ejemplo siguiente.

[!code-csharp[cscsrefQueryKeywords#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#16)]

## <a name="example"></a>Ejemplo

En este ejemplo se muestra cómo aplicar lógica adicional a los grupos después de haberlos creado, mediante el uso de una *continuación* con `into`. Para obtener más información, vea [into](into.md). En el ejemplo siguiente se consulta cada grupo para seleccionar solo aquellos cuyo valor de clave sea una vocal.

[!code-csharp[cscsrefQueryKeywords#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#17)]

## <a name="remarks"></a>Comentarios

En tiempo de compilación, las cláusulas `group` se convierten en llamadas al método <xref:System.Linq.Enumerable.GroupBy%2A>.

## <a name="see-also"></a>Vea también

- <xref:System.Linq.IGrouping%602>
- <xref:System.Linq.Enumerable.GroupBy%2A>
- <xref:System.Linq.Enumerable.ThenBy%2A>
- <xref:System.Linq.Enumerable.ThenByDescending%2A>
- [Palabras clave para consultas](query-keywords.md)
- [Language-Integrated Query (LINQ)](../../linq/index.md)
- [Crear grupos anidados](../../linq/create-a-nested-group.md)
- [Agrupar los resultados de consultas](../../linq/group-query-results.md)
- [Realizar una subconsulta en una operación de agrupación](../../linq/perform-a-subquery-on-a-grouping-operation.md)
