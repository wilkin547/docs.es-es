---
title: 'Cláusula where: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- whereclause_CSharpKeyword
helpviewer_keywords:
- where keyword [C#]
- where clause [C#]
ms.assetid: 7f9bf952-7744-4f91-b676-cddb55d107c3
ms.openlocfilehash: 33616e4eacb484b9c6eda3862cd86fdd1e6df165
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173489"
---
# <a name="where-clause-c-reference"></a><span data-ttu-id="8fb50-102">where (Cláusula, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="8fb50-102">where clause (C# Reference)</span></span>

<span data-ttu-id="8fb50-103">La cláusula `where` se usa en una expresión de consulta para especificar los elementos del origen de datos que se devuelven en dicha expresión.</span><span class="sxs-lookup"><span data-stu-id="8fb50-103">The `where` clause is used in a query expression to specify which elements from the data source will be returned in the query expression.</span></span> <span data-ttu-id="8fb50-104">Aplica una condición booleana (*predicate*) a cada elemento de origen (al que hace referencia la variable de rango) y devuelve aquellos en los que la condición especificada se cumple.</span><span class="sxs-lookup"><span data-stu-id="8fb50-104">It applies a Boolean condition (*predicate*) to each source element (referenced by the range variable) and returns those for which the specified condition is true.</span></span> <span data-ttu-id="8fb50-105">Puede que una sola expresión de consulta contenga varias cláusulas `where` y que una sola cláusula contenga varias subexpresiones de predicado.</span><span class="sxs-lookup"><span data-stu-id="8fb50-105">A single query expression may contain multiple `where` clauses and a single clause may contain multiple predicate subexpressions.</span></span>

## <a name="example"></a><span data-ttu-id="8fb50-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8fb50-106">Example</span></span>

<span data-ttu-id="8fb50-107">En el ejemplo siguiente, la cláusula `where` filtra todos los números excepto los que son inferiores a cinco.</span><span class="sxs-lookup"><span data-stu-id="8fb50-107">In the following example, the `where` clause filters out all numbers except those that are less than five.</span></span> <span data-ttu-id="8fb50-108">Si la cláusula `where` se quita, se devolverán todos los números del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="8fb50-108">If you remove the `where` clause, all numbers from the data source would be returned.</span></span> <span data-ttu-id="8fb50-109">La expresión `num < 5` es el predicado que se aplica a cada elemento.</span><span class="sxs-lookup"><span data-stu-id="8fb50-109">The expression `num < 5` is the predicate that is applied to each element.</span></span>

[!code-csharp[cscsrefQueryKeywords#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#5)]

## <a name="example"></a><span data-ttu-id="8fb50-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8fb50-110">Example</span></span>

<span data-ttu-id="8fb50-111">En una sola cláusula `where`, se pueden especificar todos los predicados que sean necesarios mediante los operadores [&&](../operators/boolean-logical-operators.md#conditional-logical-and-operator-) y [&#124;&#124;](../operators/boolean-logical-operators.md#conditional-logical-or-operator-).</span><span class="sxs-lookup"><span data-stu-id="8fb50-111">Within a single `where` clause, you can specify as many predicates as necessary by using the [&&](../operators/boolean-logical-operators.md#conditional-logical-and-operator-) and [&#124;&#124;](../operators/boolean-logical-operators.md#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="8fb50-112">En el ejemplo siguiente, la consulta especifica dos predicados para seleccionar únicamente los números pares que sean inferiores a cinco.</span><span class="sxs-lookup"><span data-stu-id="8fb50-112">In the following example, the query specifies two predicates in order to select only the even numbers that are less than five.</span></span>

[!code-csharp[cscsrefQueryKeywords#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#6)]  

## <a name="example"></a><span data-ttu-id="8fb50-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8fb50-113">Example</span></span>

<span data-ttu-id="8fb50-114">Puede que una cláusula `where` contenga uno o más métodos que devuelvan valores booleanos.</span><span class="sxs-lookup"><span data-stu-id="8fb50-114">A `where` clause may contain one or more methods that return Boolean values.</span></span> <span data-ttu-id="8fb50-115">En el ejemplo siguiente, la cláusula `where` usa un método para determinar si el valor actual de la variable de rango es par o impar.</span><span class="sxs-lookup"><span data-stu-id="8fb50-115">In the following example, the `where` clause uses a method to determine whether the current value of the range variable is even or odd.</span></span>

[!code-csharp[cscsrefQueryKeywords#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#7)]

## <a name="remarks"></a><span data-ttu-id="8fb50-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8fb50-116">Remarks</span></span>

<span data-ttu-id="8fb50-117">La cláusula `where` es un mecanismo de filtrado.</span><span class="sxs-lookup"><span data-stu-id="8fb50-117">The `where` clause is a filtering mechanism.</span></span> <span data-ttu-id="8fb50-118">Se puede colocar prácticamente en cualquier parte en una expresión de consulta, pero no puede ser la primera ni la última cláusula.</span><span class="sxs-lookup"><span data-stu-id="8fb50-118">It can be positioned almost anywhere in a query expression, except it cannot be the first or last clause.</span></span> <span data-ttu-id="8fb50-119">Puede que una cláusula `where` aparezca antes o después de una cláusula [group](group-clause.md), en función de que haya que filtrar los elementos de origen antes o después de agruparlos.</span><span class="sxs-lookup"><span data-stu-id="8fb50-119">A `where` clause may appear either before or after a [group](group-clause.md) clause depending on whether you have to filter the source elements before or after they are grouped.</span></span>

<span data-ttu-id="8fb50-120">Si un predicado especificado no es válido para los elementos del origen de datos, se producirá un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="8fb50-120">If a specified predicate is not valid for the elements in the data source, a compile-time error will result.</span></span> <span data-ttu-id="8fb50-121">Esta es una de las ventajas de la comprobación fuertemente tipada que ofrece LINQ.</span><span class="sxs-lookup"><span data-stu-id="8fb50-121">This is one benefit of the strong type-checking provided by LINQ.</span></span>

<span data-ttu-id="8fb50-122">En tiempo de compilación, la palabra clave `where` se convierte en una llamada al método de operador de consulta estándar <xref:System.Linq.Enumerable.Where%2A>.</span><span class="sxs-lookup"><span data-stu-id="8fb50-122">At compile time the `where` keyword is converted into a call to the <xref:System.Linq.Enumerable.Where%2A> Standard Query Operator method.</span></span>

## <a name="see-also"></a><span data-ttu-id="8fb50-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="8fb50-123">See also</span></span>

- [<span data-ttu-id="8fb50-124">Palabras clave para consultas (LINQ)</span><span class="sxs-lookup"><span data-stu-id="8fb50-124">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="8fb50-125">from (cláusula)</span><span class="sxs-lookup"><span data-stu-id="8fb50-125">from clause</span></span>](from-clause.md)
- [<span data-ttu-id="8fb50-126">select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="8fb50-126">select clause</span></span>](select-clause.md)
- [<span data-ttu-id="8fb50-127">Filtrado de datos</span><span class="sxs-lookup"><span data-stu-id="8fb50-127">Filtering Data</span></span>](../../programming-guide/concepts/linq/filtering-data.md)
- [<span data-ttu-id="8fb50-128">LINQ en C#</span><span class="sxs-lookup"><span data-stu-id="8fb50-128">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="8fb50-129">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="8fb50-129">Language Integrated Query (LINQ)</span></span>](../../programming-guide/concepts/linq/index.md)
