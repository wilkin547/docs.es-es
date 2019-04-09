---
title: Filtrar para filtrar en el nivel de DataContext
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 15505cd7-0df2-427a-9f86-e0f96f60ee2e
ms.openlocfilehash: 343cffa9b1c034068e5abcc652e936f89ee6a992
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59084588"
---
# <a name="how-to-filter-at-the-datacontext-level"></a><span data-ttu-id="06d17-102">Filtrar para filtrar en el nivel de DataContext</span><span class="sxs-lookup"><span data-stu-id="06d17-102">How to: Filter at the DataContext Level</span></span>
<span data-ttu-id="06d17-103">Puede filtrar `EntitySets` en el nivel de `DataContext`.</span><span class="sxs-lookup"><span data-stu-id="06d17-103">You can filter `EntitySets` at the `DataContext` level.</span></span> <span data-ttu-id="06d17-104">Tales filtros se aplican a todas las consultas realizadas con esa instancia de <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="06d17-104">Such filters apply to all queries done with that <xref:System.Data.Linq.DataContext> instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06d17-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="06d17-105">Example</span></span>  
 <span data-ttu-id="06d17-106">En el ejemplo siguiente, se usa <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> para filtrar los pedidos de clientes previamente cargados por `ShippedDate`.</span><span class="sxs-lookup"><span data-stu-id="06d17-106">In the following example, <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> is used to filter the pre-loaded orders for customers by `ShippedDate`.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#10)]
 [!code-vb[DLinqQueryConcepts#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="06d17-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="06d17-107">See also</span></span>

- [<span data-ttu-id="06d17-108">Conceptos sobre consultas</span><span class="sxs-lookup"><span data-stu-id="06d17-108">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
