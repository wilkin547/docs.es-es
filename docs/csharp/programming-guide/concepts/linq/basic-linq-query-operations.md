---
title: Operaciones básicas de consulta LINQ (C#)
description: Descubra las expresiones de consulta LINQ y algunas de las operaciones que puede realizar en una consulta.
ms.date: 07/20/2015
helpviewer_keywords:
- orderby clause [LINQ in C#]
- ordering data [LINQ in C#]
- selecting data [LINQ in C#]
- queries [LINQ in C#], basic operations
- grouping data [LINQ in C#]
- data sources [LINQ in C#]
- sorting data [LINQ in C#]
- projections [LINQ in C#]
- filtering data [LINQ in C#]
- joining data [LINQ in C#]
- select clause [LINQ in C#]
- LINQ [C#], basic query operations
- join clause [LINQ in C#]
- group clause [LINQ in C#]
ms.assetid: a7ea3421-1cf4-4df7-832a-aa22fe6379e9
ms.openlocfilehash: 9f5d39e396e9be3e633326d4034a89d874373d75
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91159298"
---
# <a name="basic-linq-query-operations-c"></a><span data-ttu-id="ff0cd-103">Operaciones básicas de consulta LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="ff0cd-103">Basic LINQ Query Operations (C#)</span></span>

<span data-ttu-id="ff0cd-104">En este tema se ofrece una breve introducción a las expresiones de consulta LINQ y algunas de las clases de operaciones típicas que se realizan en una consulta.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-104">This topic gives a brief introduction to LINQ query expressions and some of the typical kinds of operations that you perform in a query.</span></span> <span data-ttu-id="ff0cd-105">En los temas siguientes se ofrece información más detallada:</span><span class="sxs-lookup"><span data-stu-id="ff0cd-105">More detailed information is in the following topics:</span></span>  
  
 [<span data-ttu-id="ff0cd-106">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="ff0cd-106">LINQ Query Expressions</span></span>](../../../linq/index.md)  
  
 [<span data-ttu-id="ff0cd-107">Información general sobre operadores de consulta estándar (C#)</span><span class="sxs-lookup"><span data-stu-id="ff0cd-107">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)  
  
 [<span data-ttu-id="ff0cd-108">Tutorial: Creación de consultas en C#</span><span class="sxs-lookup"><span data-stu-id="ff0cd-108">Walkthrough: Writing Queries in C#</span></span>](./walkthrough-writing-queries-linq.md)  
  
> [!NOTE]
> <span data-ttu-id="ff0cd-109">Si ya está familiarizado con un lenguaje de consultas como SQL o XQuery, puede omitir la mayoría de este tema.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-109">If you already are familiar with a query language such as SQL or XQuery, you can skip most of this topic.</span></span> <span data-ttu-id="ff0cd-110">Lea la parte dedicada a la "cláusula `from`" en la sección siguiente para obtener información sobre el orden de las cláusulas en las expresiones de consulta LINQ.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-110">Read about the "`from` clause" in the next section to learn about the order of clauses in LINQ query expressions.</span></span>  
  
## <a name="obtaining-a-data-source"></a><span data-ttu-id="ff0cd-111">Obtener un origen de datos</span><span class="sxs-lookup"><span data-stu-id="ff0cd-111">Obtaining a Data Source</span></span>  

 <span data-ttu-id="ff0cd-112">En una consulta LINQ, el primer paso es especificar el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-112">In a LINQ query, the first step is to specify the data source.</span></span> <span data-ttu-id="ff0cd-113">En C#, como en la mayoría de los lenguajes de programación, se debe declarar una variable antes de poder usarla.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-113">In C# as in most programming languages a variable must be declared before it can be used.</span></span> <span data-ttu-id="ff0cd-114">En una consulta LINQ, la cláusula `from` aparece en primer lugar para introducir el origen de datos (`customers`) y la *variable de rango* (`cust`).</span><span class="sxs-lookup"><span data-stu-id="ff0cd-114">In a LINQ query, the `from` clause comes first in order to introduce the data source (`customers`) and the *range variable* (`cust`).</span></span>  
  
 [!code-csharp[csLINQGettingStarted#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#23)]  
  
 <span data-ttu-id="ff0cd-115">La variable de rango es como la variable de iteración en un bucle `foreach`, con la diferencia de que en una expresión de consulta realmente no se produce ninguna iteración.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-115">The range variable is like the iteration variable in a `foreach` loop except that no actual iteration occurs in a query expression.</span></span> <span data-ttu-id="ff0cd-116">Cuando se ejecuta la consulta, la variable de rango actúa como referencia para cada elemento sucesivo de `customers`.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-116">When the query is executed, the range variable will serve as a reference to each successive element in `customers`.</span></span> <span data-ttu-id="ff0cd-117">Dado que el compilador puede deducir el tipo de `cust`, no tiene que especificarlo explícitamente.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-117">Because the compiler can infer the type of `cust`, you do not have to specify it explicitly.</span></span> <span data-ttu-id="ff0cd-118">Una cláusula `let` puede introducir variables de rango adicionales.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-118">Additional range variables can be introduced by a `let` clause.</span></span> <span data-ttu-id="ff0cd-119">Para obtener más información, vea [let (Cláusula)](../../../language-reference/keywords/let-clause.md).</span><span class="sxs-lookup"><span data-stu-id="ff0cd-119">For more information, see [let clause](../../../language-reference/keywords/let-clause.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ff0cd-120">Para los orígenes de datos no genéricos, como <xref:System.Collections.ArrayList>, el tipo de la variable de rango debe establecerse explícitamente.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-120">For non-generic data sources such as <xref:System.Collections.ArrayList>, the range variable must be explicitly typed.</span></span> <span data-ttu-id="ff0cd-121">Para más información, consulte el [procedimiento para consultar un objeto ArrayList con LINQ (C#)](./how-to-query-an-arraylist-with-linq.md) y [Cláusula from](../../../language-reference/keywords/from-clause.md).</span><span class="sxs-lookup"><span data-stu-id="ff0cd-121">For more information, see [How to query an ArrayList with LINQ (C#)](./how-to-query-an-arraylist-with-linq.md) and [from clause](../../../language-reference/keywords/from-clause.md).</span></span>  
  
## <a name="filtering"></a><span data-ttu-id="ff0cd-122">Filtrado</span><span class="sxs-lookup"><span data-stu-id="ff0cd-122">Filtering</span></span>  

 <span data-ttu-id="ff0cd-123">Probablemente la operación de consulta más común es aplicar un filtro en forma de expresión booleana.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-123">Probably the most common query operation is to apply a filter in the form of a Boolean expression.</span></span> <span data-ttu-id="ff0cd-124">El filtro hace que la consulta devuelva solo los elementos para los que la expresión es verdadera.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-124">The filter causes the query to return only those elements for which the expression is true.</span></span> <span data-ttu-id="ff0cd-125">El resultado se genera mediante la cláusula `where`.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-125">The result is produced by using the `where` clause.</span></span> <span data-ttu-id="ff0cd-126">El filtro aplicado especifica qué elementos se deben excluir de la secuencia de origen.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-126">The filter in effect specifies which elements to exclude from the source sequence.</span></span> <span data-ttu-id="ff0cd-127">En el ejemplo siguiente, solo se devuelven los `customers` cuya dirección se encuentra en Londres.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-127">In the following example, only those `customers` who have an address in London are returned.</span></span>  
  
 [!code-csharp[csLINQGettingStarted#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#24)]  
  
 <span data-ttu-id="ff0cd-128">Puede usar los operadores lógicos `AND` y `OR` de C#, con los que ya estará familiarizado, para aplicar las expresiones de filtro que sean necesarias en la cláusula `where`.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-128">You can use the familiar C# logical `AND` and `OR` operators to apply as many filter expressions as necessary in the `where` clause.</span></span> <span data-ttu-id="ff0cd-129">Por ejemplo, para devolver solo los clientes con dirección en "London" `AND` cuyo nombre sea "Devon", escribiría el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="ff0cd-129">For example, to return only customers from "London" `AND` whose name is "Devon" you would write the following code:</span></span>  
  
 [!code-csharp[csLINQGettingStarted#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#25)]  
  
 <span data-ttu-id="ff0cd-130">Para devolver los clientes con dirección en Londres o París, escribiría el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="ff0cd-130">To return customers from London or Paris, you would write the following code:</span></span>  
  
 [!code-csharp[csLINQGettingStarted#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#26)]  
  
 <span data-ttu-id="ff0cd-131">Para obtener más información, vea [where (Cláusula)](../../../language-reference/keywords/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="ff0cd-131">For more information, see [where clause](../../../language-reference/keywords/where-clause.md).</span></span>  
  
## <a name="ordering"></a><span data-ttu-id="ff0cd-132">Ordenación</span><span class="sxs-lookup"><span data-stu-id="ff0cd-132">Ordering</span></span>  

 <span data-ttu-id="ff0cd-133">A menudo es necesario ordenar los datos devueltos.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-133">Often it is convenient to sort the returned data.</span></span> <span data-ttu-id="ff0cd-134">La cláusula `orderby` hará que los elementos de la secuencia devuelta se ordenen según el comparador predeterminado del tipo que se va a ordenar.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-134">The `orderby` clause will cause the elements in the returned sequence to be sorted according to the default comparer for the type being sorted.</span></span> <span data-ttu-id="ff0cd-135">Por ejemplo, la consulta siguiente se puede extender para ordenar los resultados según la propiedad `Name`.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-135">For example, the following query can be extended to sort the results based on the `Name` property.</span></span> <span data-ttu-id="ff0cd-136">Dado que `Name` es una cadena, el comparador predeterminado realiza una ordenación alfabética de la A a la Z.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-136">Because `Name` is a string, the default comparer performs an alphabetical sort from A to Z.</span></span>  
  
 [!code-csharp[csLINQGettingStarted#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#27)]  
  
 <span data-ttu-id="ff0cd-137">Para ordenar los resultados en orden inverso, de la Z a la A, use la cláusula `orderby…descending`.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-137">To order the results in reverse order, from Z to A, use the `orderby…descending` clause.</span></span>  
  
 <span data-ttu-id="ff0cd-138">Para obtener más información, vea [orderby (Cláusula)](../../../language-reference/keywords/orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="ff0cd-138">For more information, see [orderby clause](../../../language-reference/keywords/orderby-clause.md).</span></span>  
  
## <a name="grouping"></a><span data-ttu-id="ff0cd-139">Agrupar</span><span class="sxs-lookup"><span data-stu-id="ff0cd-139">Grouping</span></span>  

 <span data-ttu-id="ff0cd-140">La cláusula `group` permite agrupar los resultados según la clave que se especifique.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-140">The `group` clause enables you to group your results based on a key that you specify.</span></span> <span data-ttu-id="ff0cd-141">Por ejemplo, podría especificar que los resultados se agrupen por `City` para que todos los clientes de London o París estén en grupos individuales.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-141">For example you could specify that the results should be grouped by the `City` so that all customers from London or Paris are in individual groups.</span></span> <span data-ttu-id="ff0cd-142">En este caso, la clave es `cust.City`.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-142">In this case, `cust.City` is the key.</span></span>  
  
 [!code-csharp[csLINQGettingStarted#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#28)]  
  
 <span data-ttu-id="ff0cd-143">Al finalizar una consulta con una cláusula `group`, los resultados adoptan la forma de una lista de listas.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-143">When you end a query with a `group` clause, your results take the form of a list of lists.</span></span> <span data-ttu-id="ff0cd-144">Cada elemento de la lista es un objeto que tiene un miembro `Key` y una lista de elementos agrupados bajo esa clave.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-144">Each element in the list is an object that has a `Key` member and a list of elements that are grouped under that key.</span></span> <span data-ttu-id="ff0cd-145">Al procesar una iteración en una consulta que genera una secuencia de grupos, debe usar un bucle `foreach` anidado.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-145">When you iterate over a query that produces a sequence of groups, you must use a nested `foreach` loop.</span></span> <span data-ttu-id="ff0cd-146">El bucle exterior recorre en iteración cada grupo y el bucle interior recorre en iteración los miembros de cada grupo.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-146">The outer loop iterates over each group, and the inner loop iterates over each group's members.</span></span>  
  
 <span data-ttu-id="ff0cd-147">Si debe hacer referencia a los resultados de una operación de grupo, puede usar la palabra clave `into` para crear un identificador con el que se puedan realizar más consultas.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-147">If you must refer to the results of a group operation, you can use the `into` keyword to create an identifier that can be queried further.</span></span> <span data-ttu-id="ff0cd-148">La consulta siguiente devuelve solo los grupos que contienen más de dos clientes:</span><span class="sxs-lookup"><span data-stu-id="ff0cd-148">The following query returns only those groups that contain more than two customers:</span></span>  
  
 [!code-csharp[csLINQGettingStarted#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#29)]  
  
 <span data-ttu-id="ff0cd-149">Para obtener más información, vea [group (Cláusula)](../../../language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="ff0cd-149">For more information, see [group clause](../../../language-reference/keywords/group-clause.md).</span></span>  
  
## <a name="joining"></a><span data-ttu-id="ff0cd-150">Combinación</span><span class="sxs-lookup"><span data-stu-id="ff0cd-150">Joining</span></span>  

 <span data-ttu-id="ff0cd-151">Las operaciones de combinación crean asociaciones entre las secuencias que no se modelan explícitamente en los orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-151">Join operations create associations between sequences that are not explicitly modeled in the data sources.</span></span> <span data-ttu-id="ff0cd-152">Por ejemplo, puede realizar una combinación para buscar todos los clientes y distribuidores que tengan la misma ubicación.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-152">For example you can perform a join to find all the customers and distributors who have the same location.</span></span> <span data-ttu-id="ff0cd-153">En LINQ, la cláusula `join` funciona siempre con colecciones de objetos, en lugar de con tablas de base de datos directamente.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-153">In LINQ the `join` clause always works against object collections instead of database tables directly.</span></span>  
  
 [!code-csharp[csLINQGettingStarted#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#36)]  
  
 <span data-ttu-id="ff0cd-154">En LINQ no es necesario usar `join` tan a menudo como en SQL, porque las claves externas en LINQ se representan en el modelo de objetos como propiedades que contienen una colección de elementos.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-154">In LINQ, you do not have to use `join` as often as you do in SQL, because foreign keys in LINQ are represented in the object model as properties that hold a collection of items.</span></span> <span data-ttu-id="ff0cd-155">Por ejemplo, un objeto `Customer` contiene una colección de objetos `Order`.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-155">For example, a `Customer` object contains a collection of `Order` objects.</span></span> <span data-ttu-id="ff0cd-156">En lugar de realizar una combinación, tiene acceso a los pedidos usando la notación de punto:</span><span class="sxs-lookup"><span data-stu-id="ff0cd-156">Rather than performing a join, you access the orders by using dot notation:</span></span>  
  
```csharp
from order in Customer.Orders...  
```  
  
 <span data-ttu-id="ff0cd-157">Para obtener más información, vea [join (Cláusula, Referencia de C#)](../../../language-reference/keywords/join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="ff0cd-157">For more information, see [join clause](../../../language-reference/keywords/join-clause.md).</span></span>  
  
## <a name="selecting-projections"></a><span data-ttu-id="ff0cd-158">Selección (proyecciones)</span><span class="sxs-lookup"><span data-stu-id="ff0cd-158">Selecting (Projections)</span></span>  

 <span data-ttu-id="ff0cd-159">La cláusula `select` genera resultados de consulta y especifica la "forma" o el tipo de cada elemento devuelto.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-159">The `select` clause produces the results of the query and specifies the "shape" or type of each returned element.</span></span> <span data-ttu-id="ff0cd-160">Por ejemplo, puede especificar si sus resultados estarán compuestos de objetos `Customer` completos, un solo miembro, un subconjunto de miembros o algún tipo de resultado completamente diferente basado en un cálculo o en un objeto nuevo.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-160">For example, you can specify whether your results will consist of complete `Customer` objects, just one member, a subset of members, or some completely different result type based on a computation or new object creation.</span></span> <span data-ttu-id="ff0cd-161">Cuando la cláusula `select` genera algo distinto de una copia del elemento de origen, la operación se denomina *proyección*.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-161">When the `select` clause produces something other than a copy of the source element, the operation is called a *projection*.</span></span> <span data-ttu-id="ff0cd-162">El uso de proyecciones para transformar los datos es una función eficaz de las expresiones de consulta LINQ.</span><span class="sxs-lookup"><span data-stu-id="ff0cd-162">The use of projections to transform data is a powerful capability of LINQ query expressions.</span></span> <span data-ttu-id="ff0cd-163">Para obtener más información, vea [Transformaciones de datos con LINQ (C#)](./data-transformations-with-linq.md) y [select (cláusula)](../../../language-reference/keywords/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="ff0cd-163">For more information, see [Data Transformations with LINQ (C#)](./data-transformations-with-linq.md) and [select clause](../../../language-reference/keywords/select-clause.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff0cd-164">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ff0cd-164">See also</span></span>

- [<span data-ttu-id="ff0cd-165">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="ff0cd-165">LINQ Query Expressions</span></span>](../../../linq/index.md)
- [<span data-ttu-id="ff0cd-166">Tutorial: Creación de consultas en C#</span><span class="sxs-lookup"><span data-stu-id="ff0cd-166">Walkthrough: Writing Queries in C#</span></span>](./walkthrough-writing-queries-linq.md)
- [<span data-ttu-id="ff0cd-167">Palabras clave para consultas (LINQ)</span><span class="sxs-lookup"><span data-stu-id="ff0cd-167">Query Keywords (LINQ)</span></span>](../../../language-reference/keywords/query-keywords.md)
- [<span data-ttu-id="ff0cd-168">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="ff0cd-168">Anonymous Types</span></span>](../../classes-and-structs/anonymous-types.md)
