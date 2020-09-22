---
title: Aggregate Clause
ms.date: 08/28/2018
f1_keywords:
- vb.QueryAggregateIn
- vb.QueryAggregate
- vb.QueryAggregateInto
helpviewer_keywords:
- Aggregate clause [Visual Basic]
- Aggregate statement [Visual Basic]
- queries [Visual Basic], Aggregate
ms.assetid: 1315a814-5db6-4077-b34b-b141e11cc0eb
ms.openlocfilehash: be2e401c7931b2637c14a3ea3b742a2c09917939
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869989"
---
# <a name="aggregate-clause-visual-basic"></a><span data-ttu-id="0279f-102">Aggregate (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0279f-102">Aggregate Clause (Visual Basic)</span></span>

<span data-ttu-id="0279f-103">Aplica una o más funciones de agregado a una colección.</span><span class="sxs-lookup"><span data-stu-id="0279f-103">Applies one or more aggregate functions to a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0279f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0279f-104">Syntax</span></span>  
  
```vb  
Aggregate element [As type] In collection _  
  [, element2 [As type2] In collection2, [...]]  
  [ clause ]  
  Into expressionList  
```  
  
## <a name="parts"></a><span data-ttu-id="0279f-105">Partes</span><span class="sxs-lookup"><span data-stu-id="0279f-105">Parts</span></span>  
  
