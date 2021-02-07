---
description: 'Más información acerca de: cláusula Aggregate (Visual Basic)'
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
ms.openlocfilehash: 404cb4091bc11132450cf0d8d001ce426439ece7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700668"
---
# <a name="aggregate-clause-visual-basic"></a><span data-ttu-id="f7719-103">Aggregate (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f7719-103">Aggregate Clause (Visual Basic)</span></span>

<span data-ttu-id="f7719-104">Aplica una o más funciones de agregado a una colección.</span><span class="sxs-lookup"><span data-stu-id="f7719-104">Applies one or more aggregate functions to a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7719-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7719-105">Syntax</span></span>  
  
```vb  
Aggregate element [As type] In collection _  
  [, element2 [As type2] In collection2, [...]]  
  [ clause ]  
  Into expressionList  
```  
  
## <a name="parts"></a><span data-ttu-id="f7719-106">Partes</span><span class="sxs-lookup"><span data-stu-id="f7719-106">Parts</span></span>  
  
|<span data-ttu-id="f7719-107">Término</span><span class="sxs-lookup"><span data-stu-id="f7719-107">Term</span></span>|<span data-ttu-id="f7719-108">Definición</span><span class="sxs-lookup"><span data-stu-id="f7719-108">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="f7719-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="f7719-109">Required.</span></span> <span data-ttu-id="f7719-110">Variable usada para recorrer en iteración los elementos de la colección.</span><span class="sxs-lookup"><span data-stu-id="f7719-110">Variable used to iterate through the elements of the collection.</span></span>|  
|`type`|<span data-ttu-id="f7719-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f7719-111">Optional.</span></span> <span data-ttu-id="f7719-112">Tipo de `element`.</span><span class="sxs-lookup"><span data-stu-id="f7719-112">The type of `element`.</span></span> <span data-ttu-id="f7719-113">Si no se especifica ningún tipo, el tipo de `element` se deduce de `collection` .</span><span class="sxs-lookup"><span data-stu-id="f7719-113">If no type is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="f7719-114">Necesario.</span><span class="sxs-lookup"><span data-stu-id="f7719-114">Required.</span></span> <span data-ttu-id="f7719-115">Hace referencia a la colección en la que se va a operar.</span><span class="sxs-lookup"><span data-stu-id="f7719-115">Refers to the collection to operate on.</span></span>|  
|`clause`|<span data-ttu-id="f7719-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f7719-116">Optional.</span></span> <span data-ttu-id="f7719-117">Una o varias cláusulas de consulta, como una `Where` cláusula, para refinar el resultado de la consulta a fin de aplicar la cláusula o cláusulas de agregado a.</span><span class="sxs-lookup"><span data-stu-id="f7719-117">One or more query clauses, such as a `Where` clause, to refine the query result to apply the aggregate clause or clauses to.</span></span>|  
|`expressionList`|<span data-ttu-id="f7719-118">Necesario.</span><span class="sxs-lookup"><span data-stu-id="f7719-118">Required.</span></span> <span data-ttu-id="f7719-119">Una o más expresiones delimitadas por comas que identifican una función de agregado que se va a aplicar a la colección.</span><span class="sxs-lookup"><span data-stu-id="f7719-119">One or more comma-delimited expressions that identify an aggregate function to apply to the collection.</span></span> <span data-ttu-id="f7719-120">Puede aplicar un alias a una función de agregado para especificar un nombre de miembro para el resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="f7719-120">You can apply an alias to an aggregate function to specify a member name for the query result.</span></span> <span data-ttu-id="f7719-121">Si no se proporciona ningún alias, se utiliza el nombre de la función de agregado.</span><span class="sxs-lookup"><span data-stu-id="f7719-121">If no alias is supplied, the name of the aggregate function is used.</span></span> <span data-ttu-id="f7719-122">Para obtener ejemplos, vea la sección acerca de las funciones de agregado más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="f7719-122">For examples, see the section about aggregate functions later in this topic.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7719-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f7719-123">Remarks</span></span>  

 <span data-ttu-id="f7719-124">La `Aggregate` cláusula se puede utilizar para incluir funciones de agregado en las consultas.</span><span class="sxs-lookup"><span data-stu-id="f7719-124">The `Aggregate` clause can be used to include aggregate functions in your queries.</span></span> <span data-ttu-id="f7719-125">Las funciones de agregado realizan comprobaciones y cálculos sobre un conjunto de valores y devuelven un valor único.</span><span class="sxs-lookup"><span data-stu-id="f7719-125">Aggregate functions perform checks and computations over a set of values and return a single value.</span></span> <span data-ttu-id="f7719-126">Puede tener acceso al valor calculado mediante el uso de un miembro del tipo de resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="f7719-126">You can access the computed value by using a member of the query result type.</span></span> <span data-ttu-id="f7719-127">Las funciones de agregado estándar que se pueden usar son las `All` funciones,,,,,, `Any` `Average` `Count` `LongCount` `Max` `Min` y `Sum` .</span><span class="sxs-lookup"><span data-stu-id="f7719-127">The standard aggregate functions that you can use are the `All`, `Any`, `Average`, `Count`, `LongCount`, `Max`, `Min`, and `Sum` functions.</span></span> <span data-ttu-id="f7719-128">Estas funciones resultan familiares a los desarrolladores que están familiarizados con los agregados de SQL.</span><span class="sxs-lookup"><span data-stu-id="f7719-128">These functions are familiar to developers who are familiar with aggregates in SQL.</span></span> <span data-ttu-id="f7719-129">Se describen en la sección siguiente de este tema.</span><span class="sxs-lookup"><span data-stu-id="f7719-129">They are described in the following section of this topic.</span></span>  
  
 <span data-ttu-id="f7719-130">El resultado de una función de agregado se incluye en el resultado de la consulta como un campo del tipo de resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="f7719-130">The result of an aggregate function is included in the query result as a field of the query result type.</span></span> <span data-ttu-id="f7719-131">Puede proporcionar un alias para que el resultado de la función de agregado especifique el nombre del miembro del tipo de resultado de la consulta que contendrá el valor agregado.</span><span class="sxs-lookup"><span data-stu-id="f7719-131">You can supply an alias for the aggregate function result to specify the name of the member of the query result type that will hold the aggregate value.</span></span> <span data-ttu-id="f7719-132">Si no se proporciona ningún alias, se utiliza el nombre de la función de agregado.</span><span class="sxs-lookup"><span data-stu-id="f7719-132">If no alias is supplied, the name of the aggregate function is used.</span></span>  
  
 <span data-ttu-id="f7719-133">La `Aggregate` cláusula puede comenzar una consulta o se puede incluir como una cláusula adicional en una consulta.</span><span class="sxs-lookup"><span data-stu-id="f7719-133">The `Aggregate` clause can begin a query, or it can be included as an additional clause in a query.</span></span> <span data-ttu-id="f7719-134">Si la `Aggregate` cláusula comienza una consulta, el resultado es un valor único que es el resultado de la función de agregado especificada en la `Into` cláusula.</span><span class="sxs-lookup"><span data-stu-id="f7719-134">If the `Aggregate` clause begins a query, the result is a single value that is the result of the aggregate function specified in the `Into` clause.</span></span> <span data-ttu-id="f7719-135">Si se especifica más de una función de agregado en la `Into` cláusula, la consulta devuelve un tipo único con una propiedad independiente para hacer referencia al resultado de cada función de agregado en la `Into` cláusula.</span><span class="sxs-lookup"><span data-stu-id="f7719-135">If more than one aggregate function is specified in the `Into` clause, the query returns a single type with a separate property to reference the result of each aggregate function in the `Into` clause.</span></span> <span data-ttu-id="f7719-136">Si la `Aggregate` cláusula se incluye como una cláusula adicional en una consulta, el tipo devuelto en la colección de consultas tendrá una propiedad independiente para hacer referencia al resultado de cada función de agregado en la `Into` cláusula.</span><span class="sxs-lookup"><span data-stu-id="f7719-136">If the `Aggregate` clause is included as an additional clause in a query, the type returned in the query collection will have a separate property to reference the result of each aggregate function in the `Into` clause.</span></span>  
  
