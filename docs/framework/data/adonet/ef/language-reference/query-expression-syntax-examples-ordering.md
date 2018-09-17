---
title: 'Ejemplos de sintaxis de expresiones de consulta: ordenación'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: bcbc9625-7cf7-476e-85d2-058f12682f54
ms.openlocfilehash: bc8bfaabb9e90e66e4ec81e551fd66319a78ca7e
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45745802"
---
# <a name="query-expression-syntax-examples-ordering"></a><span data-ttu-id="8d233-102">Ejemplos de sintaxis de expresiones de consulta: ordenación</span><span class="sxs-lookup"><span data-stu-id="8d233-102">Query Expression Syntax Examples: Ordering</span></span>
<span data-ttu-id="8d233-103">Los ejemplos de este tema muestran cómo usar el `OrderBy` y `OrderByDescending` métodos para consultar el [modelo AdventureWorks Sales](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) con la sintaxis de expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="8d233-103">The examples in this topic demonstrate how to use the `OrderBy` and `OrderByDescending` methods to query the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) using query expression syntax.</span></span> <span data-ttu-id="8d233-104">El modelo AdventureWorks Sales que se usa en estos ejemplos se crea a partir de las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="8d233-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="8d233-105">Los ejemplos de este tema usan los siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="8d233-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="orderby"></a><span data-ttu-id="8d233-106">OrderBy</span><span class="sxs-lookup"><span data-stu-id="8d233-106">OrderBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="8d233-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8d233-107">Example</span></span>  
 <span data-ttu-id="8d233-108">En el ejemplo siguiente se utiliza <xref:System.Linq.Enumerable.OrderBy%2A> para devolver una lista de contactos organizados por apellido.</span><span class="sxs-lookup"><span data-stu-id="8d233-108">The following example uses <xref:System.Linq.Enumerable.OrderBy%2A> to return a list of contacts ordered by last name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderBySimple1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbysimple1)]
 [!code-vb[DP L2E Examples#OrderBySimple1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbysimple1)]  
  
### <a name="example"></a><span data-ttu-id="8d233-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8d233-109">Example</span></span>  
 <span data-ttu-id="8d233-110">En el ejemplo siguiente se utiliza <xref:System.Linq.Enumerable.OrderBy%2A> para ordenar una lista de contactos por longitud del apellido.</span><span class="sxs-lookup"><span data-stu-id="8d233-110">The following example uses <xref:System.Linq.Enumerable.OrderBy%2A> to sort a list of contacts by length of last name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderBySimple2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbysimple2)]
 [!code-vb[DP L2E Examples#OrderBySimple2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbysimple2)]  
  
## <a name="orderbydescending"></a><span data-ttu-id="8d233-111">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="8d233-111">OrderByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="8d233-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8d233-112">Example</span></span>  
 <span data-ttu-id="8d233-113">En el ejemplo siguiente se utiliza `orderby… descending` (`Order By … Descending`) en Visual Basic, que es equivalente al método <xref:System.Linq.Enumerable.OrderByDescending%2A>, para ordenar el precio de venta de mayor a menor.</span><span class="sxs-lookup"><span data-stu-id="8d233-113">The following example uses `orderby… descending` (`Order By … Descending` in Visual Basic), which is equivalent to the <xref:System.Linq.Enumerable.OrderByDescending%2A> method, to sort the price list from highest to lowest.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderByDescendingSimple1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbydescendingsimple1)]
 [!code-vb[DP L2E Examples#OrderByDescendingSimple1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbydescendingsimple1)]  
  
## <a name="thenby"></a><span data-ttu-id="8d233-114">ThenBy</span><span class="sxs-lookup"><span data-stu-id="8d233-114">ThenBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="8d233-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8d233-115">Example</span></span>  
 <span data-ttu-id="8d233-116">En el ejemplo siguiente se utiliza <xref:System.Linq.Queryable.OrderBy%2A> y <xref:System.Linq.Queryable.ThenBy%2A> para devolver una lista de contactos ordenados por apellido y luego por nombre.</span><span class="sxs-lookup"><span data-stu-id="8d233-116">The following example uses <xref:System.Linq.Queryable.OrderBy%2A> and <xref:System.Linq.Queryable.ThenBy%2A> to return a list of contacts ordered by last name and then by first name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderByThenBy](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbythenby)]
 [!code-vb[DP L2E Examples#OrderByThenBy](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbythenby)]  
  
## <a name="thenbydescending"></a><span data-ttu-id="8d233-117">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="8d233-117">ThenByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="8d233-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8d233-118">Example</span></span>  
 <span data-ttu-id="8d233-119">En el ejemplo siguiente se utiliza `OrderBy… Descending`, que es equivalente al método <xref:System.Linq.Enumerable.ThenByDescending%2A>, para ordenar una lista de productos, primero por nombre y después por precio de venta, de mayor a menor.</span><span class="sxs-lookup"><span data-stu-id="8d233-119">The following example uses `OrderBy… Descending`, which is equivalent to the <xref:System.Linq.Enumerable.ThenByDescending%2A> method, to sort a list of products, first by name and then by list price from highest to lowest.</span></span>  
  
 [!code-csharp[DP L2E Examples#ThenByDescendingSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#thenbydescendingsimple)]
 [!code-vb[DP L2E Examples#ThenByDescendingSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#thenbydescendingsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="8d233-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d233-120">See Also</span></span>  
 [<span data-ttu-id="8d233-121">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="8d233-121">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
