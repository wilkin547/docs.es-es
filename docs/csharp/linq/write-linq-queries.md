---
title: Escribir consultas LINQ en C#
description: Obtenga información sobre cómo escribir consultas de LINQ en C#.
ms.date: 12/01/2016
ms.assetid: 30703f79-cf3a-4d02-b892-c95d58a1d9ed
ms.openlocfilehash: ed32543b0422e0664a8577f2c27f7c7c00a719a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "65632870"
---
# <a name="write-linq-queries-in-c"></a><span data-ttu-id="5e727-103">Escribir consultas LINQ en C\#</span><span class="sxs-lookup"><span data-stu-id="5e727-103">Write LINQ queries in C\#</span></span>

<span data-ttu-id="5e727-104">En este artículo se muestran las tres formas de escribir una consulta LINQ en C#:</span><span class="sxs-lookup"><span data-stu-id="5e727-104">This article shows the three ways in which you can write a LINQ query in C#:</span></span>

1. <span data-ttu-id="5e727-105">Usar sintaxis de consulta.</span><span class="sxs-lookup"><span data-stu-id="5e727-105">Use query syntax.</span></span>

2. <span data-ttu-id="5e727-106">Usar sintaxis de método.</span><span class="sxs-lookup"><span data-stu-id="5e727-106">Use method syntax.</span></span>

3. <span data-ttu-id="5e727-107">Usar una combinación de sintaxis de consulta y sintaxis de método.</span><span class="sxs-lookup"><span data-stu-id="5e727-107">Use a combination of query syntax and method syntax.</span></span>

<span data-ttu-id="5e727-108">Los ejemplos siguientes muestran algunas consultas LINQ sencillas mediante cada enfoque enumerado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="5e727-108">The following examples demonstrate some simple LINQ queries by using each approach listed previously.</span></span> <span data-ttu-id="5e727-109">En general, la regla es usar (1) siempre que sea posible y usar (2) y (3) cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="5e727-109">In general, the rule is to use (1) whenever possible, and use (2) and (3) whenever necessary.</span></span>

> [!NOTE]
> <span data-ttu-id="5e727-110">Estas consultas funcionan en colecciones en memoria simples, pero la sintaxis básica es idéntica a la empleada en LINQ to Entities y LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="5e727-110">These queries operate on simple in-memory collections; however, the basic syntax is identical to that used in LINQ to Entities and LINQ to XML.</span></span>

## <a name="example---query-syntax"></a><span data-ttu-id="5e727-111">Ejemplo: Sintaxis de consulta</span><span class="sxs-lookup"><span data-stu-id="5e727-111">Example - Query syntax</span></span>

<span data-ttu-id="5e727-112">La manera recomendada de escribir la mayoría de las consultas es usar *sintaxis de consulta* para crear *expresiones de consulta*.</span><span class="sxs-lookup"><span data-stu-id="5e727-112">The recommended way to write most queries is to use *query syntax* to create *query expressions*.</span></span> <span data-ttu-id="5e727-113">En el siguiente ejemplo se muestran tres expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="5e727-113">The following example shows three query expressions.</span></span> <span data-ttu-id="5e727-114">La primera expresión de consulta muestra cómo filtrar o restringir los resultados mediante la aplicación de condiciones con una cláusula `where`.</span><span class="sxs-lookup"><span data-stu-id="5e727-114">The first query expression demonstrates how to filter or restrict results by applying conditions with a `where` clause.</span></span> <span data-ttu-id="5e727-115">Devuelve todos los elementos de la secuencia de origen cuyos valores sean mayores que 7 o menores que 3.</span><span class="sxs-lookup"><span data-stu-id="5e727-115">It returns all elements in the source sequence whose values are greater than 7 or less than 3.</span></span> <span data-ttu-id="5e727-116">La segunda expresión muestra cómo ordenar los resultados devueltos.</span><span class="sxs-lookup"><span data-stu-id="5e727-116">The second expression demonstrates how to order the returned results.</span></span> <span data-ttu-id="5e727-117">La tercera expresión muestra cómo agrupar los resultados según una clave.</span><span class="sxs-lookup"><span data-stu-id="5e727-117">The third expression demonstrates how to group results according to a key.</span></span> <span data-ttu-id="5e727-118">Esta consulta devuelve dos grupos en función de la primera letra de la palabra.</span><span class="sxs-lookup"><span data-stu-id="5e727-118">This query returns two groups based on the first letter of the word.</span></span>

