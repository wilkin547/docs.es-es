---
title: "Realizar operaciones de combinación personalizadas"
description: "Cómo realizar operaciones de combinación personalizadas."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 56a2a4a5-7299-497d-b3c3-23c848678911
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 51bdae75346022a7564fdb50e582c143e7762a1f
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="perform-custom-join-operations"></a><span data-ttu-id="f8559-104">Realizar operaciones de combinación personalizadas</span><span class="sxs-lookup"><span data-stu-id="f8559-104">Perform custom join operations</span></span>

<span data-ttu-id="f8559-105">En este ejemplo se muestra cómo realizar operaciones de combinación que no son posibles con la cláusula `join`.</span><span class="sxs-lookup"><span data-stu-id="f8559-105">This example shows how to perform join operations that are not possible with the `join` clause.</span></span> <span data-ttu-id="f8559-106">En una expresión de consulta, la cláusula `join` se limita a combinaciones de igualdad (y se optimiza para estas), que son con diferencia el tipo más común de operación de combinación.</span><span class="sxs-lookup"><span data-stu-id="f8559-106">In a query expression, the `join` clause is limited to, and optimized for, equijoins, which are by far the most common type of join operation.</span></span> <span data-ttu-id="f8559-107">Al realizar una combinación de igualdad, probablemente obtendrá siempre el mejor rendimiento con la cláusula `join`.</span><span class="sxs-lookup"><span data-stu-id="f8559-107">When performing an equijoin, you will probably always get the best performance by using the `join` clause.</span></span>  
  
 <span data-ttu-id="f8559-108">En cambio, la cláusula `join` no se puede usar en los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="f8559-108">However, the `join` clause cannot be used in the following cases:</span></span>  
  
-   <span data-ttu-id="f8559-109">Cuando la combinación se basa en una expresión de desigualdad (una combinación que no es de igualdad).</span><span class="sxs-lookup"><span data-stu-id="f8559-109">When the join is predicated on an expression of inequality (a non-equijoin).</span></span>  
  
-   <span data-ttu-id="f8559-110">Cuando la combinación se basa en más de una expresión de igualdad o desigualdad.</span><span class="sxs-lookup"><span data-stu-id="f8559-110">When the join is predicated on more than one expression of equality or inequality.</span></span>  
  
