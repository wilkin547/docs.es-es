---
title: Consultas basadas en el estado de tiempo de ejecución (Visual Basic)
description: Se describen diversas técnicas que el código puede usar para realizar consultas de forma dinámica según el estado del entorno de ejecución, mediante la modificación de las llamadas a métodos de LINQ o los árboles de expresión pasados a esos métodos.
ms.date: 02/14/2021
ms.assetid: 16278787-7532-4b65-98b2-7a412406c4ee
ms.openlocfilehash: fe59fc8287e67247884cfdcf1bacc6ed2a447e5a
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104875881"
---
# <a name="querying-based-on-runtime-state-visual-basic"></a><span data-ttu-id="c5347-103">Consultas basadas en el estado de tiempo de ejecución (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5347-103">Querying based on runtime state (Visual Basic)</span></span>

<span data-ttu-id="c5347-104">Considere el código que define un <xref:System.Linq.IQueryable> o un [IQueryable (of T)](<xref:System.Linq.IQueryable%601>) en un origen de datos:</span><span class="sxs-lookup"><span data-stu-id="c5347-104">Consider code that defines an <xref:System.Linq.IQueryable> or an [IQueryable(Of T)](<xref:System.Linq.IQueryable%601>) against a data source:</span></span>

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Initialize":::

<span data-ttu-id="c5347-105">Cada vez que ejecute este código, se ejecutará la misma consulta exacta.</span><span class="sxs-lookup"><span data-stu-id="c5347-105">Every time you run this code, the same exact query will be executed.</span></span> <span data-ttu-id="c5347-106">Esto no suele ser muy útil, ya que es posible que quiera que el código ejecute otras consultas en función de las condiciones en el momento de la ejecución.</span><span class="sxs-lookup"><span data-stu-id="c5347-106">This is frequently not very useful, as you may want your code to execute different queries depending on conditions at runtime.</span></span> <span data-ttu-id="c5347-107">En este artículo se describe cómo puede ejecutar otra consulta en función del estado del entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c5347-107">This article describes how you can execute a different query based on runtime state.</span></span>

## <a name="iqueryable--iqueryableof-t-and-expression-trees"></a><span data-ttu-id="c5347-108">IQueryable/IQueryable (of T) y árboles de expresión</span><span class="sxs-lookup"><span data-stu-id="c5347-108">IQueryable / IQueryable(Of T) and expression trees</span></span>

<span data-ttu-id="c5347-109">Fundamentalmente, una interfaz <xref:System.Linq.IQueryable> tiene dos componentes:</span><span class="sxs-lookup"><span data-stu-id="c5347-109">Fundamentally, an <xref:System.Linq.IQueryable> has two components:</span></span>

* <span data-ttu-id="c5347-110"><xref:System.Linq.IQueryable.Expression>&mdash;representación independiente del lenguaje y del origen de datos de los componentes de la consulta actual, en forma de un árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="c5347-110"><xref:System.Linq.IQueryable.Expression>&mdash;a language- and datasource-agnostic representation of the current query's components, in the form of an expression tree.</span></span>
* <span data-ttu-id="c5347-111"><xref:System.Linq.IQueryable.Provider>&mdash;instancia de un proveedor LINQ, que sabe cómo materializar la consulta actual en un valor o un conjunto de valores.</span><span class="sxs-lookup"><span data-stu-id="c5347-111"><xref:System.Linq.IQueryable.Provider>&mdash;an instance of a LINQ provider, which knows how to materialize the current query into a value or set of values.</span></span>

<span data-ttu-id="c5347-112">En el contexto de las consultas dinámicas, el proveedor normalmente seguirá siendo el mismo; el árbol de expresión de la consulta variará entre consultas.</span><span class="sxs-lookup"><span data-stu-id="c5347-112">In the context of dynamic querying, the provider will usually remain the same; the expression tree of the query will differ from query to query.</span></span>

<span data-ttu-id="c5347-113">Los árboles de expresión son inmutables; si quiere otro árbol de expresión (y, por tanto, otra consulta), tendrá que convertir el existente en uno nuevo y, de este modo, en una nueva interfaz <xref:System.Linq.IQueryable>.</span><span class="sxs-lookup"><span data-stu-id="c5347-113">Expression trees are immutable; if you want a different expression tree&mdash;and thus a different query&mdash;you'll need to translate the existing expression tree to a new one, and thus to a new <xref:System.Linq.IQueryable>.</span></span>