## <a name="aggregate-functions"></a><span data-ttu-id="f7719-137">Funciones de agregado</span><span class="sxs-lookup"><span data-stu-id="f7719-137">Aggregate Functions</span></span>

<span data-ttu-id="f7719-138">A continuación se enumeran las funciones de agregado estándar que se pueden usar con la `Aggregate` cláusula.</span><span class="sxs-lookup"><span data-stu-id="f7719-138">The following are the standard aggregate functions that can be used with the `Aggregate` clause.</span></span>  
  
### <a name="all"></a><span data-ttu-id="f7719-139">Todo</span><span class="sxs-lookup"><span data-stu-id="f7719-139">All</span></span>

<span data-ttu-id="f7719-140">Devuelve `true` si todos los elementos de la colección satisfacen una condición especificada; de lo contrario, devuelve `false` .</span><span class="sxs-lookup"><span data-stu-id="f7719-140">Returns `true` if all elements in the collection satisfy a specified condition; otherwise returns `false`.</span></span> <span data-ttu-id="f7719-141">A continuación se muestra un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f7719-141">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#5)]

### <a name="any"></a><span data-ttu-id="f7719-142">Cualquiera</span><span class="sxs-lookup"><span data-stu-id="f7719-142">Any</span></span>

<span data-ttu-id="f7719-143">Devuelve `true` si algún elemento de la colección satisface una condición especificada; de lo contrario, devuelve `false` .</span><span class="sxs-lookup"><span data-stu-id="f7719-143">Returns `true` if any element in the collection satisfies a specified condition; otherwise returns `false`.</span></span> <span data-ttu-id="f7719-144">A continuación se muestra un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f7719-144">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#6)]

