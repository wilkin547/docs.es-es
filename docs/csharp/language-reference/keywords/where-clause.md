---
description: 'Cláusula where: Referencia de C#'
title: 'Cláusula where: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- whereclause_CSharpKeyword
helpviewer_keywords:
- where keyword [C#]
- where clause [C#]
ms.assetid: 7f9bf952-7744-4f91-b676-cddb55d107c3
ms.openlocfilehash: 58a8dc226bb2720b6a8251f028712a80f74e893c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "89141691"
---
# <a name="where-clause-c-reference"></a><span data-ttu-id="691d2-103">where (Cláusula, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="691d2-103">where clause (C# Reference)</span></span>

<span data-ttu-id="691d2-104">La cláusula `where` se usa en una expresión de consulta para especificar los elementos del origen de datos que se devuelven en dicha expresión.</span><span class="sxs-lookup"><span data-stu-id="691d2-104">The `where` clause is used in a query expression to specify which elements from the data source will be returned in the query expression.</span></span> <span data-ttu-id="691d2-105">Aplica una condición booleana (*predicate*) a cada elemento de origen (al que hace referencia la variable de rango) y devuelve aquellos en los que la condición especificada se cumple.</span><span class="sxs-lookup"><span data-stu-id="691d2-105">It applies a Boolean condition (*predicate*) to each source element (referenced by the range variable) and returns those for which the specified condition is true.</span></span> <span data-ttu-id="691d2-106">Puede que una sola expresión de consulta contenga varias cláusulas `where` y que una sola cláusula contenga varias subexpresiones de predicado.</span><span class="sxs-lookup"><span data-stu-id="691d2-106">A single query expression may contain multiple `where` clauses and a single clause may contain multiple predicate subexpressions.</span></span>

## <a name="example"></a><span data-ttu-id="691d2-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="691d2-107">Example</span></span>

<span data-ttu-id="691d2-108">En el ejemplo siguiente, la cláusula `where` filtra todos los números excepto los que son inferiores a cinco.</span><span class="sxs-lookup"><span data-stu-id="691d2-108">In the following example, the `where` clause filters out all numbers except those that are less than five.</span></span> <span data-ttu-id="691d2-109">Si la cláusula `where` se quita, se devolverán todos los números del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="691d2-109">If you remove the `where` clause, all numbers from the data source would be returned.</span></span> <span data-ttu-id="691d2-110">La expresión `num < 5` es el predicado que se aplica a cada elemento.</span><span class="sxs-lookup"><span data-stu-id="691d2-110">The expression `num < 5` is the predicate that is applied to each element.</span></span>

[!code-csharp[cscsrefQueryKeywords#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#5)]

## <a name="example"></a><span data-ttu-id="691d2-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="691d2-111">Example</span></span>

<span data-ttu-id="691d2-112">En una sola cláusula `where`, se pueden especificar todos los predicados que sean necesarios mediante los operadores [&&](../operators/boolean-logical-operators.md#conditional-logical-and-operator-) y [&#124;&#124;](../operators/boolean-logical-operators.md#conditional-logical-or-operator-).</span><span class="sxs-lookup"><span data-stu-id="691d2-112">Within a single `where` clause, you can specify as many predicates as necessary by using the [&&](../operators/boolean-logical-operators.md#conditional-logical-and-operator-) and [&#124;&#124;](../operators/boolean-logical-operators.md#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="691d2-113">En el ejemplo siguiente, la consulta especifica dos predicados para seleccionar únicamente los números pares que sean inferiores a cinco.</span><span class="sxs-lookup"><span data-stu-id="691d2-113">In the following example, the query specifies two predicates in order to select only the even numbers that are less than five.</span></span>

[!code-csharp[cscsrefQueryKeywords#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#6)]  

## <a name="example"></a><span data-ttu-id="691d2-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="691d2-114">Example</span></span>

<span data-ttu-id="691d2-115">Puede que una cláusula `where` contenga uno o más métodos que devuelvan valores booleanos.</span><span class="sxs-lookup"><span data-stu-id="691d2-115">A `where` clause may contain one or more methods that return Boolean values.</span></span> <span data-ttu-id="691d2-116">En el ejemplo siguiente, la cláusula `where` usa un método para determinar si el valor actual de la variable de rango es par o impar.</span><span class="sxs-lookup"><span data-stu-id="691d2-116">In the following example, the `where` clause uses a method to determine whether the current value of the range variable is even or odd.</span></span>

[!code-csharp[cscsrefQueryKeywords#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#7)]

## <a name="remarks"></a><span data-ttu-id="691d2-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="691d2-117">Remarks</span></span>

<span data-ttu-id="691d2-118">La cláusula `where` es un mecanismo de filtrado.</span><span class="sxs-lookup"><span data-stu-id="691d2-118">The `where` clause is a filtering mechanism.</span></span> <span data-ttu-id="691d2-119">Se puede colocar prácticamente en cualquier parte en una expresión de consulta, pero no puede ser la primera ni la última cláusula.</span><span class="sxs-lookup"><span data-stu-id="691d2-119">It can be positioned almost anywhere in a query expression, except it cannot be the first or last clause.</span></span> <span data-ttu-id="691d2-120">Puede que una cláusula `where` aparezca antes o después de una cláusula [group](group-clause.md), en función de que haya que filtrar los elementos de origen antes o después de agruparlos.</span><span class="sxs-lookup"><span data-stu-id="691d2-120">A `where` clause may appear either before or after a [group](group-clause.md) clause depending on whether you have to filter the source elements before or after they are grouped.</span></span>

<span data-ttu-id="691d2-121">Si un predicado especificado no es válido para los elementos del origen de datos, se producirá un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="691d2-121">If a specified predicate is not valid for the elements in the data source, a compile-time error will result.</span></span> <span data-ttu-id="691d2-122">Esta es una de las ventajas de la comprobación fuertemente tipada que ofrece LINQ.</span><span class="sxs-lookup"><span data-stu-id="691d2-122">This is one benefit of the strong type-checking provided by LINQ.</span></span>

<span data-ttu-id="691d2-123">En tiempo de compilación, la palabra clave `where` se convierte en una llamada al método de operador de consulta estándar <xref:System.Linq.Enumerable.Where%2A>.</span><span class="sxs-lookup"><span data-stu-id="691d2-123">At compile time the `where` keyword is converted into a call to the <xref:System.Linq.Enumerable.Where%2A> Standard Query Operator method.</span></span>

## <a name="see-also"></a><span data-ttu-id="691d2-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="691d2-124">See also</span></span>

- [<span data-ttu-id="691d2-125">Palabras clave para consultas (LINQ)</span><span class="sxs-lookup"><span data-stu-id="691d2-125">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="691d2-126">from (cláusula)</span><span class="sxs-lookup"><span data-stu-id="691d2-126">from clause</span></span>](from-clause.md)
- [<span data-ttu-id="691d2-127">select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="691d2-127">select clause</span></span>](select-clause.md)
- [<span data-ttu-id="691d2-128">Filtrado de datos</span><span class="sxs-lookup"><span data-stu-id="691d2-128">Filtering Data</span></span>](../../programming-guide/concepts/linq/filtering-data.md)
- [<span data-ttu-id="691d2-129">LINQ en C#</span><span class="sxs-lookup"><span data-stu-id="691d2-129">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="691d2-130">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="691d2-130">Language Integrated Query (LINQ)</span></span>](../../programming-guide/concepts/linq/index.md)