[!code-csharp[csProgGuideLINQ#5](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_1.cs)]

<span data-ttu-id="5e727-119">Tenga en cuenta que el tipo de las consultas es <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="5e727-119">Note that the type of the queries is <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="5e727-120">Todas estas consultas podrían escribirse mediante `var` como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5e727-120">All of these queries could be written using `var` as shown in the following example:</span></span>

`var query = from num in numbers...`

<span data-ttu-id="5e727-121">En cada ejemplo anterior, las consultas no se ejecutan realmente hasta que se recorre en iteración la variable de consulta en una instrucción `foreach` o cualquier otra instrucción.</span><span class="sxs-lookup"><span data-stu-id="5e727-121">In each previous example, the queries do not actually execute until you iterate over the query variable in a `foreach` statement or other statement.</span></span> <span data-ttu-id="5e727-122">Para más información, vea [Introduction to LINQ Queries (Introducción a las consultas LINQ)](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="5e727-122">For more information, see [Introduction to LINQ Queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>

## <a name="example---method-syntax"></a><span data-ttu-id="5e727-123">Ejemplo: Sintaxis de método</span><span class="sxs-lookup"><span data-stu-id="5e727-123">Example - Method syntax</span></span>

<span data-ttu-id="5e727-124">Algunas operaciones de consulta deben expresarse como una llamada a método.</span><span class="sxs-lookup"><span data-stu-id="5e727-124">Some query operations must be expressed as a method call.</span></span> <span data-ttu-id="5e727-125">Los más comunes de dichos métodos son los que devuelven valores numéricos de singleton, como <xref:System.Linq.Enumerable.Sum%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, <xref:System.Linq.Enumerable.Average%2A> y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="5e727-125">The most common such methods are those that return singleton numeric values, such as <xref:System.Linq.Enumerable.Sum%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, <xref:System.Linq.Enumerable.Average%2A>, and so on.</span></span> <span data-ttu-id="5e727-126">A estos métodos siempre se los debe llamar en último lugar en cualquier consulta porque representan un solo valor y no pueden servir como origen para una operación de consulta adicional.</span><span class="sxs-lookup"><span data-stu-id="5e727-126">These methods must always be called last in any query because they represent only a single value and cannot serve as the source for an additional query operation.</span></span> <span data-ttu-id="5e727-127">En el ejemplo siguiente se muestra una llamada a método en una expresión de consulta:</span><span class="sxs-lookup"><span data-stu-id="5e727-127">The following example shows a method call in a query expression:</span></span>

[!code-csharp[csProgGuideLINQ#6](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_2.cs)]

<span data-ttu-id="5e727-128">Si el método tiene parámetros Action o Func, se proporcionan en forma de expresión [lambda](../programming-guide/statements-expressions-operators/lambda-expressions.md), como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5e727-128">If the method has Action or Func parameters, these are provided in the form of a [lambda](../programming-guide/statements-expressions-operators/lambda-expressions.md) expression, as shown in the following example:</span></span>

[!code-csharp[csProgGuideLINQ#7](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_3.cs)]

<span data-ttu-id="5e727-129">En las consultas anteriores, solo la número 4 se ejecuta inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="5e727-129">In the previous queries, only Query #4 executes immediately.</span></span> <span data-ttu-id="5e727-130">Esto se debe a que devuelve un valor único, y no una colección <xref:System.Collections.Generic.IEnumerable%601> genérica.</span><span class="sxs-lookup"><span data-stu-id="5e727-130">This is because it returns a single value, and not a generic <xref:System.Collections.Generic.IEnumerable%601> collection.</span></span> <span data-ttu-id="5e727-131">El propio método tiene que usar `foreach` para calcular su valor.</span><span class="sxs-lookup"><span data-stu-id="5e727-131">The method itself has to use `foreach` in order to compute its value.</span></span>

<span data-ttu-id="5e727-132">Cada una de las consultas anteriores puede escribirse mediante tipos implícitos con [var](../language-reference/keywords/var.md), como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5e727-132">Each of the previous queries can be written by using implicit typing with [var](../language-reference/keywords/var.md), as shown in the following example:</span></span>

[!code-csharp[csProgGuideLINQ#8](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_4.cs)]

## <a name="example---mixed-query-and-method-syntax"></a><span data-ttu-id="5e727-133">Ejemplo: Sintaxis de consulta y método combinada</span><span class="sxs-lookup"><span data-stu-id="5e727-133">Example - Mixed query and method syntax</span></span>

<span data-ttu-id="5e727-134">En este ejemplo se muestra cómo usar la sintaxis de método en los resultados de una cláusula de consulta.</span><span class="sxs-lookup"><span data-stu-id="5e727-134">This example shows how to use method syntax on the results of a query clause.</span></span> <span data-ttu-id="5e727-135">Simplemente escriba entre paréntesis la expresión de consulta y luego aplique el operador punto y llame al método.</span><span class="sxs-lookup"><span data-stu-id="5e727-135">Just enclose the query expression in parentheses, and then apply the dot operator and call the method.</span></span> <span data-ttu-id="5e727-136">En el ejemplo siguiente la consulta número 7 devuelve un recuento de los números cuyo valor está comprendido entre 3 y 7.</span><span class="sxs-lookup"><span data-stu-id="5e727-136">In the following example, query #7 returns a count of the numbers whose value is between 3 and 7.</span></span> <span data-ttu-id="5e727-137">Pero en general es mejor usar una segunda variable para almacenar el resultado de la llamada a método.</span><span class="sxs-lookup"><span data-stu-id="5e727-137">In general, however, it is better to use a second variable to store the result of the method call.</span></span> <span data-ttu-id="5e727-138">De esta manera es menos probable que la consulta se confunda con los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="5e727-138">In this manner, the query is less likely to be confused with the results of the query.</span></span>

[!code-csharp[csProgGuideLINQ#9](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_5.cs)]

<span data-ttu-id="5e727-139">Dado que la consulta número 7 devuelve un solo valor y no una colección, se ejecuta inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="5e727-139">Because Query #7 returns a single value and not a collection, the query executes immediately.</span></span>

<span data-ttu-id="5e727-140">La consulta anterior puede escribirse mediante tipos implícitos con `var` como sigue:</span><span class="sxs-lookup"><span data-stu-id="5e727-140">The previous query can be written by using implicit typing with `var`, as follows:</span></span>

```csharp
var numCount = (from num in numbers...
```

<span data-ttu-id="5e727-141">Puede escribirse en sintaxis de método como sigue:</span><span class="sxs-lookup"><span data-stu-id="5e727-141">It can be written in method syntax as follows:</span></span>

```csharp
var numCount = numbers.Where(n => n < 3 || n > 7).Count();
```

<span data-ttu-id="5e727-142">Puede escribirse mediante tipos explícitos como sigue:</span><span class="sxs-lookup"><span data-stu-id="5e727-142">It can be written by using explicit typing, as follows:</span></span>

```csharp
int numCount = numbers.Where(n => n < 3 || n > 7).Count();
```

## <a name="see-also"></a><span data-ttu-id="5e727-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e727-143">See also</span></span>

- <span data-ttu-id="5e727-144">[Walkthrough: Writing Queries in C#](../programming-guide/concepts/linq/walkthrough-writing-queries-linq.md) (Tutorial: Escribir consultas en C#)</span><span class="sxs-lookup"><span data-stu-id="5e727-144">[Walkthrough: Writing Queries in C#](../programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)</span></span>
- [<span data-ttu-id="5e727-145">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="5e727-145">Language Integrated Query (LINQ)</span></span>](index.md)
- [<span data-ttu-id="5e727-146">where (cláusula)</span><span class="sxs-lookup"><span data-stu-id="5e727-146">where clause</span></span>](../language-reference/keywords/where-clause.md)
