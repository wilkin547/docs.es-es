---
description: 'Más información acerca de: determinar si alguno o todos los elementos de una secuencia satisfacen una condición'
title: Determinar si alguno o todos los elementos de una secuencia satisfacen una condición
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 339ec145-826c-46d2-8cf2-3acd252cd072
ms.openlocfilehash: a46cf7e4e213eba830dc203f9266a408103cee80
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786113"
---
# <a name="determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition"></a><span data-ttu-id="94dc0-103">Determinar si alguno o todos los elementos de una secuencia satisfacen una condición</span><span class="sxs-lookup"><span data-stu-id="94dc0-103">Determine if Any or All Elements in a Sequence Satisfy a Condition</span></span>

<span data-ttu-id="94dc0-104">El operador <xref:System.Linq.Enumerable.All%2A> devuelve `true` si todos los elementos de una secuencia satisfacen una condición.</span><span class="sxs-lookup"><span data-stu-id="94dc0-104">The <xref:System.Linq.Enumerable.All%2A> operator returns `true` if all elements in a sequence satisfy a condition.</span></span>  
  
 <span data-ttu-id="94dc0-105">El operador <xref:System.Linq.Queryable.Any%2A> devuelve `true` si cualquier elemento de una secuencia satisface una condición.</span><span class="sxs-lookup"><span data-stu-id="94dc0-105">The <xref:System.Linq.Queryable.Any%2A> operator returns `true` if any element in a sequence satisfies a condition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94dc0-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="94dc0-106">Example</span></span>  

 <span data-ttu-id="94dc0-107">En el ejemplo siguiente se devuelve una secuencia de clientes que tienen por lo menos un pedido.</span><span class="sxs-lookup"><span data-stu-id="94dc0-107">The following example returns a sequence of customers that have at least one order.</span></span> <span data-ttu-id="94dc0-108">La `Where` / `where` cláusula se evalúa como `true` si el especificado `Customer` tiene any `Order` .</span><span class="sxs-lookup"><span data-stu-id="94dc0-108">The `Where`/`where` clause evaluates to `true` if the given `Customer` has any `Order`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#37](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#37)]
 [!code-vb[DLinqQueryExamples#37](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37)]  
  
## <a name="example"></a><span data-ttu-id="94dc0-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="94dc0-109">Example</span></span>  

 <span data-ttu-id="94dc0-110">El código de Visual Basic siguiente determina la lista de clientes que no han realizado pedidos y garantiza que, para cada cliente de esa lista, se proporciona un nombre de contacto.</span><span class="sxs-lookup"><span data-stu-id="94dc0-110">The following Visual Basic code determines the list of customers who have not placed orders, and ensures that for every customer in that list, a contact name is provided.</span></span>  
  
 [!code-vb[DLinqQueryExamples#37v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37v)]  
  
## <a name="example"></a><span data-ttu-id="94dc0-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="94dc0-111">Example</span></span>  

 <span data-ttu-id="94dc0-112">En el ejemplo de C# siguiente se devuelve una secuencia de clientes cuyos pedidos tienen un valor de `ShipCity` que empieza por "C".</span><span class="sxs-lookup"><span data-stu-id="94dc0-112">The following C# example returns a sequence of customers whose orders have a `ShipCity` beginning with "C".</span></span> <span data-ttu-id="94dc0-113">En el resultado devuelto se incluyen también los clientes que no tienen pedidos.</span><span class="sxs-lookup"><span data-stu-id="94dc0-113">Also included in the return are customers who have no orders.</span></span> <span data-ttu-id="94dc0-114">(Por diseño, el <xref:System.Linq.Queryable.All%2A> operador devuelve `true` para una secuencia vacía). Los clientes sin pedidos se eliminan en la salida de la consola mediante el `Count` operador.</span><span class="sxs-lookup"><span data-stu-id="94dc0-114">(By design, the <xref:System.Linq.Queryable.All%2A> operator returns `true` for an empty sequence.) Customers with no orders are eliminated in the console output by using the `Count` operator.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#38](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#38)]  
  
## <a name="see-also"></a><span data-ttu-id="94dc0-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="94dc0-115">See also</span></span>

- [<span data-ttu-id="94dc0-116">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="94dc0-116">Query Examples</span></span>](query-examples.md)
