---
title: Procedimiento para recuperar muchos objetos a la vez
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 18aff4d8-bde8-461b-9960-ccabb24e9d22
ms.openlocfilehash: 98827989f72b7922a325a9e13b5f46cb18ac5395
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197318"
---
# <a name="how-to-retrieve-many-objects-at-once"></a><span data-ttu-id="eb2af-102">Procedimiento para recuperar muchos objetos a la vez</span><span class="sxs-lookup"><span data-stu-id="eb2af-102">How to: Retrieve Many Objects At Once</span></span>

<span data-ttu-id="eb2af-103">Puede recuperar muchos objetos en una consulta mediante <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span><span class="sxs-lookup"><span data-stu-id="eb2af-103">You can retrieve many objects in one query by using <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb2af-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eb2af-104">Example</span></span>  

 <span data-ttu-id="eb2af-105">El código siguiente utiliza el método <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> para recuperar los objetos `Customer` y `Order`.</span><span class="sxs-lookup"><span data-stu-id="eb2af-105">The following code uses the <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> method to retrieve both `Customer` and `Order` objects.</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#9)]
 [!code-vb[DLinqQueryConcepts#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="eb2af-106">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eb2af-106">See also</span></span>

- [<span data-ttu-id="eb2af-107">Conceptos sobre consultas</span><span class="sxs-lookup"><span data-stu-id="eb2af-107">Query Concepts</span></span>](query-concepts.md)
