---
description: 'Más información acerca de cómo: controlar claves compuestas en consultas'
title: Procedimiento para administrar claves compuestas en consultas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ce2f14fd-1038-458a-91e3-a078c61f0d10
ms.openlocfilehash: 9d7c68495810bee6a383d98a75694e7cd24f1015
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738876"
---
# <a name="how-to-handle-composite-keys-in-queries"></a><span data-ttu-id="5bd65-103">Procedimiento para administrar claves compuestas en consultas</span><span class="sxs-lookup"><span data-stu-id="5bd65-103">How to: Handle Composite Keys in Queries</span></span>

<span data-ttu-id="5bd65-104">Algunos operadores sólo pueden aceptar un argumento.</span><span class="sxs-lookup"><span data-stu-id="5bd65-104">Some operators can take only one argument.</span></span> <span data-ttu-id="5bd65-105">Si su argumento debe incluir más de una columna de la base de datos, debe crear un tipo anónimo para representar la combinación.</span><span class="sxs-lookup"><span data-stu-id="5bd65-105">If your argument must include more than one column from the database, you must create an anonymous type to represent the combination.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5bd65-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5bd65-106">Example</span></span>  

 <span data-ttu-id="5bd65-107">En el ejemplo siguiente se muestra una consulta que invoca al operador `GroupBy`, que sólo acepta un argumento `key`.</span><span class="sxs-lookup"><span data-stu-id="5bd65-107">The following example shows a query that invokes the `GroupBy` operator, which can take only one `key` argument.</span></span>  
  
 [!code-csharp[DLinqCompositeKeys#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#1)]
 [!code-vb[DLinqCompositeKeys#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="5bd65-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5bd65-108">Example</span></span>  

 <span data-ttu-id="5bd65-109">La misma situación se da con las combinaciones, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5bd65-109">The same situation pertains to joins, as in the following example:</span></span>  
  
 [!code-csharp[DLinqCompositeKeys#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCompositeKeys/cs/Program.cs#2)]
 [!code-vb[DLinqCompositeKeys#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCompositeKeys/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="5bd65-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="5bd65-110">See also</span></span>

- [<span data-ttu-id="5bd65-111">Conceptos sobre consultas</span><span class="sxs-lookup"><span data-stu-id="5bd65-111">Query Concepts</span></span>](query-concepts.md)
