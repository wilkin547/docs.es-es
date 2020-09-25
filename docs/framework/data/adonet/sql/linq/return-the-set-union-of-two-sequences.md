---
title: Devolver la unión de conjuntos de dos secuencias
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
ms.openlocfilehash: 0fe32d8c3c37e99a50ca03262dc6184337b4450e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200213"
---
# <a name="return-the-set-union-of-two-sequences"></a><span data-ttu-id="0fc6f-102">Devolver la unión de conjuntos de dos secuencias</span><span class="sxs-lookup"><span data-stu-id="0fc6f-102">Return the Set Union of Two Sequences</span></span>

<span data-ttu-id="0fc6f-103">Utilice el operador <xref:System.Linq.Queryable.Union%2A> para devolver la unión de conjuntos de dos secuencias.</span><span class="sxs-lookup"><span data-stu-id="0fc6f-103">Use the <xref:System.Linq.Queryable.Union%2A> operator to return the set union of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0fc6f-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0fc6f-104">Example</span></span>  

 <span data-ttu-id="0fc6f-105">En este ejemplo <xref:System.Linq.Queryable.Union%2A> se usa para devolver una secuencia de todos los países o regiones en los que hay `Customers` o `Employees` .</span><span class="sxs-lookup"><span data-stu-id="0fc6f-105">This example uses <xref:System.Linq.Queryable.Union%2A> to return a sequence of all countries/regions in which there are either `Customers` or `Employees`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 <span data-ttu-id="0fc6f-106">En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , el <xref:System.Linq.Queryable.Union%2A> operador se define para los conjuntos multiconjunto como la concatenación no ordenada de los conjuntos multiconjunto (de hecho, el resultado de la [`UNION ALL`](/sql/t-sql/language-elements/set-operators-union-transact-sql) cláusula en SQL).</span><span class="sxs-lookup"><span data-stu-id="0fc6f-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Union%2A> operator is defined for multisets as the unordered concatenation of the multisets (effectively the result of the [`UNION ALL`](/sql/t-sql/language-elements/set-operators-union-transact-sql) clause in SQL).</span></span>

<span data-ttu-id="0fc6f-107">Para obtener más información y ejemplos, vea <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="0fc6f-107">For more info and examples, see <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0fc6f-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0fc6f-108">See also</span></span>

- [<span data-ttu-id="0fc6f-109">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="0fc6f-109">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="0fc6f-110">Traslación del operador de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="0fc6f-110">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
