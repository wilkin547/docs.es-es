---
title: Escribir consultas LINQ en C#
description: "Cómo escribir consultas."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 30703f79-cf3a-4d02-b892-c95d58a1d9ed
ms.openlocfilehash: f3efbfd232bd7e19d3db56289f57724c71dca064
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="write-linq-queries-in-c"></a><span data-ttu-id="e0549-104">Escribir consultas LINQ en C#</span><span class="sxs-lookup"><span data-stu-id="e0549-104">Write LINQ queries in C#</span></span>

<span data-ttu-id="e0549-105">Este tema muestra las tres formas de escribir una consulta LINQ en C#:</span><span class="sxs-lookup"><span data-stu-id="e0549-105">This topic shows the three ways in which you can write a LINQ query in C#:</span></span>  
  
1.  <span data-ttu-id="e0549-106">Usar sintaxis de consulta.</span><span class="sxs-lookup"><span data-stu-id="e0549-106">Use query syntax.</span></span>  
  
2.  <span data-ttu-id="e0549-107">Usar sintaxis de método.</span><span class="sxs-lookup"><span data-stu-id="e0549-107">Use method syntax.</span></span>  
  
3.  <span data-ttu-id="e0549-108">Usar una combinación de sintaxis de consulta y sintaxis de método.</span><span class="sxs-lookup"><span data-stu-id="e0549-108">Use a combination of query syntax and method syntax.</span></span>  
  
 <span data-ttu-id="e0549-109">Los ejemplos siguientes muestran algunas consultas LINQ sencillas mediante cada enfoque enumerado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e0549-109">The following examples demonstrate some simple LINQ queries by using each approach listed previously.</span></span> <span data-ttu-id="e0549-110">En general, la regla es usar (1) siempre que sea posible y usar (2) y (3) cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="e0549-110">In general, the rule is to use (1) whenever possible, and use (2) and (3) whenever necessary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0549-111">Estas consultas funcionan en colecciones en memoria simples, pero la sintaxis básica es idéntica a la empleada en LINQ to Entities y LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="e0549-111">These queries operate on simple in-memory collections; however, the basic syntax is identical to that used in LINQ to Entities and LINQ to XML.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0549-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e0549-112">Example</span></span>  
  
