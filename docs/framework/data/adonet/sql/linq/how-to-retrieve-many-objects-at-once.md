---
description: 'Más información acerca de cómo: recuperar muchos objetos a la vez'
title: Procedimiento para recuperar muchos objetos a la vez
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 18aff4d8-bde8-461b-9960-ccabb24e9d22
ms.openlocfilehash: 2bc202e09c64f2a1956b8688be30cfd87fb655c0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802013"
---
# <a name="how-to-retrieve-many-objects-at-once"></a><span data-ttu-id="3b7d5-103">Procedimiento para recuperar muchos objetos a la vez</span><span class="sxs-lookup"><span data-stu-id="3b7d5-103">How to: Retrieve Many Objects At Once</span></span>

<span data-ttu-id="3b7d5-104">Puede recuperar muchos objetos en una consulta mediante <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span><span class="sxs-lookup"><span data-stu-id="3b7d5-104">You can retrieve many objects in one query by using <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b7d5-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3b7d5-105">Example</span></span>  

 <span data-ttu-id="3b7d5-106">El código siguiente utiliza el método <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> para recuperar los objetos `Customer` y `Order`.</span><span class="sxs-lookup"><span data-stu-id="3b7d5-106">The following code uses the <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> method to retrieve both `Customer` and `Order` objects.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#9)]
 [!code-vb[DLinqQueryConcepts#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="3b7d5-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b7d5-107">See also</span></span>

- [<span data-ttu-id="3b7d5-108">Conceptos sobre consultas</span><span class="sxs-lookup"><span data-stu-id="3b7d5-108">Query Concepts</span></span>](query-concepts.md)
