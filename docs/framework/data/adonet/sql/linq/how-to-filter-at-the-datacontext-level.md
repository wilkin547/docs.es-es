---
title: 'Cómo: Filtrar en el nivel de DataContext'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 15505cd7-0df2-427a-9f86-e0f96f60ee2e
ms.openlocfilehash: c04be0bb955cff4bf796d14d45b39cac7ce4352d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33354938"
---
# <a name="how-to-filter-at-the-datacontext-level"></a><span data-ttu-id="5bd8e-102">Cómo: Filtrar en el nivel de DataContext</span><span class="sxs-lookup"><span data-stu-id="5bd8e-102">How to: Filter at the DataContext Level</span></span>
<span data-ttu-id="5bd8e-103">Puede filtrar `EntitySets` en el nivel de `DataContext`.</span><span class="sxs-lookup"><span data-stu-id="5bd8e-103">You can filter `EntitySets` at the `DataContext` level.</span></span> <span data-ttu-id="5bd8e-104">Tales filtros se aplican a todas las consultas realizadas con esa instancia de <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="5bd8e-104">Such filters apply to all queries done with that <xref:System.Data.Linq.DataContext> instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5bd8e-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5bd8e-105">Example</span></span>  
 <span data-ttu-id="5bd8e-106">En el ejemplo siguiente, se usa <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> para filtrar los pedidos de clientes previamente cargados por `ShippedDate`.</span><span class="sxs-lookup"><span data-stu-id="5bd8e-106">In the following example, <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> is used to filter the pre-loaded orders for customers by `ShippedDate`.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#10)]
 [!code-vb[DLinqQueryConcepts#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="5bd8e-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="5bd8e-107">See Also</span></span>  
 [<span data-ttu-id="5bd8e-108">Conceptos sobre consultas</span><span class="sxs-lookup"><span data-stu-id="5bd8e-108">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