<span data-ttu-id="c5347-114">En las secciones siguientes se describen técnicas específicas para realizar consultas de forma diferente en respuesta al estado del entorno de ejecución:</span><span class="sxs-lookup"><span data-stu-id="c5347-114">The following sections describe specific techniques for querying differently in response to runtime state:</span></span>

- <span data-ttu-id="c5347-115">Uso del estado del entorno de ejecución desde el árbol de expresión</span><span class="sxs-lookup"><span data-stu-id="c5347-115">Use runtime state from within the expression tree</span></span>
- <span data-ttu-id="c5347-116">Llamada a métodos de LINQ adicionales</span><span class="sxs-lookup"><span data-stu-id="c5347-116">Call additional LINQ methods</span></span>
- <span data-ttu-id="c5347-117">Variación del árbol de expresión que se pasa a los métodos de LINQ</span><span class="sxs-lookup"><span data-stu-id="c5347-117">Vary the expression tree passed into the LINQ methods</span></span>
- <span data-ttu-id="c5347-118">Construya un árbol [de expresión de expresión (of TDelegate)](xref:System.Linq.Expressions.Expression%601) mediante los métodos de generador en <xref:System.Linq.Expressions.Expression></span><span class="sxs-lookup"><span data-stu-id="c5347-118">Construct an [Expression(Of TDelegate)](xref:System.Linq.Expressions.Expression%601) expression tree using the factory methods at <xref:System.Linq.Expressions.Expression></span></span>
- <span data-ttu-id="c5347-119">Adición de nodos de llamada de método al árbol de expresión de <xref:System.Linq.IQueryable></span><span class="sxs-lookup"><span data-stu-id="c5347-119">Add method call nodes to an <xref:System.Linq.IQueryable>'s expression tree</span></span>
- <span data-ttu-id="c5347-120">Construcción de cadenas y uso de la [biblioteca dinámica de LINQ](https://dynamic-linq.net/)</span><span class="sxs-lookup"><span data-stu-id="c5347-120">Construct strings, and use the [Dynamic LINQ library](https://dynamic-linq.net/)</span></span>

## <a name="use-runtime-state-from-within-the-expression-tree"></a><span data-ttu-id="c5347-121">Uso del estado del entorno de ejecución desde el árbol de expresión</span><span class="sxs-lookup"><span data-stu-id="c5347-121">Use runtime state from within the expression tree</span></span>

<span data-ttu-id="c5347-122">Siempre que el proveedor LINQ lo admita, la manera más sencilla de realizar consultas dinámicas consiste en hacer referencia al estado del entorno de ejecución de forma directa en la consulta mediante una variable cerrada, como `length` en el ejemplo de código siguiente:</span><span class="sxs-lookup"><span data-stu-id="c5347-122">Assuming the LINQ provider supports it, the simplest way to query dynamically is to reference the runtime state directly in the query via a closed-over variable, such as `length` in the following code example:</span></span>

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Runtime_state_from_within_expression_tree":::

<span data-ttu-id="c5347-123">El árbol de expresión interno (y, por tanto, la consulta) no se ha modificado; la consulta devuelve otros valores solo porque se ha cambiado el valor de `length`.</span><span class="sxs-lookup"><span data-stu-id="c5347-123">The internal expression tree&mdash;and thus the query&mdash;haven't been modified; the query returns different values only because the value of `length` has been changed.</span></span>

## <a name="call-additional-linq-methods"></a><span data-ttu-id="c5347-124">Llamada a métodos de LINQ adicionales</span><span class="sxs-lookup"><span data-stu-id="c5347-124">Call additional LINQ methods</span></span>

<span data-ttu-id="c5347-125">Por lo general, los [métodos de LINQ integrados](https://github.com/dotnet/runtime/blob/main/src/libraries/System.Linq.Queryable/src/System/Linq/Queryable.cs) en <xref:System.Linq.Queryable> realizan dos pasos:</span><span class="sxs-lookup"><span data-stu-id="c5347-125">Generally, the [built-in LINQ methods](https://github.com/dotnet/runtime/blob/main/src/libraries/System.Linq.Queryable/src/System/Linq/Queryable.cs) at <xref:System.Linq.Queryable> perform two steps:</span></span>

* <span data-ttu-id="c5347-126">Encapsulan el árbol de expresión actual en un elemento <xref:System.Linq.Expressions.MethodCallExpression> que representa la llamada de método.</span><span class="sxs-lookup"><span data-stu-id="c5347-126">Wrap the current expression tree in a <xref:System.Linq.Expressions.MethodCallExpression> representing the method call.</span></span>
* <span data-ttu-id="c5347-127">Vuelven a pasar el árbol de expresión encapsulado al proveedor, ya sea para devolver un valor mediante el método <xref:System.Linq.IQueryProvider.Execute%2A?displayProperty=nameWithType> del proveedor, o bien para devolver un objeto de consulta traducido mediante el método <xref:System.Linq.IQueryProvider.CreateQuery%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c5347-127">Pass the wrapped expression tree back to the provider, either to return a value via the provider's <xref:System.Linq.IQueryProvider.Execute%2A?displayProperty=nameWithType> method; or to return a translated query object via the <xref:System.Linq.IQueryProvider.CreateQuery%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="c5347-128">Puede reemplazar la consulta original con el resultado de un método [IQueryable (of T)](xref:System.Linq.IQueryable%601)que devuelve para obtener una nueva consulta.</span><span class="sxs-lookup"><span data-stu-id="c5347-128">You can replace the original query with the result of an [IQueryable(Of T)](xref:System.Linq.IQueryable%601)-returning method, to get a new query.</span></span> <span data-ttu-id="c5347-129">Puede hacerlo condicionalmente en función del estado del entorno de ejecución, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c5347-129">You can do this conditionally based on runtime state, as in the following example:</span></span>

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Added_method_calls":::

## <a name="vary-the-expression-tree-passed-into-the-linq-methods"></a><span data-ttu-id="c5347-130">Variación del árbol de expresión que se pasa a los métodos de LINQ</span><span class="sxs-lookup"><span data-stu-id="c5347-130">Vary the expression tree passed into the LINQ methods</span></span>

<span data-ttu-id="c5347-131">Puede pasar otras expresiones a los métodos de LINQ, en función del estado del entorno de ejecución:</span><span class="sxs-lookup"><span data-stu-id="c5347-131">You can pass in different expressions to the LINQ methods, depending on runtime state:</span></span>

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Varying_expressions":::

<span data-ttu-id="c5347-132">También es posible que quiera crear las distintas subexpresiones mediante una biblioteca de terceros, como [PredicateBuilder](http://www.albahari.com/nutshell/predicatebuilder.aspx) de [LinqKit](http://www.albahari.com/nutshell/linqkit.aspx):</span><span class="sxs-lookup"><span data-stu-id="c5347-132">You might also want to compose the various sub-expressions using a third-party library such as [LinqKit](http://www.albahari.com/nutshell/linqkit.aspx)'s [PredicateBuilder](http://www.albahari.com/nutshell/predicatebuilder.aspx):</span></span>

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Compose_expression":::

## <a name="construct-expression-trees-and-queries-using-factory-methods"></a><span data-ttu-id="c5347-133">Creación de árboles de expresión y consultas mediante métodos de generador</span><span class="sxs-lookup"><span data-stu-id="c5347-133">Construct expression trees and queries using factory methods</span></span>

<span data-ttu-id="c5347-134">En todos los ejemplos vistos hasta ahora, se ha conocido el tipo de elemento en tiempo de compilación `String` y, por tanto, el tipo de la consulta `IQueryable(Of String)`.</span><span class="sxs-lookup"><span data-stu-id="c5347-134">In all the examples up to this point, we've known the element type at compile time&mdash;`String`&mdash;and thus the type of the query&mdash;`IQueryable(Of String)`.</span></span> <span data-ttu-id="c5347-135">Es posible que necesite agregar componentes a una consulta de cualquier tipo de elemento o agregar componentes diferentes en función del tipo de elemento.</span><span class="sxs-lookup"><span data-stu-id="c5347-135">You may need to add components to a query of any element type, or to add different components depending on the element type.</span></span> <span data-ttu-id="c5347-136">Puede crear árboles de expresión desde cero, con los métodos de generador de <xref:System.Linq.Expressions.Expression?displayProperty=fullName> y, por tanto, adaptar la expresión del entorno de ejecución a un tipo de elemento específico.</span><span class="sxs-lookup"><span data-stu-id="c5347-136">You can create expression trees from the ground up, using the factory methods at <xref:System.Linq.Expressions.Expression?displayProperty=fullName>, and thus tailor the expression at runtime to a specific element type.</span></span>

### <a name="constructing-an-expressionof-tdelegate"></a><span data-ttu-id="c5347-137">Construir una [expresión (de TDelegate)](xref:System.Linq.Expressions.Expression%601)</span><span class="sxs-lookup"><span data-stu-id="c5347-137">Constructing an [Expression(Of TDelegate)](xref:System.Linq.Expressions.Expression%601)</span></span>

<span data-ttu-id="c5347-138">Cuando se construye una expresión para pasar a uno de los métodos LINQ, en realidad se construye una instancia de [Expression (of TDelegate)](xref:System.Linq.Expressions.Expression%601), donde `TDelegate` es un tipo de delegado como `Func(Of String, Boolean)` , `Action` o un tipo de delegado personalizado.</span><span class="sxs-lookup"><span data-stu-id="c5347-138">When you construct an expression to pass into one of the LINQ methods, you're actually constructing an instance of [Expression(Of TDelegate)](xref:System.Linq.Expressions.Expression%601), where `TDelegate` is some delegate type such as `Func(Of String, Boolean)`, `Action`, or a custom delegate type.</span></span>

<span data-ttu-id="c5347-139">[Expresión (de TDelegate))](xref:System.Linq.Expressions.Expression%601) hereda de <xref:System.Linq.Expressions.LambdaExpression> , que representa una expresión lambda completa como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="c5347-139">[Expression(Of TDelegate))](xref:System.Linq.Expressions.Expression%601) inherits from <xref:System.Linq.Expressions.LambdaExpression>, which represents a complete lambda expression like the following:</span></span>

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Compiler_generated":::

<span data-ttu-id="c5347-140"><xref:System.Linq.Expressions.LambdaExpression> tiene dos componentes:</span><span class="sxs-lookup"><span data-stu-id="c5347-140">A <xref:System.Linq.Expressions.LambdaExpression> has two components:</span></span>

* <span data-ttu-id="c5347-141">una lista de parámetros `(x As String)` representada por la propiedad <xref:System.Linq.Expressions.LambdaExpression.Parameters>.</span><span class="sxs-lookup"><span data-stu-id="c5347-141">a parameter list&mdash;`(x As String)`&mdash;represented by the <xref:System.Linq.Expressions.LambdaExpression.Parameters> property</span></span>
* <span data-ttu-id="c5347-142">un cuerpo `x.StartsWith("a")` representado por la propiedad <xref:System.Linq.Expressions.LambdaExpression.Body>.</span><span class="sxs-lookup"><span data-stu-id="c5347-142">a body&mdash;`x.StartsWith("a")`&mdash;represented by the <xref:System.Linq.Expressions.LambdaExpression.Body> property.</span></span>

<span data-ttu-id="c5347-143">Los pasos básicos para construir una [expresión (de TDelegate)](xref:System.Linq.Expressions.Expression%601) son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="c5347-143">The basic steps in constructing an [Expression(Of TDelegate)](xref:System.Linq.Expressions.Expression%601) are as follows:</span></span>

* <span data-ttu-id="c5347-144">Defina objetos <xref:System.Linq.Expressions.ParameterExpression> para cada uno de los parámetros (si existen) de la expresión lambda, mediante el método generador <xref:System.Linq.Expressions.Expression.Parameter%2A>.</span><span class="sxs-lookup"><span data-stu-id="c5347-144">Define <xref:System.Linq.Expressions.ParameterExpression> objects for each of the parameters (if any) in the lambda expression, using the <xref:System.Linq.Expressions.Expression.Parameter%2A> factory method.</span></span>

    :::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_method_parameter":::

* <span data-ttu-id="c5347-145">Construya el cuerpo de <xref:System.Linq.Expressions.LambdaExpression> utilizando los valores <xref:System.Linq.Expressions.ParameterExpression> definidos por el usuario y los métodos de generador en <xref:System.Linq.Expressions.Expression>.</span><span class="sxs-lookup"><span data-stu-id="c5347-145">Construct the body of your <xref:System.Linq.Expressions.LambdaExpression>, using the <xref:System.Linq.Expressions.ParameterExpression>(s) you've defined, and the factory methods at <xref:System.Linq.Expressions.Expression>.</span></span> <span data-ttu-id="c5347-146">Por ejemplo, una expresión que represente `x.StartsWith("a")` se podría crear de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="c5347-146">For instance, an expression representing `x.StartsWith("a")` could be constructed like this:</span></span>

    :::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_method_body":::

* <span data-ttu-id="c5347-147">Ajuste los parámetros y el cuerpo en una expresión de tipo en tiempo de compilación [(de TDelegate)](xref:System.Linq.Expressions.Expression%601), con la <xref:System.Linq.Expressions.Expression.Lambda%2A> sobrecarga de Factory Method adecuada:</span><span class="sxs-lookup"><span data-stu-id="c5347-147">Wrap the parameters and body in a compile-time-typed [Expression(Of TDelegate)](xref:System.Linq.Expressions.Expression%601), using the appropriate <xref:System.Linq.Expressions.Expression.Lambda%2A> factory method overload:</span></span>

    :::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_method_lambda":::

<span data-ttu-id="c5347-148">En las secciones siguientes se describe un escenario en el que es posible que desee crear una [expresión (de TDelegate)](xref:System.Linq.Expressions.Expression%601) para pasarla a un método LINQ y proporcionar un ejemplo completo de cómo hacerlo mediante los métodos de generador.</span><span class="sxs-lookup"><span data-stu-id="c5347-148">The following sections describe a scenario in which you might want to construct an [Expression(Of TDelegate)](xref:System.Linq.Expressions.Expression%601) to pass into a LINQ method, and provide a complete example of how to do so using the factory methods.</span></span>

### <a name="scenario"></a><span data-ttu-id="c5347-149">Escenario</span><span class="sxs-lookup"><span data-stu-id="c5347-149">Scenario</span></span>

<span data-ttu-id="c5347-150">Imagine que tiene varios tipos de entidad:</span><span class="sxs-lookup"><span data-stu-id="c5347-150">Let's say you have multiple entity types:</span></span>

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Entities.vb":::

<span data-ttu-id="c5347-151">En cualquiera de estos tipos de entidad, quiere filtrar y devolver solo las entidades que contengan un texto concreto dentro de uno de sus campos `string`.</span><span class="sxs-lookup"><span data-stu-id="c5347-151">For any of these entity types, you want to filter and return only those entities that have a given text inside one of their `string` fields.</span></span> <span data-ttu-id="c5347-152">Para `Person`, le interesa buscar las propiedades `FirstName` y `LastName`:</span><span class="sxs-lookup"><span data-stu-id="c5347-152">For `Person`, you'd want to search the `FirstName` and `LastName` properties:</span></span>

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="PersonsQry":::

<span data-ttu-id="c5347-153">Pero para `Car`, solo quiere buscar la propiedad `Model`:</span><span class="sxs-lookup"><span data-stu-id="c5347-153">but for `Car`, you'd want to search only the `Model` property:</span></span>

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="CarsQry":::

<span data-ttu-id="c5347-154">Aunque podría escribir una función personalizada para `IQueryable(Of Person)` y otra para `IQueryable(Of Car)`, la siguiente función agrega este filtrado a cualquier consulta existente, con independencia del tipo de elemento específico.</span><span class="sxs-lookup"><span data-stu-id="c5347-154">While you could write one custom function for `IQueryable(Of Person)` and another for `IQueryable(Of Car)`, the following function adds this filtering to any existing query, irrespective of the specific element type.</span></span>

### <a name="example"></a><span data-ttu-id="c5347-155">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5347-155">Example</span></span>

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_methods_expression_of_tdelegate":::

<span data-ttu-id="c5347-156">Dado `TextFilter` que la función toma y devuelve un [IQueryable (of T)](xref:System.Linq.IQueryable%601) (y no solo un <xref:System.Linq.IQueryable> ), puede agregar más elementos de consulta con tipo en tiempo de compilación después del filtro de texto.</span><span class="sxs-lookup"><span data-stu-id="c5347-156">Because the `TextFilter` function takes and returns an [IQueryable(Of T)](xref:System.Linq.IQueryable%601) (and not just an <xref:System.Linq.IQueryable>), you can add further compile-time-typed query elements after the text filter.</span></span>

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_methods_expression_of_tdelegate_usage":::

## <a name="add-method-call-nodes-to-the-xrefsystemlinqiqueryables-expression-tree"></a><span data-ttu-id="c5347-157">Adición de nodos de llamada de método al árbol de expresión de <xref:System.Linq.IQueryable></span><span class="sxs-lookup"><span data-stu-id="c5347-157">Add method call nodes to the <xref:System.Linq.IQueryable>'s expression tree</span></span>

<span data-ttu-id="c5347-158">Si tiene <xref:System.Linq.IQueryable> en lugar de [IQueryable (of T)](xref:System.Linq.IQueryable%601), no puede llamar directamente a los métodos LINQ genéricos.</span><span class="sxs-lookup"><span data-stu-id="c5347-158">If you have an <xref:System.Linq.IQueryable> instead of an [IQueryable(Of T)](xref:System.Linq.IQueryable%601), you can't directly call the generic LINQ methods.</span></span> <span data-ttu-id="c5347-159">Una alternativa consiste en crear el árbol de expresión interno como se ha indicado antes y usar la reflexión para invocar el método de LINQ adecuado mientras se pasa el árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="c5347-159">One alternative is to build the inner expression tree as above, and use reflection to invoke the appropriate LINQ method while passing in the expression tree.</span></span>

<span data-ttu-id="c5347-160">También puede duplicar la funcionalidad del método de LINQ y encapsular todo el árbol en un objeto <xref:System.Linq.Expressions.MethodCallExpression> que represente una llamada al método de LINQ:</span><span class="sxs-lookup"><span data-stu-id="c5347-160">You could also duplicate the LINQ method's functionality, by wrapping the entire tree in a <xref:System.Linq.Expressions.MethodCallExpression> which represents a call to the LINQ method:</span></span>

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_methods_lambdaexpression":::

<span data-ttu-id="c5347-161">Tenga en cuenta que en este caso no tiene un marcador de posición genérico en tiempo de compilación `T` , por lo que usará la <xref:System.Linq.Expressions.Expression.Lambda%2A> sobrecarga, que no requiere información de tipo en tiempo de compilación, y que genera un <xref:System.Linq.Expressions.LambdaExpression> en lugar de una [expresión (de TDelegate)](xref:System.Linq.Expressions.Expression%601).</span><span class="sxs-lookup"><span data-stu-id="c5347-161">Note that in this case you don't have a compile-time `T` generic placeholder, so you'll use the <xref:System.Linq.Expressions.Expression.Lambda%2A> overload which doesn't require compile-time type information, and which produces a <xref:System.Linq.Expressions.LambdaExpression> instead of an an [Expression(Of TDelegate)](xref:System.Linq.Expressions.Expression%601).</span></span>

## <a name="the-dynamic-linq-library"></a><span data-ttu-id="c5347-162">Biblioteca dinámica de LINQ</span><span class="sxs-lookup"><span data-stu-id="c5347-162">The Dynamic LINQ library</span></span>

<span data-ttu-id="c5347-163">La creación de árboles de expresión mediante métodos de generador es relativamente compleja; es más fácil crear cadenas.</span><span class="sxs-lookup"><span data-stu-id="c5347-163">Constructing expression trees using factory methods is relatively complex; it is easier to compose strings.</span></span> <span data-ttu-id="c5347-164">La [biblioteca dinámica de LINQ](https://dynamic-linq.net/) expone un conjunto de métodos de extensión en <xref:System.Linq.IQueryable> correspondiente a los métodos estándar de LINQ en <xref:System.Linq.Queryable> y que aceptan cadenas en una [sintaxis especial](https://dynamic-linq.net/expression-language) en lugar de árboles de expresión.</span><span class="sxs-lookup"><span data-stu-id="c5347-164">The [Dynamic LINQ library](https://dynamic-linq.net/) exposes a set of extension methods on <xref:System.Linq.IQueryable> corresponding to the standard LINQ methods at <xref:System.Linq.Queryable>, and which accept strings in a [special syntax](https://dynamic-linq.net/expression-language) instead of expression trees.</span></span> <span data-ttu-id="c5347-165">La biblioteca genera el árbol de expresión adecuado a partir de la cadena y puede devolver la interfaz <xref:System.Linq.IQueryable> traducida resultante.</span><span class="sxs-lookup"><span data-stu-id="c5347-165">The library generates the appropriate expression tree from the string, and can return the resultant translated <xref:System.Linq.IQueryable>.</span></span>

<span data-ttu-id="c5347-166">Por ejemplo, el ejemplo anterior (incluida la construcción del árbol de expresión) se podría volver a escribir de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="c5347-166">For instance, the previous example (including the expression tree construction) could be rewritten as follows:</span></span>

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Dynamic_linq":::

## <a name="see-also"></a><span data-ttu-id="c5347-167">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c5347-167">See also</span></span>

- [<span data-ttu-id="c5347-168">Árboles de expresión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5347-168">Expression Trees (Visual Basic)</span></span>](index.md)
- <span data-ttu-id="c5347-169">[How to: Execute Expression Trees (Visual Basic)](how-to-execute-expression-trees.md) (Cómo ejecutar árboles de expresión en Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5347-169">[How to: Execute Expression Trees (Visual Basic)](how-to-execute-expression-trees.md)</span></span>
