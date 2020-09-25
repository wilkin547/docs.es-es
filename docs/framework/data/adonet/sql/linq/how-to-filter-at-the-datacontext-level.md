---
title: Procedimiento para filtrar en el nivel de DataContext
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 15505cd7-0df2-427a-9f86-e0f96f60ee2e
ms.openlocfilehash: 6fe79febd41c040e430dd772b87ca5624824bb65
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173476"
---
# <a name="how-to-filter-at-the-datacontext-level"></a><span data-ttu-id="f43f7-102">Procedimiento para filtrar en el nivel de DataContext</span><span class="sxs-lookup"><span data-stu-id="f43f7-102">How to: Filter at the DataContext Level</span></span>

<span data-ttu-id="f43f7-103">Puede filtrar `EntitySets` en el nivel de `DataContext`.</span><span class="sxs-lookup"><span data-stu-id="f43f7-103">You can filter `EntitySets` at the `DataContext` level.</span></span> <span data-ttu-id="f43f7-104">Tales filtros se aplican a todas las consultas realizadas con esa instancia de <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="f43f7-104">Such filters apply to all queries done with that <xref:System.Data.Linq.DataContext> instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f43f7-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f43f7-105">Example</span></span>  

 <span data-ttu-id="f43f7-106">En el ejemplo siguiente, se usa <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> para filtrar los pedidos de clientes previamente cargados por `ShippedDate`.</span><span class="sxs-lookup"><span data-stu-id="f43f7-106">In the following example, <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> is used to filter the pre-loaded orders for customers by `ShippedDate`.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#10)]
 [!code-vb[DLinqQueryConcepts#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="f43f7-107">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f43f7-107">See also</span></span>

- [<span data-ttu-id="f43f7-108">Conceptos sobre consultas</span><span class="sxs-lookup"><span data-stu-id="f43f7-108">Query Concepts</span></span>](query-concepts.md)
