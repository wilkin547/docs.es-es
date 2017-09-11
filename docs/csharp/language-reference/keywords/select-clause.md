---
title: "select (Cláusula, Referencia de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- select_CSharpKeyword
- select
dev_langs:
- CSharp
helpviewer_keywords:
- select keyword [C#]
- select clause [C#]
ms.assetid: df01e266-5781-4aaa-80c4-67cf28ea093f
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a505399eb79cbecbefcc53953329279a4abd92f6
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="select-clause-c-reference"></a><span data-ttu-id="422b1-102">select (Cláusula, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="422b1-102">select clause (C# Reference)</span></span>
<span data-ttu-id="422b1-103">En una expresión de consulta, la cláusula `select` especifica el tipo de valores que se producirán cuando se ejecute la consulta.</span><span class="sxs-lookup"><span data-stu-id="422b1-103">In a query expression, the `select` clause specifies the type of values that will be produced when the query is executed.</span></span> <span data-ttu-id="422b1-104">El resultado se basa en la evaluación de todas las cláusulas anteriores y en cualquier expresión de la propia cláusula `select`.</span><span class="sxs-lookup"><span data-stu-id="422b1-104">The result is based on the evaluation of all the previous clauses and on any expressions in the `select` clause itself.</span></span> <span data-ttu-id="422b1-105">Una expresión de consulta debe finalizar con una cláusula `select` o con una cláusula [group](../../../csharp/language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="422b1-105">A query expression must terminate with either a `select` clause or a [group](../../../csharp/language-reference/keywords/group-clause.md) clause.</span></span>  
  
 <span data-ttu-id="422b1-106">En el ejemplo siguiente, se muestra una cláusula `select` simple en una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="422b1-106">The following example shows a simple `select` clause in a query expression.</span></span>  
  
 <span data-ttu-id="422b1-107">[!code-cs[cscsrefQueryKeywords#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="422b1-107">[!code-cs[cscsrefQueryKeywords#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_1.cs)]</span></span>  
  
 <span data-ttu-id="422b1-108">El tipo de la secuencia generada por la cláusula `select` determina el tipo de la variable de consulta `queryHighScores`.</span><span class="sxs-lookup"><span data-stu-id="422b1-108">The type of the sequence produced by the `select` clause determines the type of the query variable `queryHighScores`.</span></span> <span data-ttu-id="422b1-109">En el caso más simple, la cláusula `select` simplemente especifica la variable de rango.</span><span class="sxs-lookup"><span data-stu-id="422b1-109">In the simplest case, the `select` clause just specifies the range variable.</span></span> <span data-ttu-id="422b1-110">Esto hace que la secuencia devuelta contenga elementos del mismo tipo que el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="422b1-110">This causes the returned sequence to contain elements of the same type as the data source.</span></span> <span data-ttu-id="422b1-111">Para obtener más información, vea [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md) (Relaciones entre tipos en las operaciones de consulta LINQ).</span><span class="sxs-lookup"><span data-stu-id="422b1-111">For more information, see [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span> <span data-ttu-id="422b1-112">En cambio, la cláusula `select` también proporciona un mecanismo eficaz para transformar (o *proyectar*) el origen de datos en nuevos tipos.</span><span class="sxs-lookup"><span data-stu-id="422b1-112">However, the `select` clause also provides a powerful mechanism for transforming (or *projecting*) source data into new types.</span></span> <span data-ttu-id="422b1-113">Para obtener más información, vea [Transformaciones de datos con LINQ (C#)](../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md).</span><span class="sxs-lookup"><span data-stu-id="422b1-113">For more information, see [Data Transformations with LINQ (C#)](../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="422b1-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="422b1-114">Example</span></span>  
 <span data-ttu-id="422b1-115">En el ejemplo siguiente, se muestran las distintas formas que puede tener una cláusula `select`.</span><span class="sxs-lookup"><span data-stu-id="422b1-115">The following example shows all the different forms that a `select` clause may take.</span></span> <span data-ttu-id="422b1-116">En cada consulta, tenga en cuenta la relación entre la cláusula `select` y el tipo de la *variable de consulta* (`studentQuery1`, `studentQuery2`, etc.).</span><span class="sxs-lookup"><span data-stu-id="422b1-116">In each query, note the relationship between the `select` clause and the type of the *query variable* (`studentQuery1`, `studentQuery2`, and so on).</span></span>  
  
 <span data-ttu-id="422b1-117">[!code-cs[cscsrefQueryKeywords#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="422b1-117">[!code-cs[cscsrefQueryKeywords#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/select-clause_2.cs)]</span></span>  
  
 <span data-ttu-id="422b1-118">Como se muestra en `studentQuery8` en el ejemplo anterior, a veces es posible que quiera que los elementos de la secuencia devuelta contengan solo un subconjunto de las propiedades de los elementos de origen.</span><span class="sxs-lookup"><span data-stu-id="422b1-118">As shown in `studentQuery8` in the previous example, sometimes you might want the elements of the returned sequence to contain only a subset of the properties of the source elements.</span></span> <span data-ttu-id="422b1-119">Al mantener la secuencia devuelta lo más pequeña posible, puede reducir los requisitos de memoria y aumentar la velocidad de ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="422b1-119">By keeping the returned sequence as small as possible you can reduce the memory requirements and increase the speed of the execution of the query.</span></span> <span data-ttu-id="422b1-120">Puede hacerlo al crear un tipo anónimo en la cláusula `select` y usar un inicializador de objeto para inicializarlo con las propiedades adecuadas del elemento de origen.</span><span class="sxs-lookup"><span data-stu-id="422b1-120">You can accomplish this by creating an anonymous type in the `select` clause and using an object initializer to initialize it with the appropriate properties from the source element.</span></span> <span data-ttu-id="422b1-121">Para obtener un ejemplo de cómo hacerlo, consulte [Inicializadores de objeto y de colección](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).</span><span class="sxs-lookup"><span data-stu-id="422b1-121">For an example of how to do this, see [Object and Collection Initializers](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="422b1-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="422b1-122">Remarks</span></span>  
 <span data-ttu-id="422b1-123">En tiempo de compilación, la cláusula `select` se convierte en una llamada de método al operador de consulta estándar <xref:System.Linq.Enumerable.Select%2A>.</span><span class="sxs-lookup"><span data-stu-id="422b1-123">At compile time, the `select` clause is translated to a method call to the <xref:System.Linq.Enumerable.Select%2A> standard query operator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="422b1-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="422b1-124">See Also</span></span>  
 <span data-ttu-id="422b1-125">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="422b1-125">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="422b1-126">[Palabras clave de consultas (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="422b1-126">[Query Keywords (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span></span>  
 <span data-ttu-id="422b1-127">[from (Cláusula)](../../../csharp/language-reference/keywords/from-clause.md) </span><span class="sxs-lookup"><span data-stu-id="422b1-127">[from clause](../../../csharp/language-reference/keywords/from-clause.md) </span></span>  
 <span data-ttu-id="422b1-128">[partial (método, referencia de C#)](../../../csharp/language-reference/keywords/partial-method.md) </span><span class="sxs-lookup"><span data-stu-id="422b1-128">[partial (Method) (C# Reference)](../../../csharp/language-reference/keywords/partial-method.md) </span></span>  
 <span data-ttu-id="422b1-129">[Tipos anónimos](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="422b1-129">[Anonymous Types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) </span></span>  
 <span data-ttu-id="422b1-130">[Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="422b1-130">[LINQ Query Expressions](../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 [<span data-ttu-id="422b1-131">Introducción a LINQ en C#</span><span class="sxs-lookup"><span data-stu-id="422b1-131">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)

