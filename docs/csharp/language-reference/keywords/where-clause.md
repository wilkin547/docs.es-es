---
title: "where (Cláusula, Referencia de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- whereclause_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- where keyword [C#]
- where clause [C#]
ms.assetid: 7f9bf952-7744-4f91-b676-cddb55d107c3
caps.latest.revision: 16
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
ms.openlocfilehash: 97d7c16d6bf8048e621141fff52a47907881fd2f
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="where-clause-c-reference"></a><span data-ttu-id="22e52-102">where (Cláusula, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="22e52-102">where clause (C# Reference)</span></span>
<span data-ttu-id="22e52-103">La cláusula `where` se usa en una expresión de consulta para especificar los elementos del origen de datos que se devuelven en dicha expresión.</span><span class="sxs-lookup"><span data-stu-id="22e52-103">The `where` clause is used in a query expression to specify which elements from the data source will be returned in the query expression.</span></span> <span data-ttu-id="22e52-104">Aplica una condición booleana (*predicate*) a cada elemento de origen (al que hace referencia la variable de rango) y devuelve aquellos en los que la condición especificada se cumple.</span><span class="sxs-lookup"><span data-stu-id="22e52-104">It applies a Boolean condition (*predicate*) to each source element (referenced by the range variable) and returns those for which the specified condition is true.</span></span> <span data-ttu-id="22e52-105">Puede que una sola expresión de consulta contenga varias cláusulas `where` y que una sola cláusula contenga varias subexpresiones de predicado.</span><span class="sxs-lookup"><span data-stu-id="22e52-105">A single query expression may contain multiple `where` clauses and a single clause may contain multiple predicate subexpressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22e52-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="22e52-106">Example</span></span>  
 <span data-ttu-id="22e52-107">En el ejemplo siguiente, la cláusula `where` filtra todos los números excepto los que son inferiores a cinco.</span><span class="sxs-lookup"><span data-stu-id="22e52-107">In the following example, the `where` clause filters out all numbers except those that are less than five.</span></span> <span data-ttu-id="22e52-108">Si la cláusula `where` se quita, se devolverán todos los números del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="22e52-108">If you remove the `where` clause, all numbers from the data source would be returned.</span></span> <span data-ttu-id="22e52-109">La expresión `num < 5` es el predicado que se aplica a cada elemento.</span><span class="sxs-lookup"><span data-stu-id="22e52-109">The expression `num < 5` is the predicate that is applied to each element.</span></span>  
  
 <span data-ttu-id="22e52-110">[!code-cs[cscsrefQueryKeywords#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="22e52-110">[!code-cs[cscsrefQueryKeywords#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="22e52-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="22e52-111">Example</span></span>  
 <span data-ttu-id="22e52-112">En una sola cláusula `where`, se pueden especificar todos los predicados que sean necesarios mediante los operadores [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) y [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md).</span><span class="sxs-lookup"><span data-stu-id="22e52-112">Within a single `where` clause, you can specify as many predicates as necessary by using the [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) and [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) operators.</span></span> <span data-ttu-id="22e52-113">En el ejemplo siguiente, la consulta especifica dos predicados para seleccionar únicamente los números pares que sean inferiores a cinco.</span><span class="sxs-lookup"><span data-stu-id="22e52-113">In the following example, the query specifies two predicates in order to select only the even numbers that are less than five.</span></span>  
  
 <span data-ttu-id="22e52-114">[!code-cs[cscsrefQueryKeywords#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="22e52-114">[!code-cs[cscsrefQueryKeywords#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="22e52-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="22e52-115">Example</span></span>  
 <span data-ttu-id="22e52-116">Puede que una cláusula `where` contenga uno o más métodos que devuelvan valores booleanos.</span><span class="sxs-lookup"><span data-stu-id="22e52-116">A `where` clause may contain one or more methods that return Boolean values.</span></span> <span data-ttu-id="22e52-117">En el ejemplo siguiente, la cláusula `where` usa un método para determinar si el valor actual de la variable de rango es par o impar.</span><span class="sxs-lookup"><span data-stu-id="22e52-117">In the following example, the `where` clause uses a method to determine whether the current value of the range variable is even or odd.</span></span>  
  
 <span data-ttu-id="22e52-118">[!code-cs[cscsrefQueryKeywords#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="22e52-118">[!code-cs[cscsrefQueryKeywords#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-clause_3.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22e52-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="22e52-119">Remarks</span></span>  
 <span data-ttu-id="22e52-120">La cláusula `where` es un mecanismo de filtrado.</span><span class="sxs-lookup"><span data-stu-id="22e52-120">The `where` clause is a filtering mechanism.</span></span> <span data-ttu-id="22e52-121">Se puede colocar prácticamente en cualquier parte en una expresión de consulta, pero no puede ser la primera ni la última cláusula.</span><span class="sxs-lookup"><span data-stu-id="22e52-121">It can be positioned almost anywhere in a query expression, except it cannot be the first or last clause.</span></span> <span data-ttu-id="22e52-122">Puede que una cláusula `where` aparezca antes o después de una cláusula [group](../../../csharp/language-reference/keywords/group-clause.md), en función de que haya que filtrar los elementos de origen antes o después de agruparlos.</span><span class="sxs-lookup"><span data-stu-id="22e52-122">A `where` clause may appear either before or after a [group](../../../csharp/language-reference/keywords/group-clause.md) clause depending on whether you have to filter the source elements before or after they are grouped.</span></span>  
  
 <span data-ttu-id="22e52-123">Si un predicado especificado no es válido para los elementos del origen de datos, se producirá un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="22e52-123">If a specified predicate is not valid for the elements in the data source, a compile-time error will result.</span></span> <span data-ttu-id="22e52-124">Esta es una de las ventajas de la comprobación estricta de tipos que [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] ofrece.</span><span class="sxs-lookup"><span data-stu-id="22e52-124">This is one benefit of the strong type-checking provided by [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span></span>  
  
 <span data-ttu-id="22e52-125">En tiempo de compilación, la palabra clave `where` se convierte en una llamada al método de operador de consulta estándar <xref:System.Linq.Enumerable.Where%2A>.</span><span class="sxs-lookup"><span data-stu-id="22e52-125">At compile time the `where` keyword is converted into a call to the <xref:System.Linq.Enumerable.Where%2A> Standard Query Operator method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22e52-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="22e52-126">See Also</span></span>  
 <span data-ttu-id="22e52-127">[Palabras clave para consultas (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="22e52-127">[Query Keywords (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span></span>  
 <span data-ttu-id="22e52-128">[from (Cláusula)](../../../csharp/language-reference/keywords/from-clause.md) </span><span class="sxs-lookup"><span data-stu-id="22e52-128">[from clause](../../../csharp/language-reference/keywords/from-clause.md) </span></span>  
 <span data-ttu-id="22e52-129">[select (Cláusula)](../../../csharp/language-reference/keywords/select-clause.md) </span><span class="sxs-lookup"><span data-stu-id="22e52-129">[select clause](../../../csharp/language-reference/keywords/select-clause.md) </span></span>  
 <span data-ttu-id="22e52-130">[Filtrado de datos](http://msdn.microsoft.com/library/cee88d0f-31aa-4c60-9452-cc122ed0057d) </span><span class="sxs-lookup"><span data-stu-id="22e52-130">[Filtering Data](http://msdn.microsoft.com/library/cee88d0f-31aa-4c60-9452-cc122ed0057d) </span></span>  
 <span data-ttu-id="22e52-131">[Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="22e52-131">[LINQ Query Expressions](../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 [<span data-ttu-id="22e52-132">Introducción a LINQ en C#</span><span class="sxs-lookup"><span data-stu-id="22e52-132">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)