|<span data-ttu-id="0279f-106">Término</span><span class="sxs-lookup"><span data-stu-id="0279f-106">Term</span></span>|<span data-ttu-id="0279f-107">Definición</span><span class="sxs-lookup"><span data-stu-id="0279f-107">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="0279f-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="0279f-108">Required.</span></span> <span data-ttu-id="0279f-109">Variable usada para recorrer en iteración los elementos de la colección.</span><span class="sxs-lookup"><span data-stu-id="0279f-109">Variable used to iterate through the elements of the collection.</span></span>|  
|`type`|<span data-ttu-id="0279f-110">Opcional.</span><span class="sxs-lookup"><span data-stu-id="0279f-110">Optional.</span></span> <span data-ttu-id="0279f-111">Tipo de `element`.</span><span class="sxs-lookup"><span data-stu-id="0279f-111">The type of `element`.</span></span> <span data-ttu-id="0279f-112">Si no se especifica ningún tipo, el tipo de `element` se deduce de `collection` .</span><span class="sxs-lookup"><span data-stu-id="0279f-112">If no type is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="0279f-113">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="0279f-113">Required.</span></span> <span data-ttu-id="0279f-114">Hace referencia a la colección en la que se va a operar.</span><span class="sxs-lookup"><span data-stu-id="0279f-114">Refers to the collection to operate on.</span></span>|  
|`clause`|<span data-ttu-id="0279f-115">Opcional.</span><span class="sxs-lookup"><span data-stu-id="0279f-115">Optional.</span></span> <span data-ttu-id="0279f-116">Una o varias cláusulas de consulta, como una `Where` cláusula, para refinar el resultado de la consulta a fin de aplicar la cláusula o cláusulas de agregado a.</span><span class="sxs-lookup"><span data-stu-id="0279f-116">One or more query clauses, such as a `Where` clause, to refine the query result to apply the aggregate clause or clauses to.</span></span>|  
|`expressionList`|<span data-ttu-id="0279f-117">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="0279f-117">Required.</span></span> <span data-ttu-id="0279f-118">Una o más expresiones delimitadas por comas que identifican una función de agregado que se va a aplicar a la colección.</span><span class="sxs-lookup"><span data-stu-id="0279f-118">One or more comma-delimited expressions that identify an aggregate function to apply to the collection.</span></span> <span data-ttu-id="0279f-119">Puede aplicar un alias a una función de agregado para especificar un nombre de miembro para el resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="0279f-119">You can apply an alias to an aggregate function to specify a member name for the query result.</span></span> <span data-ttu-id="0279f-120">Si no se proporciona ningún alias, se utiliza el nombre de la función de agregado.</span><span class="sxs-lookup"><span data-stu-id="0279f-120">If no alias is supplied, the name of the aggregate function is used.</span></span> <span data-ttu-id="0279f-121">Para obtener ejemplos, vea la sección acerca de las funciones de agregado más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="0279f-121">For examples, see the section about aggregate functions later in this topic.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0279f-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0279f-122">Remarks</span></span>  

 <span data-ttu-id="0279f-123">La `Aggregate` cláusula se puede utilizar para incluir funciones de agregado en las consultas.</span><span class="sxs-lookup"><span data-stu-id="0279f-123">The `Aggregate` clause can be used to include aggregate functions in your queries.</span></span> <span data-ttu-id="0279f-124">Las funciones de agregado realizan comprobaciones y cálculos sobre un conjunto de valores y devuelven un valor único.</span><span class="sxs-lookup"><span data-stu-id="0279f-124">Aggregate functions perform checks and computations over a set of values and return a single value.</span></span> <span data-ttu-id="0279f-125">Puede tener acceso al valor calculado mediante el uso de un miembro del tipo de resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="0279f-125">You can access the computed value by using a member of the query result type.</span></span> <span data-ttu-id="0279f-126">Las funciones de agregado estándar que se pueden usar son las `All` funciones,,,,,, `Any` `Average` `Count` `LongCount` `Max` `Min` y `Sum` .</span><span class="sxs-lookup"><span data-stu-id="0279f-126">The standard aggregate functions that you can use are the `All`, `Any`, `Average`, `Count`, `LongCount`, `Max`, `Min`, and `Sum` functions.</span></span> <span data-ttu-id="0279f-127">Estas funciones resultan familiares a los desarrolladores que están familiarizados con los agregados de SQL.</span><span class="sxs-lookup"><span data-stu-id="0279f-127">These functions are familiar to developers who are familiar with aggregates in SQL.</span></span> <span data-ttu-id="0279f-128">Se describen en la sección siguiente de este tema.</span><span class="sxs-lookup"><span data-stu-id="0279f-128">They are described in the following section of this topic.</span></span>  
  
 <span data-ttu-id="0279f-129">El resultado de una función de agregado se incluye en el resultado de la consulta como un campo del tipo de resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="0279f-129">The result of an aggregate function is included in the query result as a field of the query result type.</span></span> <span data-ttu-id="0279f-130">Puede proporcionar un alias para que el resultado de la función de agregado especifique el nombre del miembro del tipo de resultado de la consulta que contendrá el valor agregado.</span><span class="sxs-lookup"><span data-stu-id="0279f-130">You can supply an alias for the aggregate function result to specify the name of the member of the query result type that will hold the aggregate value.</span></span> <span data-ttu-id="0279f-131">Si no se proporciona ningún alias, se utiliza el nombre de la función de agregado.</span><span class="sxs-lookup"><span data-stu-id="0279f-131">If no alias is supplied, the name of the aggregate function is used.</span></span>  
  
 <span data-ttu-id="0279f-132">La `Aggregate` cláusula puede comenzar una consulta o se puede incluir como una cláusula adicional en una consulta.</span><span class="sxs-lookup"><span data-stu-id="0279f-132">The `Aggregate` clause can begin a query, or it can be included as an additional clause in a query.</span></span> <span data-ttu-id="0279f-133">Si la `Aggregate` cláusula comienza una consulta, el resultado es un valor único que es el resultado de la función de agregado especificada en la `Into` cláusula.</span><span class="sxs-lookup"><span data-stu-id="0279f-133">If the `Aggregate` clause begins a query, the result is a single value that is the result of the aggregate function specified in the `Into` clause.</span></span> <span data-ttu-id="0279f-134">Si se especifica más de una función de agregado en la `Into` cláusula, la consulta devuelve un tipo único con una propiedad independiente para hacer referencia al resultado de cada función de agregado en la `Into` cláusula.</span><span class="sxs-lookup"><span data-stu-id="0279f-134">If more than one aggregate function is specified in the `Into` clause, the query returns a single type with a separate property to reference the result of each aggregate function in the `Into` clause.</span></span> <span data-ttu-id="0279f-135">Si la `Aggregate` cláusula se incluye como una cláusula adicional en una consulta, el tipo devuelto en la colección de consultas tendrá una propiedad independiente para hacer referencia al resultado de cada función de agregado en la `Into` cláusula.</span><span class="sxs-lookup"><span data-stu-id="0279f-135">If the `Aggregate` clause is included as an additional clause in a query, the type returned in the query collection will have a separate property to reference the result of each aggregate function in the `Into` clause.</span></span>  
  