### <a name="average"></a><span data-ttu-id="f7719-145">Promedio</span><span class="sxs-lookup"><span data-stu-id="f7719-145">Average</span></span>

<span data-ttu-id="f7719-146">Calcula el promedio de todos los elementos de la colección o calcula una expresión proporcionada para todos los elementos de la colección.</span><span class="sxs-lookup"><span data-stu-id="f7719-146">Computes the average of all elements in the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="f7719-147">A continuación se muestra un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f7719-147">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#7)]

### <a name="count"></a><span data-ttu-id="f7719-148">Count</span><span class="sxs-lookup"><span data-stu-id="f7719-148">Count</span></span>

<span data-ttu-id="f7719-149">Cuenta el número de elementos de la colección.</span><span class="sxs-lookup"><span data-stu-id="f7719-149">Counts the number of elements in the collection.</span></span> <span data-ttu-id="f7719-150">Puede proporcionar una expresión opcional `Boolean` para contar solo el número de elementos de la colección que satisfacen una condición.</span><span class="sxs-lookup"><span data-stu-id="f7719-150">You can supply an optional `Boolean` expression to count only the number of elements in the collection that satisfy a condition.</span></span> <span data-ttu-id="f7719-151">A continuación se muestra un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f7719-151">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#8)]

### <a name="group"></a><span data-ttu-id="f7719-152">Group (Grupo)</span><span class="sxs-lookup"><span data-stu-id="f7719-152">Group</span></span>

