---
title: Determinar si alguno o todos los elementos de una secuencia satisfacen una condición
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 339ec145-826c-46d2-8cf2-3acd252cd072
ms.openlocfilehash: 65a9a7cf289c2006bab14cb384efb07eaea7f7a0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194432"
---
# <a name="determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition"></a><span data-ttu-id="bbbb3-102">Determinar si alguno o todos los elementos de una secuencia satisfacen una condición</span><span class="sxs-lookup"><span data-stu-id="bbbb3-102">Determine if Any or All Elements in a Sequence Satisfy a Condition</span></span>

<span data-ttu-id="bbbb3-103">El operador <xref:System.Linq.Enumerable.All%2A> devuelve `true` si todos los elementos de una secuencia satisfacen una condición.</span><span class="sxs-lookup"><span data-stu-id="bbbb3-103">The <xref:System.Linq.Enumerable.All%2A> operator returns `true` if all elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="bbbb3-104">El operador <xref:System.Linq.Queryable.Any%2A> devuelve `true` si cualquier elemento de una secuencia satisface una condición.</span><span class="sxs-lookup"><span data-stu-id="bbbb3-104">The <xref:System.Linq.Queryable.Any%2A> operator returns `true` if any element in a sequence satisfies a condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bbbb3-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bbbb3-105">Example</span></span>  

 <span data-ttu-id="bbbb3-106">En el ejemplo siguiente se devuelve una secuencia de clientes que tienen por lo menos un pedido.</span><span class="sxs-lookup"><span data-stu-id="bbbb3-106">The following example returns a sequence of customers that have at least one order.</span></span> <span data-ttu-id="bbbb3-107">La `Where` / `where` cláusula se evalúa como `true` si el especificado `Customer` tiene any `Order` .</span><span class="sxs-lookup"><span data-stu-id="bbbb3-107">The `Where`/`where` clause evaluates to `true` if the given `Customer` has any `Order`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#37](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#37)]
 [!code-vb[DLinqQueryExamples#37](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37)]  
  
## <a name="example"></a><span data-ttu-id="bbbb3-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bbbb3-108">Example</span></span>  

 <span data-ttu-id="bbbb3-109">El código de Visual Basic siguiente determina la lista de clientes que no han realizado pedidos y garantiza que, para cada cliente de esa lista, se proporciona un nombre de contacto.</span><span class="sxs-lookup"><span data-stu-id="bbbb3-109">The following Visual Basic code determines the list of customers who have not placed orders, and ensures that for every customer in that list, a contact name is provided.</span></span>  
  
 [!code-vb[DLinqQueryExamples#37v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37v)]  
  
## <a name="example"></a><span data-ttu-id="bbbb3-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bbbb3-110">Example</span></span>  

 <span data-ttu-id="bbbb3-111">En el ejemplo de C# siguiente se devuelve una secuencia de clientes cuyos pedidos tienen un valor de `ShipCity` que empieza por "C".</span><span class="sxs-lookup"><span data-stu-id="bbbb3-111">The following C# example returns a sequence of customers whose orders have a `ShipCity` beginning with "C".</span></span> <span data-ttu-id="bbbb3-112">En el resultado devuelto se incluyen también los clientes que no tienen pedidos.</span><span class="sxs-lookup"><span data-stu-id="bbbb3-112">Also included in the return are customers who have no orders.</span></span> <span data-ttu-id="bbbb3-113">(Por diseño, el <xref:System.Linq.Queryable.All%2A> operador devuelve `true` para una secuencia vacía). Los clientes sin pedidos se eliminan en la salida de la consola mediante el `Count` operador.</span><span class="sxs-lookup"><span data-stu-id="bbbb3-113">(By design, the <xref:System.Linq.Queryable.All%2A> operator returns `true` for an empty sequence.) Customers with no orders are eliminated in the console output by using the `Count` operator.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#38](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#38)]  
  
## <a name="see-also"></a><span data-ttu-id="bbbb3-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bbbb3-114">See also</span></span>

- [<span data-ttu-id="bbbb3-115">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="bbbb3-115">Query Examples</span></span>](query-examples.md)