## <a name="aggregate-functions"></a><span data-ttu-id="0279f-136">Funciones de agregado</span><span class="sxs-lookup"><span data-stu-id="0279f-136">Aggregate Functions</span></span>

<span data-ttu-id="0279f-137">A continuación se enumeran las funciones de agregado estándar que se pueden usar con la `Aggregate` cláusula.</span><span class="sxs-lookup"><span data-stu-id="0279f-137">The following are the standard aggregate functions that can be used with the `Aggregate` clause.</span></span>  
  
### <a name="all"></a><span data-ttu-id="0279f-138">Todo</span><span class="sxs-lookup"><span data-stu-id="0279f-138">All</span></span>

<span data-ttu-id="0279f-139">Devuelve `true` si todos los elementos de la colección satisfacen una condición especificada; de lo contrario, devuelve `false` .</span><span class="sxs-lookup"><span data-stu-id="0279f-139">Returns `true` if all elements in the collection satisfy a specified condition; otherwise returns `false`.</span></span> <span data-ttu-id="0279f-140">Este es un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0279f-140">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#5)]

### <a name="any"></a><span data-ttu-id="0279f-141">Any</span><span class="sxs-lookup"><span data-stu-id="0279f-141">Any</span></span>

<span data-ttu-id="0279f-142">Devuelve `true` si algún elemento de la colección satisface una condición especificada; de lo contrario, devuelve `false` .</span><span class="sxs-lookup"><span data-stu-id="0279f-142">Returns `true` if any element in the collection satisfies a specified condition; otherwise returns `false`.</span></span> <span data-ttu-id="0279f-143">Este es un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0279f-143">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#6)]

### <a name="average"></a><span data-ttu-id="0279f-144">Media</span><span class="sxs-lookup"><span data-stu-id="0279f-144">Average</span></span>

<span data-ttu-id="0279f-145">Calcula el promedio de todos los elementos de la colección o calcula una expresión proporcionada para todos los elementos de la colección.</span><span class="sxs-lookup"><span data-stu-id="0279f-145">Computes the average of all elements in the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="0279f-146">Este es un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0279f-146">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#7)]

### <a name="count"></a><span data-ttu-id="0279f-147">Count</span><span class="sxs-lookup"><span data-stu-id="0279f-147">Count</span></span>

<span data-ttu-id="0279f-148">Cuenta el número de elementos de la colección.</span><span class="sxs-lookup"><span data-stu-id="0279f-148">Counts the number of elements in the collection.</span></span> <span data-ttu-id="0279f-149">Puede proporcionar una expresión opcional `Boolean` para contar solo el número de elementos de la colección que satisfacen una condición.</span><span class="sxs-lookup"><span data-stu-id="0279f-149">You can supply an optional `Boolean` expression to count only the number of elements in the collection that satisfy a condition.</span></span> <span data-ttu-id="0279f-150">Este es un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0279f-150">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#8)]

### <a name="group"></a><span data-ttu-id="0279f-151">Group (Grupo)</span><span class="sxs-lookup"><span data-stu-id="0279f-151">Group</span></span>

