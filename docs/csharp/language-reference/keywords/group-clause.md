---
title: group (Cláusula, Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- group
- group_CSharpKeyword
helpviewer_keywords:
- group keyword [C#]
- group clause [C#]
ms.assetid: c817242e-b12c-4baa-a57e-73ee138f34d1
ms.openlocfilehash: 8b2516b4e5b418e560d5763d8e551d2ab7646da3
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "48584356"
---
# <a name="group-clause-c-reference"></a><span data-ttu-id="06b6b-102">group (Cláusula, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="06b6b-102">group clause (C# Reference)</span></span>

<span data-ttu-id="06b6b-103">La cláusula `group` devuelve una secuencia de objetos <xref:System.Linq.IGrouping%602> que contienen cero o más elementos que coinciden con el valor de clave del grupo.</span><span class="sxs-lookup"><span data-stu-id="06b6b-103">The `group` clause returns a sequence of <xref:System.Linq.IGrouping%602> objects that contain zero or more items that match the key value for the group.</span></span> <span data-ttu-id="06b6b-104">Por ejemplo, puede agrupar una secuencia de cadenas según la primera letra de cada cadena.</span><span class="sxs-lookup"><span data-stu-id="06b6b-104">For example, you can group a sequence of strings according to the first letter in each string.</span></span> <span data-ttu-id="06b6b-105">En este caso, la primera letra es la clave, es de tipo [char](char.md) y se almacena en la propiedad `Key` de cada objeto <xref:System.Linq.IGrouping%602>.</span><span class="sxs-lookup"><span data-stu-id="06b6b-105">In this case, the first letter is the key and has a type [char](char.md), and is stored in the `Key` property of each <xref:System.Linq.IGrouping%602> object.</span></span> <span data-ttu-id="06b6b-106">El compilador deduce el tipo de la clave.</span><span class="sxs-lookup"><span data-stu-id="06b6b-106">The compiler infers the type of the key.</span></span>

<span data-ttu-id="06b6b-107">Puede finalizar una expresión de consulta con una cláusula `group`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="06b6b-107">You can end a query expression with a `group` clause, as shown in the following example:</span></span>

[!code-csharp[cscsrefQueryKeywords#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#10)]

<span data-ttu-id="06b6b-108">Si quiere realizar operaciones de consulta adicionales en cada grupo, puede especificar un identificador temporal mediante la palabra clave contextual [into](into.md).</span><span class="sxs-lookup"><span data-stu-id="06b6b-108">If you want to perform additional query operations on each group, you can specify a temporary identifier by using the [into](into.md) contextual keyword.</span></span> <span data-ttu-id="06b6b-109">Cuando se usa `into`, es necesario continuar con la consulta y finalmente terminarla con una instrucción `select` u otra cláusula `group`, como se muestra en el extracto siguiente:</span><span class="sxs-lookup"><span data-stu-id="06b6b-109">When you use `into`, you must continue with the query, and eventually end it with either a `select` statement or another `group` clause, as shown in the following excerpt:</span></span>

[!code-csharp[cscsrefQueryKeywords#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#11)]

<span data-ttu-id="06b6b-110">En la sección Ejemplo de este artículo se proporcionan ejemplos más completos sobre el uso de `group` con y sin `into`.</span><span class="sxs-lookup"><span data-stu-id="06b6b-110">More complete examples of the use of `group` with and without `into` are provided in the Example section of this article.</span></span>

## <a name="enumerating-the-results-of-a-group-query"></a><span data-ttu-id="06b6b-111">Enumeración de los resultados de una consulta de grupo</span><span class="sxs-lookup"><span data-stu-id="06b6b-111">Enumerating the results of a group query</span></span>

<span data-ttu-id="06b6b-112">Dado que los objetos <xref:System.Linq.IGrouping%602> generados por una consulta `group` son esencialmente una lista de listas, debe usar un bucle [foreach](foreach-in.md) anidado para tener acceso a los elementos de cada grupo.</span><span class="sxs-lookup"><span data-stu-id="06b6b-112">Because the <xref:System.Linq.IGrouping%602> objects produced by a `group` query are essentially a list of lists, you must use a nested [foreach](foreach-in.md) loop to access the items in each group.</span></span> <span data-ttu-id="06b6b-113">El bucle exterior recorre en iteración las claves de grupo y el bucle interno recorre en iteración cada elemento del propio grupo.</span><span class="sxs-lookup"><span data-stu-id="06b6b-113">The outer loop iterates over the group keys, and the inner loop iterates over each item in the group itself.</span></span> <span data-ttu-id="06b6b-114">Un grupo puede tener una clave pero ningún elemento.</span><span class="sxs-lookup"><span data-stu-id="06b6b-114">A group may have a key but no elements.</span></span> <span data-ttu-id="06b6b-115">A continuación se muestra el bucle `foreach` que ejecuta la consulta en los ejemplos de código anteriores:</span><span class="sxs-lookup"><span data-stu-id="06b6b-115">The following is the `foreach` loop that executes the query in the previous code examples:</span></span>

[!code-csharp[cscsrefQueryKeywords#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#12)]

## <a name="key-types"></a><span data-ttu-id="06b6b-116">Tipos de clave</span><span class="sxs-lookup"><span data-stu-id="06b6b-116">Key types</span></span>

<span data-ttu-id="06b6b-117">Las claves de grupo pueden ser de cualquier tipo, como una cadena, un tipo numérico integrado, un tipo con nombre definido por el usuario o un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="06b6b-117">Group keys can be any type, such as a string, a built-in numeric type, or a user-defined named type or anonymous type.</span></span>

### <a name="grouping-by-string"></a><span data-ttu-id="06b6b-118">Agrupar por cadena</span><span class="sxs-lookup"><span data-stu-id="06b6b-118">Grouping by string</span></span>

<span data-ttu-id="06b6b-119">En los ejemplos de código anteriores se ha usado el tipo `char`.</span><span class="sxs-lookup"><span data-stu-id="06b6b-119">The previous code examples used a `char`.</span></span> <span data-ttu-id="06b6b-120">En su lugar, podría haberse especificado una clave de cadena, por ejemplo, los apellidos completos:</span><span class="sxs-lookup"><span data-stu-id="06b6b-120">A string key could easily have been specified instead, for example the complete last name:</span></span>

[!code-csharp[cscsrefQueryKeywords#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#13)]

### <a name="grouping-by-bool"></a><span data-ttu-id="06b6b-121">Agrupar por valor booleano</span><span class="sxs-lookup"><span data-stu-id="06b6b-121">Grouping by bool</span></span>

<span data-ttu-id="06b6b-122">En el ejemplo siguiente se muestra el uso de un valor booleano para una clave con el fin de dividir los resultados en dos grupos.</span><span class="sxs-lookup"><span data-stu-id="06b6b-122">The following example shows the use of a bool value for a key to divide the results into two groups.</span></span> <span data-ttu-id="06b6b-123">Observe que el valor se genera a partir de una subexpresión en la cláusula `group`.</span><span class="sxs-lookup"><span data-stu-id="06b6b-123">Note that the value is produced by a sub-expression in the `group` clause.</span></span>

[!code-csharp[cscsrefQueryKeywords#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#14)]

### <a name="grouping-by-numeric-range"></a><span data-ttu-id="06b6b-124">Agrupar por intervalo numérico</span><span class="sxs-lookup"><span data-stu-id="06b6b-124">Grouping by numeric range</span></span>

<span data-ttu-id="06b6b-125">En el ejemplo siguiente se usa una expresión para crear claves de grupo numéricas que representan un intervalo de percentil.</span><span class="sxs-lookup"><span data-stu-id="06b6b-125">The next example uses an expression to create numeric group keys that represent a percentile range.</span></span> <span data-ttu-id="06b6b-126">Observe el uso de [let](let-clause.md) como ubicación adecuada para almacenar el resultado de una llamada de método, para no tener que llamar al método dos veces en la cláusula `group`.</span><span class="sxs-lookup"><span data-stu-id="06b6b-126">Note the use of [let](let-clause.md) as a convenient location to store a method call result, so that you don't have to call the method two times in the `group` clause.</span></span> <span data-ttu-id="06b6b-127">Para obtener más información sobre cómo usar métodos en expresiones de consulta de manera segura, vea [Cómo: Controlar excepciones en expresiones de consulta](../../programming-guide/linq-query-expressions/how-to-handle-exceptions-in-query-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="06b6b-127">For more information about how to safely use methods in query expressions, see [How to: Handle Exceptions in Query Expressions](../../programming-guide/linq-query-expressions/how-to-handle-exceptions-in-query-expressions.md).</span></span>

[!code-csharp[cscsrefQueryKeywords#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#15)]

### <a name="grouping-by-composite-keys"></a><span data-ttu-id="06b6b-128">Agrupación por claves compuestas</span><span class="sxs-lookup"><span data-stu-id="06b6b-128">Grouping by composite keys</span></span>

<span data-ttu-id="06b6b-129">Use una clave compuesta cuando quiera agrupar los elementos según más de una clave.</span><span class="sxs-lookup"><span data-stu-id="06b6b-129">Use a composite key when you want to group elements according to more than one key.</span></span> <span data-ttu-id="06b6b-130">Para crear una clave compuesta se usa un tipo anónimo o un tipo con nombre para contener el elemento de clave.</span><span class="sxs-lookup"><span data-stu-id="06b6b-130">You create a composite key by using an anonymous type or a named type to hold the key element.</span></span> <span data-ttu-id="06b6b-131">En el ejemplo siguiente, supongamos que una clase `Person` se ha declarado con los miembros denominados `surname` y `city`.</span><span class="sxs-lookup"><span data-stu-id="06b6b-131">In the following example, assume that a class `Person` has been declared with members named `surname` and `city`.</span></span> <span data-ttu-id="06b6b-132">La cláusula `group` hace que se cree un grupo independiente para cada conjunto de personas con el mismo apellido y la misma ciudad.</span><span class="sxs-lookup"><span data-stu-id="06b6b-132">The `group` clause causes a separate group to be created for each set of persons with the same last name and the same city.</span></span>

```csharp
group person by new {name = person.surname, city = person.city};
```

<span data-ttu-id="06b6b-133">Use un tipo con nombre si debe pasar la variable de consulta a otro método.</span><span class="sxs-lookup"><span data-stu-id="06b6b-133">Use a named type if you must pass the query variable to another method.</span></span> <span data-ttu-id="06b6b-134">Cree una clase especial usando las propiedades autoimplementadas para las claves y, luego, invalide los métodos <xref:System.Object.Equals%2A> y <xref:System.Object.GetHashCode%2A>.</span><span class="sxs-lookup"><span data-stu-id="06b6b-134">Create a special class using auto-implemented properties for the keys, and then override the <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> methods.</span></span> <span data-ttu-id="06b6b-135">También puede usar un struct, en cuyo caso no es estrictamente necesario invalidar esos métodos.</span><span class="sxs-lookup"><span data-stu-id="06b6b-135">You can also use a struct, in which case you do not strictly have to override those methods.</span></span> <span data-ttu-id="06b6b-136">Para obtener más información, vea [Cómo: Implementar una clase ligera con propiedades autoimplementadas](../../programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md) y [How to: Query for Duplicate Files in a Directory Tree](../../programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md) (Cómo: Consultar archivos duplicados en un árbol de directorio).</span><span class="sxs-lookup"><span data-stu-id="06b6b-136">For more information see [How to: Implement a Lightweight Class with Auto-Implemented Properties](../../programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md) and [How to: Query for Duplicate Files in a Directory Tree](../../programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md).</span></span> <span data-ttu-id="06b6b-137">El último artículo contiene un ejemplo de código en el que se muestra cómo usar una clave compuesta con un tipo con nombre.</span><span class="sxs-lookup"><span data-stu-id="06b6b-137">The latter article has a code example that demonstrates how to use a composite key with a named type.</span></span>

## <a name="example"></a><span data-ttu-id="06b6b-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="06b6b-138">Example</span></span>

<span data-ttu-id="06b6b-139">En el ejemplo siguiente se muestra el patrón estándar para ordenar los datos de origen en grupos cuando no se aplica ninguna lógica de consulta adicional a los grupos.</span><span class="sxs-lookup"><span data-stu-id="06b6b-139">The following example shows the standard pattern for ordering source data into groups when no additional query logic is applied to the groups.</span></span> <span data-ttu-id="06b6b-140">Esto se denomina agrupación sin continuación.</span><span class="sxs-lookup"><span data-stu-id="06b6b-140">This is called a grouping without a continuation.</span></span> <span data-ttu-id="06b6b-141">Los elementos de una matriz de cadenas se agrupan por la primera letra.</span><span class="sxs-lookup"><span data-stu-id="06b6b-141">The elements in an array of strings are grouped according to their first letter.</span></span> <span data-ttu-id="06b6b-142">El resultado de la consulta es un tipo <xref:System.Linq.IGrouping%602> que contiene una propiedad `Key` pública de tipo `char` y una colección <xref:System.Collections.Generic.IEnumerable%601> que contiene cada elemento de la agrupación.</span><span class="sxs-lookup"><span data-stu-id="06b6b-142">The result of the query is an <xref:System.Linq.IGrouping%602> type that contains a public `Key` property of type `char` and an <xref:System.Collections.Generic.IEnumerable%601> collection that contains each item in the grouping.</span></span>

<span data-ttu-id="06b6b-143">El resultado de una cláusula `group` es una secuencia de secuencias.</span><span class="sxs-lookup"><span data-stu-id="06b6b-143">The result of a `group` clause is a sequence of sequences.</span></span> <span data-ttu-id="06b6b-144">Por consiguiente, para tener acceso a los elementos individuales de cada grupo devuelto, use un bucle `foreach` anidado dentro del bucle que recorre en iteración las claves de grupo, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="06b6b-144">Therefore, to access the individual elements within each returned group, use a nested `foreach` loop inside the loop that iterates the group keys, as shown in the following example.</span></span>

[!code-csharp[cscsrefQueryKeywords#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#16)]

## <a name="example"></a><span data-ttu-id="06b6b-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="06b6b-145">Example</span></span>

<span data-ttu-id="06b6b-146">En este ejemplo se muestra cómo aplicar lógica adicional a los grupos después de haberlos creado, mediante el uso de una *continuación* con `into`.</span><span class="sxs-lookup"><span data-stu-id="06b6b-146">This example shows how to perform additional logic on the groups after you have created them, by using a *continuation* with `into`.</span></span> <span data-ttu-id="06b6b-147">Para obtener más información, vea [into](into.md).</span><span class="sxs-lookup"><span data-stu-id="06b6b-147">For more information, see [into](into.md).</span></span> <span data-ttu-id="06b6b-148">En el ejemplo siguiente se consulta cada grupo para seleccionar solo aquellos cuyo valor de clave sea una vocal.</span><span class="sxs-lookup"><span data-stu-id="06b6b-148">The following example queries each group to select only those whose key value is a vowel.</span></span>

[!code-csharp[cscsrefQueryKeywords#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#17)]

## <a name="remarks"></a><span data-ttu-id="06b6b-149">Comentarios</span><span class="sxs-lookup"><span data-stu-id="06b6b-149">Remarks</span></span>

<span data-ttu-id="06b6b-150">En tiempo de compilación, las cláusulas `group` se convierten en llamadas al método <xref:System.Linq.Enumerable.GroupBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="06b6b-150">At compile time, `group` clauses are translated into calls to the <xref:System.Linq.Enumerable.GroupBy%2A> method.</span></span>

## <a name="see-also"></a><span data-ttu-id="06b6b-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="06b6b-151">See also</span></span>

- <xref:System.Linq.IGrouping%602>  
- <xref:System.Linq.Enumerable.GroupBy%2A>  
- <xref:System.Linq.Enumerable.ThenBy%2A>  
- <xref:System.Linq.Enumerable.ThenByDescending%2A>  
- [<span data-ttu-id="06b6b-152">Palabras clave para consultas</span><span class="sxs-lookup"><span data-stu-id="06b6b-152">Query Keywords</span></span>](query-keywords.md)  
- [<span data-ttu-id="06b6b-153">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="06b6b-153">Language Integrated Query (LINQ)</span></span>](../../linq/index.md)  
- [<span data-ttu-id="06b6b-154">Crear grupos anidados</span><span class="sxs-lookup"><span data-stu-id="06b6b-154">Create a nested group</span></span>](../../linq/create-a-nested-group.md)  
- [<span data-ttu-id="06b6b-155">Agrupar los resultados de consultas</span><span class="sxs-lookup"><span data-stu-id="06b6b-155">Group query results</span></span>](../../linq/group-query-results.md)  
- [<span data-ttu-id="06b6b-156">Realizar una subconsulta en una operación de agrupación</span><span class="sxs-lookup"><span data-stu-id="06b6b-156">Perform a subquery on a grouping operation</span></span>](../../linq/perform-a-subquery-on-a-grouping-operation.md)
