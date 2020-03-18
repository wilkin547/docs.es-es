---
title: Realizar operaciones de combinación personalizadas (LINQ en C#)
description: Obtenga información sobre cómo realizar operaciones de combinación de LINQ personalizadas en C#.
ms.date: 12/01/2016
ms.assetid: 56a2a4a5-7299-497d-b3c3-23c848678911
ms.openlocfilehash: 7051007c67bd64cd11ede2f4d5352ce3d497255f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "61659857"
---
# <a name="perform-custom-join-operations"></a><span data-ttu-id="86c38-103">Realizar operaciones de combinación personalizadas</span><span class="sxs-lookup"><span data-stu-id="86c38-103">Perform custom join operations</span></span>

<span data-ttu-id="86c38-104">En este ejemplo se muestra cómo realizar operaciones de combinación que no son posibles con la cláusula `join`.</span><span class="sxs-lookup"><span data-stu-id="86c38-104">This example shows how to perform join operations that aren't possible with the `join` clause.</span></span> <span data-ttu-id="86c38-105">En una expresión de consulta, la cláusula `join` se limita a combinaciones de igualdad (y se optimiza para estas), que son con diferencia el tipo más común de operación de combinación.</span><span class="sxs-lookup"><span data-stu-id="86c38-105">In a query expression, the `join` clause is limited to, and optimized for, equijoins, which are by far the most common type of join operation.</span></span> <span data-ttu-id="86c38-106">Al realizar una combinación de igualdad, probablemente obtendrá siempre el mejor rendimiento con la cláusula `join`.</span><span class="sxs-lookup"><span data-stu-id="86c38-106">When performing an equijoin, you will probably always get the best performance by using the `join` clause.</span></span>

<span data-ttu-id="86c38-107">En cambio, la cláusula `join` no se puede usar en los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="86c38-107">However, the `join` clause cannot be used in the following cases:</span></span>

- <span data-ttu-id="86c38-108">Cuando la combinación se basa en una expresión de desigualdad (una combinación que no es de igualdad).</span><span class="sxs-lookup"><span data-stu-id="86c38-108">When the join is predicated on an expression of inequality (a non-equijoin).</span></span>

- <span data-ttu-id="86c38-109">Cuando la combinación se basa en más de una expresión de igualdad o desigualdad.</span><span class="sxs-lookup"><span data-stu-id="86c38-109">When the join is predicated on more than one expression of equality or inequality.</span></span>

- <span data-ttu-id="86c38-110">Cuando tenga que introducir una variable de rango temporal para la secuencia de la derecha (interior) antes de la operación de combinación.</span><span class="sxs-lookup"><span data-stu-id="86c38-110">When you have to introduce a temporary range variable for the right side (inner) sequence before the join operation.</span></span>

 <span data-ttu-id="86c38-111">Para realizar combinaciones que no son de igualdad, puede usar varias cláusulas `from` para presentar cada origen de datos de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="86c38-111">To perform joins that aren't equijoins, you can use multiple `from` clauses to introduce each data source independently.</span></span> <span data-ttu-id="86c38-112">Después, aplique una expresión de predicado de una cláusula `where` a la variable de rango para cada origen.</span><span class="sxs-lookup"><span data-stu-id="86c38-112">You then apply a predicate expression in a `where` clause to the range variable for each source.</span></span> <span data-ttu-id="86c38-113">La expresión también puede adoptar la forma de una llamada de método.</span><span class="sxs-lookup"><span data-stu-id="86c38-113">The expression also can take the form of a method call.</span></span>

> [!NOTE]
> <span data-ttu-id="86c38-114">No confunda este tipo de operación de combinación personalizada con el uso de varias cláusulas `from` para acceder a colecciones internas.</span><span class="sxs-lookup"><span data-stu-id="86c38-114">Don't confuse this kind of custom join operation with the use of multiple `from` clauses to access inner collections.</span></span> <span data-ttu-id="86c38-115">Para obtener más información, vea [join (Cláusula, Referencia de C#)](../language-reference/keywords/join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="86c38-115">For more information, see [join clause](../language-reference/keywords/join-clause.md).</span></span>

## <a name="example"></a><span data-ttu-id="86c38-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="86c38-116">Example</span></span>

<span data-ttu-id="86c38-117">En el primer método del siguiente ejemplo se muestra una combinación cruzada sencilla.</span><span class="sxs-lookup"><span data-stu-id="86c38-117">The first method in the following example shows a simple cross join.</span></span> <span data-ttu-id="86c38-118">Las combinaciones cruzadas se deben usar con precaución porque pueden generar conjuntos de resultados muy grandes.</span><span class="sxs-lookup"><span data-stu-id="86c38-118">Cross joins must be used with caution because they can produce very large result sets.</span></span> <span data-ttu-id="86c38-119">En cambio, pueden resultar útiles en algunos escenarios para crear secuencias de origen en las que se ejecutan consultas adicionales.</span><span class="sxs-lookup"><span data-stu-id="86c38-119">However, they can be useful in some scenarios for creating source sequences against which additional queries are run.</span></span>

<span data-ttu-id="86c38-120">El segundo método genera una secuencia de todos los productos cuyo identificador de categoría aparece en la lista de categorías en el lado izquierdo.</span><span class="sxs-lookup"><span data-stu-id="86c38-120">The second method produces a sequence of all the products whose category ID is listed in the category list on the left side.</span></span> <span data-ttu-id="86c38-121">Observe el uso de la cláusula `let` y el método `Contains` para crear una matriz temporal.</span><span class="sxs-lookup"><span data-stu-id="86c38-121">Note the use of the `let` clause and the `Contains` method to create a temporary array.</span></span> <span data-ttu-id="86c38-122">También se puede crear la matriz antes de la consulta y eliminar la primera cláusula `from`.</span><span class="sxs-lookup"><span data-stu-id="86c38-122">It also is possible to create the array before the query and eliminate the first `from` clause.</span></span>

[!code-csharp[csProgGuideLINQ#64](~/samples/snippets/csharp/concepts/linq/how-to-perform-custom-join-operations_1.cs)]

## <a name="example"></a><span data-ttu-id="86c38-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="86c38-123">Example</span></span>

<span data-ttu-id="86c38-124">En el ejemplo siguiente, la consulta debe combinar dos secuencias basándose en las claves coincidentes que, en el caso de la secuencia interna (lado derecho), no se pueden obtener antes de la propia cláusula de combinación.</span><span class="sxs-lookup"><span data-stu-id="86c38-124">In the following example, the query must join two sequences based on matching keys that, in the case of the inner (right side) sequence, cannot be obtained prior to the join clause itself.</span></span> <span data-ttu-id="86c38-125">Si esta combinación se realizara con una cláusula `join`, se tendría que llamar al método `Split` para cada elemento.</span><span class="sxs-lookup"><span data-stu-id="86c38-125">If this join were performed with a `join` clause, then the `Split` method would have to be called for each element.</span></span> <span data-ttu-id="86c38-126">El uso de varias cláusulas `from` permite a la consulta evitar la sobrecarga que supone la llamada al método repetida.</span><span class="sxs-lookup"><span data-stu-id="86c38-126">The use of multiple `from` clauses enables the query to avoid the overhead of the repeated method call.</span></span> <span data-ttu-id="86c38-127">En cambio, puesto que `join` está optimizada, en este caso particular puede que siga resultando más rápido que usar varias cláusulas `from`.</span><span class="sxs-lookup"><span data-stu-id="86c38-127">However, since `join` is optimized, in this particular case it might still be faster than using multiple `from` clauses.</span></span> <span data-ttu-id="86c38-128">Los resultados variarán dependiendo principalmente de cuántos recursos requiera la llamada de método.</span><span class="sxs-lookup"><span data-stu-id="86c38-128">The results will vary depending primarily on how expensive the method call is.</span></span>

[!code-csharp[csProgGuideLINQ#13](~/samples/snippets/csharp/concepts/linq/how-to-perform-custom-join-operations_2.cs)]

## <a name="see-also"></a><span data-ttu-id="86c38-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="86c38-129">See also</span></span>

- [<span data-ttu-id="86c38-130">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="86c38-130">Language Integrated Query (LINQ)</span></span>](index.md)
- [<span data-ttu-id="86c38-131">join (cláusula)</span><span class="sxs-lookup"><span data-stu-id="86c38-131">join clause</span></span>](../language-reference/keywords/join-clause.md)
- [<span data-ttu-id="86c38-132">Ordenar los resultados de una cláusula join</span><span class="sxs-lookup"><span data-stu-id="86c38-132">Order the results of a join clause</span></span>](order-the-results-of-a-join-clause.md)