<span data-ttu-id="f7719-153">Hace referencia a los resultados de la consulta agrupados como resultado de `Group By` una `Group Join` cláusula o.</span><span class="sxs-lookup"><span data-stu-id="f7719-153">Refers to query results that are grouped as a result of a `Group By` or `Group Join` clause.</span></span> <span data-ttu-id="f7719-154">La `Group` función solo es válida en la `Into` cláusula de una `Group By` `Group Join` cláusula o.</span><span class="sxs-lookup"><span data-stu-id="f7719-154">The `Group` function is valid only in the `Into` clause of a `Group By` or `Group Join` clause.</span></span> <span data-ttu-id="f7719-155">Para obtener más información y ejemplos, vea cláusula [Group by](group-by-clause.md) y Group [join](group-join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="f7719-155">For more information and examples, see [Group By Clause](group-by-clause.md) and [Group Join Clause](group-join-clause.md).</span></span>

### <a name="longcount"></a><span data-ttu-id="f7719-156">LongCount</span><span class="sxs-lookup"><span data-stu-id="f7719-156">LongCount</span></span>

<span data-ttu-id="f7719-157">Cuenta el número de elementos de la colección.</span><span class="sxs-lookup"><span data-stu-id="f7719-157">Counts the number of elements in the collection.</span></span> <span data-ttu-id="f7719-158">Puede proporcionar una expresión opcional `Boolean` para contar solo el número de elementos de la colección que satisfacen una condición.</span><span class="sxs-lookup"><span data-stu-id="f7719-158">You can supply an optional `Boolean` expression to count only the number of elements in the collection that satisfy a condition.</span></span> <span data-ttu-id="f7719-159">Devuelve el resultado como `Long` .</span><span class="sxs-lookup"><span data-stu-id="f7719-159">Returns the result as a `Long`.</span></span> <span data-ttu-id="f7719-160">Para obtener un ejemplo, vea la `Count` función de agregado.</span><span class="sxs-lookup"><span data-stu-id="f7719-160">For an example, see the `Count` aggregate function.</span></span>

### <a name="max"></a><span data-ttu-id="f7719-161">Max</span><span class="sxs-lookup"><span data-stu-id="f7719-161">Max</span></span>

<span data-ttu-id="f7719-162">Calcula el valor máximo de la colección o calcula una expresión proporcionada para todos los elementos de la colección.</span><span class="sxs-lookup"><span data-stu-id="f7719-162">Computes the maximum value from the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="f7719-163">A continuación se muestra un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f7719-163">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#9)]

### <a name="min"></a><span data-ttu-id="f7719-164">Min</span><span class="sxs-lookup"><span data-stu-id="f7719-164">Min</span></span>

<span data-ttu-id="f7719-165">Calcula el valor mínimo de la colección o calcula una expresión proporcionada para todos los elementos de la colección.</span><span class="sxs-lookup"><span data-stu-id="f7719-165">Computes the minimum value from the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="f7719-166">A continuación se muestra un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f7719-166">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#10)]

### <a name="sum"></a><span data-ttu-id="f7719-167">Sum</span><span class="sxs-lookup"><span data-stu-id="f7719-167">Sum</span></span>

<span data-ttu-id="f7719-168">Calcula la suma de todos los elementos de la colección o calcula una expresión proporcionada para todos los elementos de la colección.</span><span class="sxs-lookup"><span data-stu-id="f7719-168">Computes the sum of all elements in the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="f7719-169">A continuación se muestra un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f7719-169">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#15)]

## <a name="example"></a><span data-ttu-id="f7719-170">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f7719-170">Example</span></span>  

<span data-ttu-id="f7719-171">En el ejemplo siguiente se muestra cómo utilizar la `Aggregate` cláusula para aplicar funciones de agregado al resultado de una consulta.</span><span class="sxs-lookup"><span data-stu-id="f7719-171">The following example shows how to use the `Aggregate` clause to apply aggregate functions to a query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#4)]  
  
## <a name="creating-user-defined-aggregate-functions"></a><span data-ttu-id="f7719-172">Crear User-Defined funciones de agregado</span><span class="sxs-lookup"><span data-stu-id="f7719-172">Creating User-Defined Aggregate Functions</span></span>

 <span data-ttu-id="f7719-173">Puede incluir sus propias funciones de agregado personalizadas en una expresión de consulta agregando métodos de extensión al <xref:System.Collections.Generic.IEnumerable%601> tipo.</span><span class="sxs-lookup"><span data-stu-id="f7719-173">You can include your own custom aggregate functions in a query expression by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> type.</span></span> <span data-ttu-id="f7719-174">Después, el método personalizado puede realizar un cálculo o una operación en la colección Enumerable que ha hecho referencia a la función de agregado.</span><span class="sxs-lookup"><span data-stu-id="f7719-174">Your custom method can then perform a calculation or operation on the enumerable collection that has referenced your aggregate function.</span></span> <span data-ttu-id="f7719-175">Para obtener más información sobre los métodos de extensión, vea [Métodos de extensión](../../programming-guide/language-features/procedures/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="f7719-175">For more information about extension methods, see [Extension Methods](../../programming-guide/language-features/procedures/extension-methods.md).</span></span>  
  
 <span data-ttu-id="f7719-176">Por ejemplo, en el ejemplo siguiente se muestra una función de agregado personalizada que calcula el valor medio de una colección de números.</span><span class="sxs-lookup"><span data-stu-id="f7719-176">For example, the following example shows a custom aggregate function that calculates the median value of a collection of numbers.</span></span> <span data-ttu-id="f7719-177">Hay dos sobrecargas del método de `Median` extensión.</span><span class="sxs-lookup"><span data-stu-id="f7719-177">There are two overloads of the `Median` extension method.</span></span> <span data-ttu-id="f7719-178">La primera sobrecarga acepta, como entrada, una colección de tipo `IEnumerable(Of Double)` .</span><span class="sxs-lookup"><span data-stu-id="f7719-178">The first overload accepts, as input, a collection of type `IEnumerable(Of Double)`.</span></span> <span data-ttu-id="f7719-179">Si `Median` se llama a la función de agregado para un campo de consulta de tipo `Double` , se llamará a este método.</span><span class="sxs-lookup"><span data-stu-id="f7719-179">If the `Median` aggregate function is called for a query field of type `Double`, this method will be called.</span></span> <span data-ttu-id="f7719-180">A la segunda sobrecarga del `Median` método se le puede pasar cualquier tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="f7719-180">The second overload of the `Median` method can be passed any generic type.</span></span> <span data-ttu-id="f7719-181">La sobrecarga genérica del `Median` método toma un segundo parámetro que hace referencia `Func(Of T, Double)` a la expresión lambda para proyectar un valor para un tipo (de una colección) como el valor correspondiente de tipo `Double` .</span><span class="sxs-lookup"><span data-stu-id="f7719-181">The generic overload of the `Median` method takes a second parameter that references the `Func(Of T, Double)` lambda expression to project a value for a type (from a collection) as the corresponding value of type `Double`.</span></span> <span data-ttu-id="f7719-182">A continuación, delega el cálculo del valor medio en la otra sobrecarga del `Median` método.</span><span class="sxs-lookup"><span data-stu-id="f7719-182">It then delegates the calculation of the median value to the other overload of the `Median` method.</span></span> <span data-ttu-id="f7719-183">Para obtener más información sobre las expresiones lambda, vea [expresiones lambda](../../programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="f7719-183">For more information about lambda expressions, see [Lambda Expressions](../../programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#18)]  
  
 <span data-ttu-id="f7719-184">En el ejemplo siguiente se muestran consultas de ejemplo que llaman a la `Median` función de agregado en una colección de tipo `Integer` y una colección de tipo `Double` .</span><span class="sxs-lookup"><span data-stu-id="f7719-184">The following example shows sample queries that call the `Median` aggregate function on a collection of type `Integer`, and a collection of type `Double`.</span></span> <span data-ttu-id="f7719-185">La consulta que llama a la `Median` función de agregado en la colección de tipo `Double` llama a la sobrecarga del `Median` método que acepta, como entrada, una colección de tipo `Double` .</span><span class="sxs-lookup"><span data-stu-id="f7719-185">The query that calls the `Median` aggregate function on the collection of type `Double` calls the overload of the `Median` method that accepts, as input, a collection of type `Double`.</span></span> <span data-ttu-id="f7719-186">La consulta que llama a la `Median` función de agregado en la colección de tipo `Integer` llama a la sobrecarga genérica del `Median` método.</span><span class="sxs-lookup"><span data-stu-id="f7719-186">The query that calls the `Median` aggregate function on the collection of type `Integer` calls the generic overload of the `Median` method.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="f7719-187">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7719-187">See also</span></span>

- [<span data-ttu-id="f7719-188">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f7719-188">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="f7719-189">Consultas</span><span class="sxs-lookup"><span data-stu-id="f7719-189">Queries</span></span>](index.md)
- [<span data-ttu-id="f7719-190">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="f7719-190">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="f7719-191">Cláusula From</span><span class="sxs-lookup"><span data-stu-id="f7719-191">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="f7719-192">Cláusula WHERE</span><span class="sxs-lookup"><span data-stu-id="f7719-192">Where Clause</span></span>](where-clause.md)
- [<span data-ttu-id="f7719-193">Group by (cláusula)</span><span class="sxs-lookup"><span data-stu-id="f7719-193">Group By Clause</span></span>](group-by-clause.md)
