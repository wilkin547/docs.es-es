---
description: 'Más información sobre: devolver la Unión de conjuntos de dos secuencias'
title: Devolver la unión de conjuntos de dos secuencias
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
ms.openlocfilehash: 5541316560c05712e22c54f706b02d868fadb381
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662967"
---
# <a name="return-the-set-union-of-two-sequences"></a><span data-ttu-id="65804-103">Devolver la unión de conjuntos de dos secuencias</span><span class="sxs-lookup"><span data-stu-id="65804-103">Return the Set Union of Two Sequences</span></span>

<span data-ttu-id="65804-104">Utilice el operador <xref:System.Linq.Queryable.Union%2A> para devolver la unión de conjuntos de dos secuencias.</span><span class="sxs-lookup"><span data-stu-id="65804-104">Use the <xref:System.Linq.Queryable.Union%2A> operator to return the set union of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65804-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="65804-105">Example</span></span>  

 <span data-ttu-id="65804-106">En este ejemplo <xref:System.Linq.Queryable.Union%2A> se usa para devolver una secuencia de todos los países o regiones en los que hay `Customers` o `Employees` .</span><span class="sxs-lookup"><span data-stu-id="65804-106">This example uses <xref:System.Linq.Queryable.Union%2A> to return a sequence of all countries/regions in which there are either `Customers` or `Employees`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 <span data-ttu-id="65804-107">En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , el <xref:System.Linq.Queryable.Union%2A> operador se define para los conjuntos multiconjunto como la concatenación no ordenada de los conjuntos multiconjunto (de hecho, el resultado de la [`UNION ALL`](/sql/t-sql/language-elements/set-operators-union-transact-sql) cláusula en SQL).</span><span class="sxs-lookup"><span data-stu-id="65804-107">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Union%2A> operator is defined for multisets as the unordered concatenation of the multisets (effectively the result of the [`UNION ALL`](/sql/t-sql/language-elements/set-operators-union-transact-sql) clause in SQL).</span></span>

<span data-ttu-id="65804-108">Para obtener más información y ejemplos, vea <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="65804-108">For more info and examples, see <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="65804-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="65804-109">See also</span></span>

- [<span data-ttu-id="65804-110">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="65804-110">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="65804-111">Traslación del operador de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="65804-111">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
