---
title: Devolver la unión de conjuntos de dos secuencias
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
ms.openlocfilehash: 058856243b2a8daaecd653a9b5999013de5407a8
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182530"
---
# <a name="return-the-set-union-of-two-sequences"></a><span data-ttu-id="97b37-102">Devolver la unión de conjuntos de dos secuencias</span><span class="sxs-lookup"><span data-stu-id="97b37-102">Return the Set Union of Two Sequences</span></span>
<span data-ttu-id="97b37-103">Utilice el operador <xref:System.Linq.Queryable.Union%2A> para devolver la unión de conjuntos de dos secuencias.</span><span class="sxs-lookup"><span data-stu-id="97b37-103">Use the <xref:System.Linq.Queryable.Union%2A> operator to return the set union of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97b37-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="97b37-104">Example</span></span>  
 <span data-ttu-id="97b37-105">En este ejemplo <xref:System.Linq.Queryable.Union%2A> `Customers` se usa para devolver una secuencia de todos los países o regiones en los que `Employees`hay o.</span><span class="sxs-lookup"><span data-stu-id="97b37-105">This example uses <xref:System.Linq.Queryable.Union%2A> to return a sequence of all countries/regions in which there are either `Customers` or `Employees`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 <span data-ttu-id="97b37-106">En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], el <xref:System.Linq.Queryable.Union%2A> operador se define para los conjuntos multiconjunto como la concatenación no ordenada de los conjuntos multiconjunto (de hecho, [`UNION ALL`](/sql/t-sql/language-elements/set-operators-union-transact-sql) el resultado de la cláusula en SQL).</span><span class="sxs-lookup"><span data-stu-id="97b37-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Union%2A> operator is defined for multisets as the unordered concatenation of the multisets (effectively the result of the [`UNION ALL`](/sql/t-sql/language-elements/set-operators-union-transact-sql) clause in SQL).</span></span>

<span data-ttu-id="97b37-107">Para obtener más información y ejemplos, <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>vea.</span><span class="sxs-lookup"><span data-stu-id="97b37-107">For more info and examples, see <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="97b37-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="97b37-108">See also</span></span>

- [<span data-ttu-id="97b37-109">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="97b37-109">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="97b37-110">Traslación del operador de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="97b37-110">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
