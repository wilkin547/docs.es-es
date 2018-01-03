---
title: "Determinar si alguno o todos los elementos de una secuencia satisfacen una condición"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 339ec145-826c-46d2-8cf2-3acd252cd072
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: c6322e6920ff183a837a896d0853a02248cc7c0c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition"></a><span data-ttu-id="5ed96-102">Determinar si alguno o todos los elementos de una secuencia satisfacen una condición</span><span class="sxs-lookup"><span data-stu-id="5ed96-102">Determine if Any or All Elements in a Sequence Satisfy a Condition</span></span>
<span data-ttu-id="5ed96-103">El operador <xref:System.Linq.Enumerable.All%2A> devuelve `true` si todos los elementos de una secuencia satisfacen una condición.</span><span class="sxs-lookup"><span data-stu-id="5ed96-103">The <xref:System.Linq.Enumerable.All%2A> operator returns `true` if all elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="5ed96-104">El operador <xref:System.Linq.Queryable.Any%2A> devuelve `true` si cualquier elemento de una secuencia satisface una condición.</span><span class="sxs-lookup"><span data-stu-id="5ed96-104">The <xref:System.Linq.Queryable.Any%2A> operator returns `true` if any element in a sequence satisfies a condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ed96-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5ed96-105">Example</span></span>  
 <span data-ttu-id="5ed96-106">En el ejemplo siguiente se devuelve una secuencia de clientes que tienen por lo menos un pedido.</span><span class="sxs-lookup"><span data-stu-id="5ed96-106">The following example returns a sequence of customers that have at least one order.</span></span> <span data-ttu-id="5ed96-107">El `Where` / `where` cláusula se evalúa como `true` si el determinado `Customer` tiene `Order`.</span><span class="sxs-lookup"><span data-stu-id="5ed96-107">The `Where`/`where` clause evaluates to `true` if the given `Customer` has any `Order`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#37](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#37)]
 [!code-vb[DLinqQueryExamples#37](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37)]  
  
## <a name="example"></a><span data-ttu-id="5ed96-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5ed96-108">Example</span></span>  
 <span data-ttu-id="5ed96-109">El código de Visual Basic siguiente determina la lista de clientes que no han realizado pedidos y garantiza que, para cada cliente de esa lista, se proporciona un nombre de contacto.</span><span class="sxs-lookup"><span data-stu-id="5ed96-109">The following Visual Basic code determines the list of customers who have not placed orders, and ensures that for every customer in that list, a contact name is provided.</span></span>  
  
 [!code-vb[DLinqQueryExamples#37v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37v)]  
  
## <a name="example"></a><span data-ttu-id="5ed96-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5ed96-110">Example</span></span>  
 <span data-ttu-id="5ed96-111">En el ejemplo de C# siguiente se devuelve una secuencia de clientes cuyos pedidos tienen un valor de `ShipCity` que empieza por "C".</span><span class="sxs-lookup"><span data-stu-id="5ed96-111">The following C# example returns a sequence of customers whose orders have a `ShipCity` beginning with "C".</span></span> <span data-ttu-id="5ed96-112">En el resultado devuelto se incluyen también los clientes que no tienen pedidos.</span><span class="sxs-lookup"><span data-stu-id="5ed96-112">Also included in the return are customers who have no orders.</span></span> <span data-ttu-id="5ed96-113">(Por diseño, el operador <xref:System.Linq.Queryable.All%2A> devuelve `true` para una secuencia vacía.) Los clientes sin pedidos se eliminan en los resultados de la consola mediante el operador `Count`.</span><span class="sxs-lookup"><span data-stu-id="5ed96-113">(By design, the <xref:System.Linq.Queryable.All%2A> operator returns `true` for an empty sequence.) Customers with no orders are eliminated in the console output by using the `Count` operator.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#38](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#38)]  
  
## <a name="see-also"></a><span data-ttu-id="5ed96-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ed96-114">See Also</span></span>  
 [<span data-ttu-id="5ed96-115">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="5ed96-115">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