-   <span data-ttu-id="f8559-111">Cuando tenga que introducir una variable de rango temporal para la secuencia de la derecha (interior) antes de la operación de combinación.</span><span class="sxs-lookup"><span data-stu-id="f8559-111">When you have to introduce a temporary range variable for the right side (inner) sequence before the join operation.</span></span>  
  
 <span data-ttu-id="f8559-112">Para realizar combinaciones que no son de igualdad, puede usar varias cláusulas `from` para presentar cada origen de datos de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="f8559-112">To perform joins that are not equijoins, you can use multiple `from` clauses to introduce each data source independently.</span></span> <span data-ttu-id="f8559-113">Después, aplique una expresión de predicado de una cláusula `where` a la variable de rango para cada origen.</span><span class="sxs-lookup"><span data-stu-id="f8559-113">You then apply a predicate expression in a `where` clause to the range variable for each source.</span></span> <span data-ttu-id="f8559-114">La expresión también puede adoptar la forma de una llamada de método.</span><span class="sxs-lookup"><span data-stu-id="f8559-114">The expression also can take the form of a method call.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8559-115">No confunda este tipo de operación de combinación personalizada con el uso de varias cláusulas `from` para acceder a colecciones internas.</span><span class="sxs-lookup"><span data-stu-id="f8559-115">Do not confuse this kind of custom join operation with the use of multiple `from` clauses to access inner collections.</span></span> <span data-ttu-id="f8559-116">Para obtener más información, consulte [join (Cláusula, Referencia de C#)](../language-reference/keywords/join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="f8559-116">For more information, see [join clause](../language-reference/keywords/join-clause.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8559-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f8559-117">Example</span></span>  
 <span data-ttu-id="f8559-118">En el primer método del siguiente ejemplo se muestra una combinación cruzada sencilla.</span><span class="sxs-lookup"><span data-stu-id="f8559-118">The first method in the following example shows a simple cross join.</span></span> <span data-ttu-id="f8559-119">Las combinaciones cruzadas se deben usar con precaución porque pueden generar conjuntos de resultados muy grandes.</span><span class="sxs-lookup"><span data-stu-id="f8559-119">Cross joins must be used with caution because they can produce very large result sets.</span></span> <span data-ttu-id="f8559-120">En cambio, pueden resultar útiles en algunos escenarios para crear secuencias de origen en las que se ejecutan consultas adicionales.</span><span class="sxs-lookup"><span data-stu-id="f8559-120">However, they can be useful in some scenarios for creating source sequences against which additional queries are run.</span></span>  
  
 <span data-ttu-id="f8559-121">El segundo método genera una secuencia de todos los productos cuyo identificador de categoría aparece en la lista de categorías en el lado izquierdo.</span><span class="sxs-lookup"><span data-stu-id="f8559-121">The second method produces a sequence of all the products whose category ID is listed in the category list on the left side.</span></span> <span data-ttu-id="f8559-122">Observe el uso de la cláusula `let` y el método `Contains` para crear una matriz temporal.</span><span class="sxs-lookup"><span data-stu-id="f8559-122">Note the use of the `let` clause and the `Contains` method to create a temporary array.</span></span> <span data-ttu-id="f8559-123">También se puede crear la matriz antes de la consulta y eliminar la primera cláusula `from`.</span><span class="sxs-lookup"><span data-stu-id="f8559-123">It also is possible to create the array before the query and eliminate the first `from` clause.</span></span>  
  
 <span data-ttu-id="f8559-124">[!code-cs[csProgGuideLINQ#64](../../../samples/snippets/csharp/concepts/linq/how-to-perform-custom-join-operations_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f8559-124">[!code-cs[csProgGuideLINQ#64](../../../samples/snippets/csharp/concepts/linq/how-to-perform-custom-join-operations_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8559-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f8559-125">Example</span></span>  
 <span data-ttu-id="f8559-126">En el ejemplo siguiente, la consulta debe combinar dos secuencias basándose en las claves coincidentes que, en el caso de la secuencia interna (lado derecho), no se pueden obtener antes de la propia cláusula de combinación.</span><span class="sxs-lookup"><span data-stu-id="f8559-126">In the following example, the query must join two sequences based on matching keys that, in the case of the inner (right side) sequence, cannot be obtained prior to the join clause itself.</span></span> <span data-ttu-id="f8559-127">Si esta combinación se realizara con una cláusula `join`, se tendría que llamar al método `Split` para cada elemento.</span><span class="sxs-lookup"><span data-stu-id="f8559-127">If this join were performed with a `join` clause, then the `Split` method would have to be called for each element.</span></span> <span data-ttu-id="f8559-128">El uso de varias cláusulas `from` permite a la consulta evitar la sobrecarga que supone la llamada al método repetida.</span><span class="sxs-lookup"><span data-stu-id="f8559-128">The use of multiple `from` clauses enables the query to avoid the overhead of the repeated method call.</span></span> <span data-ttu-id="f8559-129">En cambio, puesto que `join` está optimizada, en este caso particular puede que siga resultando más rápido que usar varias cláusulas `from`.</span><span class="sxs-lookup"><span data-stu-id="f8559-129">However, since `join` is optimized, in this particular case it might still be faster than using multiple `from` clauses.</span></span> <span data-ttu-id="f8559-130">Los resultados variarán dependiendo principalmente de cuántos recursos requiera la llamada de método.</span><span class="sxs-lookup"><span data-stu-id="f8559-130">The results will vary depending primarily on how expensive the method call is.</span></span>  
  
 <span data-ttu-id="f8559-131">[!code-cs[csProgGuideLINQ#13](../../../samples/snippets/csharp/concepts/linq/how-to-perform-custom-join-operations_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="f8559-131">[!code-cs[csProgGuideLINQ#13](../../../samples/snippets/csharp/concepts/linq/how-to-perform-custom-join-operations_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8559-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8559-132">See also</span></span>  
 <span data-ttu-id="f8559-133">[Expresiones de consulta LINQ](index.md) </span><span class="sxs-lookup"><span data-stu-id="f8559-133">[LINQ query expressions](index.md) </span></span>  
 <span data-ttu-id="f8559-134">[join (Cláusula, Referencia de C#)](../language-reference/keywords/join-clause.md) </span><span class="sxs-lookup"><span data-stu-id="f8559-134">[join clause](../language-reference/keywords/join-clause.md) </span></span>  
 [<span data-ttu-id="f8559-135">Ordenar los resultados de una cláusula join</span><span class="sxs-lookup"><span data-stu-id="f8559-135">Order the results of a join clause</span></span>](order-the-results-of-a-join-clause.md)

