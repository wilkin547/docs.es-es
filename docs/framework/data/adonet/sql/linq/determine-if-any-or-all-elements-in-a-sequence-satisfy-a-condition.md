---
title: Determinar si alguno o todos los elementos de una secuencia satisfacen una condición
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 339ec145-826c-46d2-8cf2-3acd252cd072
ms.openlocfilehash: d3c343d3cf5068e473efbd62de019a25cf19dc10
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54702579"
---
# <a name="determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition"></a><span data-ttu-id="1cc5f-102">Determinar si alguno o todos los elementos de una secuencia satisfacen una condición</span><span class="sxs-lookup"><span data-stu-id="1cc5f-102">Determine if Any or All Elements in a Sequence Satisfy a Condition</span></span>
<span data-ttu-id="1cc5f-103">El operador <xref:System.Linq.Enumerable.All%2A> devuelve `true` si todos los elementos de una secuencia satisfacen una condición.</span><span class="sxs-lookup"><span data-stu-id="1cc5f-103">The <xref:System.Linq.Enumerable.All%2A> operator returns `true` if all elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="1cc5f-104">El operador <xref:System.Linq.Queryable.Any%2A> devuelve `true` si cualquier elemento de una secuencia satisface una condición.</span><span class="sxs-lookup"><span data-stu-id="1cc5f-104">The <xref:System.Linq.Queryable.Any%2A> operator returns `true` if any element in a sequence satisfies a condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1cc5f-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1cc5f-105">Example</span></span>  
 <span data-ttu-id="1cc5f-106">En el ejemplo siguiente se devuelve una secuencia de clientes que tienen por lo menos un pedido.</span><span class="sxs-lookup"><span data-stu-id="1cc5f-106">The following example returns a sequence of customers that have at least one order.</span></span> <span data-ttu-id="1cc5f-107">El `Where` / `where` cláusula se evalúa como `true` si el dado `Customer` tiene `Order`.</span><span class="sxs-lookup"><span data-stu-id="1cc5f-107">The `Where`/`where` clause evaluates to `true` if the given `Customer` has any `Order`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#37](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#37)]
 [!code-vb[DLinqQueryExamples#37](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37)]  
  
## <a name="example"></a><span data-ttu-id="1cc5f-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1cc5f-108">Example</span></span>  
 <span data-ttu-id="1cc5f-109">El código de Visual Basic siguiente determina la lista de clientes que no han realizado pedidos y garantiza que, para cada cliente de esa lista, se proporciona un nombre de contacto.</span><span class="sxs-lookup"><span data-stu-id="1cc5f-109">The following Visual Basic code determines the list of customers who have not placed orders, and ensures that for every customer in that list, a contact name is provided.</span></span>  
  
 [!code-vb[DLinqQueryExamples#37v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37v)]  
  
## <a name="example"></a><span data-ttu-id="1cc5f-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1cc5f-110">Example</span></span>  
 <span data-ttu-id="1cc5f-111">En el ejemplo de C# siguiente se devuelve una secuencia de clientes cuyos pedidos tienen un valor de `ShipCity` que empieza por "C".</span><span class="sxs-lookup"><span data-stu-id="1cc5f-111">The following C# example returns a sequence of customers whose orders have a `ShipCity` beginning with "C".</span></span> <span data-ttu-id="1cc5f-112">En el resultado devuelto se incluyen también los clientes que no tienen pedidos.</span><span class="sxs-lookup"><span data-stu-id="1cc5f-112">Also included in the return are customers who have no orders.</span></span> <span data-ttu-id="1cc5f-113">(Por diseño, el operador <xref:System.Linq.Queryable.All%2A> devuelve `true` para una secuencia vacía.) Los clientes sin pedidos se eliminan en los resultados de la consola mediante el operador `Count`.</span><span class="sxs-lookup"><span data-stu-id="1cc5f-113">(By design, the <xref:System.Linq.Queryable.All%2A> operator returns `true` for an empty sequence.) Customers with no orders are eliminated in the console output by using the `Count` operator.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#38](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#38)]  
  
## <a name="see-also"></a><span data-ttu-id="1cc5f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="1cc5f-114">See also</span></span>
- [<span data-ttu-id="1cc5f-115">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="1cc5f-115">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
