---
title: Procedimiento para administrar claves compuestas en consultas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ce2f14fd-1038-458a-91e3-a078c61f0d10
ms.openlocfilehash: bc16dde89f67572b03102b1c091993ed163b443c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203532"
---
# <a name="how-to-handle-composite-keys-in-queries"></a><span data-ttu-id="928c4-102">Procedimiento para administrar claves compuestas en consultas</span><span class="sxs-lookup"><span data-stu-id="928c4-102">How to: Handle Composite Keys in Queries</span></span>

<span data-ttu-id="928c4-103">Algunos operadores sólo pueden aceptar un argumento.</span><span class="sxs-lookup"><span data-stu-id="928c4-103">Some operators can take only one argument.</span></span> <span data-ttu-id="928c4-104">Si su argumento debe incluir más de una columna de la base de datos, debe crear un tipo anónimo para representar la combinación.</span><span class="sxs-lookup"><span data-stu-id="928c4-104">If your argument must include more than one column from the database, you must create an anonymous type to represent the combination.</span></span>  
  
## <a name="example"></a><span data-ttu-id="928c4-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="928c4-105">Example</span></span>  

 <span data-ttu-id="928c4-106">En el ejemplo siguiente se muestra una consulta que invoca al operador `GroupBy`, que sólo acepta un argumento `key`.</span><span class="sxs-lookup"><span data-stu-id="928c4-106">The following example shows a query that invokes the `GroupBy` operator, which can take only one `key` argument.</span></span>  
  
 [!code-csharp[DLinqCompositeKeys#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#1)]
 [!code-vb[DLinqCompositeKeys#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="928c4-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="928c4-107">Example</span></span>  

 <span data-ttu-id="928c4-108">La misma situación se da con las combinaciones, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="928c4-108">The same situation pertains to joins, as in the following example:</span></span>  
  
 [!code-csharp[DLinqCompositeKeys#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#2)]
 [!code-vb[DLinqCompositeKeys#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="928c4-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="928c4-109">See also</span></span>

- [<span data-ttu-id="928c4-110">Conceptos sobre consultas</span><span class="sxs-lookup"><span data-stu-id="928c4-110">Query Concepts</span></span>](query-concepts.md)
