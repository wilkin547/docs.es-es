---
title: "orderby (Cláusula, Referencia de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- orderby
- orderby_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- orderby clause [C#]
- orderby keyword [C#]
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
caps.latest.revision: 17
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
ms.openlocfilehash: ec9507e4c1d9691d90d47cdbb20fdb22fc281d24
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="orderby-clause-c-reference"></a><span data-ttu-id="e5533-102">orderby (Cláusula, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="e5533-102">orderby clause (C# Reference)</span></span>
<span data-ttu-id="e5533-103">En una expresión de consulta, la cláusula `orderby` hace que la secuencia o subsecuencia (grupo) devuelta se ordene de forma ascendente o descendente.</span><span class="sxs-lookup"><span data-stu-id="e5533-103">In a query expression, the `orderby` clause causes the returned sequence or subsequence (group) to be sorted in either ascending or descending order.</span></span> <span data-ttu-id="e5533-104">Se pueden especificar varias claves para llevar a cabo una o varias operaciones de ordenación secundaria.</span><span class="sxs-lookup"><span data-stu-id="e5533-104">Multiple keys can be specified in order to perform one or more secondary sort operations.</span></span> <span data-ttu-id="e5533-105">La ordenación se realiza mediante el comparador predeterminado del tipo de elemento.</span><span class="sxs-lookup"><span data-stu-id="e5533-105">The sorting is performed by the default comparer for the type of the element.</span></span> <span data-ttu-id="e5533-106">El criterio de ordenación predeterminado es el ascendente.</span><span class="sxs-lookup"><span data-stu-id="e5533-106">The default sort order is ascending.</span></span> <span data-ttu-id="e5533-107">También puede especificar un comparador personalizado.</span><span class="sxs-lookup"><span data-stu-id="e5533-107">You can also specify a custom comparer.</span></span> <span data-ttu-id="e5533-108">En cambio, solo está disponible mediante la sintaxis basada en métodos.</span><span class="sxs-lookup"><span data-stu-id="e5533-108">However, it is only available by using method-based syntax.</span></span> <span data-ttu-id="e5533-109">Para obtener más información, consulte [Sorting Data](http://msdn.microsoft.com/library/6d76e2d7-b418-49b5-ac78-2bcd61169c48) (Ordenación de datos).</span><span class="sxs-lookup"><span data-stu-id="e5533-109">For more information, see [Sorting Data](http://msdn.microsoft.com/library/6d76e2d7-b418-49b5-ac78-2bcd61169c48).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5533-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e5533-110">Example</span></span>  
 <span data-ttu-id="e5533-111">En el ejemplo siguiente, la primera consulta ordena las palabras en orden alfabético a partir de la A y la segunda consulta ordena las mismas palabras en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="e5533-111">In the following example, the first query sorts the words in alphabetical order starting from A, and second query sorts the same words in descending order.</span></span> <span data-ttu-id="e5533-112">(La palabra clave `ascending` es el valor de ordenación predeterminado y puede omitirse).</span><span class="sxs-lookup"><span data-stu-id="e5533-112">(The `ascending` keyword is the default sort value and can be omitted.)</span></span>  
  
 <span data-ttu-id="e5533-113">[!code-cs[cscsrefQueryKeywords#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e5533-113">[!code-cs[cscsrefQueryKeywords#20](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5533-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e5533-114">Example</span></span>  
 <span data-ttu-id="e5533-115">En el ejemplo siguiente, se realiza una ordenación primaria por apellidos de los alumnos y, después, una ordenación secundaria por sus nombres.</span><span class="sxs-lookup"><span data-stu-id="e5533-115">The following example performs a primary sort on the students' last names, and then a secondary sort on their first names.</span></span>  
  
 <span data-ttu-id="e5533-116">[!code-cs[cscsrefQueryKeywords#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="e5533-116">[!code-cs[cscsrefQueryKeywords#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/orderby-clause_2.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5533-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e5533-117">Remarks</span></span>  
 <span data-ttu-id="e5533-118">En tiempo de compilación, la cláusula `orderby` se convierte en una llamada al método <xref:System.Linq.Enumerable.OrderBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="e5533-118">At compile time, the `orderby` clause is translated to a call to the <xref:System.Linq.Enumerable.OrderBy%2A> method.</span></span> <span data-ttu-id="e5533-119">Varias claves en la cláusula `orderby` se convierten en llamadas al método <xref:System.Linq.Enumerable.ThenBy%2A>.</span><span class="sxs-lookup"><span data-stu-id="e5533-119">Multiple keys in the `orderby` clause translate to <xref:System.Linq.Enumerable.ThenBy%2A> method calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5533-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5533-120">See Also</span></span>  
 <span data-ttu-id="e5533-121">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e5533-121">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="e5533-122">[Palabras clave de consultas (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="e5533-122">[Query Keywords (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md) </span></span>  
 <span data-ttu-id="e5533-123">[Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="e5533-123">[LINQ Query Expressions](../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 <span data-ttu-id="e5533-124">[group (Cláusula)](../../../csharp/language-reference/keywords/group-clause.md) </span><span class="sxs-lookup"><span data-stu-id="e5533-124">[group clause](../../../csharp/language-reference/keywords/group-clause.md) </span></span>  
 [<span data-ttu-id="e5533-125">Introducción a LINQ en C#</span><span class="sxs-lookup"><span data-stu-id="e5533-125">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)