## <a name="query-syntax"></a><span data-ttu-id="e0549-113">Sintaxis de consulta</span><span class="sxs-lookup"><span data-stu-id="e0549-113">Query syntax</span></span>  
 <span data-ttu-id="e0549-114">La manera recomendada de escribir la mayoría de las consultas es usar *sintaxis de consulta* para crear *expresiones de consulta*.</span><span class="sxs-lookup"><span data-stu-id="e0549-114">The recommended way to write most queries is to use *query syntax* to create *query expressions*.</span></span> <span data-ttu-id="e0549-115">En el siguiente ejemplo se muestran tres expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="e0549-115">The following example shows three query expressions.</span></span> <span data-ttu-id="e0549-116">La primera expresión de consulta muestra cómo filtrar o restringir los resultados mediante la aplicación de condiciones con una cláusula `where`.</span><span class="sxs-lookup"><span data-stu-id="e0549-116">The first query expression demonstrates how to filter or restrict results by applying conditions with a `where` clause.</span></span> <span data-ttu-id="e0549-117">Devuelve todos los elementos de la secuencia de origen cuyos valores sean mayores que 7 o menores que 3.</span><span class="sxs-lookup"><span data-stu-id="e0549-117">It returns all elements in the source sequence whose values are greater than 7 or less than 3.</span></span> <span data-ttu-id="e0549-118">La segunda expresión muestra cómo ordenar los resultados devueltos.</span><span class="sxs-lookup"><span data-stu-id="e0549-118">The second expression demonstrates how to order the returned results.</span></span> <span data-ttu-id="e0549-119">La tercera expresión muestra cómo agrupar los resultados según una clave.</span><span class="sxs-lookup"><span data-stu-id="e0549-119">The third expression demonstrates how to group results according to a key.</span></span> <span data-ttu-id="e0549-120">Esta consulta devuelve dos grupos en función de la primera letra de la palabra.</span><span class="sxs-lookup"><span data-stu-id="e0549-120">This query returns two groups based on the first letter of the word.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#5](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_1.cs)]  
  
 <span data-ttu-id="e0549-121">Tenga en cuenta que el tipo de las consultas es <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="e0549-121">Note that the type of the queries is <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="e0549-122">Todas estas consultas podrían escribirse mediante `var` como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e0549-122">All of these queries could be written using `var` as shown in the following example:</span></span>  
  
 `var query = from num in numbers...`  
  
 <span data-ttu-id="e0549-123">En cada ejemplo anterior, las consultas no se ejecutan realmente hasta que se recorre en iteración la variable de consulta en una instrucción `foreach` o cualquier otra instrucción.</span><span class="sxs-lookup"><span data-stu-id="e0549-123">In each previous example, the queries do not actually execute until you iterate over the query variable in a `foreach` statement or other statement.</span></span> <span data-ttu-id="e0549-124">Para más información, vea [Introduction to LINQ Queries (Introducción a las consultas LINQ)](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e0549-124">For more information, see [Introduction to LINQ Queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0549-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e0549-125">Example</span></span>  
  
## <a name="method-syntax"></a><span data-ttu-id="e0549-126">Sintaxis de método</span><span class="sxs-lookup"><span data-stu-id="e0549-126">Method syntax</span></span>  
 <span data-ttu-id="e0549-127">Algunas operaciones de consulta deben expresarse como una llamada a método.</span><span class="sxs-lookup"><span data-stu-id="e0549-127">Some query operations must be expressed as a method call.</span></span> <span data-ttu-id="e0549-128">Los más comunes de dichos métodos son los que devuelven valores numéricos de singleton, como <xref:System.Linq.Enumerable.Sum%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, <xref:System.Linq.Enumerable.Average%2A> y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="e0549-128">The most common such methods are those that return singleton numeric values, such as <xref:System.Linq.Enumerable.Sum%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, <xref:System.Linq.Enumerable.Average%2A>, and so on.</span></span> <span data-ttu-id="e0549-129">A estos métodos siempre se los debe llamar en último lugar en cualquier consulta porque representan un solo valor y no pueden servir como origen para una operación de consulta adicional.</span><span class="sxs-lookup"><span data-stu-id="e0549-129">These methods must always be called last in any query because they represent only a single value and cannot serve as the source for an additional query operation.</span></span> <span data-ttu-id="e0549-130">En el ejemplo siguiente se muestra una llamada a método en una expresión de consulta:</span><span class="sxs-lookup"><span data-stu-id="e0549-130">The following example shows a method call in a query expression:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#6](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="e0549-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e0549-131">Example</span></span>  
 <span data-ttu-id="e0549-132">Si el método tiene parámetros Action o Func, se proporcionan en forma de expresión [lambda](../programming-guide/statements-expressions-operators/lambda-expressions.md), como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e0549-132">If the method has  Action or Func parameters, these are provided in the form of a [lambda](../programming-guide/statements-expressions-operators/lambda-expressions.md) expression, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#7](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_3.cs)]  
  
 <span data-ttu-id="e0549-133">En las consultas anteriores, solo la número 4 se ejecuta inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="e0549-133">In the previous queries, only Query #4 executes immediately.</span></span> <span data-ttu-id="e0549-134">Esto se debe a que devuelve un valor único, y no una colección <xref:System.Collections.Generic.IEnumerable%601> genérica.</span><span class="sxs-lookup"><span data-stu-id="e0549-134">This is because it returns a single value, and not a generic <xref:System.Collections.Generic.IEnumerable%601> collection.</span></span> <span data-ttu-id="e0549-135">El propio método tiene que usar `foreach` para calcular su valor.</span><span class="sxs-lookup"><span data-stu-id="e0549-135">The method itself has to use `foreach` in order to compute its value.</span></span>  
  
 <span data-ttu-id="e0549-136">Cada una de las consultas anteriores puede escribirse mediante tipos implícitos con [var](../language-reference/keywords/var.md), como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e0549-136">Each of the previous queries can be written by using implicit typing with [var](../language-reference/keywords/var.md), as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#8](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_4.cs)]  
  
## <a name="example"></a><span data-ttu-id="e0549-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e0549-137">Example</span></span>  
  
## <a name="mixed-query-and-method-syntax"></a><span data-ttu-id="e0549-138">Sintaxis de consulta y método combinadas</span><span class="sxs-lookup"><span data-stu-id="e0549-138">Mixed query and method syntax</span></span>  
 <span data-ttu-id="e0549-139">En este ejemplo se muestra cómo usar la sintaxis de método en los resultados de una cláusula de consulta.</span><span class="sxs-lookup"><span data-stu-id="e0549-139">This example shows how to use method syntax on the results of a query clause.</span></span> <span data-ttu-id="e0549-140">Simplemente escriba entre paréntesis la expresión de consulta y luego aplique el operador punto y llame al método.</span><span class="sxs-lookup"><span data-stu-id="e0549-140">Just enclose the query expression in parentheses, and then apply the dot operator and call the method.</span></span> <span data-ttu-id="e0549-141">En el ejemplo siguiente la consulta número 7 devuelve un recuento de los números cuyo valor está comprendido entre 3 y 7.</span><span class="sxs-lookup"><span data-stu-id="e0549-141">In the following example, query #7 returns a count of the numbers whose value is between 3 and 7.</span></span> <span data-ttu-id="e0549-142">Pero en general es mejor usar una segunda variable para almacenar el resultado de la llamada a método.</span><span class="sxs-lookup"><span data-stu-id="e0549-142">In general, however, it is better to use a second variable to store the result of the method call.</span></span> <span data-ttu-id="e0549-143">De esta manera es menos probable que la consulta se confunda con los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="e0549-143">In this manner, the query is less likely to be confused with the results of the query.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#9](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_5.cs)]  
  
 <span data-ttu-id="e0549-144">Dado que la consulta número 7 devuelve un solo valor y no una colección, se ejecuta inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="e0549-144">Because Query #7 returns a single value and not a collection, the query executes immediately.</span></span>  
  
 <span data-ttu-id="e0549-145">La consulta anterior puede escribirse mediante tipos implícitos con `var` como sigue:</span><span class="sxs-lookup"><span data-stu-id="e0549-145">The previous query can be written by using implicit typing with `var`, as follows:</span></span>  
  
```csharp  
var numCount = (from num in numbers...  
```  
  
 <span data-ttu-id="e0549-146">Puede escribirse en sintaxis de método como sigue:</span><span class="sxs-lookup"><span data-stu-id="e0549-146">It can be written in method syntax as follows:</span></span>  
  
```csharp  
var numCount = numbers.Where(n => n < 3 || n > 7).Count();  
```  
  
 <span data-ttu-id="e0549-147">Puede escribirse mediante tipos explícitos como sigue:</span><span class="sxs-lookup"><span data-stu-id="e0549-147">It can be written by using explicit typing, as follows:</span></span>  
  
```csharp  
int numCount = numbers.Where(n => n < 3 || n > 7).Count();  
```  
  
## <a name="see-also"></a><span data-ttu-id="e0549-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0549-148">See Also</span></span>  
  <span data-ttu-id="e0549-149">[Tutorial: Escribir consultas en C#](../programming-guide/concepts/linq/walkthrough-writing-queries-linq.md) </span><span class="sxs-lookup"><span data-stu-id="e0549-149">[Walkthrough: Writing Queries in C#](../programming-guide/concepts/linq/walkthrough-writing-queries-linq.md) </span></span>  
 [<span data-ttu-id="e0549-150">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="e0549-150">LINQ Query Expressions</span></span>](index.md)  
 [<span data-ttu-id="e0549-151">where (cláusula)</span><span class="sxs-lookup"><span data-stu-id="e0549-151">where clause</span></span>](../language-reference/keywords/where-clause.md)
