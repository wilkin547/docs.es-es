---
description: 'Cláusula select: Referencia de C#'
title: 'Cláusula select: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- select_CSharpKeyword
- select
helpviewer_keywords:
- select keyword [C#]
- select clause [C#]
ms.assetid: df01e266-5781-4aaa-80c4-67cf28ea093f
ms.openlocfilehash: d67c99cc841c08a63cc83843a07a46e80199b9d1
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "89136907"
---
# <a name="select-clause-c-reference"></a><span data-ttu-id="a5808-103">select (Cláusula, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="a5808-103">select clause (C# Reference)</span></span>

<span data-ttu-id="a5808-104">En una expresión de consulta, la cláusula `select` especifica el tipo de valores que se producirán cuando se ejecute la consulta.</span><span class="sxs-lookup"><span data-stu-id="a5808-104">In a query expression, the `select` clause specifies the type of values that will be produced when the query is executed.</span></span> <span data-ttu-id="a5808-105">El resultado se basa en la evaluación de todas las cláusulas anteriores y en cualquier expresión de la propia cláusula `select`.</span><span class="sxs-lookup"><span data-stu-id="a5808-105">The result is based on the evaluation of all the previous clauses and on any expressions in the `select` clause itself.</span></span> <span data-ttu-id="a5808-106">Una expresión de consulta debe finalizar con una cláusula `select` o con una cláusula [group](group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a5808-106">A query expression must terminate with either a `select` clause or a [group](group-clause.md) clause.</span></span>

<span data-ttu-id="a5808-107">En el ejemplo siguiente, se muestra una cláusula `select` simple en una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="a5808-107">The following example shows a simple `select` clause in a query expression.</span></span>

[!code-csharp[cscsrefQueryKeywords#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Select.cs#8)]  

<span data-ttu-id="a5808-108">El tipo de la secuencia generada por la cláusula `select` determina el tipo de la variable de consulta `queryHighScores`.</span><span class="sxs-lookup"><span data-stu-id="a5808-108">The type of the sequence produced by the `select` clause determines the type of the query variable `queryHighScores`.</span></span> <span data-ttu-id="a5808-109">En el caso más simple, la cláusula `select` simplemente especifica la variable de rango.</span><span class="sxs-lookup"><span data-stu-id="a5808-109">In the simplest case, the `select` clause just specifies the range variable.</span></span> <span data-ttu-id="a5808-110">Esto hace que la secuencia devuelta contenga elementos del mismo tipo que el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="a5808-110">This causes the returned sequence to contain elements of the same type as the data source.</span></span> <span data-ttu-id="a5808-111">Para obtener más información, vea [Relaciones entre tipos en operaciones de consulta LINQ](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="a5808-111">For more information, see [Type Relationships in LINQ Query Operations](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span> <span data-ttu-id="a5808-112">En cambio, la cláusula `select` también proporciona un mecanismo eficaz para transformar (o *proyectar*) el origen de datos en nuevos tipos.</span><span class="sxs-lookup"><span data-stu-id="a5808-112">However, the `select` clause also provides a powerful mechanism for transforming (or *projecting*) source data into new types.</span></span> <span data-ttu-id="a5808-113">Para obtener más información, vea [Transformaciones de datos con LINQ (C#)](../../programming-guide/concepts/linq/data-transformations-with-linq.md).</span><span class="sxs-lookup"><span data-stu-id="a5808-113">For more information, see [Data Transformations with LINQ (C#)](../../programming-guide/concepts/linq/data-transformations-with-linq.md).</span></span>

## <a name="example"></a><span data-ttu-id="a5808-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a5808-114">Example</span></span>

<span data-ttu-id="a5808-115">En el ejemplo siguiente, se muestran las distintas formas que puede tener una cláusula `select`.</span><span class="sxs-lookup"><span data-stu-id="a5808-115">The following example shows all the different forms that a `select` clause may take.</span></span> <span data-ttu-id="a5808-116">En cada consulta, tenga en cuenta la relación entre la cláusula `select` y el tipo de la *variable de consulta* (`studentQuery1`, `studentQuery2`, etc.).</span><span class="sxs-lookup"><span data-stu-id="a5808-116">In each query, note the relationship between the `select` clause and the type of the *query variable* (`studentQuery1`, `studentQuery2`, and so on).</span></span>

[!code-csharp[cscsrefQueryKeywords#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Select.cs#9)]

<span data-ttu-id="a5808-117">Como se muestra en `studentQuery8` en el ejemplo anterior, a veces es posible que quiera que los elementos de la secuencia devuelta contengan solo un subconjunto de las propiedades de los elementos de origen.</span><span class="sxs-lookup"><span data-stu-id="a5808-117">As shown in `studentQuery8` in the previous example, sometimes you might want the elements of the returned sequence to contain only a subset of the properties of the source elements.</span></span> <span data-ttu-id="a5808-118">Al mantener la secuencia devuelta lo más pequeña posible, puede reducir los requisitos de memoria y aumentar la velocidad de ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="a5808-118">By keeping the returned sequence as small as possible you can reduce the memory requirements and increase the speed of the execution of the query.</span></span> <span data-ttu-id="a5808-119">Puede hacerlo al crear un tipo anónimo en la cláusula `select` y usar un inicializador de objeto para inicializarlo con las propiedades adecuadas del elemento de origen.</span><span class="sxs-lookup"><span data-stu-id="a5808-119">You can accomplish this by creating an anonymous type in the `select` clause and using an object initializer to initialize it with the appropriate properties from the source element.</span></span> <span data-ttu-id="a5808-120">Para obtener un ejemplo de cómo hacerlo, consulte [Inicializadores de objeto y de colección](../../programming-guide/classes-and-structs/object-and-collection-initializers.md).</span><span class="sxs-lookup"><span data-stu-id="a5808-120">For an example of how to do this, see [Object and Collection Initializers](../../programming-guide/classes-and-structs/object-and-collection-initializers.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="a5808-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a5808-121">Remarks</span></span>

<span data-ttu-id="a5808-122">En tiempo de compilación, la cláusula `select` se convierte en una llamada de método al operador de consulta estándar <xref:System.Linq.Enumerable.Select%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5808-122">At compile time, the `select` clause is translated to a method call to the <xref:System.Linq.Enumerable.Select%2A> standard query operator.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5808-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5808-123">See also</span></span>

- [<span data-ttu-id="a5808-124">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="a5808-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a5808-125">Palabras clave para consultas (LINQ)</span><span class="sxs-lookup"><span data-stu-id="a5808-125">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="a5808-126">from (cláusula)</span><span class="sxs-lookup"><span data-stu-id="a5808-126">from clause</span></span>](from-clause.md)
- [<span data-ttu-id="a5808-127">partial (Método) (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="a5808-127">partial (Method) (C# Reference)</span></span>](partial-method.md)
- [<span data-ttu-id="a5808-128">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="a5808-128">Anonymous Types</span></span>](../../programming-guide/classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="a5808-129">LINQ en C#</span><span class="sxs-lookup"><span data-stu-id="a5808-129">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="a5808-130">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="a5808-130">Language Integrated Query (LINQ)</span></span>](../../programming-guide/concepts/linq/index.md)
