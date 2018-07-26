---
title: Devolver la unión de conjuntos de dos secuencias
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
ms.openlocfilehash: 13e5e821f68e839039569b4ac8a993a20c45ab27
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2018
ms.locfileid: "37403952"
---
# <a name="return-the-set-union-of-two-sequences"></a><span data-ttu-id="e1eeb-102">Devolver la unión de conjuntos de dos secuencias</span><span class="sxs-lookup"><span data-stu-id="e1eeb-102">Return the Set Union of Two Sequences</span></span>
<span data-ttu-id="e1eeb-103">Utilice el operador <xref:System.Linq.Queryable.Union%2A> para devolver la unión de conjuntos de dos secuencias.</span><span class="sxs-lookup"><span data-stu-id="e1eeb-103">Use the <xref:System.Linq.Queryable.Union%2A> operator to return the set union of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1eeb-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e1eeb-104">Example</span></span>  
 <span data-ttu-id="e1eeb-105">En este ejemplo se utiliza <xref:System.Linq.Queryable.Union%2A> para devolver una secuencia de todos los países en los que hay `Customers` o `Employees`.</span><span class="sxs-lookup"><span data-stu-id="e1eeb-105">This example uses <xref:System.Linq.Queryable.Union%2A> to return a sequence of all countries in which there are either `Customers` or `Employees`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 <span data-ttu-id="e1eeb-106">En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], <xref:System.Linq.Queryable.Union%2A> operador se define para conjuntos múltiples como la concatenación no ordenada de los conjuntos múltiples (hecho, el resultado de la [ `UNION ALL` ](https://docs.microsoft.com/en-us/sql/t-sql/language-elements/set-operators-union-transact-sql?view=sql-server-2017) cláusula de SQL).</span><span class="sxs-lookup"><span data-stu-id="e1eeb-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Union%2A> operator is defined for multisets as the unordered concatenation of the multisets (effectively the result of the [`UNION ALL`](https://docs.microsoft.com/en-us/sql/t-sql/language-elements/set-operators-union-transact-sql?view=sql-server-2017) clause in SQL).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1eeb-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1eeb-107">See Also</span></span>  
 [<span data-ttu-id="e1eeb-108">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="e1eeb-108">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="e1eeb-109">Traslación del operador de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="e1eeb-109">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
