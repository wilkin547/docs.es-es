---
description: 'Más información acerca de cómo: filtrar en el nivel de DataContext'
title: Procedimiento para filtrar en el nivel de DataContext
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 15505cd7-0df2-427a-9f86-e0f96f60ee2e
ms.openlocfilehash: ffb287ac1ef8cc19044ec3d519e745f905fe213d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785983"
---
# <a name="how-to-filter-at-the-datacontext-level"></a><span data-ttu-id="4de33-103">Procedimiento para filtrar en el nivel de DataContext</span><span class="sxs-lookup"><span data-stu-id="4de33-103">How to: Filter at the DataContext Level</span></span>

<span data-ttu-id="4de33-104">Puede filtrar `EntitySets` en el nivel de `DataContext`.</span><span class="sxs-lookup"><span data-stu-id="4de33-104">You can filter `EntitySets` at the `DataContext` level.</span></span> <span data-ttu-id="4de33-105">Tales filtros se aplican a todas las consultas realizadas con esa instancia de <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="4de33-105">Such filters apply to all queries done with that <xref:System.Data.Linq.DataContext> instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4de33-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4de33-106">Example</span></span>  

 <span data-ttu-id="4de33-107">En el ejemplo siguiente, se usa <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> para filtrar los pedidos de clientes previamente cargados por `ShippedDate`.</span><span class="sxs-lookup"><span data-stu-id="4de33-107">In the following example, <xref:System.Data.Linq.DataLoadOptions.AssociateWith%28System.Linq.Expressions.LambdaExpression%29?displayProperty=nameWithType> is used to filter the pre-loaded orders for customers by `ShippedDate`.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#10)]
 [!code-vb[DLinqQueryConcepts#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="4de33-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="4de33-108">See also</span></span>

- [<span data-ttu-id="4de33-109">Conceptos sobre consultas</span><span class="sxs-lookup"><span data-stu-id="4de33-109">Query Concepts</span></span>](query-concepts.md)