<span data-ttu-id="0279f-152">Hace referencia a los resultados de la consulta agrupados como resultado de `Group By` una `Group Join` cláusula o.</span><span class="sxs-lookup"><span data-stu-id="0279f-152">Refers to query results that are grouped as a result of a `Group By` or `Group Join` clause.</span></span> <span data-ttu-id="0279f-153">La `Group` función solo es válida en la `Into` cláusula de una `Group By` `Group Join` cláusula o.</span><span class="sxs-lookup"><span data-stu-id="0279f-153">The `Group` function is valid only in the `Into` clause of a `Group By` or `Group Join` clause.</span></span> <span data-ttu-id="0279f-154">Para obtener más información y ejemplos, vea cláusula [Group by](group-by-clause.md) y Group [join](group-join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="0279f-154">For more information and examples, see [Group By Clause](group-by-clause.md) and [Group Join Clause](group-join-clause.md).</span></span>

### <a name="longcount"></a><span data-ttu-id="0279f-155">LongCount</span><span class="sxs-lookup"><span data-stu-id="0279f-155">LongCount</span></span>

<span data-ttu-id="0279f-156">Cuenta el número de elementos de la colección.</span><span class="sxs-lookup"><span data-stu-id="0279f-156">Counts the number of elements in the collection.</span></span> <span data-ttu-id="0279f-157">Puede proporcionar una expresión opcional `Boolean` para contar solo el número de elementos de la colección que satisfacen una condición.</span><span class="sxs-lookup"><span data-stu-id="0279f-157">You can supply an optional `Boolean` expression to count only the number of elements in the collection that satisfy a condition.</span></span> <span data-ttu-id="0279f-158">Devuelve el resultado como `Long` .</span><span class="sxs-lookup"><span data-stu-id="0279f-158">Returns the result as a `Long`.</span></span> <span data-ttu-id="0279f-159">Para obtener un ejemplo, vea la `Count` función de agregado.</span><span class="sxs-lookup"><span data-stu-id="0279f-159">For an example, see the `Count` aggregate function.</span></span>

### <a name="max"></a><span data-ttu-id="0279f-160">Max</span><span class="sxs-lookup"><span data-stu-id="0279f-160">Max</span></span>

<span data-ttu-id="0279f-161">Calcula el valor máximo de la colección o calcula una expresión proporcionada para todos los elementos de la colección.</span><span class="sxs-lookup"><span data-stu-id="0279f-161">Computes the maximum value from the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="0279f-162">Este es un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0279f-162">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#9)]

### <a name="min"></a><span data-ttu-id="0279f-163">Min</span><span class="sxs-lookup"><span data-stu-id="0279f-163">Min</span></span>

<span data-ttu-id="0279f-164">Calcula el valor mínimo de la colección o calcula una expresión proporcionada para todos los elementos de la colección.</span><span class="sxs-lookup"><span data-stu-id="0279f-164">Computes the minimum value from the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="0279f-165">Este es un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0279f-165">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#10)]

### <a name="sum"></a><span data-ttu-id="0279f-166">Sum</span><span class="sxs-lookup"><span data-stu-id="0279f-166">Sum</span></span>

<span data-ttu-id="0279f-167">Calcula la suma de todos los elementos de la colección o calcula una expresión proporcionada para todos los elementos de la colección.</span><span class="sxs-lookup"><span data-stu-id="0279f-167">Computes the sum of all elements in the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="0279f-168">Este es un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0279f-168">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#15)]

## <a name="example"></a><span data-ttu-id="0279f-169">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0279f-169">Example</span></span>  

<span data-ttu-id="0279f-170">En el ejemplo siguiente se muestra cómo utilizar la `Aggregate` cláusula para aplicar funciones de agregado al resultado de una consulta.</span><span class="sxs-lookup"><span data-stu-id="0279f-170">The following example shows how to use the `Aggregate` clause to apply aggregate functions to a query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#4)]  
  
## <a name="creating-user-defined-aggregate-functions"></a><span data-ttu-id="0279f-171">Crear funciones de agregado definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="0279f-171">Creating User-Defined Aggregate Functions</span></span>

 <span data-ttu-id="0279f-172">Puede incluir sus propias funciones de agregado personalizadas en una expresión de consulta agregando métodos de extensión al <xref:System.Collections.Generic.IEnumerable%601> tipo.</span><span class="sxs-lookup"><span data-stu-id="0279f-172">You can include your own custom aggregate functions in a query expression by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> type.</span></span> <span data-ttu-id="0279f-173">Después, el método personalizado puede realizar un cálculo o una operación en la colección Enumerable que ha hecho referencia a la función de agregado.</span><span class="sxs-lookup"><span data-stu-id="0279f-173">Your custom method can then perform a calculation or operation on the enumerable collection that has referenced your aggregate function.</span></span> <span data-ttu-id="0279f-174">Para obtener más información sobre los métodos de extensión, vea [Métodos de extensión](../../programming-guide/language-features/procedures/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="0279f-174">For more information about extension methods, see [Extension Methods](../../programming-guide/language-features/procedures/extension-methods.md).</span></span>  
  
 <span data-ttu-id="0279f-175">Por ejemplo, en el ejemplo siguiente se muestra una función de agregado personalizada que calcula el valor medio de una colección de números.</span><span class="sxs-lookup"><span data-stu-id="0279f-175">For example, the following example shows a custom aggregate function that calculates the median value of a collection of numbers.</span></span> <span data-ttu-id="0279f-176">Hay dos sobrecargas del método de `Median` extensión.</span><span class="sxs-lookup"><span data-stu-id="0279f-176">There are two overloads of the `Median` extension method.</span></span> <span data-ttu-id="0279f-177">La primera sobrecarga acepta, como entrada, una colección de tipo `IEnumerable(Of Double)` .</span><span class="sxs-lookup"><span data-stu-id="0279f-177">The first overload accepts, as input, a collection of type `IEnumerable(Of Double)`.</span></span> <span data-ttu-id="0279f-178">Si `Median` se llama a la función de agregado para un campo de consulta de tipo `Double` , se llamará a este método.</span><span class="sxs-lookup"><span data-stu-id="0279f-178">If the `Median` aggregate function is called for a query field of type `Double`, this method will be called.</span></span> <span data-ttu-id="0279f-179">A la segunda sobrecarga del `Median` método se le puede pasar cualquier tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="0279f-179">The second overload of the `Median` method can be passed any generic type.</span></span> <span data-ttu-id="0279f-180">La sobrecarga genérica del `Median` método toma un segundo parámetro que hace referencia `Func(Of T, Double)` a la expresión lambda para proyectar un valor para un tipo (de una colección) como el valor correspondiente de tipo `Double` .</span><span class="sxs-lookup"><span data-stu-id="0279f-180">The generic overload of the `Median` method takes a second parameter that references the `Func(Of T, Double)` lambda expression to project a value for a type (from a collection) as the corresponding value of type `Double`.</span></span> <span data-ttu-id="0279f-181">A continuación, delega el cálculo del valor medio en la otra sobrecarga del `Median` método.</span><span class="sxs-lookup"><span data-stu-id="0279f-181">It then delegates the calculation of the median value to the other overload of the `Median` method.</span></span> <span data-ttu-id="0279f-182">Para obtener más información sobre las expresiones lambda, vea [expresiones lambda](../../programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="0279f-182">For more information about lambda expressions, see [Lambda Expressions](../../programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#18)]  
  
 <span data-ttu-id="0279f-183">En el ejemplo siguiente se muestran consultas de ejemplo que llaman a la `Median` función de agregado en una colección de tipo `Integer` y una colección de tipo `Double` .</span><span class="sxs-lookup"><span data-stu-id="0279f-183">The following example shows sample queries that call the `Median` aggregate function on a collection of type `Integer`, and a collection of type `Double`.</span></span> <span data-ttu-id="0279f-184">La consulta que llama a la `Median` función de agregado en la colección de tipo `Double` llama a la sobrecarga del `Median` método que acepta, como entrada, una colección de tipo `Double` .</span><span class="sxs-lookup"><span data-stu-id="0279f-184">The query that calls the `Median` aggregate function on the collection of type `Double` calls the overload of the `Median` method that accepts, as input, a collection of type `Double`.</span></span> <span data-ttu-id="0279f-185">La consulta que llama a la `Median` función de agregado en la colección de tipo `Integer` llama a la sobrecarga genérica del `Median` método.</span><span class="sxs-lookup"><span data-stu-id="0279f-185">The query that calls the `Median` aggregate function on the collection of type `Integer` calls the generic overload of the `Median` method.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="0279f-186">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0279f-186">See also</span></span>

- [<span data-ttu-id="0279f-187">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0279f-187">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="0279f-188">Consultas</span><span class="sxs-lookup"><span data-stu-id="0279f-188">Queries</span></span>](index.md)
- [<span data-ttu-id="0279f-189">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="0279f-189">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="0279f-190">Cláusula FROM</span><span class="sxs-lookup"><span data-stu-id="0279f-190">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="0279f-191">Cláusula WHERE</span><span class="sxs-lookup"><span data-stu-id="0279f-191">Where Clause</span></span>](where-clause.md)
- [<span data-ttu-id="0279f-192">Cláusula Group By</span><span class="sxs-lookup"><span data-stu-id="0279f-192">Group By Clause</span></span>](group-by-clause.md)
