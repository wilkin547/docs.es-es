---
title: Devolver la intersección de conjuntos de dos secuencias
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d09c344e-3548-4944-a3ed-051880e3f5b8
ms.openlocfilehash: bb1785b12df2e8a835ba49ae59d0448fbebf794c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506828"
---
# <a name="return-the-set-intersection-of-two-sequences"></a><span data-ttu-id="dcaf1-102">Devolver la intersección de conjuntos de dos secuencias</span><span class="sxs-lookup"><span data-stu-id="dcaf1-102">Return the Set Intersection of Two Sequences</span></span>
<span data-ttu-id="dcaf1-103">Utilice el operador <xref:System.Linq.Queryable.Intersect%2A> para devolver la intersección de conjuntos de dos secuencias.</span><span class="sxs-lookup"><span data-stu-id="dcaf1-103">Use the <xref:System.Linq.Queryable.Intersect%2A> operator to return the set intersection of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dcaf1-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dcaf1-104">Example</span></span>  
 <span data-ttu-id="dcaf1-105">En este ejemplo se utiliza <xref:System.Linq.Queryable.Intersect%2A> para devolver una secuencia de todos los países en los que viven `Customers` y `Employees`.</span><span class="sxs-lookup"><span data-stu-id="dcaf1-105">This example uses <xref:System.Linq.Queryable.Intersect%2A> to return a sequence of all countries in which both `Customers` and `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#42](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#42)]
 [!code-vb[DLinqQueryExamples#42](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#42)]  
  
 <span data-ttu-id="dcaf1-106">En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], la operación <xref:System.Linq.Queryable.Intersect%2A> se define correctamente sólo en conjuntos.</span><span class="sxs-lookup"><span data-stu-id="dcaf1-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Intersect%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="dcaf1-107">La semántica de conjuntos múltiples no está definida.</span><span class="sxs-lookup"><span data-stu-id="dcaf1-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcaf1-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="dcaf1-108">See also</span></span>
- [<span data-ttu-id="dcaf1-109">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="dcaf1-109">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="dcaf1-110">Traslación del operador de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="dcaf1-110">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
